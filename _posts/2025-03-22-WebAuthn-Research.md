---
title: WebAuthn Research
date: 2025-03-29 21:25:10 +1300
categories: [Authentication, Web]
tags: [passwordless, webauthn]
description: My WebAuthn and Passwordless Authentication Research Assessment
---
# Introduction:

## What is WebAuthn and passwordless authentication, and why is it important?

To understand why passwordless authentication is so important for the future, we need to look at how the traditional passwords that are everywhere on the internet came to be. Now passwords themselves have been around for centuries, used by the Romans and many others, but passwords as we know them were created  in 1960 at the Massachusetts Institute of Technology (MIT) by Fernando Corbato, as a way to make sure users could only access their own specific files that were being stored on a single disk file (Editor, 2017). Unfortunately, even back then the password proved that it was not as secure as hoped, as just 2 years after the password was created, the first documented case of password theft also occurred (McMillan, 2012).

Now when Fernando created the password, he had no idea just how much technology would change and as he was primarily a researcher, security was not his first concern (McMillan, 2012). So, passwords were never meant to the first line of defence for all our personal data and accounts the way that they are today.

Which brings us to passwordless authentication, a viable alternative for the future of account security. Passwordless authentication allows users access to applications and services using either something you are or something you have, or occasionally a combination of the two. This is instead of just reusing the same weak password based on your cat’s name.

Something you are refers to biometrics such as face recognition, fingerprints, and voice recognition. Something you have refers to a user’s device, passkeys, and one-time password tokens (OTP) (Prasad, 2025).

This blog will be looking at one passwordless authentication specification particularly, the Web Authentication API, more commonly known as WebAuthn. WebAuthn was created by W3C and FIDO with the assistance of Google, Mozilla, Microsoft, Yubico and others (WebAuthn, n.d.). Browsers implement WebAuthn to authenticate users with biometrics and passkeys instead of a traditional password. (George, 2024)

# Technical Overview of WebAuthn and Passwordless Authentication

Passwordless authentication works by allowing users to authenticate themselves, e.g. log in by utilizing something they have or something they are, or even both. Which is used instead of the traditional methods of passwords, passphrases, and security questions (Prasad, 2025).

Now that we know how passwordless authentication works, let’s look at how WebAuthn works. WebAuthn allows an application to register and authenticate users by employing public key cryptography (also known as asymmetric cryptography) instead of traditional cryptography methods (WebAuthn, n.d.). To understand how WebAuthn works, we need to look at how public key cryptography works.

Public key cryptography works by generating two separate keys, a public and a private key, with WebAuthn this private key is stored on the user’s device. The public key gets stored on the WebAuthn server, but even if an attacker managed to retrieve the public key, it is useless without its private key, which being securely stored on the user’s device (Ungvarsky, 2024).

One way to understand public key cryptography is to think of it like a trapdoor, easy to fall though (create the private/public keypair) but impossible to go back up without a ladder (private key) to help you.

WebAuthn allows applications to work with the authenticators that are now built into devices, such as Windows Hello or Apple’s Touch ID. This means that a private-public keypair will be generated for that application instead of the user creating a password. The private key gets stored on the user’s device and the public key with an automatically generated credential ID gets stored on the application’s server.

When a user attempts to authenticate themselves, the server will go and get the public key to check against the private key provided by the user’s device, if they match, the user will be authenticated successfully (WebAuthn, n.d.).

### Key Features of WebAuthn (WebAuthn, n.d.):

•	Strong: The authentication of WebAuthn is backed by a Hardware Security Module, which can safely store private keys and perform the necessary cryptographic operations required by WebAuthn.

•	Scoped: A keypair is only useful for one specific origin, like browser cookies. A keypair which was registered for ‘example.com’ will not work at ‘evil-example.com’ which lessens the threat of phishing.

•	Attested: Authenticators such as Windows Hello can provide servers with certificates to help verify that the public key came from that authenticator, and not a fake authenticator.

# Applications

### Google, Apple, and Microsoft:
Google Chrome provides built in support for WebAuthn protocols. Recent versions of Chrome have also provided support for passkeys (Kitamura, 2022). Passkeys are a specific implementation of WebAuthn, created by Apple, Google, and Microsoft to simplify the user experience across different platforms (Paktiti, 2025). 
Microsoft has implemented the use of WebAuthn in Windows Hello, which allows for a quick log in experience by using biometric data. (Microsoft, 2024). Apple also utilises passkeys to simplify account registration for apps and website, making sure that the passkeys are usable across all Apple devices (Apple, 2024).

### GitHub and Discord: 

