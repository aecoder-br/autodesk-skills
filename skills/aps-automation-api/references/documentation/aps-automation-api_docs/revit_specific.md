# Aps-Automation-Api_Docs - Revit Specific

**Pages:** 5

---

## About this Walkthrough

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/revit/about_this_tutorial

**Contents:**
    - Jump To
- About this Walkthrough
- Postman walkthrough

This walkthrough guides you through the process of executing a Revit add-in on the Automation Service. It doesn’t teach you how to create a Revit add-in. Instead, it limits itself teaching you how to run a Revit add-in on the Automation Service. For instructions on how to create Revit add-ins, visit the Revit Developer Center.

Revit add-ins are typically designed to interact with the Revit User Interface (UI). However, no user interaction is possible on the Automation Service. Before you execute an add-in on the Automation Service, you must strip it of all references to the UI. Task 1 of this walkthrough walks you through converting a Revit add-in to an Automation API ready add-in. It requires you to modify C# code. If you are not proficient in C#, you can download the Automation API ready add-in DeleteWalls.dll from here, and start from Task 2.

Postman is a popular tool that provides an easy-to-use interface to send HTTP requests. The Postman Collection at https://github.com/autodesk-platform-services/aps-tutorial-postman/tree/master/DA4Revit collates all the HTTP requests used in this walkthrough. If you are familiar with Postman, you can import this Postman Collection and use Postman to send requests instead of cURL.

On the Postman Collection, requests are grouped by task. The group has the same name as the corresponding task in the walkthrough.

Task 1 is performed exclusively on Visual Studio. It does not send any requests to APS. Because Postman deals only with requests, there is no Task 1 in the Postman Collection.

Similarly, requests are named such that they have the same names as the corresponding step within the task.

You can install Postman from here.

You can learn how to install and use Postman from here.

---

## Handling Revit Failures

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/handling-failures

**Contents:**
    - Jump To
- Handling Revit Failures
- Overview of Failure Processing
- Default Failure Handling
- Custom Failure Handling
- FailuresProcessor

Normally posted failures are processed by Revit’s standard failure resolution UI at the end of a transaction when Transaction.Commit() or Transaction.Rollback() are invoked. The user is presented information and options to deal with the failures.

If an operation (or set of operations) on the document requires some special treatment from a Revit addin for certain errors, failure handling can be customized to carry out this resolution. Custom failure handling can be supplied:

Finally, the API offers the ability to completely replace the standard failure processing user interface using the interface IFailuresProcessor. Although the first two methods for handling failures should be sufficient in most cases, this last option can be used in special cases, such as to provide a better failure processing UI (UI is not available the Automation API) or when an application is used as a front-end on top of Revit.

It is important to remember there are many things happening between the call to Transaction.Commit() and the actual processing of failures. Auto-join, overlap checks, group checks and workset editability checks are just to name a few. These checks and changes may make some failures disappear or, more likely, can post new failures. Therefore, conclusions cannot be drawn about the state of failures to be processed when Transaction.Commit() is called. To process failure correctly, it is necessary to hook up the actual failure processing mechanism.

When failures processing begins, all changes to a document that are supposed to be made in the transaction are made, and all failures are posted. Therefore, no uncontrolled changes to a document are allowed during failures processing. There is a limited ability to resolve failures via the restricted interface provided by FailureAccessor. If this has happened all end of transaction checks and failure processing must be repeated. So, there may be a few failure resolution cycles at the end of one transaction.

Each cycle of failures processing includes 3 steps:

Each of these 3 steps can control what happens next by returning different FailureProcessingResults. The options are:

Depending on the severity of failures posted in the transaction and whether the transaction is being committed or rolled back, each of these 3 steps may have certain options to resolve errors. All information about failures posted in a document, information about ability to perform certain operations to resolve failures and API to perform such operations are provided via the FailuresAccessor class. The Document can be used to obtain additional information, but it cannot be changed other than via FailuresAccessor.

The DesignAutomationBridge comes with a default failure handler. This failure handler will suppress all the warnings it encounters. In case of errors it will try to resolve them. If resolved successfully, the transaction will proceed with commit. If the default resolution is to delete elements the failure handler will not perform the delete action and will proceed with roll back.

You can implement your own custom failure handler to override the default failure handler. The failure posting API is easy to use. A custom failure definition can be registered in the HandleDesignAutomationReadyEvent() method of an external application, and then the failure severity and resolution type can be set. To register a failures processor, implement the interface IFailuresProcessor and register it using the Application.RegisterFailuresProcessor() method. Here is a code fragment to register a custom failure handler.

