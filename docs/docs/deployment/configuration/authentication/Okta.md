---
title: Okta
---

:::tip

Organisations within Flagsmith can be locked to a single authentication method if required, meaning that accounts can
neither be created or logged into with anything other than the method specified.

This can be configured at an Organisation level by a Super-Administrator. Please get in touch if you need help with
this.

:::

## Prerequisites

### SaaS Customers & Private Cloud

To configure the Okta integration with Flagsmith, you must have created a valid organisation at app.flagsmith.com or
your private cloud URL. The organisation must be on our Enterprise plan. You should contact the Flagsmith support team
(support@flagsmith.com) to create a SAML organisation and we will provide you with your organisation name.

### Enterprise Self Hosted

To configure the Okta integration with Flagsmith self hosted, you must be using an Enterprise licence to self host the
Flagsmith application. You should then complete the steps listed [here](/deployment/configuration/authentication/saml)
up to and including the line which states ‘_Once you've completed these fields, hit the Save button to create the SAML
configuration._’

## Supported Features

:::info

The Okta integration sits on top of SAML. As a result you can also take advantage of
[SAML Group Sync](/system-administration/saml#group-sync) is part of the Okta integration.

:::

- IdP-initiated SSO
- SP-initiated SSO
- Group Sync

## Procedure

- In Okta, select the Sign On tab for the Flagsmith app, then click Edit.
  - Scroll down to Advanced Sign-on Settings.
  - Enter Base API Url (if using SaaS this should be [https://api.flagsmith.com](https://api.flagsmith.com), otherwise
    it will be your self hosted / private cloud API URL) and SAML Organisation (this should have been provided by
    Flagsmith support)
  - Click Save.
- In Okta, on the ‘Sign on’ tab, under ‘SAML Signing Certificates’, click ‘Actions’ -> ‘View IdP Metadata’ on the first
  certificate in the list.
  - **For SaaS customers: **Save this metadata to a file and send it to Flagsmith
    ([support@flagsmith.com](mailto:support@flagsmith.com))
  - **For Self-Hosted customers: **Copy this metadata and paste it into the ‘Idp metadata xml’ field in the Flagsmith
    admin dashboard as per the instructions [here](/deployment/configuration/authentication/saml).
- Once Flagsmith support have confirmed that the metadata has been uploaded, you should now be able to sign in via the
  Okta applications dashboard and the Flagsmith dashboard (by entering the organisation name given to you by Flagsmith
  support).

## Troubleshooting & Tips

- If your users are unable to sign in to the Flagsmith application via Okta, it’s important to check if they already
  have a user account in Flagsmith with their Okta email address. If they do, make sure that they are not a member of
  any other organisations than the one set up in the Okta integration.
