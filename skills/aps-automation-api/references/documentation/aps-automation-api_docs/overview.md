# Aps-Automation-Api_Docs - Overview

**Pages:** 5

---

## Aliases and IDs

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/overview/aliases-and-ids

**Contents:**
    - Jump To
- Aliases and IDs
- AppBundle and Activity Aliases
  - $LATEST alias
- IDs
  - Unqualified ID
  - Fully qualified ID
  - What form of ID to use

In order to be able to use a version of an AppBundle or an Activity, you have to specify an Alias for it. You can view an Alias as a user-friendly name for a specific AppBundle and/or Activity version.

There is no need for a 1-to-1 mapping between versions and Aliases. You can have many versions of an AppBundle and/or Activity and only some of these versions can have an Alias assigned to them.

Also, you can re-assign an existing alias to a different version at any time. This gives you the flexibility to swap, for example, a version of an activity used within your WorkItems without the need to update each and every WorkItem.

An example of the use of Aliases is to have a “Beta” and a “Production” Alias for an AppBundle/Activity. The “Production” Alias is assigned to your stable version of an AppBundle/Activity and the “Beta” Alias is assigned to a newer version of the same AppBundle/Activity. When the “Beta” version becomes stable, you assign the “Production” Alias to this newer version of the AppBundle/Activity.

For every AppBundle and Activity, the system always creates a special Alias named “$LATEST”. The main purpose of this Alias is for listing AppBundles and Activities. It can also be used in

calls. Note however, that it must not be used in other calls where an Alias (as part of fully qualified ID, see later) is expected. You must use the real Alias that you created for the AppBundle or the Activity in those calls.

An ID (id) is a user friendly name you provide for your AppBundle or Activity when you POST them for the first time.

In later calls, you use the ID to refer to that AppBundle and/or Activity. Note that the Automation API distinguishes between two kinds of such ID:

Unqualified ID is the single string you used during the POST request creating the AppBundle or the Activity.

Fully qualified IDs consist of three parts:

For the nickname, this can be up to 20 characters long consisting of a-z, A-Z, 0-9 and _ (underscore) only.

AppBundle, Activity, Version and Alias names can be up to 40 characters long.

For example, an Inventor App shares an Activity named “Configuration” to other users. “Configuration” is the unqualified ID of that Activity. Its fully qualified ID is Inventor.Configuration+prod, for its production version, and Inventor.Configuration+Beta for it’s newer beta version (when there is one).

Check HTTP Specification pages to find out the correct form of ID (unqualified or fully qualified) to be used in a specific call.

As a general rule, you typically use an unqualified ID when it is part of a URL or in the request body when creating the AppBundle and/or the Activity (i.e. when the Alias is not known yet). The only exception when a fully qualified ID is expected in the URL is the GET call for the AppBundle or the Activity details ([GET] /appbundles/:id and [GET] /activities/:id).

A fully qualified ID is returned in most calls that include the ID in the response. If an Alias has not been assigned to the AppBundle/Activity yet, the response will contain a fully qualified ID without the third part (the Alias).

The fully qualified ID is often referred to as “(owner.name+label)” in the HTTP Specification .

**Examples:**

Example 1 (sass):
```sass
Inventor.Configuration+prod
```

Example 2 (sass):
```sass
Inventor.Configuration+Beta
```

---

## API Basics

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/overview/basics

**Contents:**
    - Jump To
- API Basics
- Typical Workflows
  - Using a Pre-Existing Activity
  - Using a Custom Activity

Familiarize yourself with these concepts that are used throughout the documentation:

Use this workflow to execute a previously-created Activity, supplying one or more documents as inputs. The Activity will already have had the necessary AppBundles associated with it. The Activity defines the expected input and output files.

This workflow applies to both your own Activities and Activities that are shared with you.

This workflow is used when you need to create a new Activity and associate one or more AppBundles that define the custom programs or scripts to be executed on one or more documents.

(following steps are the same as for ‘Using a Pre-Existing Activity’)

---

## API Basics

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/basics

**Contents:**
    - Jump To
- API Basics
- Typical Workflows
  - Using a Pre-Existing Activity
  - Using a Custom Activity

Familiarize yourself with these concepts that are used throughout the documentation:

Use this workflow to execute a previously-created Activity, supplying one or more documents as inputs. The Activity will already have had the necessary AppBundles associated with it. The Activity defines the expected input and output files.

