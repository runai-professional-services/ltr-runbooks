---
title: Configure SSO
nav_order: 2
parent: Platform Configuration
---

# Implementing SSO

<span class="fs-3">
  <a href="https://docs.run.ai/v2.20/admin/authentication/authentication-overview/" class="btn" target="_blank" rel="noopener">Docs</a>
</span>

*Note - Always refer to documentation - this is just a students' guide*

## Pre-Reqs

This lab will run through the implementation of Single Sign On (SSO) using a pre-configured OIDC tenant. For production use, your infra teams will need to configure this and provide you with the relevant parameters. The configuration of the IDp itself is beyond the scope of this lab.

## OIDC Parameters

For the purpose of this lab, your IDp admin has provided you with the following parameters:

```bash
# Discovery URL:        
https://sso.learn-to.run/application/o/provider-for-run-ai-oidc/.well-known/openid-configuration
# Client ID:
clientid
# Client Secret:
clientsecret
# Scopes:
openid, runai
# Logout URL:
https://sso.learn-to.run/application/o/provider-for-run-ai-oidc/end-session/
```

## Configure SSO

- Navigate to Admin / Security
- Add an Identity Provider of type "Custom OpenID Connect"
- Provide the metadata file as "From URL"
- Paste in the Discovery URL and the client ID and Secret
- Add the additional scopes (email and profile) to the "Scopes" section
- Click "Save"

## Configure the Logout URL

- Click on "+REDIRECT URL" and paste in the correct value

## Check Authentication is Correct

*IMPORTANT - Always test SSO configuration in a clean privacy browser*

- In a new privacy browser, open the application and attempt to log in with SSO
- You should see that you are correctly authenticated *BUT*, you will see a permissions error

## Configure Authorisation for Admins

- In your non-privacy browser window, logged in as a local administrator, Open "Access" and create a "NEW ACCESS RULE"
- Select "Subject" / "SSO Group"
- Our IDp Admin has told us that admins are in a group called "System Administrators". Add that to the group name.
- Select the system role of "System administrator" and set the scope to global
- Save the rule

## Configure Authorisation for Viewers

- In your non-privacy browser window, logged in as a local administrator, Open "Access" and create a "NEW ACCESS RULE"
- Select "Subject" / "SSO Group"
- Our IDp Admin has told us that admins are in a group called "Viewers". Add that to the group name.
- Select the system role of "Viewers" and set the scope to global
- Save the rule

## Test our Authorisations

### Administrator

- In a clean privacy browser, attempt to log into the platform with the following credentials, having selected the "SSO" option for sign in:

```bash
#username:
runai-admin@nvidia.com
#password:
Abcd!234
```

- Ensure that you have a working SSO login and that you have admin privileges

### Viewer

- In another clean privacy browser, attempt to log into the platform with the following credentials, having selected the "SSO" option for sign in:

```bash
#username:
runai-viewer@nvidia.com
#password:
Abcd!234
```

- Ensure that you have a working SSO login and that you only have privileges by attempting to create an now project or other object
  