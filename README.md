# chrome-extension-boilerplate

Starting point for writing chrome extension

## How to load the extension to Chrome

1. Open Chrome and navigate to `chrome://extensions`
2. Enable the Developer mode by toggling the switch in the top right corner
3. Click on the `Load unpacked` button and select this project's directory.
4. The extension should now be loaded and visible in the list of extensions

## Manifest.json

The `manifest.json` file is the manifest of your Chrome extension. It contains metadata about the extension and describes its permissions, actions, and other details.

Here's a brief description of each key in the `manifest.json` file:

- `manifest_version`: Specifies the version of the manifest format. For most extensions, this should be set to `3`.
- `name`: The name of the extension.
- `version`: The version of the extension.
- `description`: A brief description of the extension.
- `icons`: The icons for the extension. The specified sizes are the minimum recommended sizes.
- `permissions`: The permissions required by the extension. In this case, the extension requires the `activeTab` permission.
- `action`: Describes the action of the extension. In this case, the extension has a popup that opens when the user clicks on the extension icon.

## Developing Simple Opened Page Manipulation

To develop a simple opened page manipulation using the extension, you can use the `content_scripts` field in the `manifest.json` file to inject a script into the webpage. This script can then manipulate the page's content.

Here's an example of how to inject a script into the webpage:

```json
"content_scripts": [
  {
    "matches": ["<all_urls>"],
    "js": ["contentScript.js"]
  }
]
```

In the `contentScript.js` file, you can use JavaScript to manipulate the page's content. For example:

```javascript
// contentScript.js
document.body.style.backgroundColor = "yellow";
```

This script changes the background color of the webpage to yellow.

## Tips and Tricks of Common Functions/Methods

Here are some tips and tricks for common functions/methods used in extension development:

- `chrome.tabs.query()`: Use this method to get a list of tabs that match certain criteria, such as the current tab or all tabs with a certain URL.
- `chrome.tabs.executeScript()`: Use this method to inject a script into a tab and execute it.
- `chrome.runtime.sendMessage()`: Use this method to send a message from a content script to a background script.
- `chrome.storage.local.get()`: Use this method to retrieve data from the extension's local storage.

Some common patterns to keep in mind:

- Use `chrome.tabs.query()` to get the current tab and then use `chrome.tabs.executeScript()` to inject a script into it.
- Use `chrome.runtime.sendMessage()` to communicate between content scripts and background scripts.
- Use `chrome.storage.local.get()` to retrieve data from local storage and `chrome.storage.local.set()` to set data.

## Recommended Extension Development Tools

Here are some recommended tools for extension development:

- [**Chrome Extension CLI**](https://github.com/dutiyesh/chrome-extension-cli): A command-line tool for creating, building, and packaging Chrome extensions.
- [**Chrome Extension Developer Tools**](https://developer.chrome.com/docs/extensions/mv3/getstarted/): A set of tools built into Chrome for debugging and testing extensions.
- [**WebExtensions Polyfill**](https://github.com/mozilla/webextension-polyfill): A library that provides a set of polyfills for WebExtensions APIs, making it easier to develop extensions that work across multiple browsers.
- [**Extension Boilerplate**](https://github.com/Jonghakseo/chrome-extension-boilerplate-react-vite): This boilerplate helps you create Chrome/Firefox extensions using React and Typescript. It improves the build speed and development experience by using Vite and Turborepo.
