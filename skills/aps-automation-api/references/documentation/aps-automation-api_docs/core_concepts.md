# Aps-Automation-Api_Docs - Core Concepts

**Pages:** 55

---

## activities/:id/aliases/:aliasId

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/activities-id-aliases-aliasId-GET

**Contents:**
    - Jump To
- activities/:id/aliases/:aliasId
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
  - Response

Successfully get the details of an Activity’s alias.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id/aliases/:aliasId' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id/aliases/:aliasId' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (json):
```json
{
  "version": 1,
  "id": "prod"
}
```

---

## activities/:id/aliases/:aliasId

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/activities-id-aliases-aliasId-PATCH

**Contents:**
    - Jump To
- activities/:id/aliases/:aliasId
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Request
- Body Structure
  - Response

Modifies alias details.

Successfully modify an alias details.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
application/json
```

Example 3 (json):
```json
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id/aliases/:aliasId' \
  -X 'PATCH' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "version": 1
      }'
```

Example 4 (json):
```json
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id/aliases/:aliasId' \
  -X 'PATCH' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "version": 1
      }'
```

---

## activities/:id/aliases

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/activities-id-aliases-POST

**Contents:**
    - Jump To
- activities/:id/aliases
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Request
- Body Structure
  - Response

Creates a new alias for this Activity.

Successfully create a new Activity alias.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
application/json
```

Example 3 (json):
```json
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id/aliases' \
  -X 'POST' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "version": 1,
        "id": "prod"
      }'
```

Example 4 (json):
```json
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id/aliases' \
  -X 'POST' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "version": 1,
        "id": "prod"
      }'
```

---

## activities/:id/versions/:version

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/activities-id-versions-version-GET

**Contents:**
    - Jump To
- activities/:id/versions/:version
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
  - Response

Gets the details of the specified version of the Activity.

It supports Box, Google Drive and Amazon Simple Storage Service (S3) services.

Examples of using argument “multiparts”:

Amazon Simple Storage Service (S3):

Successfully get the details of an Activity’s version.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id/versions/:version' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id/versions/:version' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (json):
```json
{
  "commandLine": [
    "$(engine.path)\\InventorCoreConsole.exe /i \"$(args[InventorDoc].path)\" /al \"$(appbundles[ChangeParams].path)\" \"$(args[InventorParams].path)\""
  ],
  "parameters": {
    "InventorDoc": {
      "verb": "get"
    },
    "InventorParams": {
      "localName": "params.json",
      "verb": "get"
    },
    "OutputIpt": {
      "localName": "Result.ipt",
      "verb": "post"
    },
    "OutputIam": {
      "localName": "Result.zip",
      "verb": "post"
    },
    "OutputBmp": {
      "localName": "Result.bmp",
      "verb": "post"
    }
  },
  "id": "SampleActivity",
  "engine": "Autodesk.Inventor+23",
  "appbundles": [
    "owner.ChangeParams+prod"
  ],
  "description": "Human readable description of the object.",
  "version": 1
}
```

---

## activities/:id/versions

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/activities-id-versions-POST

**Contents:**
    - Jump To
- activities/:id/versions
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Request
- Body Structure
  - Response

Creates a new version of the Activity.

It supports Box, Google Drive and Amazon Simple Storage Service (S3) services.

Examples of using argument “multiparts”:

Amazon Simple Storage Service (S3):

It supports Box, Google Drive and Amazon Simple Storage Service (S3) services.

Examples of using argument “multiparts”:

Amazon Simple Storage Service (S3):

Successfully create a new verison of an Activity.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
application/json
```

Example 3 (sass):
```sass
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/SampleActivity/versions' \
  -X 'POST' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "commandLine": [
          "$(engine.path)\\InventorCoreConsole.exe /i \"$(args[InventorDoc].path)\" /al \"$(appbundles[ChangeParams].path)\" \"$(args[InventorParams].path)\""
        ],
        "parameters": {
          "InventorDoc": {
            "verb": "get"
          },
          "InventorParams": {
            "localName": "params.json",
            "verb": "get"
          },
          "OutputIpt": {
            "localName": "Result.ipt",
            "verb": "post"
          },
          "OutputIam": {
            "localName": "Result.zip",
            "verb": "post"
          },
          "OutputBmp": {
            "localName": "Result.bmp",
            "verb": "post"
          }
        },
        "engine": "Autodesk.Inventor+23",
        "appbundles": [
          "owner.ChangeParams+prod"
        ],
        "description": "Human readable description of the object."
      }'
```

Example 4 (sass):
```sass
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/SampleActivity/versions' \
  -X 'POST' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "commandLine": [
          "$(engine.path)\\InventorCoreConsole.exe /i \"$(args[InventorDoc].path)\" /al \"$(appbundles[ChangeParams].path)\" \"$(args[InventorParams].path)\""
        ],
        "parameters": {
          "InventorDoc": {
            "verb": "get"
          },
          "InventorParams": {
            "localName": "params.json",
            "verb": "get"
          },
          "OutputIpt": {
            "localName": "Result.ipt",
            "verb": "post"
          },
          "OutputIam": {
            "localName": "Result.zip",
            "verb": "post"
          },
          "OutputBmp": {
            "localName": "Result.bmp",
            "verb": "post"
          }
        },
        "engine": "Autodesk.Inventor+23",
        "appbundles": [
          "owner.ChangeParams+prod"
        ],
        "description": "Human readable description of the object."
      }'
```

---

## activities/:id/versions

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/activities-id-versions-GET

**Contents:**
    - Jump To
- activities/:id/versions
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Request
- Query String Parameters
  - Response

Lists all versions of the specified Activity.

Successfully list all versions of an Activity.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id/versions' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id/versions' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (json):
```json
{
  "paginationToken": "",
  "data": [
    1
  ]
}
```

---

## activities/:id

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/activities-id-GET

**Contents:**
    - Jump To
- activities/:id
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
  - Response

Gets the details of the specified Activity. Note that the {id} parameter must be a QualifiedId (owner.name+label).

It supports Box, Google Drive and Amazon Simple Storage Service (S3) services.

Examples of using argument “multiparts”:

Amazon Simple Storage Service (S3):

Successfully get the details of an Activity.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (json):
```json
{
  "commandLine": [
    "$(engine.path)\\InventorCoreConsole.exe /i \"$(args[InventorDoc].path)\" /al \"$(appbundles[ChangeParams].path)\" \"$(args[InventorParams].path)\""
  ],
  "parameters": {
    "InventorDoc": {
      "verb": "get"
    },
    "InventorParams": {
      "localName": "params.json",
      "verb": "get"
    },
    "OutputIpt": {
      "localName": "Result.ipt",
      "verb": "post"
    },
    "OutputIam": {
      "localName": "Result.zip",
      "verb": "post"
    },
    "OutputBmp": {
      "localName": "Result.bmp",
      "verb": "post"
    }
  },
  "id": "owner.SampleActivity+test",
  "engine": "Autodesk.Inventor+23",
  "appbundles": [
    "owner.ChangeParams+prod"
  ],
  "description": "Human readable description of the object.",
  "version": 1
}
```

---

## activities/:id

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/activities-id-DELETE

**Contents:**
    - Jump To
- activities/:id
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
- Example

Deletes the specified Activity, including all versions and aliases.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id' \
  -X 'DELETE' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities/:id' \
  -X 'DELETE' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (unknown):
```unknown
204 No Content
```

---

## activities

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/activities-GET

**Contents:**
    - Jump To
- activities
- Resource Information
  - Request
- Headers
  - Request
- Query String Parameters
  - Response
- HTTP Status Code Summary
  - Response

Lists all available Activities, including Activities shared with this app.

Successfully get all available Activities.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/activities' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (json):
```json
{
  "paginationToken": "",
  "data": [
    "Autodesk.Nop+Latest",
    "AutoCAD.AcSvfPublish+prod",
    "Revit.RvtIOSandboxTestActivity2018+prod",
    "3dsMax.HelloWorld+Latest",
    "Revit.RvtIOSketchItActivity2018+prod",
    "Inventor.BasicPluginTest+prod",
    "3dsMax.bakeToTexture+Latest",
    "Inventor.iLogic_Volume2020+prod",
    "AutoCAD.AcF2dPublish+prod",
    "AutoCAD.AcLMVPublish+prod",
    "AutoCAD.PlotToPDF+prod",
    "Inventor.Configuration+Beta",
    "Inventor.ChangeParams+prod"
  ]
}
```

---

## Activity Variable Arguments

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/vararg

**Contents:**
    - Jump To
- Activity Variable Arguments
- Example 1
- Example 2

An activity may need to process variable counts of inputs or generate variable counts of outputs. To describe such variable number of arguments activity authors will use a specially named parameter. The parameter must be named …

Given the above activity, users can submit workitems as Combinator:

Given the above activity, users can submit workitems as below:

**Examples:**

Example 1 (json):
```json
{
  "id": "CombinePdf",
  "engine": "Autodesk.AutoCAD+24_3",
  "parameters": {
      "...": {
        "verb": "put" // will match any extra arguments as outputs in the workitem using verb "put"
      },
      "output": {
          "verb": "put",
          "description": "result",
          "required": false,
          "localName": "result.pdf"
      }
  }
}
```

Example 2 (json):
```json
{
  "id": "CombinePdf",
  "engine": "Autodesk.AutoCAD+24_3",
  "parameters": {
      "...": {
        "verb": "put" // will match any extra arguments as outputs in the workitem using verb "put"
      },
      "output": {
          "verb": "put",
          "description": "result",
          "required": false,
          "localName": "result.pdf"
      }
  }
}
```

Example 3 (json):
```json
{
  "activityId" : "mynickname.CombinePdf+prod",
  "arguments" {
      "output": {
          "url" : "http://sample.com/result.pdf"
      },
      "result1" : {
          "url": "http://sample.com/some.ext",
          "localName":"some.ext"
      },
      "result2" : {
          "url": "http://sample.com/some_more.ext",
          "localName":"some_more.ext"
      }
  }
}
```

Example 4 (json):
```json
{
  "activityId" : "mynickname.CombinePdf+prod",
  "arguments" {
      "output": {
          "url" : "http://sample.com/result.pdf"
      },
      "result1" : {
          "url": "http://sample.com/some.ext",
          "localName":"some.ext"
      },
      "result2" : {
          "url": "http://sample.com/some_more.ext",
          "localName":"some_more.ext"
      }
  }
}
```

---

## Aliases and IDs

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/aliases-and-ids

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

## Aliases and IDs

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/aliases-and-ids/

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

## appbundles/:id/aliases/:aliasId

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/appbundles-id-aliases-aliasId-PATCH

**Contents:**
    - Jump To
- appbundles/:id/aliases/:aliasId
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Request
- Body Structure
  - Response

Modify alias details.

Successfully modify an AppBundle’s alias.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
application/json
```

Example 3 (json):
```json
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles/:id/aliases/:aliasId' \
  -X 'PATCH' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "version": 1
      }'
```

Example 4 (json):
```json
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles/:id/aliases/:aliasId' \
  -X 'PATCH' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "version": 1
      }'
```