This workflow applies to both your own Activities and Activities that are shared with you.

This workflow is used when you need to create a new Activity and associate one or more AppBundles that define the custom programs or scripts to be executed on one or more documents.

(following steps are the same as for ‘Using a Pre-Existing Activity’)

---

## Field Guide

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/field-guide/

**Contents:**
    - Jump To
- Field Guide
- Entity Relationships
- Activity
  - Examples
    - AutoCAD
    - 3ds Max
    - Inventor
    - Revit
    - Fusion

As described in the API Basics page, there are four primary entities in the Automation API for executing custom programs or running scripts on input files:

An Activity is an action that can be executed within the core engine (AutoCAD, 3dsMax, Inventor or Fusion). For example, this might be plotting a DWG to PDF, updating the CAD standards in a drawing file or modifying the assembly based on iLogic parameters in Inventor.

A WorkItem is a specification of the processing job for an Activity, and it is submitted to and executed by the core engine.

Note that a WorkItem cannot be modified after it has been created.

An AppPackage is a module that is used by an Activity in order to perform a particular action.

An Engine is what executes a WorkItem job and processes the actions specified by an Activity.

A variable $(workitem.id) can be used in the payload. The following fields support variable expansion:

Note: Use of the command line is not support with the Fusion engine.

The command line contains variables of the form $(collection[index].property) where collection may have the following values:

1.1. path: full path to the file system entry (file or folder) for the argument/setting.

Note that this may be different than the localName for input arguments when the Content - Disposition header value is provided by the server. It is also different from localName when zip`=`true, in this case path will be determined like this:

1.2. value: string value of the argument/setting

2.1. path: full path to the folder where the appbundle is executing from.

3.1. path: full path to the folder where the engine is executing from.

$(engine.path)/AcCoreConsole.exe /i “$(args[hostDwg].path)” /s $(setting[script].path)

“$(appbundles[Autodesk.ShardingApp].path)/AcReadEx.exe” /i “$(args[hostDwg].path)” /retries $(args[retries].value))

Note: args and appbundles must be provided between quotes.

The working directory of the executable running in the context of the service will also contain a <workitem.id>_Job.das file. Appbundles can use this information to get to the details of the submitted work.

For example, you can use the following C# code to read this the contents of this file in your appbundle code:

var json = File.ReadAllText($”{Environment.ExpandEnvironmentVariables(“%DAS_WORKITEM_ID%”)}_job.das”);

This file contents are encoded as JSON. The following attributes will be present on the root object:

**Examples:**

Example 1 (json):
```json
{
    "commandLine": [
        "$(engine.path)\\accoreconsole.exe /i $(args[HostDwg].path) /al \"$(appbundles[Publish2View22].path)\" /s \"$(settings[script].path)\""
    ],
    "parameters": {
        "HostDwg": {
            "verb": "get",
            "description": "Host drawing",
            "localName": "$(EmptyDwg)"
        },
        "Result": {
            "zip": true,
            "verb": "post",
            "description": "Results",
            "localName": "result"
        }
    },
    "engine": "Autodesk.AutoCAD+22",
    "appbundles": [
        "AutoCAD.Publish2View22+prod"
    ],
    "settings": {
        "script": "(command \"_prepareforpropertyextraction\" \"index.json\")\n(command \"_indexextractor\" \"index.json\")\n(command \"_publishtosvf\" \"./output/result.svf\")\n(command \"_createbubblepackage\" \"./output\" \"./result\" \"\" \"\")\n"
    },
    "description": "AutoCAD translation sample generating SVF via core console.",
    "version": 1,
    "id": "AutoCAD.AcSvfPublish+prod"
}
```

Example 2 (json):
```json
{
    "commandLine": [
        "$(engine.path)\\accoreconsole.exe /i $(args[HostDwg].path) /al \"$(appbundles[Publish2View22].path)\" /s \"$(settings[script].path)\""
    ],
    "parameters": {
        "HostDwg": {
            "verb": "get",
            "description": "Host drawing",
            "localName": "$(EmptyDwg)"
        },
        "Result": {
            "zip": true,
            "verb": "post",
            "description": "Results",
            "localName": "result"
        }
    },
    "engine": "Autodesk.AutoCAD+22",
    "appbundles": [
        "AutoCAD.Publish2View22+prod"
    ],
    "settings": {
        "script": "(command \"_prepareforpropertyextraction\" \"index.json\")\n(command \"_indexextractor\" \"index.json\")\n(command \"_publishtosvf\" \"./output/result.svf\")\n(command \"_createbubblepackage\" \"./output\" \"./result\" \"\" \"\")\n"
    },
    "description": "AutoCAD translation sample generating SVF via core console.",
    "version": 1,
    "id": "AutoCAD.AcSvfPublish+prod"
}
```

