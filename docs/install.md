# Installation Guide

This guide explains how to install and configure Westwood SharePoint Attachment.

## 1. Import the Managed Solution

1. Download the latest managed solution from GitHub Releases.
2. Open [Power Apps Maker Portal](https://make.powerapps.com).
3. Select the target environment.
4. Go to **Solutions**.
5. Select **Import solution**.
6. Upload:

```text
SharePointEmailAttachment_1_0_0_2_managed.zip
```

7. Complete the import.
8. Publish all customizations if prompted.

## 2. Configure Environment Variables

After import, configure the solution environment variables.

| Environment Variable | Description |
|---|---|
| `wwd_SharePointTenantId` | Microsoft Entra tenant ID used for SharePoint/Graph access and licence validation. |
| `wwd_SharePointClientId` | App registration client ID used by the server-side plugin. |
| `wwd_SharePointClientSecret` | App registration client secret. |
| `wwd_SharePointHost` | SharePoint host, for example `contoso.sharepoint.com`. |
| `wwd_SharePointAttachmentSizeLimitMb` | Maximum file size allowed for attachment, for example `15`. |

Example:

```text
wwd_SharePointTenantId = <tenant-guid>
wwd_SharePointClientId = <app-registration-client-id>
wwd_SharePointClientSecret = <app-registration-secret>
wwd_SharePointHost = contoso.sharepoint.com
wwd_SharePointAttachmentSizeLimitMb = 15
```

## 3. Configure Microsoft Entra App Registration

The server-side plugin needs an app registration that can read SharePoint files.

See the full guide:

```text
docs/app-registration.md
```

Typical Microsoft Graph application permissions:

- `Sites.Read.All`, or
- `Files.Read.All`, or
- `Sites.Selected` with explicit site grants

Admin consent must be granted.

Use the least privileged option that fits your organisation’s governance requirements.

## 4. Assign Security Roles

Assign roles as needed.

| Role | Purpose |
|---|---|
| `Westwood SharePoint Attachment User` | Optional role for users who need the control. Existing Dynamics roles may already provide the required Email/Attachment privileges. |
| `Westwood SharePoint Attachment Admin` | Used by administrators configuring the solution. |
| `Westwood License Administrator` | Used by administrators managing product licence records. |

Normal users do not need access to the licence table or environment variable values.

## 5. Add the PCF Control to the Email Form

1. Open the target Email form in the model-driven app form designer.
2. Add or select a text/place-holder column to host the PCF control.
3. Add the `Westwood SharePoint Attachment` control.
4. Configure the visible properties.

| Property | Description |
|---|---|
| `Tenant ID` | Microsoft Entra tenant ID. |
| `Environment ID` | Dataverse environment ID, used for diagnostics/support. |
| `Allowed Regarding Entities` | Comma-separated table logical names allowed for document retrieval. |
| `Title` | Optional title shown above the document list. |
| `Page Size` | Optional number of documents shown per page. |

Example:

```text
Allowed Regarding Entities = account,contact,opportunity
```

The Custom API names are built into the control and do not need to be configured.

## 6. Publish and Test

1. Save the Email form.
2. Publish all customizations.
3. Open or create an Email record.
4. Set the Regarding record to a supported table.
5. Open the tab/section containing the control.
6. Confirm SharePoint documents are listed.
7. Select a file and click **Attach Selected**.

## Required SharePoint Setup

Native Dataverse SharePoint integration must already be enabled and working for the relevant tables.

The control expects Dataverse to have SharePoint Document Location records for the Regarding record.