The IFailuresProcessor interface gets control last, after the FailuresProcessing event is processed. There is only one active IFailuresProcessor in a Revit session. If there is a previously registered failures processor, it is discarded. If the addin does not provide a failure processor of its own, then the default failure processor from Revit engine will be active. You can deactivate the default failure processor from the Revit engine by passing null to RegisterFailuresProcessor(). In the absence of all failure processors, Revit resolves failures via the default failure resolution type.

Warning: The IFailuresProcessor.ProcessFailures() method is allowed to return WaitForUserInput, which leaves the transaction pending so that the FailuresProcessor can display UI and get user input before resolving the failure. Don’t use WaitForUserInput; there is no UI or user interaction in the Automation API eco-system.

The code for the default failure handler from the Automation API can be seen in FailureProcessor.cs. Revit can be seen in FailureProcessor.cs.

The code implements IFailuresProcessor and suppresses any warnings. If there are errors, the code rolls back the transaction. If you need a different behavior, you can modify the code for the default FailureProcessor to fit your specifications.

**Examples:**

Example 1 (scala):
```scala
public void HandleDesignAutomationReadyEvent(object sender, DesignAutomationReadyEventArgs e)
{
   // Hook up a custom FailuresProcessing.
   Application rvtApp = e.DesignAutomationData.RevitApp;
   rvtApp.FailuresProcessing += OnFailuresProcessing;

   // Run the application logic.
   e.Succeeded = SketchItFunc(e.DesignAutomationData);

}

// Overwrite the failure processor to ignore all warnings and resolve all resolvable errors.
private void OnFailuresProcessing(object sender, FailuresProcessingEventArgs e)
{
   var fa = e?.GetFailuresAccessor();

   // Ignore all warnings.
   fa.DeleteAllWarnings();

   // Resolve all resolvable errors.
   var failures = fa.GetFailureMessages();
   if (!failures.Any())
   {
      return;
   }

   failures = failures.Where(fail => fail.HasResolutions()).ToList();
   fa.ResolveFailures(failures);
}
```

Example 2 (scala):
```scala
public void HandleDesignAutomationReadyEvent(object sender, DesignAutomationReadyEventArgs e)
{
   // Hook up a custom FailuresProcessing.
   Application rvtApp = e.DesignAutomationData.RevitApp;
   rvtApp.FailuresProcessing += OnFailuresProcessing;

   // Run the application logic.
   e.Succeeded = SketchItFunc(e.DesignAutomationData);

}

// Overwrite the failure processor to ignore all warnings and resolve all resolvable errors.
private void OnFailuresProcessing(object sender, FailuresProcessingEventArgs e)
{
   var fa = e?.GetFailuresAccessor();

   // Ignore all warnings.
   fa.DeleteAllWarnings();

   // Resolve all resolvable errors.
   var failures = fa.GetFailureMessages();
   if (!failures.Any())
   {
      return;
   }

   failures = failures.Where(fail => fail.HasResolutions()).ToList();
   fa.ResolveFailures(failures);
}
```

---

## Revit Automation Service Release Notes

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/change_history/revit_release_notes

**Contents:**
    - Jump To
- Revit Automation Service Release Notes
- April 2026
- April 2025
- April 2024
- April 2023
- March 2023
- September 2022
- March 2022
- September 2021

Added support for Revit version 2027.

Added support for Revit version 2026.

Added support for Revit version 2025.

Improved the security and resiliency of Revit automation.

Added support for Revit version 2024.

Read about our Engine Lifecycle Policy.

Fixed an issue where the Revit Cloud Model publish status would not be updated in Revit Home, even after the new model was saved to the Cloud.

Improved the success rate for Revit Cloud Model publish operations after the model is initiated to the cloud.

Added Autodesk Docs integration to the the Automation Service for Revit, which supports access and modification to both Revit non-workshared cloud models and Revit workshared cloud models.

Improved Revit engine by pre-installing additional commonly used fonts on the worker instances.

Improved the security and resiliency of the Automation Service for Revit jobs.

Improved performance for the Revit queue on the Automation Service by decreasing machine spin-up latency. Overall job processing times should be optimized.

Improved the machine specifications running Revit on the Automation Service, increasing total maximum memory from 16 GB to 32 GB.

Improved memory utilization for Revit instances.

Improved the security and resiliency of the Automation Service for Revit.

Improved stability for Revit 2019 - 2022 jobs that process or run against Revit models containing structural connections.

Improved the security and resiliency of the Automation Service for Revit jobs.

Added support for Revit version 2022.

Added the ability to export to PDF when using Revit version 2022.

Improved the security and resiliency of the Automation Service for Revit jobs.

Updated Revit 2021 version 2021.1.2.

Improved the security and resiliency of the Automation Service for Revit jobs.

