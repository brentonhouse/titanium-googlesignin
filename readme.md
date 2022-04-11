[//]: # (header-start)

<h1 align="center">
	<a href="https://blog.axway.com/mobile-apps/changes-to-application-development-services">
		Preparing for end of Axway
	</a>	
</h1>
<h2 align="center">
	👇 &nbsp; support for Amplify Cloud and Mobile   &nbsp; 👇
</h2>	

<a href="https://brenton.house/saying-goodbye-to-axway-amplify-titanium-31a44f3671de">
	<p align="center">
		<img src="https://cdn.secure-api.org/images/RIP-Axway-Amplify-Titanium.png" alt="RIP Axway Amplify Titanium (2010 - 2022)" width="80%" />
	</p>
</a>	
<p align="center">
	<a href="https://blog.axway.com/mobile-apps/changes-to-application-development-services">
			🪦 &nbsp; RIP Axway Amplify Titanium (2010 - 2022)
	</a>
</p>
<p align="center">
	<a href="https://blog.axway.com/mobile-apps/prepare-your-apps-for-appcelerator-end-of-support">
			🪦 &nbsp; RIP Axway Amplify Cloud Services (2012 - 2022)
	</a>
</p>
<p align="center">
	<a href="https://blog.axway.com/mobile-apps/prepare-your-apps-for-appcelerator-end-of-support">
			🪦 &nbsp; RIP Axway Amplify Crash Analytics (2015 - 2022)
	</a>
</p>

<hr>
<h4 align="center">
🛑 &nbsp;&nbsp; <a href="https://blog.axway.com/mobile-apps/prepare-your-apps-for-appcelerator-end-of-support">Axway support for Amplify products has ended</a> for most products related to mobile and cloud. 
</h4>

<h4 align="center">
A few of the open-source versions of Axway Amplify products will live on after <a href="">Axway Amplify End-of-Life</a> (EOL) announcements.  However, all closed-source projects and most open-source projects are now dead.  
	</h4>

<p>&nbsp;</p>

> 👉 &nbsp;&nbsp; A group of Axway employees, ex-Axway employees, and some developers from Titanium community have created a legal org and now officially decide all matters related to future of these products.  

<p>&nbsp;</p>
<hr>


## API FAQ:

* [API Best Practices](https://brenton.house)
* [What is API Security?](https://brenton.house/what-is-api-security-5ca8117d4911)
* [OWASP Top 10 List for API Security](https://www.youtube.com/watch?v=GLVHDj0Cpg4)
* [What is API Security?](https://brenton.house/what-is-api-security-5ca8117d4911)
* [Top API Trends for 2022](https://brenton.house/top-10-api-integration-trends-for-2022-49b05f2ef299)
* [What is a Frankenstein API?](https://brenton.house/what-is-a-frankenstein-api-4d6e59fca6)
* [What is a Zombie API?](https://brenton.house/what-is-a-zombie-api-6e5427c39b6a)
* [API Developer Experience](https://brenton.house/keys-to-winning-with-an-awesome-api-developer-experience-62dd2fa668f4)
* [API Cybersecurity 101](https://brenton.house/what-is-api-security-5ca8117d4911)
* [YouTube API Videos](https://youtube.com/brentonhouse)
* [YouTube API Shorts Videos](https://youtube.com/apishorts)

&nbsp;

[![Click to watch on Youtube](https://img.youtube.com/vi/GLVHDj0Cpg4/0.jpg)](https://www.youtube.com/watch?v=GLVHDj0Cpg4&list=PLsy9MwYlG1pew6sktCAIFD5tbrXy9HUQ7  "Click to watch on YouTube")


> &nbsp; [↑ Watch video on YouTube ↑](https://www.youtube.com/watch?v=GLVHDj0Cpg4&list=PLsy9MwYlG1pew6sktCAIFD5tbrXy9HUQ7)

&nbsp;



<p>&nbsp;</p>
<hr>

<p>&nbsp;</p>
<p>&nbsp;</p>

[//]: # (header-end)
# @titanium/googlesignin

[![@titanium/googlesignin](https://img.shields.io/npm/v/@titanium/googlesignin.png)](https://www.npmjs.com/package/@titanium/googlesignin)
[![Dependabot Status](https://api.dependabot.com/badges/status?host=github&repo=brentonhouse/titanium-googlesignin)](https://dependabot.com)

<br/>

* [📝 Description](#-description)
* [🚀 Getting Started](#-getting-started)
	* [Install `@titanium/googlesignin` in root of project](#install-titaniumgooglesignin-in-root-of-project)
	* [Add required properties to iOS plist in `tiapp.xml`](#add-required-properties-to-ios-plist-in-tiappxml)
* [✨Features](#features)
* [Requirements](#requirements)
* [Example](#example)
* [APIs](#apis)
		* [Methods](#methods)
		* [Properties](#properties)
		* [Events](#events)
* [License](#license)
* [Authors](#authors)
* [📚Learn More](#learn-more)
* [📣 Feedback](#-feedback)
* [©️ Legal](#️-legal)


## 📝 Description

Native modules that allows you to use the Google Sign-in SDK with Axway Titanium native mobile apps.   
     
> This is a repackaging of the compiled iOS module for [ti.googlesignin](https://github.com/hansemannn/titanium-google-signin) to allow for installation via npm.

## 🚀 Getting Started

### Install `@titanium/googlesignin` in root of project

```bash
npm install @titanium/googlesignin
```

### Add required properties to iOS plist in `tiapp.xml`


```xml
<ti:app xmlns:ti="http://ti.appcelerator.org">
	<ios>
		<plist>
			<key>CFBundleURLTypes</key>
			<array>
				<dict>
					<key>CFBundleTypeRole</key>
					<string>Editor</string>
					<key>CFBundleURLName</key>
					<string>google</string>
					<key>CFBundleURLSchemes</key>
					<array>
						<!-- Example: com.googleusercontent.apps.123456789-xxxxxxxx -->
						<string>YOUR_REVERSE_CLIENT_ID</string>
					</array>
				</dict>
			</array>
		</plist>
	</ios>
</ti:app>
```


## ✨Features

* [x] Includes Titanium native iOS module: `ti.googlesignin 3.0.0`

## Requirements

- 

## Example

This module was designed to follow a similar scheme like Ti.Facebook and Ti.GoogleSignIn.

```js
const google = require('ti.googlesignin');

google.initialize({
	clientID: 'xxxxxxxx-123456789.apps.googleusercontent.com',

    // Optional properties:
    serverClientID: '<server-client-id>',
    scopes: ['https://www.googleapis.com/auth/plus.login'], // See https://developers.google.com/identity/protocols/googlescopes for more
    language: 'de', // Or 'de-DE', 'en-US', etc.
    loginHint: 'Titanium rocks!',
    hostedDomain: 'https://my-hosted-domain.com',
    shouldFetchBasicProfile: false, // Default: true
	openIDRealm: 'my-openID-realm',
});

google.addEventListener('login', e => {
	if (!e.success) {
		Ti.API.error(`Cannot login to Google: ${e.error}`);
		return;
	}

	const result = e.user;
	console.info('Logged in to Google!');
	// Do something with user result
});

google.addEventListener('logout', e => {
	console.info('Google Logged out / disconnected!');
});

// sign in
google.signIn();

// sign out
if (google.hasAuthInKeychain()) {
	google.disconnect();
}

```

## APIs

#### Methods

- [x] `signIn()`
- [x] `signInSilently()`
- [x] `signOut()`
- [x] `disconnect()`
- [x] `hasAuthInKeychain` -> Boolean
- [x] `currentUserImageURLWithSize(size)` -> String

#### Properties

* [x] `language` (String, `get|set`)
* [x] `currentUser` (Dictionary, `get`)
    * `id` (String) 
    * `scopes` (Array<String>) 
    * `serverAuthCode` (String) 
    * `hostedDomain` (String) 
    * `profile` (Dictionary)
        * `name` (String)
        * `givenName` (String)
        * `familyName` (String)
        * `email` (String)
        * `hasImage` (Boolean)
    * `authentication` (Dictionary)
        * `clientID` (String)
        * `accessToken` (String)
        * `accessTokenExpirationDate` (Date)
        * `refreshToken` (String)
        * `idToken` (String)
        * `idTokenExpirationDate` (Date)

#### Events

- [x] `login`
- [x] `logout`
- [x] `cancel`
- [x] `load`
- [x] `open`
- [x] `close`

The `login`- and `logout` events include a `success` flag as well as a `user` key that includes the following user-infos:
```
id, scopes, serverAuthCode, hostedDomain, profile, authentication
```

## License

Apache 2.0

## Authors

Hans Knöchel



## 📚Learn More

⭐  [ti.googlesignin GitHub Repo](https://github.com/hansemannn/titanium-google-signin) - Repo for original ti.googlesignin module   


## 📣 Feedback

Have an idea or a comment?  [Join in the conversation here](https://github.com/brentonhouse/titanium-googlesignin/issues)! 

## ©️ Legal

Modules are licensed under Apache 2.0 from https://github.com/appcelerator-modules/titanium-googlesignin

Alloy is developed by Appcelerator and the community and is Copyright © 2012-Present by Appcelerator, Inc. All Rights Reserved.

Alloy is made available under the Apache Public License, version 2. See their license file for more information.

Appcelerator is a registered trademark of Appcelerator, Inc. Titanium is a registered trademark of Appcelerator, Inc. Please see the LEGAL information about using trademarks, privacy policy, terms of usage and other legal information at http://www.appcelerator.com/legal.