---

## appbundles/:id/aliases/:aliasId

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/appbundles-id-aliases-aliasId-GET

**Contents:**
    - Jump To
- appbundles/:id/aliases/:aliasId
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
  - Response

Successfully get the details of an AppBundle’s alias.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles/:id/aliases/:aliasId' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles/:id/aliases/:aliasId' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (json):
```json
{
  "version": 1,
  "id": "prod"
}
```

---

## appbundles/:id/aliases

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/appbundles-id-aliases-GET

**Contents:**
    - Jump To
- appbundles/:id/aliases
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Request
- Query String Parameters
  - Response

Lists all aliases for the specified AppBundle.

Successfully list all aliases for an AppBundle.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles/:id/aliases' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles/:id/aliases' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (json):
```json
{
  "paginationToken": "",
  "data": [
    {
      "version": 1,
      "id": "prod"
    },
    {
      "version": 1,
      "id": "$LATEST"
    }
  ]
}
```

---

## appbundles/:id/aliases

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/appbundles-id-aliases-POST

**Contents:**
    - Jump To
- appbundles/:id/aliases
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Request
- Body Structure
  - Response

Creates a new alias for this AppBundle.

Limit: 1. Number of aliases (LimitAliases).

Successfully create a new alias for an AppBundle.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
application/json
```

Example 3 (json):
```json
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles/:id/aliases' \
  -X 'POST' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "version": 1,
        "id": "prod"
      }'
```

Example 4 (json):
```json
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles/:id/aliases' \
  -X 'POST' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "version": 1,
        "id": "prod"
      }'
```

---

## appbundles/:id/versions

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/appbundles-id-versions-GET

**Contents:**
    - Jump To
- appbundles/:id/versions
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Request
- Query String Parameters
  - Response

Lists all versions of the specified AppBundle.

Successfully list all versions of an AppBundle.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles/:id/versions' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles/:id/versions' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (json):
```json
{
  "paginationToken": "",
  "data": [
    1
  ]
}
```

---

## appbundles/:id

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/appbundles-id-GET

**Contents:**
    - Jump To
- appbundles/:id
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
  - Response

Gets the details of the specified AppBundle. Note that the {id} parameter must be a QualifiedId (owner.name+label).

It supports Box, Google Drive and Amazon Simple Storage Service (S3) services.

Examples of using argument “multiparts”:

Amazon Simple Storage Service (S3):

Successfully get the details of an AppBundle.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles/:id' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles/:id' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (json):
```json
{
  "package": "https://dasprod-store.s3.us-east-1.amazonaws.com/apps/hcX",
  "id": "owner.ChangeParams+test"
  "engine": "Autodesk.Inventor+23",
  "version": 10
}
```

---

## appbundles

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/appbundles-GET

**Contents:**
    - Jump To
- appbundles
- Resource Information
  - Request
- Headers
  - Request
- Query String Parameters
  - Response
- HTTP Status Code Summary
  - Response

Lists all available AppBundles, including AppBundles shared with this app.

Successfully get all AppBundles.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (json):
```json
{
  "paginationToken": "",
  "data": [
    "AutoCAD.Publish2View22+prod",
    "Revit.RVTIOSandboxTestPackage2018+prod",
    "Inventor.iLogicSampleAppPackage+prod",
    "Inventor.Configuration+Beta",
    "AutoCAD.Publish2View23+prod",
    "Inventor.ChangeParams+prod",
    "3dsMax.bakeToTexture+prod",
    "Revit.RVTIOSketchItPackage2018+prod"
  ]
}
```

---

## appbundles

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/appbundles-POST

**Contents:**
    - Jump To
- appbundles
- Resource Information
  - Request
- Headers
  - Request
- Body Structure
  - Response
- HTTP Status Code Summary
  - Response

Creates a new AppBundle.

It is highly recommended to create nickname before creating AppBundle. The nickname is used as a clearer alternative name when identifying AppBundles and Activities, as compared to using the Client ID.

The ‘file’ field must be at the end, all fields after ‘file’ will be ignored.

It supports Box, Google Drive and Amazon Simple Storage Service (S3) services.

Examples of using argument “multiparts”:

Amazon Simple Storage Service (S3):

It supports Box, Google Drive and Amazon Simple Storage Service (S3) services.

Examples of using argument “multiparts”:

Amazon Simple Storage Service (S3):

Successfully create a new AppBundle.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
application/json
```

Example 3 (sass):
```sass
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles' \
  -X 'POST' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "id": "ChangeParams",
        "engine": "Autodesk.Inventor+23",
        "description": "Changes parameters in ipt or asm file"
      }'
```

Example 4 (sass):
```sass
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/appbundles' \
  -X 'POST' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "id": "ChangeParams",
        "engine": "Autodesk.Inventor+23",
        "description": "Changes parameters in ipt or asm file"
      }'
```

---

## AutoCAD Automation Service Release Notes

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/change_history/acad_release_notes

**Contents:**
    - Jump To
- AutoCAD Automation Service Release Notes
- Release Date: 2025-03-30
- Release Date: 2024-03-30
- Release Date: 2023-07-28
- Release Date: 2023-03-06
- Release Date: 2021-06-17

Support for AutoCAD 2026 core engine (25.1, engine alias: Autodesk.AutoCAD+25_1)

Support for AutoCAD 2025 core engine (25.0, engine alias: Autodesk.AutoCAD+25_0)

Support for AutoCAD 2024 core engine (24.3, engine alias: Autodesk.AutoCAD+24_3)

Support for AutoCAD 2023 core engine (24.2, engine alias: Autodesk.AutoCAD+24_2)

Support for AutoCAD 2022 core engine (24.1, engine alias: Autodesk.AutoCAD+24_1)

---

## Callbacks

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/fusion_specific/callbacks/

**Contents:**
    - Jump To
- Callbacks
- OnProgress
- OnDemand

The Fusion engine uses a different approach to callbacks than other engines. Instead of the standard callback mechanism, Fusion provides specialized methods in the “adsk” namespace that work with TypeScript to handle callback functionality. This approach is designed to integrate seamlessly with Fusion’s TypeScript-based API.

For information about callbacks for other engines, see the standard callback mechanism documentation.

To send a message to the URL defined in the OnProgress property in the WorkItem you can use the following code:

The following JSON will be sent to the URL defined in the WorkItem:

The result of the function is an integer that represents the status of the request. If the request was successful the result will be 200.

To download a file that is defined as OnDemand in the Activity you can use the following code:

The result of the function is an integer that represents the status of the request. If the request was successful the result will be 200. If the integer is -1 the request failed without being able to send a message to the URL defined in the WorkItem. In any case the message will contain more information about the error.

**Examples:**

Example 1 (unknown):
```unknown
result = adsk.OnProgress("Progress message");
```

Example 2 (unknown):
```unknown
result = adsk.OnProgress("Progress message");
```

Example 3 (json):
```json
{
        "id": "taskID",
        "progress": "Progress message"
}
```

Example 4 (json):
```json
{
        "id": "taskID",
        "progress": "Progress message"
}
```

---

## Callbacks

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/callbacks/

**Contents:**
    - Jump To
- Callbacks
- onDemand callback
- onProgress callback
- onComplete callback
- Example
  - Engine support for callbacks

Note: Fusion handles callbacks differently to the other engines. Please see the Fusion Specific Info page on Callbacks for more information.

The Automation API allows you to define an Activity and a WorkItem in a way that makes it possible to gain better control over the execution flow of the WorkItem processing. This is done using a callback mechanism for three different types of events.

The callback events are:

The onDemand callback allows you to provide additional input data to a WorkItem during the WorkItem execution, when needed.

Using the onDemand callback requires it to be specified in both the Activity and the WorkItem. Also, your AppBundle has to support it: to invoke the onDemand callback, it has to write a specially formatted string to the output and it also has to handle the response in a specific way. A detailed walkthrough named Use onDemand Inputs is provided in the Advanced section of the How-to Guide.

Note: The AutoCAD engine additionally supports onDemand callbacks for a WorkItem’s output as well.

The onProgress callback allows you to check for the status of a WorkItem execution on a periodic basis. When defined, the Automation service calls the onProgress callback approximately every 30 seconds. The callback body includes the ID of the WorkItem that triggered it.

Note that the Automation service starts calling the onProgress callback only after the WorkItem is taken from the SQS queue and the actual processing of it is started.

It is also possible to invoke the onProgress callback directly from an AppBundle by writing a specially formatted string to trace output. The format is like this:

I.e. invoking the onProgress call from your add-in may look like

You can use the callback not only to monitor the status of the execution, but also to cancel the job if needed. To cancel a running job, send an HTTP 205 Reset Content response to the received onProgress callback. You should not use DELETE workitems/:id to cancel a WorkItem that uses the onProgress callback once this WorkItem is picked from the SQS queue for execution.

The onComplete callback lets you know when the WorkItem execution has ended without the need to actively check for the WorkItem status periodically. The callback body includes the ID of the WorkItem that triggered it, along with the WorkItem status and the URL for the WorkItem report. Time and other data are also included in the stats section, same as in the response to GET workitems/:id call.

In order to use both the onProgress and onComplete callbacks, it is only required to include them in the WorkItem’s “arguments” section as shown here:

The activityId has to be a fully qualified ID, see Aliases and IDs section. The URLs in the onProgress and onComplete sections should point to your web server endpoints dedicated to handling these callbacks.

Sample request body for the default (timer-run) onProgress callback:

Sample request body for the custom (as shown in the above onProgress custom call example) onProgress callback:

Sample request body for the onComplete callback:

See Fusion Specific Info

Note: Use onProgress/onDemand (input only) synchronously in the add-in code. For example, calling Console.ReadLine() immediately after Console.WriteLine(“!ACESAPI:acesHttpOperation(onProgress,,,<your-callback-body-content>,)”). If this contract is violated, you may get inconsistent results for callbacks.

**Examples:**

Example 1 (unknown):
```unknown
!ACESAPI:acesHttpOperation("onProgress","","","{<your-call-body-content>}","")
```

Example 2 (unknown):
```unknown
!ACESAPI:acesHttpOperation("onProgress","","","{<your-call-body-content>}","")
```

Example 3 (json):
```json
LogTrace("!ACESAPI:acesHttpOperation({0},\"\",\"\",{1},\"\")",
         "onProgress",
         "{ \"current-progress\": 30, \"step\": \"apply parameters\" }");
```

Example 4 (json):
```json
LogTrace("!ACESAPI:acesHttpOperation({0},\"\",\"\",{1},\"\")",
         "onProgress",
         "{ \"current-progress\": 30, \"step\": \"apply parameters\" }");
```

---

## Code Samples

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/code_samples/code_samples

**Contents:**
    - Jump To
- Code Samples
- Automation API Tools
- Change Height and Width
- Create custom Activity and AppBundle
- CountDelete
- SketchIt
- Create Window Family and Save to BIM 360 Project
- Upgrade Revit Files to a Newer Release
- Check Issues

Applies to: AutoCAD, Revit, Inventor, 3ds Max’

https://github.com/autodesk-platform-services/aps-design-automation-tools

