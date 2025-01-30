# Reddit to Quran Extension

A browser extension that redirects Reddit to random verses from the Quran. Each time you try to visit Reddit, you'll be redirected to a different verse on Quran.com.

## Installation

1. Clone or download this repository

2. Create a new directory and add these two files:

   - `manifest.json`
   - `background.js` (includes the Surahs data and redirect logic)

3. Load the extension in your browser:
   - Open Brave browser
   - Go to `brave://extensions/`
   - Enable "Developer mode" in the top right
   - Click "Load unpacked"
   - Select the directory containing your extension files

## How it Works

When you try to visit Reddit, the extension:
1. Generates a random verse selection from the Quran
2. Creates a redirect URL to that specific verse on Quran.com
3. Automatically redirects your browser to that verse

Each visit to Reddit will take you to a different random verse.

## Troubleshooting

If the extension isn't working:
1. Make sure it's enabled in `brave://extensions/`
2. Clear your browser cache
3. Make sure Reddit isn't open in any other tabs
4. Disable other extensions that might interfere with redirects

To see debug logs:
1. Go to `brave://extensions/`
2. Find this extension
3. Click "service worker" to open DevTools
4. Check the Console tab for logs

## Files

### manifest.json
```json
{
  "manifest_version": 3,
  "name": "Reddit to Quran Redirector",
  "version": "1.0",
  "description": "Redirects reddit.com to random Quran verses",
  "permissions": [
    "declarativeNetRequest",
    "declarativeNetRequestFeedback",
    "webNavigation"
  ],
  "host_permissions": [
    "*://*.reddit.com/*"
  ],
  "background": {
    "service_worker": "background.js"
  }
}
```

### background.js
Contains:
- Full Surahs data array
- Random verse selection logic
- Redirect rule management
- Navigation event handling

## Modifying the Extension

To add more websites to redirect from:
1. Add the domain to the `host_permissions` array in `manifest.json`
2. Modify the URL matching condition in the redirect rule in `background.js`

## Uninstalling

To remove the extension:
1. Go to `brave://extensions/`
2. Find the extension
3. Click "Remove"

Or click the "Remove" button in the extension card.