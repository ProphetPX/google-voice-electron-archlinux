# Maintainer: ProphetPX <prophetpx@gmail.com>
pkgname=google-voice-electron-archlinux
pkgver=1.3.1
pkgrel=3
pkgdesc="An electron shell wrapper for the google voice app tailored for Arch Linux"
arch=("any")
url="https://github.com/ProphetPX/google-voice-electron-archlinux"
license=("ISC")
depends=("electron" "nodejs" "npm")
source=("package.json")
sha256sums=("SKIP")

package() {
    # 1. Setup secure internal application path structures
    install -d "$pkgdir/usr/lib/$pkgname"

    # 2. Extract configuration metadata, local scripts, assets, and backend modules
    cp "$srcdir/package.json" "$pkgdir/usr/lib/$pkgname/"
    cp -r "$startdir/src" "$pkgdir/usr/lib/$pkgname/"
    cp -r "$startdir/node_modules" "$pkgdir/usr/lib/$pkgname/"
    cp -r "$startdir/images" "$pkgdir/usr/lib/$pkgname/"

    # 3. Mount the desktop system application launcher profile safely inside the sandbox
    install -d "$pkgdir/usr/share/applications"
    install -Dm644 "$startdir/google-voice-desktop.desktop" "$pkgdir/usr/share/applications/google-voice-desktop.desktop"

    # 4. Integrate high-resolution visual branding icon assets
    if [ -f "$startdir/images/icon.png" ]; then
        install -Dm644 "$startdir/images/icon.png" "$pkgdir/usr/share/pixmaps/google-voice.png"
    fi

    # 5. Build an execution binary routing script that passes our clean folder layout pointer (.)
    install -d "$pkgdir/usr/bin"
    echo -e "#!/bin/sh\nexec electron /usr/lib/$pkgname \".\" \"\$@\"" > "$pkgdir/usr/bin/google-voice-desktop"
    chmod +x "$pkgdir/usr/bin/google-voice-desktop"
}