Displays and creates AppBundles, Activities, and WorkItems.

Node.js, Automation_API_v3

Applies to: AutoCAD, Revit, Inventor

https://github.com/Autodesk-Forge/design.automation-python-tutorial

Updates the width and height parameters of a Dynamic Block (AutoCAD), RVT Window Family instance (Revit), or an IPT part (Inventor).

Python, Automation_API_v3

https://github.com/Autodesk-Forge/design.automation-.net-custom.activity.sample

Extracts a list of layers and blocks from an AutoCAD model. Demonstrates the creation of Activities and AppBundles to run a custom command in the Automation Service ecosystem.

Visual_Studio_2017, C#, Automation_API_v3

https://github.com/autodesk-platform-services/aps-count-delete-walls

Counts and deletes Revit elements in a host and link model. This sample is based on an APS Tutorial and includes two Revit add-in projects; CountIt and DeleteElement.

Visual_Studio_2017, C#, Automation_API_v3

https://github.com/autodesk-platform-services/aps-sketchit-revit

Creates sketch lines for walls and floors on a SVG Canvas. Also generates a Revit model for download as well as display in the Viewer. In addition to using the Automation API, this app also leverages other Autodesk Platform Service APIs like the Data Management API (OSS), the Viewer SDK, and the Model Derivative API.

JavaScript, Automation_API_v3, Data_Management_API_v2

https://github.com/autodesk-platform-services/aps-create-revit-family

Creates a family of windows from a window style you select and saves them in a BIM 360 project. This app also leverages other Autodesk platform services like the Data Management API (OSS) and the BIM 360 API.

JavaScript_ES6, Node_JS, BIM_360, Automation_API_v3

https://github.com/autodesk-platform-services/aps-upgradefiles-revit

Picks Revit files from a BIM 360 Hub, upgrades them to Revit 2019 and saves them back to the BIM 360 Hub.

JavaScript_ES6, Node_JS, Data_Management_API_v2, Automation_API_v3

https://github.com/autodesk-platform-services/aps-checkmodels-createissues-revit

Performs a basic design check whenever a new rvt file or a version of a rvt file is uploaded to a BIM 360 folder and generates a list of elements that did not pass.

C#, Data_Management_API_v2, Automation_API_v3, Webhooks_v1

https://github.com/autodesk-platform-services/aps-revit-file-parameters-exchange

Exports Revit parameters to a local Excel file as well as imports Revit parameters from a local Excel file.

C#, Data_Management_API_v2, Automation_API_v3, Viewer_v7

**Examples:**

Example 1 (unknown):
```unknown
Automation_API_v3
```

Example 2 (unknown):
```unknown
Automation_API_v3
```

Example 3 (unknown):
```unknown
Visual_Studio_2017
```

Example 4 (unknown):
```unknown
Automation_API_v3
```

---

## Engine Lifecycle Policy

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/engine-lifecycle

**Contents:**
    - Jump To
- Engine Lifecycle Policy
- 3ds Max engine versions
- AutoCAD engine versions
- Fusion engine versions
- Inventor engine versions
- Revit Engine versions

Note: Fusion’s engine policy is different and outlined below.

The following table lists all currently available engine versions and their deprecation and removal dates.

The following table lists all currently available engine versions and their deprecation and removal dates.

Note: Engine versions marked with * should have already been removed under the present lifecycle policy. The removal dates were postponed to give partners time to adopt this new policy.

The following table lists all currently available engine versions and their deprecation and removal dates.

The following table lists all currently available engine versions and their deprecation and removal dates.

Note: Engine versions marked with * should have already been removed under the present lifecycle policy. The removal dates were postponed to give partners time to adopt this new policy.

---

## Engine Lifecycle Policy

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/engine-lifecycle/

**Contents:**
    - Jump To
- Engine Lifecycle Policy
- 3ds Max engine versions
- AutoCAD engine versions
- Fusion engine versions
- Inventor engine versions
- Revit Engine versions

Note: Fusion’s engine policy is different and outlined below.

The following table lists all currently available engine versions and their deprecation and removal dates.

The following table lists all currently available engine versions and their deprecation and removal dates.

Note: Engine versions marked with * should have already been removed under the present lifecycle policy. The removal dates were postponed to give partners time to adopt this new policy.

The following table lists all currently available engine versions and their deprecation and removal dates.

The following table lists all currently available engine versions and their deprecation and removal dates.

Note: Engine versions marked with * should have already been removed under the present lifecycle policy. The removal dates were postponed to give partners time to adopt this new policy.

---

## forgeapps/:id

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/forgeapps-id-DELETE

**Contents:**
    - Jump To
- forgeapps/:id
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
- Example

Delete all data associated with the given app.

All AppBundles and Activities are DELETED.

This may take up to 2 minutes. During this time the app will not be able to make successful requests.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/forgeapps/:id' \
  -X 'DELETE' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/forgeapps/:id' \
  -X 'DELETE' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (unknown):
```unknown
204 No Content
```

---

## forgeapps/:id

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/forgeapps-id-PATCH/

**Contents:**
    - Jump To
- forgeapps/:id
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Request
- Body Structure
  - Response

Creates/updates the nickname for the current app. The nickname is used as a clearer alternative name when identifying AppBundles and Activities, as compared to using the Client ID. Once you have defined a nickname, it MUST be used instead of the Client ID.

The new nickname cannot be in use by any other app.

The app cannot have any data when this endpoint is invoked. Use the ‘DELETE /forgeapps/me’ endpoint (cautiously!!!) to remove all data from this app. ‘DELETE /forgeapps/me’ is also the only way to remove the nickname.

Note the nickname is supplied in the body, not as a query-parameter.

Successfully update the user’s nickname.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
application/json
```

Example 3 (json):
```json
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/forgeapps/:id' \
  -X 'PATCH' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "nickname": "",
        "publicKey": {
          "Exponent": "",
          "Modulus": ""
        }
      }'
```

Example 4 (json):
```json
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/forgeapps/:id' \
  -X 'PATCH' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "nickname": "",
        "publicKey": {
          "Exponent": "",
          "Modulus": ""
        }
      }'
```

---

## forgeapps/:id

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/forgeapps-id-GET

**Contents:**
    - Jump To
- forgeapps/:id
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
- Example

Return the given app’s nickname.

If the app has no nickname, this route will return its id.

Successfully get the user’s nickname.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/forgeapps/:id' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/forgeapps/:id' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

---

## ILogic logging

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/inventor_specific

**Contents:**
    - Jump To
- ILogic logging

ILogic logging is supported in engines starting with 2019. This feature allows you to see iLogic Logger entries, iLogic engine events and failures. All iLogic specific logger events start with the “[iLogic]” prefix.

By default the log level is set to Warning. This will ensure that the log will not get too chatty. However, you can easily change the log level in your iLogic scripts. The scope of this setting is global. Once you set it to Trace for example, you will be able to see all the details of iLogic engine running your scripts - like what triggered the iLogic rule and what the rule’s name is.

In order to change the logging level you simply use this code inside of your iLogic script.

The available log levels are:

To log information/warning/error etc. you then simply call

**Examples:**

Example 1 (unknown):
```unknown
iLogicVb.Automation.LogControl.Level = LogLevel.Trace
```

Example 2 (unknown):
```unknown
iLogicVb.Automation.LogControl.Level = LogLevel.Trace
```

Example 3 (rust):
```rust
LogLevel.None
LogLevel.Trace
LogLevel.Info
LogLevel.Debug
LogLevel.Warn
LogLevel.Error
LogLevel.Fatl
```

Example 4 (rust):
```rust
LogLevel.None
LogLevel.Trace
LogLevel.Info
LogLevel.Debug
LogLevel.Warn
LogLevel.Error
LogLevel.Fatl
```

---

## ILogic logging

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/inventor_specific/ilogic-logging

**Contents:**
    - Jump To
- ILogic logging

ILogic logging is supported in engines starting with 2019. This feature allows you to see iLogic Logger entries, iLogic engine events and failures. All iLogic specific logger events start with the “[iLogic]” prefix.

By default the log level is set to Warning. This will ensure that the log will not get too chatty. However, you can easily change the log level in your iLogic scripts. The scope of this setting is global. Once you set it to Trace for example, you will be able to see all the details of iLogic engine running your scripts - like what triggered the iLogic rule and what the rule’s name is.

In order to change the logging level you simply use this code inside of your iLogic script.

The available log levels are:

To log information/warning/error etc. you then simply call

**Examples:**

Example 1 (unknown):
```unknown
iLogicVb.Automation.LogControl.Level = LogLevel.Trace
```

Example 2 (unknown):
```unknown
iLogicVb.Automation.LogControl.Level = LogLevel.Trace
```

Example 3 (rust):
```rust
LogLevel.None
LogLevel.Trace
LogLevel.Info
LogLevel.Debug
LogLevel.Warn
LogLevel.Error
LogLevel.Fatl
```

Example 4 (rust):
```rust
LogLevel.None
LogLevel.Trace
LogLevel.Info
LogLevel.Debug
LogLevel.Warn
LogLevel.Error
LogLevel.Fatl
```

---

## Inventor Command Line Reference

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/cmdLine/cmdLine-inventor

**Contents:**
    - Jump To
- Inventor Command Line Reference
- Standard parameters
- Calling external iLogic script
- Calling a custom plugin
  - Accessing command line arguments by position
  - Accessing command line arguments by name
  - Use extension methods to parse command line parameters
  - Exceptions
- Example

The commandLine parameter of an Activity lets you specify the executable (InventorCoreConsole.Exe - the Inventor Core Console) that must be run and the command line arguments that must be passed when a WorkItem executes the Activity. In addition to the supported standard parameters you can specify custom arguments, which can be accessed from within custom plugins.

The following table lists standard parameters. The first four can be used together with Inventor Core Console.

A custom script is called by specifying /s on the command line, e.g.

Another way of using Inventor Core Console is to call a custom plugin, e.g.

One can even parameterize the custom plugin by adding custom command line arguments, e.g.

InventorCoreConsole.exe /al “plugin_to_use” /i “input_file.ipt” command subcommand /customArg1 value1 /customSwitch /customArg2 value2a value2b /additionalValues value1,value2,value3

Command line arguments passed to the plugin are pre-processed and stored in a NameValueMap object.

All arguments other than predefined (i.e. options other than /i, /s, /p, /v, /al, /isolate, /h, /? and corresponding values) are available in the NameValueMap object.

Command line arguments are split by white space characters. One way of accessing these arguments is to access individual tokens by their position on the command line. The previous example is split into these ten tokens:

You can access the individual token, e.g. map.Item["_6"]. The returned value in this case is "customArg2".

An alternative and more robust way of accessing command line arguments is to access them by name. The command line is interpreted in the following way:

The previous example is interpreted in the following way:

You can install the utility NuGet Autodesk.Forge.DesignAutomation.Inventor.Utils <https://www-1.nuget.org/packages/Autodesk.Forge.DesignAutomation.Inventor.Utils/>. Through your NuGet manager.

You can use extension methods from NameValueMapExtension to further parse command line arguments. The documentation of the extension class is available here.

NameValueMapExtension is a class that is designed to extend the functionality of the NameValueMap. It does not change the functionality or the underlying data of the original map; rather, it makes working with the map’s data easier.

Since NameValueMapExtension is an extension class, there is no need to initialize it. After installing the Utility from NuGet, you can use the extension methods on NameValueMap immediately.

Consider the following command line arguments:

First, lets include the extension helper into our project:

You can now use "additionalValue1" as an index to get the intValue:

The same index can also be used as a string

You can even get a collection of values. Lets consider the following command line arguments:

You can then simply call one of the As[Type]Collection() extension methods to get the collection of the data on the given index. The following code

yields the following output:

Please note that the data must be convertible to the desired type. The value "3.15" can be converted to double and string but the value "value" can only be represented as a string.

The As[type] and As[type]Collection extension methods are avaible for 5 basic types

Lets use the following example to demonstrate both the bool and enum use cases:

Consider the following custom enum:

Now, we can access the properties using the following way:

Last but not least, there is a pair of generic extension methods that you can use to try to convert the value to a different type that implements the IConvertible interface - link to https://docs.microsoft.com/en-us/dotnet/api/system.iconvertible?view=netcore-3.1.

All extension methods except TryGetValueAs can raise two types of exceptions:

The method TryGetValueAs on the other hand is exception safe and returns a boolean success value. In the unsuccessful case the outValue is set to the default value of the given type.

The following example demonstrates the use of the new command line functionality.

Let us create a new Activity with the following command line:

The activity calls a custom plugin wrapped in an app bundle. The input for the plugin is a given inventor document supplemented by the list of five additional command line arguments. Two of these arguments are hardcoded in the command line definition - customSwitch and customArg. The remaining three arguments are parameterized and their values are defined by the work item (customCollection, intParam and doubleParam).

The RunWithArguments(Document doc, NameValueMap map) entry method of app bundle custom plugin is called by Inventor. Custom arguments are included in the map object. One can access them using NameValueMapExtension in the following way:

**Examples:**

Example 1 (unknown):
```unknown
commandLine
```

Example 2 (unknown):
```unknown
InventorCoreConsole.exe /s "custom_script.iLogicVb"
```

Example 3 (unknown):
```unknown
InventorCoreConsole.exe /s "custom_script.iLogicVb"
```

Example 4 (unknown):
```unknown
InventorCoreConsole.exe /al "plugin_to_use" /i "input_file.ipt"
```

---

## Task 2 – Create a Nickname for the app

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/autocad/task2-create-nickname

**Contents:**
    - Jump To
- Task 2 – Create a Nickname for the app
- Step 1 - Create a nickname
  - Request
  - Response

APS uses the Client ID that was generated in the previous task to uniquely identify the app you created. The Client ID can be long and cryptic, and hence a source of irritation when you reference data you add to your app.

A Nickname is a way to map an app’s Client ID to an easy-to-use name that you can use in place of the Client ID.

You can assign a nickname to an app only if there is no data associated with that app. That is why we are creating the nickname before we do anything else with the app.

By the end of this task, you will know how to create a nickname to reference an app.

You will use the following API endpoint in this task:

**Examples:**

Example 1 (json):
```json
curl -X PATCH \
  'https://developer.api.autodesk.com/da/us-east/v3/forgeapps/me' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d ' {"nickname": "<YOUR_NICKNAME>"}'