Example 3 (json):
```json
{
    "id": "ExportToFBX",
    "commandLine": "$(engine.path)/3dsmaxbatch.exe -sceneFile \"$(args[InputFile].path)\" \"$(settings[script].path)\"",
    "description": "Export a single max file to FBX",
    "appbundles": [
        ],
    "engine" : "Autodesk.3dsMax+2021",
    "parameters": {
        "InputFile" : {
            "zip": false,
            "description": "Input 3ds Max file",
            "ondemand": false,
            "required": true,
            "verb": "get",
            "localName": "input.max"
        },
        "OutputFile": {
            "zip": false,
            "ondemand": false,
            "verb": "put",
            "description": "Output FBX file",
            "required": true,
            "localName": "output.fbx"
        }
    },
    "settings": {
       "script": "exportFile (sysInfo.currentdir + \"/output.fbx\") #noPrompt using:FBXEXP"
   }
}
```

Example 4 (json):
```json
{
    "id": "ExportToFBX",
    "commandLine": "$(engine.path)/3dsmaxbatch.exe -sceneFile \"$(args[InputFile].path)\" \"$(settings[script].path)\"",
    "description": "Export a single max file to FBX",
    "appbundles": [
        ],
    "engine" : "Autodesk.3dsMax+2021",
    "parameters": {
        "InputFile" : {
            "zip": false,
            "description": "Input 3ds Max file",
            "ondemand": false,
            "required": true,
            "verb": "get",
            "localName": "input.max"
        },
        "OutputFile": {
            "zip": false,
            "ondemand": false,
            "verb": "put",
            "description": "Output FBX file",
            "required": true,
            "localName": "output.fbx"
        }
    },
    "settings": {
       "script": "exportFile (sysInfo.currentdir + \"/output.fbx\") #noPrompt using:FBXEXP"
   }
}
```

---

## Field Guide

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/field-guide

**Contents:**
    - Jump To
- Field Guide
- Entity Relationships
- Activity
  - Examples
    - AutoCAD
    - 3ds Max
    - Inventor
    - Revit
    - Fusion

As described in the API Basics page, there are four primary entities in the Automation API for executing custom programs or running scripts on input files:

An Activity is an action that can be executed within the core engine (AutoCAD, 3dsMax, Inventor or Fusion). For example, this might be plotting a DWG to PDF, updating the CAD standards in a drawing file or modifying the assembly based on iLogic parameters in Inventor.

A WorkItem is a specification of the processing job for an Activity, and it is submitted to and executed by the core engine.

Note that a WorkItem cannot be modified after it has been created.

An AppPackage is a module that is used by an Activity in order to perform a particular action.

An Engine is what executes a WorkItem job and processes the actions specified by an Activity.

A variable $(workitem.id) can be used in the payload. The following fields support variable expansion:

Note: Use of the command line is not support with the Fusion engine.

The command line contains variables of the form $(collection[index].property) where collection may have the following values:

1.1. path: full path to the file system entry (file or folder) for the argument/setting.

Note that this may be different than the localName for input arguments when the Content - Disposition header value is provided by the server. It is also different from localName when zip`=`true, in this case path will be determined like this:

1.2. value: string value of the argument/setting

2.1. path: full path to the folder where the appbundle is executing from.

3.1. path: full path to the folder where the engine is executing from.

$(engine.path)/AcCoreConsole.exe /i “$(args[hostDwg].path)” /s $(setting[script].path)

“$(appbundles[Autodesk.ShardingApp].path)/AcReadEx.exe” /i “$(args[hostDwg].path)” /retries $(args[retries].value))

Note: args and appbundles must be provided between quotes.

The working directory of the executable running in the context of the service will also contain a <workitem.id>_Job.das file. Appbundles can use this information to get to the details of the submitted work.

For example, you can use the following C# code to read this the contents of this file in your appbundle code:

