# Westwood SharePoint Attachment

Westwood SharePoint Attachment is a Dynamics 365 / Dataverse managed solution that lets users browse SharePoint documents related to a Dataverse record and attach selected files directly to an Email.

The solution is designed for model-driven apps where native Dataverse SharePoint integration is already enabled.

## Current Release

```text
Version: 1.0.0.2
Managed solution: SharePointEmailAttachment_1_0_0_2_managed.zip
```

Download the managed solution from the GitHub **Releases** page.

## Demo Video

Watch Westwood SharePoint Attachment in action:

```text
https://youtu.be/8ojkE5KLU3s
```

The video shows the control embedded on the Email form, loading related SharePoint documents, selecting files, and attaching them directly to the Email.

## What Is Included

- PCF control for Email forms
- Dataverse Custom APIs
- Server-side plugin assembly
- Product licence table
- Licence admin model-driven app
- Security roles
- Environment variable definitions
- 14-day trial support
- Tenant-bound signed licence validation

## Prerequisites

Before installing, make sure the target environment has:

- Dynamics 365 / Dataverse model-driven apps.
- Native out-of-the-box Dataverse SharePoint integration enabled.
- SharePoint document locations configured for the tables you want to use.
- Permission to import managed solutions.
- Permission to configure environment variables.
- Permission to assign security roles.
- Microsoft Entra app registration with SharePoint/Graph read permissions.

The control relies on native Dataverse SharePoint document locations. It does not replace Microsoft’s out-of-the-box SharePoint integration.

## Quick Start

1. Download `SharePointEmailAttachment_1_0_0_2_managed.zip` from the latest GitHub release.
2. Import the managed solution into your target Dataverse environment.
3. Configure the required environment variables.
4. Assign the relevant security roles.
5. Add the PCF control to the Email form.
6. Open an Email record and test document listing.
7. Use the 14-day trial or apply a licence key.

Detailed instructions:

- [Installation Guide](docs/install.md)
- [Microsoft Entra App Registration](docs/app-registration.md)
- [Licensing Guide](docs/licensing.md)
- [Troubleshooting](docs/troubleshooting.md)
- [Release Notes](docs/release-notes.md)

## Licensing

Westwood SharePoint Attachment is licensed per Microsoft tenant.

The licence key is bound to your Microsoft tenant ID. Environment ID and Organisation ID may be captured for support and diagnostics, but paid entitlement is validated at tenant level.

The solution includes a 14-day trial. A valid licence from Westwood Software is required after the trial period.

For licence keys and support:

```text
sales@westwoodsoftware.net
```

## Support

Website:

```text
https://westwoodsoftware.net
```

Email:

```text
sales@westwoodsoftware.net
```

## Commercial Notice

Westwood SharePoint Attachment is commercial software. Do not redistribute the managed solution or licence keys without written permission from Westwood Software.