```

Example 2 (json):
```json
curl -X PATCH \
  'https://developer.api.autodesk.com/da/us-east/v3/forgeapps/me' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d ' {"nickname": "<YOUR_NICKNAME>"}'
```

Example 3 (typescript):
```typescript
<YOUR_ACCESS_TOKEN>
```

Example 4 (unknown):
```unknown
409 Conflict
```

---

## Task 2 – Create a Nickname for the app

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/fusion/task2-create-nickname

**Contents:**
    - Jump To
- Task 2 – Create a Nickname for the app
- Step 1 - Create a nickname
  - Request
  - Response

APS uses the Client ID that was generated in the previous task to uniquely identify the app you created. The Client ID can be long and cryptic, and hence a source of irritation when you reference data you add to your app.

A Nickname is a way to map an app’s Client ID to an easy-to-use name that you can use in place of the Client ID.

You can assign a nickname to an app only if there is no data associated with that app. That is why we are creating the nickname before we do anything else with the app.

By the end of this task, you will know how to create a nickname to reference an app.

You will use the following API endpoint in this task:

**Examples:**

Example 1 (json):
```json
curl -X PATCH \
  'https://developer.api.autodesk.com/da/us-east/v3/forgeapps/me' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d ' {"nickname": "<YOUR_NICKNAME>"}'
```

Example 2 (json):
```json
curl -X PATCH \
  'https://developer.api.autodesk.com/da/us-east/v3/forgeapps/me' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -H 'Content-Type: application/json' \
  -d ' {"nickname": "<YOUR_NICKNAME>"}'
```

Example 3 (typescript):
```typescript
<YOUR_ACCESS_TOKEN>
```

Example 4 (unknown):
```unknown
409 Conflict
```

---

## Task 3 – Upload an AppBundle to the Automation Service

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/autocad/task3-upload-appbundle

**Contents:**
    - Jump To
- Task 3 – Upload an AppBundle to the Automation Service
- Step 1 - Download the AutoCAD CRX plug-in
- Step 2 - Build an AppBundle
- Step 3 - Register the AppBundle
  - Request
  - Response
- Step 4 - Upload the AppBundle
- Step 5 - Create an alias for the AppBundle
- Additional notes

An AppBundle is a package that contains the files of an AutoCAD plug-in.

By the end of this task you will be able to:

You will use the following operations to handle AppBundles in this task:

You need to download a CRX plug-in called command.dll from the GitHub repository provided below. This plug-in contains a command called LISTLAYERS, which extracts layer names from an input drawing file and stores them in a text file.

An AppBundle is a zip file that includes the AutoCAD CRX plug-in, a manifest file called PackageContents.xml, and related files organized in a specific way. It follows a format similar to an Autodesk Exchange App’s Autoloader. AppBundle allows you to upload the plug-in and its dependencies for execution. The PackageContents.xml file provides runtime instructions to the Automation Service, helping it locate and load the plug-in.

Note: For more information on PackageContents.xml, see PackageContents.xml Format Reference

Note: If you are unable to build the AppBundle, download and use ListLayers.zip for subsequent steps from here

The structure of ListLayers.zip should look similar to the following code block.

Before you upload the AppBundle to the Automation Service, you must register the AppBundle.

Upload the AppBundle to the signed URL returned by endpointURL in the previous step.

When you registered the AppBundle in step 2, it was registered as version 1 of the AppBundle. In this step, you create an alias named my_working_version to reference that version. You can think of the alias as a tag that points to a version of an AppBundle.

If you make changes to the AppBundle, some time later, you must register it as a new version and then upload it. You can then update the alias to point to the newer version of the AppBundle. Consequently, endpoints referencing the AppBundle using the alias get access to the updated version of the AppBundle.

A CRX plug-in is a module that has been coded against the AcCoreMgd.dll instead of the AcMgd.dll, against which ARX plug-ins are coded. You can think of a CRX plug-in as an ARX plug-in that is designed to run against the core functionality of AutoCAD. To ensure that a CRX plug-in is restricted to core functionality, Visual Studio projects used to build CRX plug-ins are allowed to access only a subset of the libraries that ARX plug-ins can access. If you know how to build ARX plug-ins, you already have the knowledge required to build CRX plug-ins. Use the following links for more information:

**Examples:**

Example 1 (xml):
```xml
<?xml version="1.0" encoding="utf-8" ?>
<ApplicationPackage
  SchemaVersion="1.0"
  Version="1.0">
  <Components>
      <RuntimeRequirements
          OS="Win64"
          Platform="AutoCAD" />
      <ComponentEntry
          AppName="ListLayers"
          ModuleName="./Contents/command.dll"
          AppDescription="AutoCAD.IO .net test app"
          LoadOnCommandInvocation="True"
          LoadOnAutoCADStartup="False">
          <Commands GroupName="MyTestCommands">
              <Command Global="LISTLAYERS" Local="LISTLAYERS" />
          </Commands>
      </ComponentEntry>
  </Components>
</ApplicationPackage>
```

Example 2 (xml):
```xml
<?xml version="1.0" encoding="utf-8" ?>
<ApplicationPackage
  SchemaVersion="1.0"
  Version="1.0">
  <Components>
      <RuntimeRequirements
          OS="Win64"
          Platform="AutoCAD" />
      <ComponentEntry
          AppName="ListLayers"
          ModuleName="./Contents/command.dll"
          AppDescription="AutoCAD.IO .net test app"
          LoadOnCommandInvocation="True"
          LoadOnAutoCADStartup="False">
          <Commands GroupName="MyTestCommands">
              <Command Global="LISTLAYERS" Local="LISTLAYERS" />
          </Commands>
      </ComponentEntry>
  </Components>
</ApplicationPackage>
```

Example 3 (unknown):
```unknown
PackageContents.xml
```

Example 4 (unknown):
```unknown
ListLayers.zip
|-- ListLayers.bundle
|   |-- PackageContents.xml
|   |-- Contents
|   |   |-- command.dll
```

---

## Task 3 – Upload an AppBundle to the Automation Service

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/autocad/task3-upload-appbundle/

**Contents:**
    - Jump To
- Task 3 – Upload an AppBundle to the Automation Service
- Step 1 - Download the AutoCAD CRX plug-in
- Step 2 - Build an AppBundle
- Step 3 - Register the AppBundle
  - Request
  - Response
- Step 4 - Upload the AppBundle
- Step 5 - Create an alias for the AppBundle
- Additional notes

An AppBundle is a package that contains the files of an AutoCAD plug-in.

By the end of this task you will be able to:

You will use the following operations to handle AppBundles in this task:

You need to download a CRX plug-in called command.dll from the GitHub repository provided below. This plug-in contains a command called LISTLAYERS, which extracts layer names from an input drawing file and stores them in a text file.

An AppBundle is a zip file that includes the AutoCAD CRX plug-in, a manifest file called PackageContents.xml, and related files organized in a specific way. It follows a format similar to an Autodesk Exchange App’s Autoloader. AppBundle allows you to upload the plug-in and its dependencies for execution. The PackageContents.xml file provides runtime instructions to the Automation Service, helping it locate and load the plug-in.

Note: For more information on PackageContents.xml, see PackageContents.xml Format Reference

Note: If you are unable to build the AppBundle, download and use ListLayers.zip for subsequent steps from here

The structure of ListLayers.zip should look similar to the following code block.

Before you upload the AppBundle to the Automation Service, you must register the AppBundle.

Upload the AppBundle to the signed URL returned by endpointURL in the previous step.

When you registered the AppBundle in step 2, it was registered as version 1 of the AppBundle. In this step, you create an alias named my_working_version to reference that version. You can think of the alias as a tag that points to a version of an AppBundle.

If you make changes to the AppBundle, some time later, you must register it as a new version and then upload it. You can then update the alias to point to the newer version of the AppBundle. Consequently, endpoints referencing the AppBundle using the alias get access to the updated version of the AppBundle.

A CRX plug-in is a module that has been coded against the AcCoreMgd.dll instead of the AcMgd.dll, against which ARX plug-ins are coded. You can think of a CRX plug-in as an ARX plug-in that is designed to run against the core functionality of AutoCAD. To ensure that a CRX plug-in is restricted to core functionality, Visual Studio projects used to build CRX plug-ins are allowed to access only a subset of the libraries that ARX plug-ins can access. If you know how to build ARX plug-ins, you already have the knowledge required to build CRX plug-ins. Use the following links for more information:

**Examples:**

Example 1 (xml):
```xml
<?xml version="1.0" encoding="utf-8" ?>
<ApplicationPackage
  SchemaVersion="1.0"
  Version="1.0">
  <Components>
      <RuntimeRequirements
          OS="Win64"
          Platform="AutoCAD" />
      <ComponentEntry
          AppName="ListLayers"
          ModuleName="./Contents/command.dll"
          AppDescription="AutoCAD.IO .net test app"
          LoadOnCommandInvocation="True"
          LoadOnAutoCADStartup="False">
          <Commands GroupName="MyTestCommands">
              <Command Global="LISTLAYERS" Local="LISTLAYERS" />
          </Commands>
      </ComponentEntry>
  </Components>