After looking though different services and apps, I discovered that GitHub allows users to register a passkey, so that the users can choose to use a passkey in future instead of a password to log in. 
Recently, Discord have made security keys, which are also built on WebAuthn available to Discord users. Now, they can use their devices authentication, such as Windows Hello, etc, to securely log in to Discord in the future. Discord has also promised to continue providing WebAuthn-based passwordless logins in the future (Toulas, 2023).

# Impact on Web Development and Society

The use of passwordless authentication, particularly WebAuthn, has the potential to significantly transform the user experience and the security side of web development.

One significant impact on society would be eliminating the need for users to remember multiple passwords, which would reduce the users frustration with services and save the users time (George, 2024).

WebAuthn allows users to authenticate themselves using their biometrics, which simplifies the process and makes it more user-friendly (Pullanieswaran, 2024). However, as always, challenges remain especially around device dependency. Since the private key required to gain access to their services is stored on the user’s device, they must have their device on hand to be able to authenticate themselves.

 This requirement poses an issue for users in the process of changing to a new device or lacking access to their normal device for whatever reason (George, 2024). The users wishing to change their device may encounter difficulties that didn’t previously exist, but as syncing technology advances, these difficulties should reduce.

From a web development perspective, WebAuthn is offering significant security improvements. The use of public-key cryptography reduces the risk of database breaches as only the public key is stored in the database, which is useless to attackers (WebAuthn, n.d.). This also offers increased protection against phishing attacks, as the users’ credentials are unique to each application. (Pullanieswaran, 2024). Besides this, WebAuthn would also help companies to meet regulatory compliance standards, enhancing both their security and legal obligations (Kondakrindi, 2024).

In summary, passwordless authentication in the form of WebAuthn won’t just enhance user experience, but also web security, by providing solutions for both users and developers while dealing with the historical challenges of traditional passwords.

# Critical Analysis

### Strengths:

The reason that WebAuthn should have widespread adoption is because of the many ways that it improves security, user experiences, and because it is usable in so many platforms.

One way that WebAuthn improves security is by using public-key cryptography, which significantly reduces the risk of a database breach, meaning that users data is safer than ever (WebAuthn, n.d.). Other important security improvements include WebAuthn’s resistance to phishing attacks, as the credentials used to authenticate users cannot be used at another site (Pullanieswaran, 2024). 

User experiences can also be improved by the implementation of WebAuthn, as users are able to be authenticated with a single action, such as fingerprint or facial recognition. This eliminates the hassle of creating and memorizing complex passwords for users and creates an effortless login (Pullanieswaran, 2024). Users are also able to use a single passkey across multiple devices, increasing the ease with which users can log in. 

There is also the bonus that most major browsers have included inbuilt support for and features of WebAuthn in recent versions (Brown, 2024). Which signals that major companies are starting to increase the focus on passwordless authentication being a main authentication method.

### Weaknesses:

Unfortunately, nothing is perfect, and that includes WebAuthn. Some of the weaknesses of WebAuthn include usability, compatibility, and account recovery.

The usability concerns are that it may be challenging for users accustomed to the traditional authentication to transition into using unknown passwordless systems. Also, users with older devices or operating systems may struggle to effectively use passwordless systems if the devices or operating systems don’t support WebAuthn (Kondakrindi, 2024).

Compatibility issues arise because WebAuthn is not backward compatible with the older systems that rely on the use of passwords. Which could be a limiting factor in its acceptance by certain users and organizations (Bisceglia, 2025)

The challenges of account recovery stem from the fact that the normal reset mechanisms were designed with traditional passwords in mind. So, those recovery systems may glitch if trying to recover a passwordless account. This means that a new recovery system should be set up for passwordless authentication, which if not handled carefully could potentially introduce new bugs and security issues (Kondakrindi, 2024).

### Ethical:

While WebAuthn and passwordless authentication offer great benefits to the future of authentication, the ethical concerns should always be considered before making any big decisions.

The use of WebAuthn as the main authentication method raises ethical concerns about privacy risks involved in biometric data. As biometric data, once compromised, cannot be changed like a password, there needs to be clear security measures in place to protect the user’s sensitive data. Having clear and transparent data collection policies is essential to ensure the users are giving their informed consent (Pullanieswaran, 2024).

Additionally, the dependency on biometrics may force the users who cannot or choose not to use biometrics into using them, which may alienate those users and limit their freedom of choice and accessibility. Companies should make sure to have alternative authentications in place to ensure continued inclusivity (George, 2024).

# Personal Reflections

The reason I chose to research passwordless authentication and WebAuthn for this blog is because I am studying both web development and cybersecurity, and this topic has proved to be a good blend of these two areas. The knowledge I have collected about WebAuthn could also prove useful for my potential career in web development or cybersecurity.

Over the course of my research, I was surprised by how many applications passwordless registration methods use the WebAuthn framework but also the fact that even though many applications are offering passkeys as an alternative for logging in, those applications are still initially registering users with traditional passwords first.

