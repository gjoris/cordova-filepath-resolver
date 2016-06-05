# cordova-filepath-resolver

This plugin allows you to resolve the native filesystem path for Android content 
URIs and is based on code in the [aFileChooser](https://github.com/iPaulPro/aFileChooser/blob/master/aFileChooser/src/com/ipaulpro/afilechooser/utils/FileUtils.java) library.

Original inspiration [from StackOverflow](http://stackoverflow.com/questions/20067508/get-real-path-from-uri-android-kitkat-new-storage-access-framework).

Original version by [hiddentao](https://github.com/hiddentao/cordova-plugin-filepath). 

This version requires at least Cordova 6.0.0, and solves the permission issues in Android 6.

## Installation

```bash
$ cordova plugin add cordova-filepath-resolver
```

* Ionic

For Ionic specifically, you can also use:

```bash
$ ionic plugin add cordova-filepath-resolver
```

## Supported Platforms

* Android

## Usage

Once installed the plugin defines the `window.FilePath` object. To resolve a 
file path:

```js
window.FilePath.resolveNativePath('content://...', successCallback, errorCallback);
```

##### AngularJS

When using this with AngularJS (for instance, in Ionic), you can (also) retrieve a reference to the FilePath function via the $window object:

```js
$window['FilePath'].resolveNativePath('content://...', successCallback, errorCallback);
```

##### successCallback
Returns the ``file://`` file path.

##### errorCallback
Returns the following object:
```js
{ code: <integer>, message: <string> }
```
Possible error codes are:
* ``-1`` - describes an invalid action
* ``0`` - ``file://`` path could not be resolved
* ``1`` - the native path links to a cloud file (e.g: from Google Drive app)

## LICENSE

Apache (see LICENSE.md)