</ApplicationPackage>
```

Example 2 (xml):
```xml
<?xml version="1.0" encoding="utf-8" ?>
<ApplicationPackage
  SchemaVersion="1.0"
  Version="1.0">
  <Components>
      <RuntimeRequirements
          OS="Win64"
          Platform="AutoCAD" />
      <ComponentEntry
          AppName="ListLayers"
          ModuleName="./Contents/command.dll"
          AppDescription="AutoCAD.IO .net test app"
          LoadOnCommandInvocation="True"
          LoadOnAutoCADStartup="False">
          <Commands GroupName="MyTestCommands">
              <Command Global="LISTLAYERS" Local="LISTLAYERS" />
          </Commands>
      </ComponentEntry>
  </Components>
</ApplicationPackage>
```

Example 3 (unknown):
```unknown
PackageContents.xml
```

Example 4 (unknown):
```unknown
ListLayers.zip
|-- ListLayers.bundle
|   |-- PackageContents.xml
|   |-- Contents
|   |   |-- command.dll
```

---

## Task 4 – Publish an Activity

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/fusion/task4-publish-activity

**Contents:**
    - Jump To
- Task 4 – Publish an Activity
- Step 1 - Create a new Activity
  - Request
  - Response
- Step 2 - Create an alias to the Activity
  - Request
  - Response
- Step 3 - Update an existing Activity
  - Request

An Activity is an action that can be executed in the Automation Service. You create and post Activities to run specific AppBundles.

By the end of this task, you will know:

You will use the following operations to handle Activities for this task:

To create a new Activity named ConfigureDesignActivity, post this request:

The response includes:

The Automation API does not let you reference an Activity by its id. You must always reference an Activity by an alias. Note that an alias points to a specific version of an Activity and not the Activity itself.

To create an alias named current_version, which refers to version 1 of the ConfigureDesignActivity:

NOTE: This step is optional

The Automation API does not let you overwrite an Activity once you have created it. If you want to modify/update an existing Activity, you must update it as a new version. If you try to overwrite an existing Activity, the Automation Service returns a `409 Conflict error.

To create a new version of an Activity:

Note: You can omit id from the request body. If you include id in the request body, set it to null. If you don’t set it to null, the Automation Service throws an error.

NOTE: Perform this step only if you carried out Step 3

Currently, the alias current_version points to version 1 of the Activity.

You can reassign the alias current_version to point to version 2 of the Activity.

To update the alias, you can either:

To send a PATCH request:

**Examples:**

Example 1 (sass):
```sass
curl -X POST \
  'https://developer.api.autodesk.com/da/us-east/v3/activities' \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -d '{
        "id": "ConfigureDesignActivity",
        "engine": "Autodesk.Fusion+Latest",
        "commandline": [],
        "parameters": {
            "TaskParameters": {
                "verb": "read",
                "description": "the parameters for the script",
                "required": false
            },
            "PersonalAccessToken": {
                "verb": "read",
                "description": "the personal access token to use",
                "required": true
            }
        },
        "appbundles": [
            "YOUR_NICKNAME.ConfigureDesignAppBundle+my_working_version"
        ],
        "settings": {},
        "description": ""
    }'
```

Example 2 (sass):
```sass
curl -X POST \
  'https://developer.api.autodesk.com/da/us-east/v3/activities' \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -d '{
        "id": "ConfigureDesignActivity",
        "engine": "Autodesk.Fusion+Latest",
        "commandline": [],
        "parameters": {
            "TaskParameters": {
                "verb": "read",
                "description": "the parameters for the script",
                "required": false
            },
            "PersonalAccessToken": {
                "verb": "read",
                "description": "the personal access token to use",
                "required": true
            }
        },
        "appbundles": [
            "YOUR_NICKNAME.ConfigureDesignAppBundle+my_working_version"
        ],
        "settings": {},
        "description": ""
    }'
```

Example 3 (json):
```json
{
  "id": "<YOUR_NICKNAME>.ConfigureDesignActivity",
  "engine": "Autodesk.Fusion+Latest",
  "appbundles": [
      "<YOUR_NICKNAME>.ConfigureDesignAppBundle+my_working_version"
  ],
  "settings": {},
  "description": "",
  "version": 1
}
```

Example 4 (json):
```json
{
  "id": "<YOUR_NICKNAME>.ConfigureDesignActivity",
  "engine": "Autodesk.Fusion+Latest",
  "appbundles": [
      "<YOUR_NICKNAME>.ConfigureDesignAppBundle+my_working_version"
  ],
  "settings": {},
  "description": "",
  "version": 1
}
```

---

## Task 4 – Publish an Activity

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/autocad/task4-publish-activity

**Contents:**
    - Jump To
- Task 4 – Publish an Activity
- Step 1 - Create a new Activity
  - Request
  - Response
- Step 2 - Create an alias to the Activity
  - Request
  - Response
- Step 3 - Update an existing Activity
  - Request

An Activity is an action that can be executed in the Automation Service. You create and post Activities to run specific AppBundles.

By the end of this task, you will know:

You will use the following operations to handle Activities for this task:

To create a new Activity named ListLayersActivity, post this request:

The response includes:

The Automation API does not let you reference an Activity by its id. You must always reference an Activity by an alias. Note that an alias points to a specific version of an Activity and not the Activity itself.

To create an alias named current_version, which refers to version 1 of the ListLayersActivity:

NOTE: This step is optional

The Automation API does not let you overwrite an Activity once you have created it. If you want to modify/update an existing Activity, you must update it as a new version. If you try to overwrite an existing Activity, the Automation Service returns a `409 Conflict error.

To create a new version of an Activity:

Note: You can omit id from the request body. If you include id in the request body, set it to null. If you don’t set it to null, the Automation Service throws an error.

NOTE: Perform this step only if you carried out Step 3

Currently, the alias current_version points to version 1 of the Activity.

You can reassign the alias current_version to point to version 2 of the Activity.

To update the alias, you can either:

To send a PATCH request:

**Examples:**

Example 1 (sass):
```sass
curl -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/activities \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -d '{
        "id": "ListLayersActivity",
        "commandLine": [
            "$(engine.path)\\accoreconsole.exe /i \"$(args[InputDwg].path)\" /al \"$(appbundles[ListLayers].path)\" /s \"$(settings[script].path)\""
        ],
        "parameters": {
            "InputDwg": {
            "zip": false,
            "ondemand": false,
            "verb": "get",
            "description": "Input drawing file",
            "localName": "Input.dwg"
            },
            "result": {
            "zip": false,
            "ondemand": false,
            "verb": "put",
            "description": "Results",
            "required": true,
            "localName": "layers.txt"
            }
        },
        "engine": "Autodesk.AutoCAD+24_3",
        "appbundles": [
            "<YOUR_APP_NICKNAME>.ListLayers+my_working_version"
        ],
        "settings": {
            "script": "(command \"LISTLAYERS\")\n"
        },
        "description": "Extracts layer names from an input drawing file and saves them to a text file"
    }''
```

Example 2 (sass):
```sass
curl -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/activities \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -d '{
        "id": "ListLayersActivity",
        "commandLine": [
            "$(engine.path)\\accoreconsole.exe /i \"$(args[InputDwg].path)\" /al \"$(appbundles[ListLayers].path)\" /s \"$(settings[script].path)\""
        ],
        "parameters": {
            "InputDwg": {
            "zip": false,
            "ondemand": false,
            "verb": "get",
            "description": "Input drawing file",
            "localName": "Input.dwg"
            },
            "result": {
            "zip": false,
            "ondemand": false,
            "verb": "put",
            "description": "Results",
            "required": true,
            "localName": "layers.txt"
            }
        },
        "engine": "Autodesk.AutoCAD+24_3",
        "appbundles": [
            "<YOUR_APP_NICKNAME>.ListLayers+my_working_version"
        ],
        "settings": {
            "script": "(command \"LISTLAYERS\")\n"
        },
        "description": "Extracts layer names from an input drawing file and saves them to a text file"
    }''
```

Example 3 (unknown):
```unknown
commandLine
```

Example 4 (unknown):
```unknown
$(engine.path)\\accoreconsole.exe
```

---

## Task 5 – Submit a WorkItem

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/fusion/task5-post-workitem

**Contents:**
    - Jump To
- Task 5 – Submit a WorkItem
- Step 1 - Generate a Personal Access Token
- Step 2 - Create a WorkItem
  - Request
- Step 3 - Check status of the WorkItem
  - Request
  - Response

When you post a WorkItem to the Automation Service, you are instructing the service to execute an Activity.

The relationship between an Activity and a WorkItem can be thought of as the relationship between a “function definition” and “function call”. Named parameters of the Activity have corresponding named arguments of the WorkItem. Like in function calls, optional parameters of the Activity can be skipped and left unspecified while posting a WorkItem.

By the end of this task, you will be able to:

You will use the following operations to work with WorkItems in this task:

To get a personal access token (PAT), simply access your autodesk profile via the following link: https://profile.autodesk.com/security and follow the instructions. Generate a PAT for product scope “Fusion Automation API” or “Project Alpine”. Either product scope will work.

The table below describes the different options for authentication and authorization for submitting Fusion WorkItems to the Automation Service.

Required Body Content

To create a WorkItem to execute the Activity ConfigureDesignActivity:

The response contains the id of the posted WorkItem:

WorkItems are queued before they are processed. A WorkItem’s processing time will vary depending on the size and complexity of the input files, the type of processing done by the AppBundle, and the size of the output files.

In this walkthrough, you will be checking the WorkItem status to see if it has completed. However, the best practice is to use the onComplete argument when submitting a WorkItem. The onComplete argument lets you specify a callback URL, which will be called once the WorkItem is completed. For more information see the documentation on callbacks here.

You can check the status of a WorkItem by calling [GET] /workitems/{id}:

**Examples:**

Example 1 (sass):
```sass
curl -X POST \
  'https://developer.api.autodesk.com/da/us-east/v3/workitems' \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -d '{
          "activityId": "<YOUR_NICKNAME>.ConfigureDesignActivity+my_current_version", \
     "arguments": {
        "PersonalAccessToken": "<YOUR_PERSONAL_ACCESSTOKEN>",
        "TaskParameters": "{\n  \"fileURN\": \"urn:adsk.wipprod:dm.lineage:shuH8zKvThW_4Tdu-m22sw\",\n  \"parameters\": {\n    \"d3\": \"40mm\"\n  }\n}"
      }
  }'