var json = File.ReadAllText($”{Environment.ExpandEnvironmentVariables(“%DAS_WORKITEM_ID%”)}_job.das”);

This file contents are encoded as JSON. The following attributes will be present on the root object:

**Examples:**

Example 1 (json):
```json
{
    "commandLine": [
        "$(engine.path)\\accoreconsole.exe /i $(args[HostDwg].path) /al \"$(appbundles[Publish2View22].path)\" /s \"$(settings[script].path)\""
    ],
    "parameters": {
        "HostDwg": {
            "verb": "get",
            "description": "Host drawing",
            "localName": "$(EmptyDwg)"
        },
        "Result": {
            "zip": true,
            "verb": "post",
            "description": "Results",
            "localName": "result"
        }
    },
    "engine": "Autodesk.AutoCAD+22",
    "appbundles": [
        "AutoCAD.Publish2View22+prod"
    ],
    "settings": {
        "script": "(command \"_prepareforpropertyextraction\" \"index.json\")\n(command \"_indexextractor\" \"index.json\")\n(command \"_publishtosvf\" \"./output/result.svf\")\n(command \"_createbubblepackage\" \"./output\" \"./result\" \"\" \"\")\n"
    },
    "description": "AutoCAD translation sample generating SVF via core console.",
    "version": 1,
    "id": "AutoCAD.AcSvfPublish+prod"
}
```

Example 2 (json):
```json
{
    "commandLine": [
        "$(engine.path)\\accoreconsole.exe /i $(args[HostDwg].path) /al \"$(appbundles[Publish2View22].path)\" /s \"$(settings[script].path)\""
    ],
    "parameters": {
        "HostDwg": {
            "verb": "get",
            "description": "Host drawing",
            "localName": "$(EmptyDwg)"
        },
        "Result": {
            "zip": true,
            "verb": "post",
            "description": "Results",
            "localName": "result"
        }
    },
    "engine": "Autodesk.AutoCAD+22",
    "appbundles": [
        "AutoCAD.Publish2View22+prod"
    ],
    "settings": {
        "script": "(command \"_prepareforpropertyextraction\" \"index.json\")\n(command \"_indexextractor\" \"index.json\")\n(command \"_publishtosvf\" \"./output/result.svf\")\n(command \"_createbubblepackage\" \"./output\" \"./result\" \"\" \"\")\n"
    },
    "description": "AutoCAD translation sample generating SVF via core console.",
    "version": 1,
    "id": "AutoCAD.AcSvfPublish+prod"
}
```

Example 3 (json):
```json
{
    "id": "ExportToFBX",
    "commandLine": "$(engine.path)/3dsmaxbatch.exe -sceneFile \"$(args[InputFile].path)\" \"$(settings[script].path)\"",
    "description": "Export a single max file to FBX",
    "appbundles": [
        ],
    "engine" : "Autodesk.3dsMax+2021",
    "parameters": {
        "InputFile" : {
            "zip": false,
            "description": "Input 3ds Max file",
            "ondemand": false,
            "required": true,
            "verb": "get",
            "localName": "input.max"
        },
        "OutputFile": {
            "zip": false,
            "ondemand": false,
            "verb": "put",
            "description": "Output FBX file",
            "required": true,
            "localName": "output.fbx"
        }
    },
    "settings": {
       "script": "exportFile (sysInfo.currentdir + \"/output.fbx\") #noPrompt using:FBXEXP"
   }
}
```

Example 4 (json):
```json
{
    "id": "ExportToFBX",
    "commandLine": "$(engine.path)/3dsmaxbatch.exe -sceneFile \"$(args[InputFile].path)\" \"$(settings[script].path)\"",
    "description": "Export a single max file to FBX",
    "appbundles": [
        ],
    "engine" : "Autodesk.3dsMax+2021",
    "parameters": {
        "InputFile" : {
            "zip": false,
            "description": "Input 3ds Max file",
            "ondemand": false,
            "required": true,
            "verb": "get",
            "localName": "input.max"
        },
        "OutputFile": {
            "zip": false,
            "ondemand": false,
            "verb": "put",
            "description": "Output FBX file",
            "required": true,
            "localName": "output.fbx"
        }
    },
    "settings": {
       "script": "exportFile (sysInfo.currentdir + \"/output.fbx\") #noPrompt using:FBXEXP"
   }
}
```

---
