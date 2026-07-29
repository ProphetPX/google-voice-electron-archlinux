# Google Voice Desktop (Arch Linux Port)

An optimized, secure desktop app wrapper for the Google Voice website, tailored for Arch Linux and its derivatives (such as Garuda). This application runs natively using your system-installed Electron framework out of a local user directory to ensure perfect path resolution.

## Key Enhancements in This Fork

* **Strict Sandboxing Security:** Explicitly locks down window properties by disabling context isolation leaks and Node integration, keeping the app strictly isolated from your system files.
* **Modern Context Menu:** Restores clean right-click navigation behavior while permanently stripping out invasive developer tools like "Inspect Element."
* **Reliable Preferences Store:** Eliminates broken background IPC hooks, allowing sliders, themes, and configuration checkboxes to save and apply layout changes instantly.

---

## Installation & Setup

To install the application cleanly onto your machine, run the following sequence in your terminal:

```fish
# 1. Clone the repository fork
git clone https://github.com
cd google-voice-electron-archlinux

# 2. Download the required production runtime dependencies
npm install --omit=dev --ignore-scripts

# 3. Create a personal terminal command shortcut
mkdir -p ~/.local/bin
echo "#!/bin/sh\ncd \$(pwd)\nexec electron ." > ~/.local/bin/google-voice-desktop
chmod +x ~/.local/bin/google-voice-desktop

# 4. Generate the application launcher menu icon profile
echo "[Desktop Entry]
Version=1.0
Type=Application
Name=Voice Desktop
Comment=An electron shell wrapper for the google voice app
Exec=/home/\$USER/.local/bin/google-voice-desktop
Icon=\$(pwd)/images/icon.png
Terminal=false
StartupWMClass=voice-desktop-app
Categories=Office;Network;InstantMessaging;
MimeType=text/html;" > ~/.local/share/applications/google-voice-desktop.desktop
```

---

## How to Execute

Once the setup commands are completed, you can close your terminal. You can launch the application instantly through your system start menu by looking for **Voice Desktop**, or by typing this command from any location in your terminal:

```fish
google-voice-desktop
```

---

## Configuration & Customization

You can change display settings, apply custom visual themes (such as Dracula, Solar, or Minty), and manage interface styles cleanly inside the dedicated **Settings** window. 

* **Accessing Settings:** Right-click the application icon inside your system tray taskbar panel and choose **Settings**.
* **System Tray Control:** Closing the application window with the `X` button will safely minimize it directly to your system tray taskbar panel to preserve live incoming message notifications. To close the app completely, right-click the system tray icon and select **Quit**.

