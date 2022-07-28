# Maintainer: Michał Walenciak <kicer86@gmail.com>
pkgname=media-downloader
pkgver=2.4.0
pkgrel=1
pkgdesc="This project is a Qt/C++ based frontend to youtube-dl and it can be used to download any media file supported by youtube-dl"
arch=('i686' 'x86_64')
url="https://github.com/mhogomchungu/media-downloader"
license=('GPL2')
depends=('qt5-base')
makedepends=('cmake' 'git' 'yt-dlp' 'you-get' 'youtube-dl' 'gallery-dl' 'wget' 'aria2')
provides=("${pkgname}")
source=(https://codeload.github.com/mhogomchungu/$pkgname/tar.gz/$pkgver)
sha256sums=('SKIP')

build()
{
    cd $pkgname-$pkgver
    mkdir -p build
    cd build
    cmake -DCMAKE_INSTALL_PREFIX=/usr -DCMAKE_BUILD_TYPE=None -Wno-dev ..
    make
}

package()
{
    cd "$pkgname-$pkgver"
    cd build
    make DESTDIR="$pkgdir/" install
}

