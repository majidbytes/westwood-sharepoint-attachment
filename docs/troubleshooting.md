# Troubleshooting

## The control shows no documents

Check:

- The Email has a Regarding record.
- The Regarding table has native SharePoint integration enabled.
- A SharePoint Document Location exists for the Regarding record.
- The user has read access to SharePoint Site and SharePoint Document Location records.
- The configured app registration has permission to read the SharePoint site/files.
- `Allowed Regarding Entities` includes the Regarding table logical name.

## The control says the licence is invalid

Check:

- The tenant ID configured on the control matches the tenant ID in the licence.
- The licence row is active.
- The licence key has not been modified.
- The licence has not expired.
- There are not multiple active licence rows for the same product/tenant.

## Trial is active even after entering a key

Check:

- The licence key was saved successfully.
- The Product License row status reason changed to `Licensed`.
- The derived fields were populated after saving the key.
- The Email form was fully refreshed.
- There are not duplicate active rows for `sharepoint-attachment`.

## Attach Selected is disabled

Check:

- A document is selected.
- Trial or paid licence is active.
- The user has permission to create Email attachments.

## File attachment fails

Check:

- File size is below `wwd_SharePointAttachmentSizeLimitMb`.
- SharePoint app registration has permission to download the file.
- The selected file belongs to the resolved SharePoint folder for the Regarding record.
- The Email record exists and has been saved.

## Environment variable issues

Check:

- `wwd_SharePointTenantId` is populated.
- `wwd_SharePointClientId` is populated.
- `wwd_SharePointClientSecret` is populated and not expired.
- `wwd_SharePointHost` does not include `https://`.
- `wwd_SharePointAttachmentSizeLimitMb` is a valid whole number.

## Support

Email:

```text
sales@westwoodsoftware.net
```

Include:

- Environment URL
- Tenant ID
- Organisation ID, if available
- Screenshot of the error
- Approximate date/time of the issue