```

Example 2 (sass):
```sass
curl -X POST \
  'https://developer.api.autodesk.com/da/us-east/v3/workitems' \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -d '{
          "activityId": "<YOUR_NICKNAME>.ConfigureDesignActivity+my_current_version", \
     "arguments": {
        "PersonalAccessToken": "<YOUR_PERSONAL_ACCESSTOKEN>",
        "TaskParameters": "{\n  \"fileURN\": \"urn:adsk.wipprod:dm.lineage:shuH8zKvThW_4Tdu-m22sw\",\n  \"parameters\": {\n    \"d3\": \"40mm\"\n  }\n}"
      }
  }'
```

Example 3 (json):
```json
{
    "status": "pending",
    "stats": {
        "timeQueued": "2023-09-27T08:52:30.7161306Z"
    },
    "id": "<YOUR_WORKITEM_ID>"
}
```

Example 4 (json):
```json
{
    "status": "pending",
    "stats": {
        "timeQueued": "2023-09-27T08:52:30.7161306Z"
    },
    "id": "<YOUR_WORKITEM_ID>"
}
```

---

## Task 6 - Open Result in Fusion

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/fusion/task6-open-result-in-fusion

**Contents:**
    - Jump To
- Task 6 - Open Result in Fusion
- Open Result in Fusion

Once the WorkItem has completed executing the Activity, the Automation Service uploads the resulting file to Fusion Teams. You can use the Fusion desktop client on you local machine to check the result of the WorkItem.

**Examples:**

Example 1 (unknown):
```unknown
Fusion Automation Service
```

Example 2 (unknown):
```unknown
Nut v1 modify parameters
```

---

## Task 6 – Submit a WorkItem

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/autocad/task6-post-workitem

**Contents:**
    - Jump To
- Task 6 – Submit a WorkItem
- Step 1 - Send a WorkItem
  - Request
  - Response
- Step 2 - Check status of a WorkItem
  - Request
  - Response

When you post a WorkItem to the Automation Service, you are instructing the service to execute an Activity.

The relationship between an Activity and a WorkItem can be thought of as the relationship between a “function definition” and “function call”. Named parameters of the Activity have corresponding named arguments of the WorkItem. Like in function calls, optional parameters of the Activity can be skipped and left unspecified while posting a WorkItem.

By the end of this task, you will be able to:

You will use the following operations to work with WorkItems in this task:

To create a WorkItem to execute the Activity ListLayersActivity:

The response contains the id of the posted WorkItem:

WorkItems are queued before they are processed. A WorkItem’s processing time will vary depending on the size and complexity of the input files, the type of processing done by the AppBundle, and the size of the output files.

In this walkthrough, you will be checking the WorkItem status to see if it has completed. However, the best practice is to use the onComplete argument when submitting a WorkItem. The onComplete argument enables you to specify a callback URL, which will be called once the WorkItem is completed. For more information see the documentation on callbacks here.

You can check the status of a WorkItem by calling `GET /v3/workitems/{id}`_ :

**Examples:**

Example 1 (sass):
```sass
curl -X POST \
  'https://developer.api.autodesk.com/da/us-east/v3/workitems' \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -d '{
          "activityId": "<YOUR_APP_NICKNAME>.ListLayersActivity+my_current_version",
          "arguments": {
                  "InputDwg": {
                          "url": "urn:adsk.objects:os.object:<YOUR_BUCKET_KEY>/<OBJECT_KEY_4_INPUT_FILE>",
                          "verb": "get",
              "headers": {
                  "Authorization": "Bearer <YOUR_ACCESS_TOKEN>"
              }
                  },
                  "result": {
                          "url": "urn:adsk.objects:os.object:<YOUR_BUCKET_KEY>/<OBJECT_KEY_4_OUTPUT_FILE>",
                          "verb": "put",
              "headers": {
                  "Authorization": "Bearer <YOUR_ACCESS_TOKEN>"
              }
                  }
          }
    }'
```

Example 2 (sass):
```sass
curl -X POST \
  'https://developer.api.autodesk.com/da/us-east/v3/workitems' \
  -H 'Content-Type: application/json' \
  -H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
  -d '{
          "activityId": "<YOUR_APP_NICKNAME>.ListLayersActivity+my_current_version",
          "arguments": {
                  "InputDwg": {
                          "url": "urn:adsk.objects:os.object:<YOUR_BUCKET_KEY>/<OBJECT_KEY_4_INPUT_FILE>",
                          "verb": "get",
              "headers": {
                  "Authorization": "Bearer <YOUR_ACCESS_TOKEN>"
              }
                  },
                  "result": {
                          "url": "urn:adsk.objects:os.object:<YOUR_BUCKET_KEY>/<OBJECT_KEY_4_OUTPUT_FILE>",
                          "verb": "put",
              "headers": {
                  "Authorization": "Bearer <YOUR_ACCESS_TOKEN>"
              }
                  }
          }
    }'
```

Example 3 (unknown):
```unknown
ListLayersActivity
```

Example 4 (json):
```json
{
    "status": "pending",
    "stats": {
        "timeQueued": "2019-10-17T11:21:50.5619735Z"
    },
    "id": "<YOUR_WORKITEM_ID>"
}
```

---

## Troubleshooting

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/troubleshooting

**Contents:**
    - Jump To
- Troubleshooting
- Common Issues
  - Requesting support for failed WorkItems
  - “Cannot parse ID” error on alias creation for AppBundle/Activity
  - “Failed to prepare app package(s)” error when executing a WorkItem
  - Non-English filenames in ZIP files
  - 504 gateway timeout issue
  - 413 payload too large error
- Revit-specific issues

Please provide the following information when requesting support for failed WorkItems:

If the issue cannot be identified from the above information, further diagnosis will require the following:

There are the following limitations on alias names:

Note that there is a limit on the number of aliases. For more details, check the Rate Limits and Quotas page. For more details on unqualified/fully qualified IDs, check the Aliases and IDs page.

If you encounter this error, it might be caused by an issue that occurred when uploading the AppBundle zip file.

By default, most ZIP archivers do not use UTF-8 encoding to store filenames, and ZIP archives created from them do not store a code page for filenames. As a result, the Automation Service needs a hint to extract filenames from the archive correctly. Use one of the following workarounds if filenames in your ZIP archive are not in the ASCII code page:

If you encounter a “504 gateway timeout” error, it is often sufficient to retry the request to resolve it.

If you encounter a “413 Payload too large” error when posting a WorkItem, it may be due to one of the following reasons:

For the permitted size of JSON payload, check the Rate Limits and Quotas page.

If you encounter this error, your file is most likely not opening with the correct options.

To open the file properly, you must specify the correct behavior by opening the file within your add-in.

Implement the following:

To access and modify both Revit workshared cloud models and non-workshared cloud models, please refer to the Revit Cloud Models Integration page.

If you encounter this error, it might be due to problems opening IPT/IAM files, iLogic errors, etc.

This is a known issue in Inventor engines. It is recommended that you use the function DrawingDocument.SaveAsInventorDWG() instead:

This is a known issue in Inventor engines when using functions ExportBuildingComponent and ExportBuildingComponentWithOptions. The error “Unspecified error (Exception from HRESULT: 0x80004005 (E_FAIL))” appears when trying to export building components using Inventor engines.

It is recommended that you use Revit together with Inventor to convert the RFA and IFC files. Please check the inventor2revit sample for reference.

On the Automation Service, some functions that work with Excel formats are not supported.

It is recommended that you start with the sample plugin to build your own plugin bundle and upload the bundle to the Automation Service.

If you need to save your document, we recommend that you do so in your plug-in instead of your iLogic rule. Do not use the ThisDoc.Save() command in iLogic rules.

**Examples:**

Example 1 (json):
```json
"countItParams": {
  "url": "data:application/json,{'walls': true, 'floors': true, 'doors': true, 'windows': true}"
}
```

Example 2 (json):
```json
"countItParams": {
  "url": "data:application/json,{'walls': true, 'floors': true, 'doors': true, 'windows': true}"
}
```

Example 3 (unknown):
```unknown
Application rvtApp = data.RevitApp;
OpenOptions openOptions = new OpenOptions();
FilePath modelFilePath = new FilePath("relative/path/to/file");
openOptions.DetachFromCentralOption = DetachFromCentralOption.DetachAndPreserveWorksets;
Document doc = rvtApp.OpenDocumentFile(modelFilePath, openOptions);
```

Example 4 (unknown):
```unknown
Application rvtApp = data.RevitApp;
OpenOptions openOptions = new OpenOptions();
FilePath modelFilePath = new FilePath("relative/path/to/file");
openOptions.DetachFromCentralOption = DetachFromCentralOption.DetachAndPreserveWorksets;
Document doc = rvtApp.OpenDocumentFile(modelFilePath, openOptions);
```

---

## Use OnDemand Inputs

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/using-on-demand-inputs/

**Contents:**
    - Jump To
- Use OnDemand Inputs
- Example
- Example
- Example
- function parameters
- Known issues:

Once you have a running custom AppBundle with an Activity and a WorkItem, you can consider more advanced processing.

This walkthrough will explain how you can optimize data downloads using so called onDemand inputs in Activities and WorkItems. This mechanism allows your AppBundle to ask for additional data to be downloaded using an http call during WorkItem processing only on an as-needed basis.

Conceptually, onDemand inputs allow your AppBundle to access additional resources based on the actual run of a given WorkItem, using a url that can be parameterized to query exactly the data you need right now. It can either access additional specific design files on your storage, or call your own server’s http API to query for json data etc.

There are several steps you need to take in order to be able to use onDemand inputs. First, when you are creating your activity, you must specify some of the input arguments as being onDemand. Note that onDemand can only be used when the parameter verb is get or head.

Second, you must refer to this parameter when sending the WorkItem, as shown here:

Third, your AppBundle add-in has to be able to ask for the optional onDemand input. This is done via writing specially formatted text to the log trace. The required format is best documented in the following method that handles a request for such an optional input and waits for the http call result:

An actual call to the function can be made like

The tricky pieces here are:

The method to support onDemand calls from an add-in is part of the Inventor Visual Studio template .

**Examples:**

Example 1 (lua):
```lua
curl -i -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/activities
  ...
  -d '{
  "id": "MyActivity",
  ...
    "parameters": {
      "InventorDoc": {
        "verb": "get"
      },
      "OptionalIpt": {
        "verb": "get",
        "onDemand": true
      },
      ...
    }
  }
