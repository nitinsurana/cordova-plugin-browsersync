#Cordova Browser-Sync Plugin

Integarting [BrowserSync](http://browsersync.io) into your Cordova workflow. 

- Watch files in the `www` folder and automatically reload HTML and CSS in all connected devices
- Use BtowserSync's dashboard to control devices and reload them.
- Synchronize scrolls, clicks and form inputs across multiple devices.
- Supports real devices and emulators for iOS and Android platforms

## Demo
Here is a [blog post](http://blog.nparashuram.com/2015/08/using-browser-sync-with-cordova.html) explaning the plugin and its internals.

[![Cordova Browser-Sync Plugin demo video](http://img.youtube.com/vi/XTXYhYS2m0c/0.jpg)](http://www.youtube.com/watch?v=XTXYhYS2m0c)

## Usage

There are three ways to use the code in this plugin. Ensure that you have added the `ws:` and `unsafe-inline` CSP policies to your `default-src` section of the CSP meta tag (`<meta content=...>`) in index.html file.

### As a Cordova Plugin (Easiest)
This simplest way to integrate this in your Cordova workflow is to add it as a plugin

```
cordova plugin add https://github.com/axemclion/cordova-plugin-browsersync.git
```

and then run run the cordova with `cordova run`

### As a Cordova Project Hook
Clone this repo and run `npm run createHook` to get a `after_prepare.js`. Add this file as an `after_prepare` [hook](http://cordova.apache.org/docs/en/edge/guide_appdev_hooks_index.md.html) to your config.xml. 
For example

```
<hook type="after_prepare" src="scripts/after_prepare.js" />
```

### Integrate into your workflow
You can also `require('cordova-plugin-browsersync)` in your node module and use the `changeHost` function and `browserSyncServer` directly in your existing workflow. 