Improved the security and resiliency of the Automation Service for Revit jobs.

Updated Revit 2021 version 2021.1.1.

Fixed Revit 2019 and Revit 2020 performance issue, which could cause Automation Service Revit jobs to perform slower compared to Revit running on a standard workstation.

Fixed an issue with Revit 2019 which could cause a hang at job completion.

Improved the security and resiliency of the Automation Service for Revit jobs.

Fixed an issue which could prematurely terminate longer running jobs.

Updated Revit 2020 support to Revit 2020.2.3.

Improved the security and resiliency of the Automation Service for Revit jobs.

Improved the security and resiliency of the Automation Service for Revit jobs.

Updated Revit 2021 support to Revit 2021.1.

Improved the security and resiliency of the Automation Service for Revit jobs.

Improved the default behavior for opening and saving models that have worksharing enabled, in order to preserve worksets on open, and support saving the model as a new central.

Updated Revit 2020 support to Revit 2020.2.2.

Improved the security and resiliency of the Automation Service for Revit jobs.

Added support for Revit version 2021.

Updated Revit 2020 support to Revit 2020.2.1.

Improved the documentation and code samples to include the latest resources for Revit.

Improved the security and resiliency of the Automation Service for Revit jobs.

Improved the security and resiliency of the Automation Service for Revit jobs.

Updated Revit 2020 support to Revit 2020.2.

Added functionality of onDemand input parameter, which allows an AppBundle to access additional input data resources during WorkItem processing; such as from a server, network or other storage location.

Increased the maximum upload timeout to be 300 seconds.

Fixed an issue where an AppBundle or Activity name could be incorrectly parsed if certain characters were specified.

Fixed an issue where non-ASCII characters could display incorrectly in the resulting log file.

Fixed an issue where WorkItems using Revit 2020 could time out after one minute of execution.

Added the ability to override the default 3 hour processing timeout limit for all jobs, or override the processing timeout limit for a specific job only.

Added support for Revit version 2020.

Added support for open + export IFC to the Revit 2018 engine. Also added support for open + export + link IFC to the Revit 2019-2020 engines.

Enabled the ability to use a virtual printer driver with the Revit engine.

Added customer accessible Revit code samples for the Automation API.

Improved the documentation and code samples to include the latest resources for Revit.

Improved the performance and resiliency of the Automation Service for Revit jobs related to larger and long running jobs.

Increased the timeout for Revit jobs on the Automation Service to support longer running jobs.

Enhanced the Automation Service Bridge (formerly known as the Design Automation Bridge) for Revit and made it available as a public facing nuget package.

Released Revit Automation API and documentation for public beta.

---

## Task 1 – Convert Revit Add-in to an Automation API Compatible Add-in

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/revit/step1-convert-addin

**Contents:**
    - Jump To
- Task 1 – Convert Revit Add-in to an Automation API Compatible Add-in
- Step 1 - Clone Git repository
- Step 2 - Repair references
- Step 3 - Add a package reference to the DesignAutomationBridge DLL
- Step 4 - Remove references to user interface elements
- Step 5 - Convert IExternalApplication or IExternalCommand to IExternalDBApplication
- Step 6 - Add an event handler for DesignAutomationReady
- Step 7 - Handle failures encountered by Revit
- Step 8 - Build the add-in

This task converts an add-in that runs on Revit to an add-in that runs on the Automation Service.

Prerequisites for this task are:

By the end of this task you will know how to convert a regular Revit add-in to one that runs on the Automation Service.

Clone the Git Repository for the DeleteWalls Sample, go to the folder named Desktop_Version, and open DeleteWalls.sln in Visual Studio.

The DeleteWalls Sample Git repository contains the source code for an add-in named DeleteWalls. DeleteWalls reads a .rvt file and produces another .rvt file with all the walls deleted.

The repository contains two folders for two different versions of DeleteWalls. The folder named Desktop_Version contains a C# project that produces a typical Revit add-in that runs only on Revit. It does not run on the Automation Service. The folder named Design-Automation_Version contains the same project, modified to run on the Automation Service. The objective of this task is to start with the C# project in Desktop_Version and end up with the project in Design-Automation_Version.

The C# project you cloned may expect to find RevitAPI.dll in a location that is different to where it resides on your computer. To eliminate the risk of a broken reference:

Autodesk provides a library that contains the functionality an add-in needs to interface with the Revit Automation Service. This library is known as the Automation Service Bridge (formerly known as the Design Automation Bridge) and is distributed as a NuGet package at https://www.nuget.org/packages/Autodesk.Forge.DesignAutomation.Revit.

|Tip: When inserting the package reference using Visual Studio, search for Autodesk.Forge.DesignAutomation.Revit with the Include prerelease option selected.