```

Example 2 (lua):
```lua
curl -i -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/activities
  ...
  -d '{
  "id": "MyActivity",
  ...
    "parameters": {
      "InventorDoc": {
        "verb": "get"
      },
      "OptionalIpt": {
        "verb": "get",
        "onDemand": true
      },
      ...
    }
  }
```

Example 3 (sass):
```sass
curl -i -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/workitems \
  ...
  -d '{
  "activityId": "MyActivity+prod",
  ...
  "arguments": {
    "InventorDoc": {
      "url": "https://s3-us-east-1.amazonaws.com/inventorio-prod/documentation/APIBasics/Box.ipt"
    },
    "OptionalIpt": {
      "url": "https://s3-us-east-1.amazonaws.com/inventorio-prod/documentation/APIBasics"
    }
  ...
  }
}
```

Example 4 (sass):
```sass
curl -i -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/workitems \
  ...
  -d '{
  "activityId": "MyActivity+prod",
  ...
  "arguments": {
    "InventorDoc": {
      "url": "https://s3-us-east-1.amazonaws.com/inventorio-prod/documentation/APIBasics/Box.ipt"
    },
    "OptionalIpt": {
      "url": "https://s3-us-east-1.amazonaws.com/inventorio-prod/documentation/APIBasics"
    }
  ...
  }
}
```

---

## Use OnDemand Inputs

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/common

**Contents:**
    - Jump To
- Use OnDemand Inputs
- Example
- Example
- Example
- function parameters
- Known issues:

Once you have a running custom AppBundle with an Activity and a WorkItem, you can consider more advanced processing.

This walkthrough will explain how you can optimize data downloads using so called onDemand inputs in Activities and WorkItems. This mechanism allows your AppBundle to ask for additional data to be downloaded using an http call during WorkItem processing only on an as-needed basis.

Conceptually, onDemand inputs allow your AppBundle to access additional resources based on the actual run of a given WorkItem, using a url that can be parameterized to query exactly the data you need right now. It can either access additional specific design files on your storage, or call your own server’s http API to query for json data etc.

There are several steps you need to take in order to be able to use onDemand inputs. First, when you are creating your activity, you must specify some of the input arguments as being onDemand. Note that onDemand can only be used when the parameter verb is get or head.

Second, you must refer to this parameter when sending the WorkItem, as shown here:

Third, your AppBundle add-in has to be able to ask for the optional onDemand input. This is done via writing specially formatted text to the log trace. The required format is best documented in the following method that handles a request for such an optional input and waits for the http call result:

An actual call to the function can be made like

The tricky pieces here are:

The method to support onDemand calls from an add-in is part of the Inventor Visual Studio template .

**Examples:**

Example 1 (lua):
```lua
curl -i -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/activities
  ...
  -d '{
  "id": "MyActivity",
  ...
    "parameters": {
      "InventorDoc": {
        "verb": "get"
      },
      "OptionalIpt": {
        "verb": "get",
        "onDemand": true
      },
      ...
    }
  }
```

Example 2 (lua):
```lua
curl -i -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/activities
  ...
  -d '{
  "id": "MyActivity",
  ...
    "parameters": {
      "InventorDoc": {
        "verb": "get"
      },
      "OptionalIpt": {
        "verb": "get",
        "onDemand": true
      },
      ...
    }
  }
```

Example 3 (sass):
```sass
curl -i -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/workitems \
  ...
  -d '{
  "activityId": "MyActivity+prod",
  ...
  "arguments": {
    "InventorDoc": {
      "url": "https://s3-us-east-1.amazonaws.com/inventorio-prod/documentation/APIBasics/Box.ipt"
    },
    "OptionalIpt": {
      "url": "https://s3-us-east-1.amazonaws.com/inventorio-prod/documentation/APIBasics"
    }
  ...
  }
}
```

Example 4 (sass):
```sass
curl -i -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/workitems \
  ...
  -d '{
  "activityId": "MyActivity+prod",
  ...
  "arguments": {
    "InventorDoc": {
      "url": "https://s3-us-east-1.amazonaws.com/inventorio-prod/documentation/APIBasics/Box.ipt"
    },
    "OptionalIpt": {
      "url": "https://s3-us-east-1.amazonaws.com/inventorio-prod/documentation/APIBasics"
    }
  ...
  }
}
```

---

## Use OnDemand Inputs

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/common/using-on-demand-inputs

**Contents:**
    - Jump To
- Use OnDemand Inputs
- Example
- Example
- Example
- function parameters
- Known issues:

Once you have a running custom AppBundle with an Activity and a WorkItem, you can consider more advanced processing.

This walkthrough will explain how you can optimize data downloads using so called onDemand inputs in Activities and WorkItems. This mechanism allows your AppBundle to ask for additional data to be downloaded using an http call during WorkItem processing only on an as-needed basis.

Conceptually, onDemand inputs allow your AppBundle to access additional resources based on the actual run of a given WorkItem, using a url that can be parameterized to query exactly the data you need right now. It can either access additional specific design files on your storage, or call your own server’s http API to query for json data etc.

There are several steps you need to take in order to be able to use onDemand inputs. First, when you are creating your activity, you must specify some of the input arguments as being onDemand. Note that onDemand can only be used when the parameter verb is get or head.

Second, you must refer to this parameter when sending the WorkItem, as shown here:

Third, your AppBundle add-in has to be able to ask for the optional onDemand input. This is done via writing specially formatted text to the log trace. The required format is best documented in the following method that handles a request for such an optional input and waits for the http call result:

An actual call to the function can be made like

The tricky pieces here are:

The method to support onDemand calls from an add-in is part of the Inventor Visual Studio template .

**Examples:**

Example 1 (lua):
```lua
curl -i -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/activities
  ...
  -d '{
  "id": "MyActivity",
  ...
    "parameters": {
      "InventorDoc": {
        "verb": "get"
      },
      "OptionalIpt": {
        "verb": "get",
        "onDemand": true
      },
      ...
    }
  }
```

Example 2 (lua):
```lua
curl -i -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/activities
  ...
  -d '{
  "id": "MyActivity",
  ...
    "parameters": {
      "InventorDoc": {
        "verb": "get"
      },
      "OptionalIpt": {
        "verb": "get",
        "onDemand": true
      },
      ...
    }
  }
```

Example 3 (sass):
```sass
curl -i -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/workitems \
  ...
  -d '{
  "activityId": "MyActivity+prod",
  ...
  "arguments": {
    "InventorDoc": {
      "url": "https://s3-us-east-1.amazonaws.com/inventorio-prod/documentation/APIBasics/Box.ipt"
    },
    "OptionalIpt": {
      "url": "https://s3-us-east-1.amazonaws.com/inventorio-prod/documentation/APIBasics"
    }
  ...
  }
}
```

Example 4 (sass):
```sass
curl -i -X POST \
  https://developer.api.autodesk.com/da/us-east/v3/workitems \
  ...
  -d '{
  "activityId": "MyActivity+prod",
  ...
  "arguments": {
    "InventorDoc": {
      "url": "https://s3-us-east-1.amazonaws.com/inventorio-prod/documentation/APIBasics/Box.ipt"
    },
    "OptionalIpt": {
      "url": "https://s3-us-east-1.amazonaws.com/inventorio-prod/documentation/APIBasics"
    }
  ...
  }
}
```

---

## V3 Changelog

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/change_history/changelog_v3

**Contents:**
    - Jump To
- V3 Changelog
- Release Date: 2025-06-30
- Release Date: 2024-03-12
- Release Date: 2021-03-15
- Release Date: 2021-02-17
- Release Date: 2020-11-20
- Release Date: 2020-10-20
- Release Date: 2020-10-01
- Release Date: 2020-08-20

ILogic log output is now part of the report.txt. The logs produced by iLogic start with [iLogic] prefix. This feature is supported in engines 2019 and upwards.

The Automation Service will now produce additional information on WorkItem failures. This information can be used to either debug the issue or contact support.

The POST /workitems operation will no longer return 429 errors as frequently as it did previously.

Validation of inputs has been enhanced so that the server detects additional invalid input conditions and returns a status of 400 for them.

Create nickname has improved error messaging. The error message for invalid nicknames is more detailed and the server retruns a status of 400 if the ClientId is used as a nickname.

Job reports are now uploaded every five minutes. This could be helpful if your job runs longer and you would like to see the reports during the process.

Create activity has improved error messaging which can report that the activity’s command-line doesn’t match the activity’s parameters.

Fixed a bug where “timeFinished” was being incorrectly included in the workitem status even when the job was in progress.

Validation to Activity creation to ensure that paths specified as command line parameters are encapsulated by quotes. The server now raises an error if paths are not placed within quotes.

Activity parameters that start with the string “adsk” are now reserved for internal use by the Automation Service.

WorkItem limits have been simplified. The limits for maximum number of downloads, maximum number of uploads, maximum total size of all downloads, maximum total size of all uploads, maximum download time, and maximum upload time have been removed.

This is the General Availability release of the Automation API V3.

This is first release of the Automation API (Beta) V3.

**Examples:**

Example 1 (unknown):
```unknown
GET workitems?startAfterTime=:epochSecondsInUTC
```

Example 2 (unknown):
```unknown
POST workitems/status
```

Example 3 (unknown):
```unknown
POST workitems/combine
```

---

## V3 Changelog

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/change_history/

**Contents:**
    - Jump To
- V3 Changelog
- Release Date: 2025-06-30
- Release Date: 2024-03-12
- Release Date: 2021-03-15
- Release Date: 2021-02-17
- Release Date: 2020-11-20
- Release Date: 2020-10-20
- Release Date: 2020-10-01
- Release Date: 2020-08-20

ILogic log output is now part of the report.txt. The logs produced by iLogic start with [iLogic] prefix. This feature is supported in engines 2019 and upwards.

The Automation Service will now produce additional information on WorkItem failures. This information can be used to either debug the issue or contact support.

The POST /workitems operation will no longer return 429 errors as frequently as it did previously.

Validation of inputs has been enhanced so that the server detects additional invalid input conditions and returns a status of 400 for them.

Create nickname has improved error messaging. The error message for invalid nicknames is more detailed and the server retruns a status of 400 if the ClientId is used as a nickname.

Job reports are now uploaded every five minutes. This could be helpful if your job runs longer and you would like to see the reports during the process.

Create activity has improved error messaging which can report that the activity’s command-line doesn’t match the activity’s parameters.

Fixed a bug where “timeFinished” was being incorrectly included in the workitem status even when the job was in progress.

Validation to Activity creation to ensure that paths specified as command line parameters are encapsulated by quotes. The server now raises an error if paths are not placed within quotes.

Activity parameters that start with the string “adsk” are now reserved for internal use by the Automation Service.

WorkItem limits have been simplified. The limits for maximum number of downloads, maximum number of uploads, maximum total size of all downloads, maximum total size of all uploads, maximum download time, and maximum upload time have been removed.

This is the General Availability release of the Automation API V3.

This is first release of the Automation API (Beta) V3.

**Examples:**

Example 1 (unknown):
```unknown
GET workitems?startAfterTime=:epochSecondsInUTC
```

Example 2 (unknown):
```unknown
POST workitems/status
```

Example 3 (unknown):
```unknown
POST workitems/combine
```

---

## WebSockets for When Callbacks Aren’t an Option

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/developers_guide/websocket-api

**Contents:**
    - Jump To
- WebSockets for When Callbacks Aren’t an Option
- Setup and Connection
- Authentication
- Making Requests
- Additional Resources

Note: WebSockets are not supported with the Fusion engine.

When using the Automation API directly from a client device (such as a desktop computer, mobile phone, or laptop), you cannot set up onComplete or onProgress callbacks that point back to the client device. This limitation forces applications to make repeated GET requests to check workitem progress, which is inefficient and increases energy consumption. To address this issue, the Automation API provides WebSocket endpoints that enable real-time communication.

The WebSocket API works with any client that can issue standard WebSocket requests. You can use it from a browser with the standard WebSocket API, from the command line using tools like wscat, or with any other WebSocket library or toolset.

The WebSocket host is websockets.forgedesignautomation.io.

To connect using wscat, use this command:

Once connected, wscat will display:

You need a valid authentication token to make requests through the WebSocket API. Obtain your token following the same steps used for HTTP requests.

The examples below use 2-legged tokens for simplicity. For production scenarios, use 3-legged tokens instead. Review the background information for guidance on using 3-legged tokens with the Automation API.

All WebSocket messages must be valid JSON. If you send invalid JSON, you’ll receive an error response:

To submit a workitem, send a properly formatted JSON request with your authentication token (replace <your token> with your actual bearer token):

You’ll immediately receive a status response indicating the workitem is queued:

When the workitem completes, you’ll automatically receive the final result:

For complete API details and advanced usage scenarios, see the WebSocket reference documentation.

**Examples:**

Example 1 (unknown):
```unknown
wscat -c wss://websockets.forgedesignautomation.io
```

Example 2 (unknown):
```unknown
wscat -c wss://websockets.forgedesignautomation.io
```

Example 3 (sass):
```sass
connected (press CTRL+C to quit)
>
```

Example 4 (sass):
```sass
connected (press CTRL+C to quit)
>
```

---

## workitems/batch

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/workitems-batch-POST

**Contents:**
    - Jump To
- workitems/batch
- Resource Information
  - Request
- Headers
  - Request
- Body Structure
  - Response
- HTTP Status Code Summary
  - Response

The new WorkItems are always placed on the queue and later picked up by an engine.

The following limits apply:

Per-engine. These limits are enforced when the engine processes the workitem.

Service wide. These limits are enforced during workitem submission.

Failure to download optional input arguments is OK. Failure to find or upload optional output arguments is OK.

For example, to receive data, POST/PUT requires request body which can be passed by ‘requestContent’.

It supports Box, Google Drive and Amazon Simple Storage Service (S3) services.

Examples of using argument “multiparts”:

Amazon Simple Storage Service (S3):

Successfully create a batch of new WorkItems.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
application/json
```

