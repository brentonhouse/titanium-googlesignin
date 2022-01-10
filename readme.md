[//]: # (header-start)

<a href="https://brenton.house/saying-goodbye-to-axway-amplify-titanium-31a44f3671de">
<h1 align="center">
	Axway Amplify End-of-Life Announcement
</h1>
<h2 align="center">
	👇 &nbsp; See notes below  &nbsp; 👇
</h2>	
</a>

<a href="https://brenton.house/saying-goodbye-to-axway-amplify-titanium-31a44f3671de">
	<p align="center">
		<img src="https://cdn.secure-api.org/images/RIP-Axway-Amplify-Titanium.png" alt="RIP Axway Amplify Titanium (2010 - 2022)" width="80%" />
	</p>
</a>
<a href="https://brenton.house/saying-goodbye-to-axway-amplify-titanium-31a44f3671de">
	<p align="center">
		🪦 &nbsp; RIP Axway Amplify Titanium (2010 - 2022)
	</p>
</a>
<a href="https://brenton.house/saying-goodbye-to-axway-amplify-titanium-31a44f3671de">
	<p align="center">
		🪦 &nbsp; RIP Axway Amplify Cloud Services (2012 - 2022)
	</p>
</a>
<hr>
<a href="https://brenton.house/saying-goodbye-to-axway-amplify-titanium-31a44f3671de">
	<h4 align="center">
🛑 &nbsp;&nbsp; All products affected by the announcements will not be supported by Axway effective their EOL dates in 2022.
</h4>

<h4 align="center">
Some Open-Source versions of Axway products will live on after End-of-Life (EOL) Axway Amplify product announcements.  However, some products are closed-source and will NOT continue after the shut down in 2022.  
	</h4>
</a>
<p>&nbsp;</p>

> 👉 &nbsp;&nbsp; Stay tuned for more info as plans are being made to save the Titanium project and move it under the control of a independent group of developers.

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