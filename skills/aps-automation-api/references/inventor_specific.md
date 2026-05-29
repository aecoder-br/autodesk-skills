# Aps-Automation-Api_Docs - Inventor Specific

**Pages:** 3

---

## About this Walkthrough

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/inventor/about-this-tutorial

**Contents:**
    - Jump To
- About this Walkthrough
- Postman walkthrough
- Additional resources for C# programmers

This walkthrough guides you through the process of loading an Inventor add-in and resizing an Inventor part or assembly. It doesn’t teach you how to create Inventor add-ins. Instead, it points you to resources that can teach you how to create them (See Task 3).

This walkthrough uses cURL to send HTTP requests to APS. cURL is able to clearly show request and response information. It, however, is not the best tool to demonstrate a workflow by sending a series of HTTP requests to APS. We have hence provided a Postman based walkthrough to make it easier for you to send requests to APS.

Postman is a popular tool that provides an easy-to-use interface to send HTTP requests. The Postman walkthrough comes with a collection of pre-populated HTTP requests that you can modify. This gives you the ability to experiment without having to write a single line of code.

On the Postman Collection, requests are grouped by task. The group has the same name as the corresponding task in the cURL walkthrough on the APS developer portal.

Similarly, requests are named such that they have the same names as the corresponding step in the cURL walkthrough on the APS developer portal.

A video of a demonstration covering content similar to that of this walkthrough is available at https://www.autodesk.com/autodesk-university/class/Getting-Started-Design-Automation-Inventor-Forge-2019#video. If you are a C# programmer, we recommend that you watch this video.

After you follow the cURL or Postman walkthrough, and you have been introduced to the WorkItem creation and WorkItem execution workflow, you can look at this Visual Studio extension.

---

## About this Walkthrough

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/inventor

**Contents:**
    - Jump To
- About this Walkthrough
- Postman walkthrough
- Additional resources for C# programmers

This walkthrough guides you through the process of loading an Inventor add-in and resizing an Inventor part or assembly. It doesn’t teach you how to create Inventor add-ins. Instead, it points you to resources that can teach you how to create them (See Task 3).

This walkthrough uses cURL to send HTTP requests to APS. cURL is able to clearly show request and response information. It, however, is not the best tool to demonstrate a workflow by sending a series of HTTP requests to APS. We have hence provided a Postman based walkthrough to make it easier for you to send requests to APS.

Postman is a popular tool that provides an easy-to-use interface to send HTTP requests. The Postman walkthrough comes with a collection of pre-populated HTTP requests that you can modify. This gives you the ability to experiment without having to write a single line of code.

On the Postman Collection, requests are grouped by task. The group has the same name as the corresponding task in the cURL walkthrough on the APS developer portal.

Similarly, requests are named such that they have the same names as the corresponding step in the cURL walkthrough on the APS developer portal.

A video of a demonstration covering content similar to that of this walkthrough is available at https://www.autodesk.com/autodesk-university/class/Getting-Started-Design-Automation-Inventor-Forge-2019#video. If you are a C# programmer, we recommend that you watch this video.

After you follow the cURL or Postman walkthrough, and you have been introduced to the WorkItem creation and WorkItem execution workflow, you can look at this Visual Studio extension.

---

## Task 7 - Download the Results

**URL:** https://aps.autodesk.com/en/docs/design-automation/v3/tutorials/inventor/task7-download-results

**Contents:**
    - Jump To
- Task 7 - Download the Results
- Step 1 - Get a S3 download URL for resized IPT file
  - Request
  - Response
- Step 2 - Download resized IPT file from OSS
  - Request
  - Response
- Step 3 - Get a download URL for BMP file
  - Request

After you submit a WorkItem, you must wait for it to complete and download the results.

By the end of this task, you will be able to:

You will use the following operation in this task:

Now that your WorkItem has finished successfully, the resulting IPT file should have been uploaded to OSS. You can now use the Data Management API to download it to your local machine.

Note: This download is directly from S3 (or a CDN). So, it doesn’t need an Authorization header.

The file should download to your local machine.

Note: This download is directly from S3 (or a CDN). So, it doesn’t need an Authorization header.

The file should download to your local machine.

**Examples:**

Example 1 (typescript):
```typescript
curl -X GET \
      'https://developer.api.autodesk.com/oss/v2/buckets/<YOUR_BUCKET_KEY>/objects/<RESIZED_IPT_FILENAME>/signeds3download'
      - H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
      - H 'Content-Type: application/json'
```

Example 2 (typescript):
```typescript
curl -X GET \
      'https://developer.api.autodesk.com/oss/v2/buckets/<YOUR_BUCKET_KEY>/objects/<RESIZED_IPT_FILENAME>/signeds3download'
      - H 'Authorization: Bearer <YOUR_ACCESS_TOKEN>' \
      - H 'Content-Type: application/json'
```

Example 3 (json):
```json
{
    "status": "complete",
    "url": "<SIGNED_URL_TO_RESIZED_IPT_FILE>",
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
    "url": "<SIGNED_URL_TO_RESIZED_IPT_FILE>",
    "params": {
        "content-type": "application/octet-stream",
        "content-disposition": "attachment; filename*=utf-8''ResultSmall.ipt; filename=ResultSmall.ipt; creation-date=\"Wed, 27 Sep 2023 08:52:52 GMT\"; modification-date=\"Wed, 27 Sep 2023 08:52:52 GMT\"; read-date=\"Wed, 27 Sep 2023 08:52:52 GMT\"; size=240128"
    },
    "size": 240128,
    "sha1": "064db8ddbfc3779335518f496ca232b140783201"
}
```

---
