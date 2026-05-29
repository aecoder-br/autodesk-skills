# Aps-Automation-Api_Docs - Developer Guide

**Pages:** 11

---

## APS Rate Limits and Quotas

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/rate-limits/forge-rate-limits

**Contents:**
    - Jump To
- APS Rate Limits and Quotas
- Rate Limits
  - Notification
    - Response Header (429)
    - Response Body (429)
- Quotas
  - Notification
- Scope
  - Rate Limit Scope

The Autodesk Platform Service (APS) provides a set of cloud resources that are shared among many applications and services. Autodesk strives to ensure that there are plenty of cloud resources to serve all platform users. However, runaway applications and malicious attacks can quickly consume resources and diminish service. To avoid overconsumption and service degradation, APS sets rate limits and quotas for users of each of its services. This page describes how those rate limits and quotas work.

Rate limits are simple: a rate limit sets the maximum number of API calls an application can make per minute. Rate limits help keep the number of API calls within the capacity of the service, and guard against instability and attacks such as denial-of-service attacks. This ensures availability and consistent quality of service for all users.

The rate limits may vary by each service or by endpoints within a service. Rate limits are currently placed at a generous level that shouldn’t cause problems with applications running under normal circumstances. They may come into play and limit an application if the application generates an unusually high volume of API calls.

Rate limits are not guaranteed service levels. If a service is overloaded for any reason, request rate limits may effectively drop until the overload condition ends.

When an application exceeds the published rate limit for a given endpoint, the API returns an HTTP 429 "Too many requests" response code. The response header has a parameter named Retry-After that specifies how many seconds to wait before making a new request. We strongly recommend that you retry a request only after the waiting period has elapsed.

The following example shows a typical 429 response.

Quotas come into play after a service request is accepted. A quota limits an application’s use of resources as the application carries out activities within an APS service. Quotas may limit, for example, file sizes uploaded, downloaded, and processed; the amount of processing time allowed per job; an application’s monthly service consumption; and so on. Each APS service may have a set of built-in quotas. They may also offer custom quotas that a user or application can set to lower resource consumption below the built-in limits if desired to further restrict resource use.

Note again that quotas are not guaranteed service levels. Quota limits may drop temporarily if a service is overloaded.

Exceeding a quota typically occurs when an API request specifies excessive resource use. The service receiving the request replies with an error response that specifies the quota violation. Sometimes, where resource use doesn’t occur until after a request is received (the request places a job on a queue, for example), the quota violation occurs during later execution and throws an error there. In that case the requester may set up a callback to provide error notification. If a callback isn’t possible, the requester can poll regularly (but not too frequently) to make sure that execution is carried out correctly.

The scope of APS rate limits and quotas (how widely or narrowly they apply) varies across APIs and resource types. Scope is defined by how request rate or resource use is tallied: on the client side whether it’s tallied per user ID or application, for example, and on the service side whether it’s applied across an entire API, for example, or to individual endpoints or resources within an API.

Rate limits on the client side may apply per user ID or per application. On the service side, a rate limit may apply across an entire API or to individual endpoints within an API, changing from one endpoint to another.

Quotas on the client side may apply per user ID or per application. On the service side, they may apply to a particular resource type, to the underlying engine servicing a request, to an endpoint, or other qualifying attributes. Because quotas are typically resource-specific, their scope is often narrowly defined.

API specific rate limit and quota pages spell out the scope for each API’s rate limit and quota.

If a rate limit or quota causes problems for an application with reasonable resource use, you can request a limit or quota change by contacting support via https://aps.autodesk.com/get-help.

**Examples:**

Example 1 (unknown):
```unknown
HTTP 429 "Too many requests"
```

Example 2 (unknown):
```unknown
Retry-After
```

Example 3 (yaml):
```yaml
HTTP/1.1 429 Too Many Requests
Content-Type: application/json
Retry-After: 25
Server: Apigee Router
Content-Length: 44
```

Example 4 (yaml):
```yaml
HTTP/1.1 429 Too Many Requests
Content-Type: application/json
Retry-After: 25
Server: Apigee Router
Content-Length: 44
```

---

## APS Rate Limits and Quotas

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/rate-limits

