# Google Voice Desktop (Arch Linux Port)

An optimized, secure desktop app wrapper for the Google Voice website, tailored specifically for Arch Linux and its derivatives (such as Garuda). This application runs natively using the system-installed Electron framework.

## Key Enhancements in This Fork

* **Strict Sandboxing Security:** Explicitly locks down window properties by disabling context isolation leaks and Node integration, keeping the app strictly isolated from your system files.
* **Modern Context Menu:** Restores clean right-click navigation behavior while permanently stripping out invasive developer tools like "Inspect Element."
* **Automated Package Lifecycle:** Provides a clean `PKGBUILD` mapping framework that automates installation natively via the system package manager.
* **Unified Workspace Structure:** Purged of broken external layout paths and optimized to run completely flat.

---

## Installation via Pacman (Recommended)

To compile from source and install the package cleanly onto your Garuda or Arch system using your local package builder toolkit, run the following sequence in your terminal:

```fish
# 1. Clone the repository fork
git clone https://github.com
cd google-voice-electron-archlinux

# 2. Securely pull down local runtime dependencies 
npm install --omit=dev --ignore-scripts

# 3. Compile the system package archive and install it
makepkg -sifC
```

---

## How to Execute

Once installed, you can launch the application instantly through your desktop application menu by looking for **Voice Desktop**, or by executing this binary launcher command directly from your terminal:

```fish
google-voice-desktop
```

---

## Configuration & Customization

You can change display settings, apply custom visual themes (such as Dracula, Solar, or Minty), and manage interface styles cleanly inside the dedicated **Settings** window. 

* **Accessing Settings:** Right-click the application icon inside your Garuda system tray taskbar panel and choose **Settings**.
* **System Tray Control:** Closing the application window with the `X` button will safely minimize it directly to your system tray taskbar panel to preserve live incoming message notifications. To close the app completely, right-click the system tray icon and select **Quit**.