A challenging aspect of this research initially, was understanding how WebAuthn works. Once I understood it, I then found it difficult finding sources to help me make sure my research was being based on accurate facts. I will also admit that trying to make sure my written research made sense to readers was something that challenged me but overall, this experience has been educational.

# Research Log

### Key sources and how they shaped my understanding:

One of the key sources I consulted was an article about the difference between passkeys and WebAuthn as it explained some of the features in simpler terms than others. Also, it helped me to realize that while there is a difference between passkeys and WebAuthn, the difference is not what I assumed it was in the beginning of my research process (Bisceglia, 2025).

 The main journal article that I referred to while writing my research, was (George, 2024). This journal article helped me to understand the ways in which passwordless authentication will change the way users log in to applications and approach security. This article also helped me to write my research as it had similar themes throughout which I used to support my ideas. 

### Challenges I faced:

Challenges I faced over this research process include:

•	Understanding how WebAuthn and passwordless authentication worked and being able to explain that to others without making it too technical for non-IT people to understand.

•	Finding research sources, I found getting the search terms right to be able to find the information I was looking for was quite tricky, especially at the beginning of the research process.

•	Making sure the sources I found were reliable, as many of the articles I found ended with ads about their business, typically a business operating within the password industry. So, I made sure to gather information from multiple different articles to be sure the information wasn’t biased. 

### How my perspective on WebAuthn evolved over time:

Originally, I thought that WebAuthn and passkeys were two entirely different things used together to authenticate a user. After further research, I realized that WebAuthn is more like building blocks, like WebAuthn provides the framework and support from which applications can create a user interface.

Passkeys are a specific implementation of those WebAuthn building blocks. In web development terms, WebAuthn would be the back end, and passkeys would be the user facing front end. 





# References


Apple. (2024, September 26). About the security of passkeys. 
    Retrieved from Apple Support: https://support.apple.com/en-nz/102195#:~:text=Credential%20security,as%20many%20devices%20as%20possible.

Bisceglia, N. (2025, January 24). Passkey vs. WebAuthn: What's the Difference? 
    Retrieved from Team Password: https://teampassword.com/blog/passkey-vs-webauthn#benefits-of-webauthn

Brown, A. (2024, Sept 20). WebAuthn vs FIDO2: Understanding the Differences. Retrieved from Descope: https://www.descope.com/blog/post/webauthn-vs-fido2#the-      
   biggest-benefits-of-webauthn-and-fido2

Editor. (2017, May 04). A short history of the computer password. Retrieved from WeLiveSecurity: https://www.welivesecurity.com/2017/05/04/short-history-computer- 
   password/

George, D. A. (2024). The Dawn of Passkeys: Evaluating a Passwordless Future. Partners Universal Innovative Research Publication, 202-220.

Kitamura, E. (2022, Nov 30). Passwordless sign-in on forms with WebAuthn passkey autofill. Retrieved from Chrome for Developers: 
   https://developer.chrome.com/docs/identity/webauthn-conditional-ui#:~:text=a%20condtional%20UI-,How%20it%20works,added%20security%20benefit%20of%20passkeys.

Kondakrindi, R. (2024). FIDO2: A New Era in Secure Web Authentication. International Journal of Computer Engineering and Technology, 841-858.

McMillan, R. (2012, Jan 27). The World's First Computer Password? It Was Useless Too. Retrieved from Wired: https://www.wired.com/2012/01/computer-password/

Microsoft. (2024, November 22). WebAuthn APIs for passwordless authentication on Windows. Retrieved from Microsoft Learn: https://learn.microsoft.com/en- 
    us/windows/security/identity-protection/hello-for-business/webauthn-apis

Paktiti, M. (2025, March 24). An introduction to WebAuthn. Retrieved from WorkOS: https://workos.com/blog/intro-to- 
     webauthn#:~:text=This%20means%20users%20no%20longer,login%20methods%20across%20the%20web.

Prasad, A. (2025). Breaking Barriers: Passwordless Authentication as the Future of Security. International Journal of Computer Applications, 29-35.

Pullanieswaran, P. (2024, Jan 3). WebAuthn - A Short Introduction. Retrieved from Auth0: https://auth0.com/blog/webauthn-a-short-introduction/#Key-Features-of- 
    WebAuthn

Toulas, B. (2023, December 14). Discord adds Security Key support for all users to enhance security. Retrieved from Bleeping Computer: 
     https://www.bleepingcomputer.com/news/security/discord-adds-security-key-support-for-all-users-to-enhance-security/

Ungvarsky, J. (2024). Public-Key Cryptography. Retrieved from EBSCO: https://www.ebsco.com/research-starters/computer-science/public-key-cryptography
     WebAuthn. (n.d.). Retrieved from WebAuthn Guide: https://webauthn.guide/






