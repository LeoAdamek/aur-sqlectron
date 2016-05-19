# Maintainer: Leo Adamek <code[at]adamek[dot]me>
pkgname=sqlectron-gui
pkgver=1.8.0
pkgrel=1
pkgdesc="A simple and lightweight SQL client desktop with cross database and platform support."
arch=('x86_64')
url="https://sqlectron.github.io/"

license=('MIT')
depends=('desktop-file-utils' 'nodejs')
source=(Sqlectron-${pkgver}-amd64.deb::https://github.com/sqlectron/sqlectron-gui/releases/download/v${pkgver}/Sqlectron-{$pkgver}-amd64.deb)
md5sums=('a1ecf94c65ce98a6e1e48ad4e751b05d')
install=${pkgname}.install

package() {
    msg2 "Extracting data.tar.xz"
    bsdtar -xf data.tar.xz -C "${pkgdir}/"

  find "${pkgdir}" -type f -exec chmod 644 {} \;
  find "${pkgdir}" -type d -exec chmod 755 {} \;

  chmod 755 "${pkgdir}"/opt/Sqlectron/Sqlectron

  mkdir -p "${pkgdir}"/usr/local/bin/

  # Create a symlink in the default $PATH
  ln -s "${pkgdir}"/opt/Sqlectron/Sqlectron "${pkgdir}"/usr/local/bin/sqlectron-gui
}
