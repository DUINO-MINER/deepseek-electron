# Maintainer: Tu Nombre <kixew34@gmail.com>
pkgname=deepseek-electron
pkgver=1.0.0
pkgrel=1
pkgdesc="Aplicación Electron para DeepSeek Chat"
arch=('x86_64')
url="https://chat.deepseek.com"
license=('MIT')
depends=('electron' 'nodejs')
source=("https://github.com/DUINO-MINER/deepseek-electron/releases/download/electron/deepseek-electron-$pkgver-linux-x64.tar.gz")
sha256sums=('SKIP') # No exixte

prepare() {
  # Descomprime el archivo .tar.gz
  tar -xzf "$srcdir/deepseek-electron-$pkgver-linux-x64.tar.gz" -C "$srcdir"
}

package() {
  # Copia los archivos de la aplicación
  install -d "$pkgdir/usr/bin"
  install -Dm755 "$srcdir/deepseek-electron-linux-x64/deepseek-electron" "$pkgdir/usr/bin/deepseek-electron"

  # Copia los recursos (opcional, si es necesario)
  cp -r "$srcdir/deepseek-electron-linux-x64/resources" "$pkgdir/usr/lib/deepseek-electron/"

  # Crea un lanzador para el menú de aplicaciones (opcional)
  install -d "$pkgdir/usr/share/applications"
  cat > "$pkgdir/usr/share/applications/deepseek-electron.desktop" <<EOF
[Desktop Entry]
Name=DeepSeek Chat
Exec=deepseek-electron
Icon=deepseek-electron
Type=Application
Categories=Network;Chat;
Comment=Aplicación Electron para DeepSeek Chat
EOF
}