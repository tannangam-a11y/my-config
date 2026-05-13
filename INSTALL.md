# IDH Browser Extension - Installation Guide

## 📋 Requirements
- Chrome, Edge, or any Chromium-based browser
- IDH Desktop App installed and running

## 🚀 Installation Steps

### 1. Load the Extension in Chrome/Edge

1. Open Chrome/Edge and go to `chrome://extensions` (or `edge://extensions`)
2. Enable **Developer mode** (toggle in top-right)
3. Click **Load unpacked**
4. Select the `extension` folder: `D:\internet-download-helper\extension`
5. The IDH extension should now appear in your extensions list

### 2. Install Native Messaging Host (Optional - for direct app communication)

The extension can work without this step by using the `idh://` protocol fallback.
For full native messaging support:

1. Open PowerShell as Administrator
2. Run:
```powershell
cd D:\internet-download-helper
node scripts\install-native-host.cjs
```

### 3. Using the Extension

#### Right-click Context Menu:
- **Download with IDH** - on any link
- **Download Video with IDH** - on video elements
- **Download Audio with IDH** - on audio elements
- **Download Image with IDH** - on images
- **Download All Media with IDH** - on any page
- **Open IDH App** - launches the desktop app

#### Floating Button:
When a video is detected on a page, a blue "⬇ IDH" button appears
in the bottom-right corner. Click it to download the video.

#### Extension Popup:
Click the IDH icon in the toolbar to see all detected media on the current page.

## 🔧 Troubleshooting

### Extension not appearing?
- Make sure Developer mode is enabled
- Check that the manifest.json is valid
- Try reloading the extension

### "Download with IDH" not working?
- Make sure the IDH desktop app is running
- Check that the Vite dev server is running on port 5173
- Try using the popup to scan the page manually

### Native messaging not connecting?
- Run the install script as Administrator
- Restart the browser after installation
- Check Windows Registry for the key

## 📁 Extension Files

```
extension/
├── manifest.json          # Extension manifest (v3)
├── background.js          # Service worker
├── content.js             # Content script (video detection)
├── popup.html             # Popup UI
├── popup.js               # Popup logic
├── icons/
│   ├── icon16.png         # 16x16 icon
│   ├── icon48.png         # 48x48 icon
│   └── icon128.png        # 128x128 icon
└── INSTALL.md             # This file
```
