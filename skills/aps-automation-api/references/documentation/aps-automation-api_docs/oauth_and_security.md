# Aps-Automation-Api_Docs - Oauth And Security

**Pages:** 2

---

## Task 1 – Obtain an Access Token

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/fusion/task1-authenticate

**Contents:**
    - Jump To
- Task 1 – Obtain an Access Token
- Step 1 - Register an App
- Step 2 - Convert Client ID and Secret to Base64 encoded string
- Step 3 - Use encoded string to obtain an Access Token

This task produces a two-legged OAuth token with a scope sufficient to authenticate the remaining tasks in this walkthrough.

By the end of this task, you will know how to obtain a two-legged access token when the Client ID and Client Secret is known.

You use the following operations in this task:

Follow the instructions on Create an App to register the App you will create for this walkthrough.

You must combine your Client ID with the Client Secret and convert it to a Base64 encoded string before you can request a two-legged OAuth access token.

Note: There are online tools that you can use to convert the combined string to a Base64 encoded string. However, we don’t recommend that you use such tools. Exposing your Client ID and Client Secret to an online tool can be a security threat.

You should receive a string that looks like RjZEbjh5cGVtMWo4UDZzVXo4SVgzcG1Tc09BOTlHVVQ6QVNOa3c4S3F6MXQwV1hISw==.

Call the POST token endpoint:

The Base64 encoded Client ID + Client Secret are passed through the Authorization header. The grant_type and scope are specified as form fields in the request body.

Note: The bucket:read scope is not required for the walkthrough. However, you will need bucket:read if you plan to list the files in a bucket.

A successful response, in relevant part, will look like this (though again, the example is formatted for ease of reading):

**Examples:**

Example 1 (typescript):
```typescript
<CLIENT_ID>:<CLIENT_SECRET>
```

Example 2 (typescript):
```typescript
<CLIENT_ID>:<CLIENT_SECRET>
```

Example 3 (unknown):
```unknown
b64encode()
```

Example 4 (unknown):
```unknown
Convert.ToBase64String()
```

---

## Task 1 – Obtain an Access Token

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/3dsmax/task1-authenticate

**Contents:**
    - Jump To
- Task 1 – Obtain an Access Token
- Step 1 - Register an App
- Step 2 - Convert Client ID and Secret to Base64 encoded string
- Step 3 - Use encoded string to obtain an Access Token

This task produces a two-legged OAuth token with a scope sufficient to authenticate the remaining tasks in this walkthrough.

By the end of this task, you will know how to obtain a two-legged access token when the Client ID and Client Secret is known.

You use the following operations in this task:

Follow the instructions on Create an App to register the App you will create for this walkthrough.

You must combine your Client ID with the Client Secret and convert it to a Base64 encoded string before you can request a two-legged OAuth access token.

Note: There are online tools that you can use to convert the combined string to a Base64 encoded string. However, we don’t recommend that you use such tools. Exposing your Client ID and Client Secret to an online tool can be a security threat.

You should receive a string that looks like RjZEbjh5cGVtMWo4UDZzVXo4SVgzcG1Tc09BOTlHVVQ6QVNOa3c4S3F6MXQwV1hISw==.

Call the POST token endpoint:

The Base64 encoded Client ID + Client Secret are passed through the Authorization header. The grant_type and scope are specified as form fields in the request body.

Note: The bucket:read scope is not required for the walkthrough. However, you will need bucket:read if you plan to list the files in a bucket.

A successful response, in relevant part, will look like this (though again, the example is formatted for ease of reading):

**Examples:**

Example 1 (typescript):
```typescript
<CLIENT_ID>:<CLIENT_SECRET>
```

Example 2 (typescript):
```typescript
<CLIENT_ID>:<CLIENT_SECRET>
```

Example 3 (unknown):
```unknown
b64encode()
```

Example 4 (unknown):
```unknown
Convert.ToBase64String()
```

---