Since there is no UI interaction on the Automation Service, you must remove all references to UI elements.

In the .cs file that implements your add-in (DeleteWalls.cs in this case):

Whenever you are converting a Revit add-in in general, make sure that you:

Since there is no UI interaction on the Automation Service, you can’t use the Revit UI to initiate commands. In order to initiate commands with the Automation Service, you must implement OnStartup and OnShutdown in your add-in. These functions receive a ControlledApplication instead of a UIControlledApplication. The functions return an ExternalDBApplicationResult object:

For this task, in DeleteWalls.cs, implement OnStartup and OnShutdown as shown in the following code block.

DesignAutomationBridge defines the event DesignAutomationReadyEvent. The Revit engine raises the DesignAutomationReadyEvent when it’s ready to run your add-in. The event handler is the entry point to your code.

During the execution of your add-in, all files you load from the disk or write to the disk must go into the Windows current working directory. In the Automation Service, write access is limited to the current working directory and its children.

When an add-in runs on Revit, the add-in uses the UI to communicate warnings and errors. Since there is no UI interaction on the Automation Service, you must use an alternate strategy to handle failures.

For this walkthrough, you will use the default error handler. You don’t need to add any code to enable the default error handler because it comes by default with the Automation Service Bridge (formerly known as the Design Automation Bridge). The default error handler suppresses warnings and resolves errors automatically by applying the default options. If resolution of an error fails, it rolls back the failed action.

For more information refer Handling Revit Failures .

You should now have an Automation API compatible Revit add-in.

**Examples:**

Example 1 (unknown):
```unknown
Autodesk.Forge.DesignAutomation.Revit
```

Example 2 (unknown):
```unknown
Autodesk.Revit.UI
```

Example 3 (unknown):
```unknown
DesignAutomationFramework
```

Example 4 (julia):
```julia
using Autodesk.Revit.ApplicationServices;
using Autodesk.Revit.DB;
using DesignAutomationFramework;
```

---

## Task 8 - Download the Results

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/revit/step8-download-results

**Contents:**
    - Jump To
- Task 8 - Download the Results
- Step 1 - Get a S3 download URL for resulting RVT file
  - Request
  - Response
- Step 2 - Download resulting RVT file from OSS
  - Request
  - Response

After you submit a WorkItem, you must wait for it to complete and download the results.

By the end of this task, you will be able to:

You will use the following operation in this task:

Now that your WorkItem has finished successfully, the resulting text file should have been uploaded to OSS. You can now use the Data Management API to download it to your local machine.

Note: This download is directly from S3 (or a CDN). So, it doesn’t need an Authorization header.

The file should download to your local machine.

**Examples:**

Example 1 (typescript):
```typescript
curl -X GET \
      'https://developer.api.autodesk.com/oss/v2/buckets/<YOUR_BUCKET_KEY>/objects/<RESULT_FILE_OBJECT_KEY>/signeds3download'
      - H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
      - H 'Content-Type: application/json'
```

Example 2 (typescript):
```typescript
curl -X GET \
      'https://developer.api.autodesk.com/oss/v2/buckets/<YOUR_BUCKET_KEY>/objects/<RESULT_FILE_OBJECT_KEY>/signeds3download'
      - H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
      - H 'Content-Type: application/json'
```

Example 3 (json):
```json
{
    "status": "complete",
    "url": "<SIGNED_URL_TO_RESULT_FILE>",
    "params": {
        "content-type": "application/octet-stream",
        "content-disposition": "attachment; filename*=utf-8''ResultSmall.ipt; filename=ResultSmall.ipt; creation-date=\"Wed, 27 Sep 2023 08:52:52 GMT\"; modification-date=\"Wed, 27 Sep 2023 08:52:52 GMT\"; read-date=\"Wed, 27 Sep 2023 08:52:52 GMT\"; size=240128"
    },
    "size": 240128,
    "sha1": "064db8ddbfc3779335518f496ca232b140783201"
}
```

Example 4 (json):
```json
{
    "status": "complete",
    "url": "<SIGNED_URL_TO_RESULT_FILE>",
    "params": {
        "content-type": "application/octet-stream",
        "content-disposition": "attachment; filename*=utf-8''ResultSmall.ipt; filename=ResultSmall.ipt; creation-date=\"Wed, 27 Sep 2023 08:52:52 GMT\"; modification-date=\"Wed, 27 Sep 2023 08:52:52 GMT\"; read-date=\"Wed, 27 Sep 2023 08:52:52 GMT\"; size=240128"
    },
    "size": 240128,
    "sha1": "064db8ddbfc3779335518f496ca232b140783201"
}
```

---
