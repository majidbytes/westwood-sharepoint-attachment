# Release Notes

## v1.0.0.2

Initial managed solution release.

Demo video:

```text
https://youtu.be/8ojkE5KLU3s
```

### Includes

- PCF control for attaching SharePoint documents to Dynamics 365 Emails.
- Dataverse Custom APIs for listing and attaching documents.
- Server-side plugin assembly.
- Product licence table.
- Admin model-driven app for licence entry.
- Security roles.
- Environment variable definitions.
- 14-day trial support.
- Tenant-bound signed licence validation.
- Licence key auto-application on Product License rows.

### Managed Solution

```text
SharePointEmailAttachment_1_0_0_2_managed.zip
```

### Prerequisites

- Native Dataverse / Dynamics 365 SharePoint integration enabled.
- Microsoft Entra app registration with SharePoint/Graph read permissions.
- Model-driven app Email form configuration.

### Known Notes

- Licensing is enforced at Microsoft tenant level.
- Environment ID and Organisation ID are used for diagnostics/support.
- The control requires SharePoint Document Location records created by native Dataverse SharePoint integration.
