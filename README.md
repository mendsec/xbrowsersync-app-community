# **xBrowserSync - Community Edition (Active Fork)**

**This is a community-maintained fork of the original xBrowserSync project. The main project has been discontinued, and this version aims to fix compatibility issues and add improvements, ensuring the extension continues to function on modern browsers.**

---

### What problem does this project solve?

The original xBrowserSync stopped working correctly in browsers like Google Chrome due to the transition to **Manifest V3**, which introduced new security policies. This fork resolves that incompatibility by refactoring the code to comply with the new rules.

With this version, you can continue to securely and encrypted sync your **Browse history, bookmarks, passwords, and open tabs** across different browsers, including **Chrome, Firefox, and Edge**.

---

### How to use the extension

1.  **Download the source code** from this repository.
2.  **Open your browser** (Chrome, Firefox, etc.).
3.  **Go to the extensions page** (`chrome://extensions` or `about:addons`).
4.  **Enable "Developer mode"**.
5.  **Click "Load unpacked"** and select the source code folder you downloaded.
6.  Follow the instructions to set up the extension with your sync ID and password.

---

### How to contribute

Your help is essential for the success of this project. If you're a developer, here are a few ways you can contribute:

1.  **Report bugs:** Found an issue? Open a GitHub issue to let us know.
2.  **Submit code:** If you've implemented an improvement or fixed a bug, fork this repository and submit a **Pull Request**.
3.  **Suggest new features:** Share your ideas for improving the extension.

---

### Original README.md Content (Archived)

# xBrowserSync

## Desktop browser web extensions and Android app

[![Latest release](https://img.shields.io/github/release/xbrowsersync/app.svg)](https://github.com/xbrowsersync/app/blob/master/LICENSE.md) [![GitHub license](https://img.shields.io/github/license/xbrowsersync/app.svg)](https://github.com/xbrowsersync/app/releases/latest) [![build](https://github.com/xbrowsersync/app/actions/workflows/build.yml/badge.svg)](https://github.com/xbrowsersync/app/actions/workflows/build.yml) [![Coverage Status](https://coveralls.io/repos/github/xbrowsersync/app/badge.svg?branch=master)](https://coveralls.io/github/xbrowsersync/app?branch=master) [![Crowdin](https://badges.crowdin.net/xbrowsersync-app/localized.svg)](https://crowdin.com/project/xbrowsersync-app) ![Dependencies](https://img.shields.io/depfu/xbrowsersync/app) [![Liberapay patrons](http://img.shields.io/liberapay/patrons/xbrowsersync.svg?logo=liberapay)](https://liberapay.com/xbrowsersync/donate)

[![GitHub forks](https://img.shields.io/github/forks/xbrowsersync/app.svg?style=social&label=Fork)](https://github.com/xbrowsersync/app/fork)
[![GitHub stars](https://img.shields.io/github/stars/xbrowsersync/app.svg?style=social&label=Star)](https://github.com/xbrowsersync/app)

xBrowserSync is a free tool for syncing browser data between different browsers and devices, built for privacy and anonymity. For full details, see [www.xbrowsersync.org](https://www.xbrowsersync.org/).

This repository contains the source code for the browser web extensions and Android mobile app used for syncing to an xBrowserSync service. You can get the official releases of the xBrowserSync clients from the various app stores, but if you’d like to build from source you can do so here.

## Prerequisites

- NPM. It’s bundled with [Node.js](https://nodejs.org/) so [download and install it](https://nodejs.org/en/download/) for your platform.

## Installation

CD into the source directory and install the package and dependencies using NPM:

    $ npm install

### Android

You must follow the Cordova Android [installation guide](https://cordova.apache.org/docs/en/latest/guide/platforms/android/index.html) in order to develop xBrowserSync for Android. Once that's done, run the following commands in the xBrowserSync source directory:

    $ npm install -g cordova@11.0.0
    $ cd ./res/android
    $ cordova prepare

## Building

Run a debug build for the given platform:

    $ npm run build:[platform]

or

    $ npm run watch:[platform]

Replace [platform] with the name of the platform to build. The app code will be output to the 'build/[platform]' folder. Available platforms:

- android
- chromium
- firefox

### Debugging in Chrome

Once you have built xBrowserSync for Chromium, browse to `chrome://extensions`, enable Developer mode, click "Load unpacked" and browse to `build/chromium` within the xBrowserSync source directory.

Note: We recommend creating a new Chrome profile for testing so you do not affect your actual profile data.

### Debugging in Firefox

Use the [web-ext](https://developer.mozilla.org/en-US/docs/Mozilla/Add-ons/WebExtensions/Getting_started_with_web-ext) tool for testing xBrowserSync in Firefox. Once that is installed and you have built xBrowserSync for Firefox, CD into `build/firefox` within the xBrowserSync source directory and run the following command:

    $ web-ext run --verbose

Firefox will open using a temporary profile and the xBrowserSync extension will be installed from the built source.

### Debugging in Android

After building, in order to run the app you'll need to execute the relevant [cordova cli](https://cordova.apache.org/docs/en/latest/reference/cordova-cli/index.html) commands. For example, to run the app on a connected device, CD into `build/android` within the xBrowserSync source directory and run the following commands:

    $ cordova build android
    $ cordova run android --device

Make sure to run the `cordova build` command at least once after running a fresh build so that required gradle files are copied (`cordova run` alone does not copy these files).

## Packaging

Run a release build and then package for the given platform:

    $ npm run package:[platform]

Replace [platform] with the name of the platform to build. The package will be output to the 'dist' folder.

## Issues

If you’ve found a bug or wish to request a new feature, please submit it [here](https://github.com/xbrowsersync/app/issues/).

## Translation

If you would like to help with translating xBrowserSync into another language, please read the [Translations](https://github.com/xbrowsersync/app/wiki/Translations) wiki page to get started.
