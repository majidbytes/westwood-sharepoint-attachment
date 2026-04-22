# Licensing Guide

Westwood SharePoint Email Attachment is licensed per Microsoft tenant.

## Trial

If no paid licence is configured, the solution creates a 14-day trial licence automatically.

Trial rows include an internal fingerprint. If a trial date or trial identity field is manually changed, the trial becomes invalid.

## Paid Licence

After purchase, email Westwood Software with:

- Company name
- Buyer email address
- Stripe receipt number or payment reference
- Dynamics 365 / Dataverse environment URL
- Microsoft tenant ID
- Organisation ID, optional

Email:

```text
sales@westwoodsoftware.net
```

Westwood Software will verify payment and issue a signed tenant-bound licence key.

## Applying a Licence Key

1. Open the `Westwood SharePoint Attachment Admin` app.
2. Open the Product License row for:

```text
sharepoint-attachment
```

3. Paste the licence key into the `License Key` field.
4. Save the row.

The solution validates the key and populates the derived fields automatically, including:

- Product code
- Tenant ID
- Licence type
- Issued date
- Expiry date, if applicable
- Stripe payment reference
- Status reason

After saving, refresh the Email form. The control should show:

```text
License active.
```

## Licence Scope

The licence key is bound to your Microsoft tenant ID.

Environment ID and Organisation ID may be captured for support and diagnostics, but paid entitlement is validated at tenant level.

## Licence Types

Supported licence types include:

- Trial
- Perpetual
- Subscription
- Partner
- Internal

For a perpetual licence, the licence expiry date is blank.

For a subscription licence, the licence expiry date controls when the paid entitlement expires.