**Contents:**
    - Jump To
- APS Rate Limits and Quotas
- Rate Limits
  - Notification
    - Response Header (429)
    - Response Body (429)
- Quotas
  - Notification
- Scope
  - Rate Limit Scope

The Autodesk Platform Service (APS) provides a set of cloud resources that are shared among many applications and services. Autodesk strives to ensure that there are plenty of cloud resources to serve all platform users. However, runaway applications and malicious attacks can quickly consume resources and diminish service. To avoid overconsumption and service degradation, APS sets rate limits and quotas for users of each of its services. This page describes how those rate limits and quotas work.

Rate limits are simple: a rate limit sets the maximum number of API calls an application can make per minute. Rate limits help keep the number of API calls within the capacity of the service, and guard against instability and attacks such as denial-of-service attacks. This ensures availability and consistent quality of service for all users.

The rate limits may vary by each service or by endpoints within a service. Rate limits are currently placed at a generous level that shouldn’t cause problems with applications running under normal circumstances. They may come into play and limit an application if the application generates an unusually high volume of API calls.

Rate limits are not guaranteed service levels. If a service is overloaded for any reason, request rate limits may effectively drop until the overload condition ends.

When an application exceeds the published rate limit for a given endpoint, the API returns an HTTP 429 "Too many requests" response code. The response header has a parameter named Retry-After that specifies how many seconds to wait before making a new request. We strongly recommend that you retry a request only after the waiting period has elapsed.

The following example shows a typical 429 response.

Quotas come into play after a service request is accepted. A quota limits an application’s use of resources as the application carries out activities within an APS service. Quotas may limit, for example, file sizes uploaded, downloaded, and processed; the amount of processing time allowed per job; an application’s monthly service consumption; and so on. Each APS service may have a set of built-in quotas. They may also offer custom quotas that a user or application can set to lower resource consumption below the built-in limits if desired to further restrict resource use.

Note again that quotas are not guaranteed service levels. Quota limits may drop temporarily if a service is overloaded.

Exceeding a quota typically occurs when an API request specifies excessive resource use. The service receiving the request replies with an error response that specifies the quota violation. Sometimes, where resource use doesn’t occur until after a request is received (the request places a job on a queue, for example), the quota violation occurs during later execution and throws an error there. In that case the requester may set up a callback to provide error notification. If a callback isn’t possible, the requester can poll regularly (but not too frequently) to make sure that execution is carried out correctly.

The scope of APS rate limits and quotas (how widely or narrowly they apply) varies across APIs and resource types. Scope is defined by how request rate or resource use is tallied: on the client side whether it’s tallied per user ID or application, for example, and on the service side whether it’s applied across an entire API, for example, or to individual endpoints or resources within an API.

Rate limits on the client side may apply per user ID or per application. On the service side, a rate limit may apply across an entire API or to individual endpoints within an API, changing from one endpoint to another.

Quotas on the client side may apply per user ID or per application. On the service side, they may apply to a particular resource type, to the underlying engine servicing a request, to an endpoint, or other qualifying attributes. Because quotas are typically resource-specific, their scope is often narrowly defined.

API specific rate limit and quota pages spell out the scope for each API’s rate limit and quota.

If a rate limit or quota causes problems for an application with reasonable resource use, you can request a limit or quota change by contacting support via https://aps.autodesk.com/get-help.

**Examples:**

Example 1 (unknown):
```unknown
HTTP 429 "Too many requests"
```

Example 2 (unknown):
```unknown
Retry-After
```

Example 3 (yaml):
```yaml
HTTP/1.1 429 Too Many Requests
Content-Type: application/json
Retry-After: 25
Server: Apigee Router
Content-Length: 44
```

Example 4 (yaml):
```yaml
HTTP/1.1 429 Too Many Requests
Content-Type: application/json
Retry-After: 25
Server: Apigee Router
Content-Length: 44
```

---

## Automation API Rate Limit and Quotas

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/rate-limits/da-rate-limits/

**Contents:**
    - Jump To
