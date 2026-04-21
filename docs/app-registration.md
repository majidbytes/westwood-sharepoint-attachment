# Microsoft Entra App Registration

Westwood SharePoint Attachment uses a server-side Dataverse plugin to list and download SharePoint files. The plugin requires a Microsoft Entra app registration with permission to read SharePoint files.

Do not use a Westwood Software app registration in a customer environment. The customer should create or provide an app registration in their own Microsoft tenant.

## 1. Create App Registration

1. Open [Azure Portal](https://portal.azure.com).
2. Go to **Microsoft Entra ID**.
3. Go to **App registrations**.
4. Select **New registration**.
5. Name:

```text
Westwood SharePoint Attachment
```

6. Supported account types:

```text
Accounts in this organizational directory only
```

7. Redirect URI:

```text
Leave blank
```

8. Select **Register**.

## 2. Copy IDs

After creation, copy:

```text
Application (client) ID
Directory (tenant) ID
```

Use these later in Dataverse environment variables:

```text
wwd_SharePointClientId
wwd_SharePointTenantId
```

## 3. Create Client Secret

1. Open the app registration.
2. Go to **Certificates & secrets**.
3. Select **New client secret**.
4. Description:

```text
Westwood SharePoint Attachment
```

5. Expiry:

```text
6 or 12 months, depending on your organisation policy
```

6. Select **Add**.
7. Copy the secret **Value** immediately.

Use it in:

```text
wwd_SharePointClientSecret
```

Important: copy the secret value immediately. It cannot be viewed again later.

## 4. Add API Permissions

Open the app registration and go to **API permissions**.

Add Microsoft Graph application permissions.

Recommended simple option:

```text
Microsoft Graph > Application permissions > Sites.Read.All
```

Then select:

```text
Grant admin consent
```

Alternative broader option:

```text
Files.Read.All
```

For stricter governance, use:

```text
Sites.Selected
```

`Sites.Selected` is more secure but requires additional SharePoint site-level permission grants. Use it only if your organisation is comfortable configuring selected-site permissions.

## 5. Configure Dataverse Environment Variables

In the imported Dataverse solution, set:

```text
wwd_SharePointTenantId = <Directory tenant ID>
wwd_SharePointClientId = <Application client ID>
wwd_SharePointClientSecret = <Client secret value>
wwd_SharePointHost = <tenant>.sharepoint.com
wwd_SharePointAttachmentSizeLimitMb = 15
```

Example:

```text
wwd_SharePointHost = contoso.sharepoint.com
```

Do not include `https://` in `wwd_SharePointHost`.

## 6. Secret Rotation

The client secret expires based on the expiry selected when it was created.

Before it expires:

1. Create a new client secret on the same app registration.
2. Update `wwd_SharePointClientSecret` in Dataverse.
3. Test the control.
4. Delete the old secret after confirming the new one works.

## 7. Security Notes

- Store the client secret securely.
- Rotate the secret before expiry.
- Use the least privileged permission model acceptable to your organisation.
- `Sites.Selected` is preferred for stricter production environments, but requires extra site permission setup.
- Do not commit client secrets to source control.
- Do not send client secrets by email unless your organisation allows that process.