Example 3 (unknown):
```unknown
failedLimitProcessingTime
```

Example 4 (unknown):
```unknown
failedDownload
```

---

## workitems/combine

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/workitems-combine-POST

**Contents:**
    - Jump To
- workitems/combine
- Resource Information
  - Request
- Headers
  - Request
- Body Structure
  - Response
- HTTP Status Code Summary
  - Response

The allows users to create a simple fan-in workflow where 1-N workitems (parts) must complete before the final workitem (combinator) is processed.

The following limits apply:

Per-engine. These limits are enforced when the engine processes the workitem.

Service wide. These limits are enforced during workitem submission.

More explanation is at WorkItem Combine API Reference.

Successfully create a new WorkItem.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
application/json
```

Example 3 (sass):
```sass
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/workitems/combine' \
  -X 'POST' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "parts": [
          {
            "activityId": "mynickname.part+prod",
            "arguments": {
            "HostDwg": {
              "url": "https://s3.amazonaws.com/TestDwg/host.dwg",
              "verb": "get"
            },
            "Result": {
              "url": "das://intermediate/vararg_page1.pdf",
               "verb":  "put"
              }
            }
          },
          {
            "activityId": "mynickname.part+prod",
            "arguments": {
            "HostDwg": {
              "url": "https://s3.amazonaws.com/TestDwg/1/xref.dwg",
              "verb": "get"
            },
            "Result": {
              "url": "das://intermediate/vararg_page2.pdf",
              "verb":  "put"
            }
            }
          }
        ],
        "combinator": {
          "activityId" : "mynickname.combinator+prod",
          "arguments" : {
            "result" : {
              "url": "https://cdn.us.oss.api.autodesk.com/oss/v2/signedresources/123?region=US",
              "verb": "put"
            }
          }
        }
      }'
```

Example 4 (sass):
```sass
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/workitems/combine' \
  -X 'POST' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '{
        "parts": [
          {
            "activityId": "mynickname.part+prod",
            "arguments": {
            "HostDwg": {
              "url": "https://s3.amazonaws.com/TestDwg/host.dwg",
              "verb": "get"
            },
            "Result": {
              "url": "das://intermediate/vararg_page1.pdf",
               "verb":  "put"
              }
            }
          },
          {
            "activityId": "mynickname.part+prod",
            "arguments": {
            "HostDwg": {
              "url": "https://s3.amazonaws.com/TestDwg/1/xref.dwg",
              "verb": "get"
            },
            "Result": {
              "url": "das://intermediate/vararg_page2.pdf",
              "verb":  "put"
            }
            }
          }
        ],
        "combinator": {
          "activityId" : "mynickname.combinator+prod",
          "arguments" : {
            "result" : {
              "url": "https://cdn.us.oss.api.autodesk.com/oss/v2/signedresources/123?region=US",
              "verb": "put"
            }
          }
        }
      }'
```

---

## workitems/:id

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/workitems-id-DELETE/

**Contents:**
    - Jump To
- workitems/:id
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
- Example

Cancels a specific WorkItem.

If the WorkItem is on the queue, it is removed from the queue and not processed.

If the WorkItem is already being processed, then it may or may not be interrupted and cancelled.

If the WorkItem has already finished processing, then it has no effect on the processing or results.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/workitems/:id' \
  -X 'DELETE' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/workitems/:id' \
  -X 'DELETE' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (unknown):
```unknown
204 No Content
```

---

## workitems/:id

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/workitems-id-GET

**Contents:**
    - Jump To
- workitems/:id
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
  - Response

Gets the status of a specific WorkItem.

Typically used to ‘poll’ for the completion of a WorkItem, but see the use of the ‘onComplete’ argument for an alternative that does not require ‘polling’.

Successfully get the status of a WorkItem.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
failedLimitProcessingTime
```

Example 3 (unknown):
```unknown
failedDownload
```

Example 4 (unknown):
```unknown
failedInstructions
```

---

## workitems/:id

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/workitems-id-GET/

**Contents:**
    - Jump To
- workitems/:id
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
  - Response

Gets the status of a specific WorkItem.

Typically used to ‘poll’ for the completion of a WorkItem, but see the use of the ‘onComplete’ argument for an alternative that does not require ‘polling’.

Successfully get the status of a WorkItem.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
failedLimitProcessingTime
```

Example 3 (unknown):
```unknown
failedDownload
```

Example 4 (unknown):
```unknown
failedInstructions
```

---

## workitems/:id

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/workitems-id-DELETE

**Contents:**
    - Jump To
- workitems/:id
- Resource Information
  - Request
- Headers
  - Request
- URI Parameters
  - Response
- HTTP Status Code Summary
- Example

Cancels a specific WorkItem.

If the WorkItem is on the queue, it is removed from the queue and not processed.

If the WorkItem is already being processed, then it may or may not be interrupted and cancelled.

If the WorkItem has already finished processing, then it has no effect on the processing or results.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/workitems/:id' \
  -X 'DELETE' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/workitems/:id' \
  -X 'DELETE' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a'
```

Example 4 (unknown):
```unknown
204 No Content
```

---

## workitems/status

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/reference/http/workitems-status-POST

**Contents:**
    - Jump To
- workitems/status
- Resource Information
  - Request
- Headers
  - Request
- Body Structure
  - Response
- HTTP Status Code Summary
  - Response

Get WorkItem status for an array of WorkItem Ids.

Successfully get the status of a WorkItem.

**Examples:**

Example 1 (typescript):
```typescript
Bearer <token>
```

Example 2 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/workitems/status' \
  -X 'POST' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '[
        "03d65402faeb4409ac672f341462f689",
        "032a3a8e25b3409584194e7221a40059",
        "1230059b3409584194e7221230059000",
        "02d6d69106b14946b319ab68d68cc04f"
      ]'
```

Example 3 (unknown):
```unknown
curl -v 'https://developer.api.autodesk.com/da/us-east/v3/workitems/status' \
  -X 'POST' \
  -H 'Authorization: Bearer AuIPTf4KYLTYGVnOHQ0cuolwCW2a' \
  -H 'Content-Type: application/json' \
  -d '[
        "03d65402faeb4409ac672f341462f689",
        "032a3a8e25b3409584194e7221a40059",
        "1230059b3409584194e7221230059000",
        "02d6d69106b14946b319ab68d68cc04f"
      ]'
```

Example 4 (json):
```json
{
  "results": [
      {
          "status": "success",
          "reportUrl": "https://dasprod-store.s3.amazonaws.com/workItem/mynickname/03d65402faeb4409ac672f341462f689/report.txt",
          "activityId": "mynickname.myApp1+prod",
          "stats": {
              "timeQueued": "2024-03-06T03:11:09.1510699Z",
              "timeDownloadStarted": "2024-03-06T03:11:09.2898279Z",
              "timeInstructionsStarted": "2024-03-06T03:11:09.4473947Z",
              "timeInstructionsEnded": "2024-03-06T03:11:12.9289128Z",
              "timeUploadEnded": "2024-03-06T03:11:12.9633762Z",
              "timeFinished": "2024-03-06T03:11:13.3608607Z",
              "bytesDownloaded": 87040,
              "bytesUploaded": 3
          },
          "id": "03d65402faeb4409ac672f341462f689"
      },
      {
          "status": "success",
          "reportUrl": "https://dasprod-store.s3.amazonaws.com/workItem/mynickname/02d6d69106b14946b319ab68d68cc04f/report.txt",
          "activityId": "mynickname.myApp1+prod",
          "stats": {
              "timeQueued": "2024-03-06T04:07:34.6920266Z",
              "timeDownloadStarted": "2024-03-06T04:07:36.0231791Z",
              "timeInstructionsStarted": "2024-03-06T04:07:39.9518961Z",
              "timeInstructionsEnded": "2024-03-06T04:08:15.9285096Z",
              "timeUploadEnded": "2024-03-06T04:08:16.1572555Z",
              "timeFinished": "2024-03-06T04:08:17.0213784Z",
              "bytesDownloaded": 113,
              "bytesUploaded": 352256
          },
          "id": "02d6d69106b14946b319ab68d68cc04f"
      }
  ],
  "errors": {
      "032a3a8e25b3409584194e7221a40059": "Not found",
      "1230059b3409584194e7221230059000": "Not found"
  }
}
```

---