- Automation API Rate Limit and Quotas
- Rate Limit
- Quotas
  - Scope
  - WorkItem Quotas
  - WorkItem Heartbeat
  - Activity and App Bundle Quotas
  - Quota Violation Notification
  - Setting Custom Quotas

The Automation service observes a rate limit and a set of quotas to ensure that all clients get sufficient service and that runaway applications don’t consume excessive resources. APS Rate Limits and Quotas describes rate limits and quotas in general.

The Automation Service has a rate limit of 100 calls per minute by an app (identified by Client ID). Exceeding that limit returns an HTTP 429 response.

Automation Service quotas limit an app’s resource consumption when using the Automation API.

Quotas are enforced individually for each app (identified by client ID) that uses the Automation service. Furthermore, quotas apply to the different elements used by the application:

Quota limits may differ depending on the engine the application uses: AutoCAD, Inventor, Revit, 3ds Max, or Fusion.

The quota descriptions that follow each define the element to which the quota applies and the limit for each engine.

These quotas limit a work item’s resource consumption. The quotas are typically different for each engine as listed below.

The WorkItem quota is the same across all engines: a WorkItem’s processing time (when it runs an app in an app bundle) cannot exceed one minute without a “heartbeat” to indicate that it is working correctly and not in an infinite loop. The simplest heartbeat is for the app to send output to the standard output (or trace output) stream from your code. However, if you invoke a single operation that is expected to take more than one minute (opening a large file, for example), you can send the output asynchronously. See the Visual Studio Extension code for examples.

These quotas limit resource consumption by activities and app bundles. The quotas can be different for each engine as listed below. Additionally, AppBundles and Activities can be shared by up to 30 other apps.

The Automation Service reports quota violations in different ways depending on the type of quota. For work items, the service can’t determine violations when a work item is submitted and put on the job queue. Once the work item is processed, if the work item exceeds a quota then the work item fails. The best practice for determining if a work item has exceeded a quota is to use the OnComplete callback in the GET workitems endpoint and use it to check for work item failure.

Activity and app bundle quota violations are reported in endpoint failure responses after trying to submit or modify an app bundle or activity with parameters that violate a quota.

The Automation API lets you set custom quotas that are lower than the default quotas specified above. Custom quotas can help reduce cloud credit consumption.

Most custom quotas are set using the PUT servicelimits operation. These quotas control WorkItem upload and download limits, upload and download size, processing time, payload size, and other work item limits. The quotas also control app and activity version and alias limits, payload size, and other limits. You can find these custom quotas described in detail in PUT servicelimits.

POST workitems also sets a custom quota through its limitProcessingTimeSec attribute. A WorkItem’s maximum duration of processing time is set by default to a value ranging from 100 to 10800 seconds (as shown in the work item quotas table above) depending on the engine used. limitProcessingTimeSec can change that value for a single work item down or up to a maximum of 400 to 43200 seconds (also shown in the table above) depending on the engine used.

APS by default does not limit the total time each month that an app takes to run automations. If you want to set a monthly limit, use the PUT servicelimits operation to set the limitMonthlyProcessingTimeInHours attribute in frontendLimits. This limits the amount of Automation API specific processing time that the app is allowed to consume each month. If the application reaches the consumption limit, the Automation Service rejects subsequent WorkItems for the remainder of the calendar month.

**Examples:**

Example 1 (unknown):
```unknown
limitProcessingTimeSec
```

Example 2 (unknown):
```unknown
limitProcessingTimeSec
```

Example 3 (unknown):
```unknown
limitProcessingTimeSec
```

Example 4 (unknown):
```unknown
limitMonthlyProcessingTimeInHours
```

---

## Custom Fonts Support

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/revit_specific/custom-fonts-support

**Contents:**
    - Jump To
- Custom Fonts Support
- Supported Fonts

The Automation API cloud-based worker instances that process your Revit models may not have the same fonts installed as your local Revit environment. When a required font is unavailable, the system automatically substitutes it with a similar font, which can affect the visual appearance of exported models and drawings.

To improve output quality and reduce font substitution issues, we now pre-install commonly used fonts on all worker instances. This ensures better visual fidelity for most projects without requiring additional configuration.

The following fonts are available on all worker instances:

All standard Windows Server 2019 built-in fonts

