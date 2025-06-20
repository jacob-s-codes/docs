---
title: "Projects in Tesseral"
subtitle: "Everything in Tesseral happens within a Project"
---

## What is a project?

Everything in Tesseral happens within a Project. Tesseral anticipates that each Project corresponds to a unique deployment of an application. 

For example, suppose you intend for Tesseral to handle auth for a software application you're working on -- called MyApp. Imagine further that you have a *Dev* environment, a *Staging* environment, and a *Production* environment. In this case, you should create three Projects: *MyApp Dev*, *MyApp Staging*, and *MyApp Production*. 

In fact, when you first sign up for Tesseral, we create *two* projects for you: one Project intended for development and another intended for production.

## Properties of Projects

Projects directly relate to the following Tesseral concepts:
* [Organizations](#projects-and-organizations)
* [Publishable keys](#projects-and-publishable-keys)
* [Backend API keys](#projects-and-backend-api-keys)

<Frame caption="Everything in Tesseral happens within a project" >
    <img src = "/assets/concepts/hierarchy-project.png">
    </img>
</Frame>


Projects have the following top level properties:

* [ID](#id)
* [Display name](#display-name)
* [Create time](#create-time)
* [Update time](#update-time)
* [Log in with Google](#log-in-with-google)
* [Log in with Microsoft](#log-in-with-microsoft)
* [Log in with GitHub](#log-in-with-github)
* [Log in with Email](#log-in-with-email)
* [Log in with Password](#log-in-with-password)
* [Log in with SAML](#log-in-with-saml)
* [Log in with Authenticator App](#log-in-with-authenticator-app)
* [Log in with Passkey](#log-in-with-passkey)
* [Google OAuth Client ID](#google-oauth-client-id)
* [Google OAuth Client Secret](#google-oauth-client-secret)
* [Microsoft OAuth Client ID](#microsoft-oauth-client-id)
* [Microsoft OAuth Client Secret](#microsoft-oauth-client-secret)
* [GitHub OAuth Client ID](#github-oauth-client-id)
* [GitHub OAuth Client Secret](#github-oauth-client-secret)
* [Vault domain](#vault-domain)
* [Vault domain custom](#vault-domain-custom)
* [Trusted domains](#trusted-domains)
* [Cookie domain](#cookie-domain)
* [Redirect URI](#redirect-uri)
* [After login redirect URI](#after-login-redirect-uri)
* [After signup redirect URI](#after-signup-redirect-uri)
* [Email send-from domain](#email-send-from-domain)
* [RBAC Policy](#rbac-policy)

### Related concepts

#### Projects and Organizations

[Organizations](/docs/concepts/organizations) in Tesseral correspond to businesses (or similar entities, such as schools or nonprofits) that use your application. Each Organization belongs to exactly one Project. A Project may -- and typically does -- have many Organizations. Organizations cannot exist outside of a Project. 

You may view the Organizations within a Project. To do so, first navigate to the relevant Project. Then select *Organizations* from the navigation bar.

#### Projects and Publishable Keys

[Publishable Keys](/docs/concepts/publishable-keys) help Tesseral's [client-side SDKs](/docs/sdks/clientside-sdks) find your Project. A Publishable Key always identifies exactly one Project. However, a given Project may have many Publishable Keys. 

A Publishable Key is not a secret. 

You may view the Publishable Keys within a Project. To do so, first navigate to the relevant Project. Then select *Project API Keys* from the navigation bar. You will find the Publishable Keys for the Project on a card marked *Publishable Keys*. 

#### Projects and Backend API Keys

[Backend API Keys](/docs/concepts/backend-api-keys) identify your app to Tesseral's [backend API](/docs/backend-api-reference), which you'll often use with Tesseral's [server-side SDKs](/docs/sdks/serverside-sdks). A Backend API Key always identifies exactly one Project. However, a given Project may have many Backend API Keys. 

Your Backend API Keys must always remain secret.

You may view the Backend API Keys within a Project. To do so, first navigate to the relevant Project. Then select *Project API Keys* from the navigation bar. You will find the Backend API Keys for the Project on a card marked *Backend API Keys*. 





### Top-level properties
#### ID

Each Project record has a universally unique identifier in Tesseral called `id`. This identifier always starts with the prefix `project_`. For example, `project_9nc2a3f0i4bl1c5darqq0l8g2` is a valid identifier for a Project.

#### Display name

Each Project record may have a display name, identified in the [Backend API](/docs/backend-api-reference) as `displayName`. This is a string that may not be unique. We recommend following the convention of the default Projects, e.g., *MyApp Dev*. 

#### Create time
Identified in the [Backend API](/docs/backend-api-reference) as `createTime`, this field simply represents the timestamp from when the Project record was created.

#### Update time

Identified in the [Backend API](/docs/backend-api-reference) as `updateTime`, this field  represents the timestamp from the last change to the Project record's properties.

#### Log in with Google

Identified in the [Backend API](/docs/backend-api-reference) as `logInWithGoogle`, this boolean field represents whether [Login with Google](/docs/login-methods/primary-factors/log-in-with-google) is enabled for the Project. 

Be aware that Organizations have [a similar property](/docs/concepts/organizations#log-in-with-google). If Login with Google is enabled for the Project but *not* enabled for a given Organization, no one within that Organization will be able to use Login with Google.

#### Log in with Microsoft

Identified in the [Backend API](/docs/backend-api-reference) as `logInWithMicrosoft`, this boolean field represents whether [Login with Microsoft](/docs/login-methods/primary-factors/microsoft) is enabled for the Project.

Be aware that Organizations have [a similar property](/docs/concepts/organizations#log-in-with-microsoft). If Login with Microsoft is enabled for the Project but *not* enabled for a given Organization, no one within that Organization will be able to use Login with Microsoft.

#### Log in with GitHub

Identified in the [Backend API](/docs/backend-api-reference) as `logInWithGithub`, this boolean field represents whether [Login with GitHub](/docs/login-methods/primary-factors/log-in-with-github) is enabled for the Project.

Be aware that Organizations have [a similar property](/docs/concepts/organizations#log-in-with-google). If Login with GitHub is enabled for the Project but *not* enabled for a given Organization, no one within that Organization will be able to use Login with GitHub.

#### Log in with Email

Identified in the [Backend API](/docs/backend-api-reference) as `logInWithEmail`, this boolean field represents whether [logging in with email](/docs/login-methods/primary-factors/-magic-links) is enabled for the Project.

Be aware that Organizations have [a similar property](/docs/concepts/organizations#log-in-with-email). If logging in with email is enabled for the Project but *not* enabled for a given Organization, no one within that Organization will be able to log in via email.


#### Log in with Password

Identified in the [Backend API](/docs/backend-api-reference) as `logInWithPassword`, this boolean field represents whether [logging in with passwords](/docs/login-methods/primary-factors/log-in-with-password) is enabled for the Project.

Be aware that Organizations have [a similar property](/docs/concepts/organizations#log-in-with-password). If logging in with passwords is enabled for the Project but *not* enabled for a given Organization, no one within that Organization will be able to use passwords.


#### Log in with SAML

Identified in the [Backend API](/docs/backend-api-reference) as `logInWithSaml`, this boolean field represents whether [logging in with SAML single sign-on](/docs/login-methods/primary-factors/log-in-with-enterprise-sso-saml) is enabled for the Organization.

Be aware that Organizations have [a similar property](/docs/concepts/organizations#log-in-with-saml). If logging in with SAML is enabled for the Project but *not* enabled for a given Organization, no one within that Organization will be able to use SAML SSO.


#### Log in with Authenticator App

Identified in the [Backend API](/docs/backend-api-reference) as `logInWithAuthenticatorApp`, this boolean field represents whether [logging in with an authenticator app](/docs/login-methods/secondary-factors/authentication-mfa) is enabled for the Organization.

Be aware that Organizations have [a similar property](/docs/concepts/organizations#log-in-with-authenticator-app). If logging in with authenticator apps is enabled for the Project but *not* enabled for a given Organization, no one within that Organization will be able to log in with passkeys.


#### Log in with Passkey

Identified in the [Backend API](/docs/backend-api-reference) as `logInWithPasskey`, this boolean field represents whether [logging in with passkey](/docs/login-methods/secondary-factors/log-in-with-passkey) as a [secondary factor](/docs/features/multifactor-authentication-mfa) is enabled for the Project.

Be aware that Organizations have [a similar property](/docs/concepts/organizations#log-in-with-passkey). If logging in with passkeys is enabled for the Project but *not* enabled for a given Organization, no one within that Organization will be able to log in with passkeys.


#### Google OAuth Client ID

Login with Google uses a protocol called OAuth. To use Login with Google with your app, you must register an *OAuth Client* with Google. You can read more about this process in [Google's documentation](https://developers.google.com/identity/protocols/oauth2).

When you register an OAuth Client with Google, you will receive a *Client ID* from Google. 

This is a non-sensitive string that will appear as a query parameter every time someone uses Login with Google to access your application. It looks something like this: `1005640118348-amh5tgkq641oru4fbhr3psm3gt2tcc94.apps.googleusercontent.com`. (This is actually the Client ID for using Login with Google for the New York Times.)


#### Google OAuth Client Secret

Login with Google uses a protocol called OAuth. To use Login with Google with your app, you must register your application with Google. You can read more about this process in [Google's documentation](https://developers.google.com/identity/protocols/oauth2).

When you register an application with Google, you will receive a *Client Secret* from Google. 

This is a *sensitive* value. Tesseral only stores it in encrypted form. You can only write to this value, and you cannot read it back out.


#### Microsoft OAuth Client ID

Login with Microsoft uses a protocol called OAuth. To use Login with Microsoft with your app, you must register an *OAuth Client* with Microsoft. You can read more about this process in [Microsoft's documentation](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app?tabs=client-secret%2Cexpose-a-web-api).

When you have registered your application with Microsoft, Microsoft will generate an *Application (client) ID* field. 

This is a non-sensitive string that uniquely identifies your application to Microsoft. It looks something like this: `99x12a11-84g1-0764-e648-91378ej456725`. (This is a made-up value.)

#### Microsoft OAuth Client Secret

Login with Microsoft uses a protocol called OAuth. To use Login with Microsoft with your app, you must register an *OAuth Client* with Microsoft. You can read more about this process in [Microsoft's documentation](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app?tabs=client-secret%2Cexpose-a-web-api).

This is a *sensitive* value. Tesseral only stores it in encrypted form. You can only write to this value, and you cannot read it back out.

#### GitHub OAuth Client ID

Login with GitHub uses a protocol called OAuth. To use Login with GitHub with your app, you must register an *OAuth Client* with GitHub. You can read more about this process in [GitHub's documentation](https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/creating-an-oauth-app).

When you register an OAuth Client with GitHub, you will receive a *Client ID* from GitHub.

This is a non-sensitive string that will appear as a query parameter every time someone uses Login with GitHub to access your application. It looks something like this: `Ov24lb8r3bwJrtWJl5aR`.


#### GitHub OAuth Client Secret

Login with GitHub uses a protocol called OAuth. To use Login with GitHub with your app, you must register your application with GitHub. You can read more about this process in [GitHub's documentation](https://docs.github.com/en/apps/oauth-apps/building-oauth-apps/creating-an-oauth-app).

When you register an application with GitHub, you will receive a *Client Secret* from GitHub.

This is a *sensitive* value. Tesseral only stores it in encrypted form. You can only write to this value, and you cannot read it back out.

#### Vault Domain

Tesseral hosts a domain on your behalf that powers [login
flows](/docs/features/customizing-your-login-experience), [self-serve User
settings](/docs/features/self-serve-user-settings), [self-serve Organization
settings](/docs/features/self-serve-user-settings), and
the [Tesseral Frontend API](/docs/frontend-api-reference).

The Vault Domain is the domain that your Project's Vault runs on.

#### Trusted Domains

Every Project has a set of Trusted Domains. Clientside code cannot access
information about the current logged-in [User](/docs/concepts/users) unless that
code is running on a Trusted Domain. For every domain you use the [Tesseral
React SDK](/docs/sdks/clientside-sdks/tesseral-sdk-react) from, add that domain
as a Trusted Domain.

Tesseral will always include your [Vault Domain](#vault-domain) as a Trusted
Domain.

Under the hood, Trusted Domains control the
[CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Guides/CORS) and
[WebAuthn Related Origins](https://w3c.github.io/webauthn/#sctn-related-origins)
configuration of your Project's Vault. You do not need to understand how CORS or
WebAuthn work to use Tesseral.

#### Cookie Domain

Tesseral uses cookies to keep authentication state on your users' web browsers.
Those cookies are always associated with your Project's Cookie Domain.

Make sure your Cookie Domain is a equal to or a "parent domain" of both your web
application's domain (e.g. `app.company.com`) and your Project's [Vault
Domain](#vault-domain) (e.g. `vault.app.company.com`).

For example, if your web application runs on `app.company.com` and your Vault
Domain is `vault.app.company.com`, then `app.company.com` or `company.com` are
valid Cookie Domains for you. 

Tesseral recommends you choose the "deepest" domain
possible (e.g. `app.company.com` is "deeper" than `company.com`), so that as few
domains as possible have access to your user's authentication cookies.

#### Redirect URIs

Tesseral frequently needs to redirect your users. Concretely, Tesseral redirects a user to your application in either of two scenarios:
1. When the user successfully **logs in** through the [Vault UI](/docs/features/customizing-your-login-experience)
2. When the user successfully **signs up** through the [Vault UI](/docs/features/customizing-your-login-experience)

By default, Tesseral routes users to the same place in both scenarios using the [Default Redirect URI](#default-redirect-uri). However, you *can* use the [After-Login Redirect URI](#after-login-redirect-uri) and [After-Signup Redirect URI](#after-signup-redirect-uri) fields to deviate from default behavior.

##### Default Redirect URI

When you first sign up for Tesseral, the Tesseral console asks for two domains: one for your production app and another for where you run local development. Tesseral uses this data to populate the *Default Redirect URI* for your production and development Projects, respectively. By default, Tesseral redirects users to the Default Redirect UI whenever users successfully log in *or* sign up.


##### After-Login Redirect URI

If you wish to override the Default Redirect URI in cases where users successfully log in, you can optionally populate the *After-Login Redirect URI*. Tesseral will redirect to this URI whenever a user successfully logs in. 


##### After-Signup Redirect URI

If you wish to override the Default Redirect URI in cases where users successfully *sign up*, you can optionally populate the *After-Signup Redirect URI*. Tesseral will redirect to this URI whenever a user successfully signs up. For example, you may wish to use the After-Signup Redirect URI to route new users into a specific onboarding flow. 

#### Email Send-From Domain

Tesseral often needs to send emails on your behalf. For example, Tesseral will require a new user to verify their email address -- which requires that Tesseral send the user an email. 

The *Email Send-From Domain* setting describes the mail domain from which Tesseral sends emails. By default, Tesseral sends such emails from `mail.tesseral.app`.

You may optionally configure Tesseral to send emails from a domain that you control. You may, for instance, have Tesseral send emails from `mail.vault.myapp.com.`

Learn more about transactional emails in Tesseral [here](/docs/features/transactional-emails). 

#### RBAC Policy

In order to support [Role-Based Access
Control](/docs/features/role-based-access-control), every Project has exactly
one [RBAC Policy](/docs/features/role-based-access-control#rbac-policy). An RBAC
Policy is a list of [Actions](/docs/features/role-based-access-control#actions).
