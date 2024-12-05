## Authentication

Authentication is the process of confirming and validating ownership of an identity associated with an entity. This process shouldn't be confused with authorization. While they are similar and closely related, they are distinct processes.

When an entity attempts to use a system, the system prompts it to provide and prove its identity. This typically happens via one or more means, such as providing a username and password or a hardware token (associated with a registered entity).

### Entity

An entity is any object attempting to use a system. This is typically a human, but it can also include computers, services, and even other objects such as vehicles.

### Identity

An identity is a collection of attributes and information associated with an entity. Some of these attributes uniquely identify an entity and are often used in the authentication process. Below are a few examples:

- Email address
- Home address
- Username
- User ID

## Authentication process flow

The video below illustrates a typical process flow when a user attempts to authenticate to a web application. The first part of the illustration shows what happens when authentication is successful. The second half illustrates what typically happens when authentication is unsuccessful.

## Common types of authentication

### Password authentication

In this form of authentication, the system will prompt the entity attempting to use it to provide both its username or other unique identifier (the entity's identity) and the password associated with the username or identifier (this validates the entity has the provided identity, i.e., the entity is who it says it is).

Since identity validation relies on providing the password associated with the identity, it's important that this password is private and hard to guess.

### Tokens and access keys

In this form of authentication, a single token (or access key) is provided by the entity to the system. Tokens are commonly associated with an identity, hence additional data (such as a username) isn't required.

Much like passwords, the token (or access key) proves the validity of the identity associated with it. Therefore, tokens must be private and difficult to produce or guess.

### Hardware token

As the name suggests, this form of authentication is similar to token-based authentication, except a piece of hardware is used to store, and provide or generate, a token to authenticate an entity.

Again, since physical access to the hardware token proves ownership of an identity, these tokens should be kept on-person and not be shared or left unattended.

### Biometrics

In this form of authentication, an individual's biometric properties are used to provide both identification and ownership of that identification. Below are some common biometric properties that are used:

- Fingerprints
- Facial recognition
- Voice recognition

### Multi-factor authentication (MFA)

This is where more than one method of authentication from independent categories of credentials is used to verify the user's identity. The goal of MFA is to create a layered defense and make it more difficult for an unauthorized person to access a target, such as a physical location, computing device, network, or database. Two-factor authentication (2FA) is a form of MFA that specifically uses two different forms of authentication.

MFA can help to protect against phishing attacks, where users' passwords are captured, as well as any attacks where passwords are stolen or guessed, such as credential stuffing or automated guessing.

## Impact

The process of authentication confirms and validates the identity of the entity interacting with the system, so if this step is missed, the system cannot know or trust anything about the entity. In addition, authentication forms a vital step to authorization.

## Real-world examples

### Facebook

OAuth is a standard often used by applications to grant access to the site via another account. In February 2013, [Facebook had a vulnerability](https://threatpost.com/facebook-patches-oauth-authentication-vulnerability-022613/77563/) because it implemented this feature in its platform. The vulnerability meant an attacker could gain full access to a victim's account by getting them to visit a specially crafted website.

### Apple

[Sign in with Apple](https://en.wikipedia.org/wiki/Sign_in_with_Apple) is an Apple service that allows users to authenticate to other services and accounts using their Apple account. In May 2020, a [vulnerability was identified](https://bhavukjain.com/blog/2020/05/30/zeroday-signin-with-apple/) in this service which would allow another user to sign in to accounts as another user.

This vulnerability could have allowed an attacker to access other user accounts on services that supported this means of authentication.

### Dropbox

In June 2011, a post on Pastebin outlined a [severe vulnerability with Dropbox,](https://techcrunch.com/2011/06/20/dropbox-security-bug-made-passwords-optional-for-four-hours/) which allowed users to log into accounts using any password. Since many use Dropbox to store all types of information, some of it potentially sensitive, this was a significant security risk. This particular vulnerability remained live for around four hours.