---

## Handling Revit Failures

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/revit_specific/handling-failures/

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

## Handling Revit Failures

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/revit_specific

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

## Handling Revit Failures

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/revit_specific/handling-failures

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

## Reference downloading

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/reference-downloading

**Contents:**
    - Jump To
- Reference downloading
- 1. Autodesk Docs
- 2. OneDrive
- 3. DropBox
- 4. Google Drive
- 5. Box

The Automation Service is able to follow and download references embedded in design files. Client applications can trigger this function by using the refget verb instead of get in an argument inside a workitem.

The following storage types are supported:

The service recognizes URLs of the form https://developer.api.autodesk.com/data/v1/projects/:projectId/items/:itemId. For more information see the Data Management API documentation. When used in this context, refget verb also honor/download connected support files. You must use a 3-legged OAuth token with at least data:read scope to download Autodesk Docs files.

The service recognizes URLs of the form https://graph.microsoft.com/v1.0/drives/:driveId/items/:itemId/. For more information see the OneDrive API documentation. Note that only item id references are supported, item path references will cause an error.

The service recognizes URLs of the form das://dropbox/:fileId. The :fileId must be valid DropBox id starting with id:. For more information see the DropBox API documentation.

The service recognizes URLs of the form https://www.googleapis.com/drive/v3/files/:fileId. For more information see the Google Drive API documentation.

The service recognizes URLs of the form https://api.box.com/2.0/files/:fileId. For more information see the Box API documentation.

**Examples:**

Example 1 (yaml):
```yaml
https://developer.api.autodesk.com/data/v1/projects/:projectId/items/:itemId
```

Example 2 (json):
```json
{
    "activityId": "AutoCAD.PlotToPDF+prod",
    "arguments": {
        "HostDwg": {
            "url": "https://developer.api.autodesk.com/data/v1/projects/b.25b50afe-1892-46b0-8ae6-be035605fd51/items/urn:adsk.wipprod:dm.lineage:CC-mn_2VQYunOdGi1cVdlQ",
            "verb": "refget",
            "headers" : {
                "Authorization": "Bearer <AN AUTODESK TOKEN>"
            }
        },
        "Result": {
            "url": "urn:adsk.objects:os.object:<YOUR_BUCKET_KEY>/<OBJECT_KEY>",
            "verb": "put",
            "headers": {
                "Authorization": "Bearer <AN AUTODESK TOKEN>"
            }
        }
    }
}
```

Example 3 (json):
```json
{
    "activityId": "AutoCAD.PlotToPDF+prod",
    "arguments": {
        "HostDwg": {
            "url": "https://developer.api.autodesk.com/data/v1/projects/b.25b50afe-1892-46b0-8ae6-be035605fd51/items/urn:adsk.wipprod:dm.lineage:CC-mn_2VQYunOdGi1cVdlQ",
            "verb": "refget",
            "headers" : {
                "Authorization": "Bearer <AN AUTODESK TOKEN>"
            }
        },
        "Result": {
            "url": "urn:adsk.objects:os.object:<YOUR_BUCKET_KEY>/<OBJECT_KEY>",
            "verb": "put",
            "headers": {
                "Authorization": "Bearer <AN AUTODESK TOKEN>"
            }
        }
    }
}
```

Example 4 (yaml):
```yaml
https://graph.microsoft.com/v1.0/drives/:driveId/items/:itemId/
```

---

## Revit Cloud Model Integration

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/revit_specific/revit-cloud-model-integration/

**Contents:**
    - Jump To
- Revit Cloud Model Integration
- Overview
- Authentication Requirements
- Element Ownership Validation

The Revit Automation Service integration with Autodesk Docs enables you to access and modify both workshared and non-workshared cloud models using standard Revit Cloud Model (RCM) Desktop APIs. This functionality is available for Revit 2022, Revit 2023, and Revit 2024.

To access cloud models, you must provide user authentication through the adsk3LeggedToken WorkItem argument.

Setting up authentication:

The 3-legged token allows your application to access the user’s cloud models without requiring their direct credentials. When this token is provided, the Automation service establishes the necessary user context and enables Revit Cloud Model APIs within the automation environment.

Important: Without a valid adsk3LeggedToken, cloud model APIs like Document.OpenDocumentFile() will fail to open cloud models. Standard APIs that don’t require user context will continue to work normally.

For a complete implementation example, see our code sample.

The service validates whether the authenticated user already has elements checked out in the target cloud model. If existing checkouts are detected, the system posts a warning (FailureDefinitionId: 'BuiltInFailures.OpeningFailures.ModelAlreadyCheckedOutByUser').

Default behavior: The automation job stops when this warning occurs to prevent conflicts with existing modifications.

Custom handling: You can implement a custom failures processor to bypass this warning and continue processing. However, be aware that proceeding may invalidate the user’s existing uncommitted changes.

For more information about customizing failure handling, see Handling Revit Failures.

**Examples:**

Example 1 (unknown):
```unknown
adsk3LeggedToken
```

Example 2 (sass):
```sass
scope=code:all
```

Example 3 (unknown):
```unknown
adsk3LeggedToken
```

Example 4 (unknown):
```unknown
adsk3LeggedToken
```

---

## TypeScript

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/fusion_specific/typescript

**Contents:**
    - Jump To
- TypeScript
- Local Development and Debugging
- API Restrictions
- Text and Fonts
- Forum Support

The Fusion API enables you to create scripts and add-ins that automate design workflows. While Fusion’s desktop API supports Python and C++ development, the Fusion Automation API exclusively uses TypeScript.

This page explains how to develop TypeScript scripts for the Fusion engine, including the tools available for local development and the API restrictions you should be aware of.

We provide a TypeScript Add-In that lets you develop, debug, and test scripts locally before deploying them via the Automation API. Download the add-in from our GitHub repository.

For detailed usage instructions, see the add-in documentation.

The add-in includes built-in reference documentation for all available TypeScript API classes and methods.

The TypeScript API provides most of the functionality available in Fusion’s desktop APIs, with these key limitations:

These restrictions ensure scripts run reliably in the cloud automation environment.

The Automation API for Fusion supports the use of text and fonts in designs, but there are some limitations in the supported fonts. If a Fusion design is opened using the service, and uses an unsupported font, the font will default to Arial. Below is a list of supported fonts:

Post questions and get community help on the Fusion API and Scripts forum. This public forum connects you with other developers and Autodesk experts who can help troubleshoot Fusion API issues.

---

## Using 3-legged OAuth Tokens

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/3-legged-oauth-token-usage

**Contents:**
    - Jump To
- Using 3-legged OAuth Tokens

You can write client applications that use a 3-legged OAuth token with the Automation Service when the code making the call to the Automation API resides on the end-user’s device (for example, a mobile app or web app). You must exercise caution so as not to expose your apps to undue risk. There is a security risk when storing the Client ID or Client Secret on the end-user device (as required when you want to use a 2-legged token), which is the reason to use a 3-legged token. However, there are additional risks that you must consider. This topic describes some of these risks and the facilities that the Automation API offers to mitigate them.

The problem with scenarios involving 3-legged OAuth tokens is that when the end user makes a REST API call, the payer is not the end user, at least not directly. The payer is the app that allows the end user to obtain the 3-legged token. The payer wants to control which APS APIs the 3-legged token is allowed to call. This problem is traditionally solved with scopes. However, scopes can only restrict endpoints; they cannot restrict the request body. A malicious user can change the request body to call a different activity than you intended.

To solve this problem, the Automation API offers the following protections:

The following steps demonstrate what developers need to do to sign their WorkItems. Before you continue, download the latest Das.WorkitemSigner for Windows from here.

These changes aim to improve clarity and structure while maintaining the technical accuracy of the document.

**Examples:**

Example 1 (unknown):
```unknown
Das.WorkitemSigner.exe generate mykey.json
```

Example 2 (unknown):
```unknown
Das.WorkitemSigner.exe generate mykey.json
```

Example 3 (unknown):
```unknown
Das.WorkitemSigner.exe export mykey.json mypublickey.json
```

Example 4 (unknown):
```unknown
Das.WorkitemSigner.exe export mykey.json mypublickey.json
```

---
