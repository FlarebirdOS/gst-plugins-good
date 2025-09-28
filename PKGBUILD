pkgname=gst-plugins-good
pkgver=1.26.6
pkgrel=1
pkgdesc="Multimedia graph framework - good plugins"
arch=('x86_64')
url="https://gstreamer.freedesktop.org/"
license=('LGPL-2.1-or-later')
depends=(
    'aalib'
    'cairo'
    'flac'
    'gdk-pixbuf'
    'gstreamer'
    'gst-plugins-base-libs'
    'lame'
    'libdv'
    'libpulse'
    'libvpx'
    'mpg123'
    'speex'
    'taglib'
)

makedepends=(
    'glib2-devel'
    'meson'
    'nasm'
    'valgrind'
    'wayland'
)
source=(https://gstreamer.freedesktop.org/src/gst-plugins-good/${pkgname}-${pkgver}.tar.xz)
sha256sums=(d0956535c8315856df9ca2de495f7725128b462863b3c7cd357ef64fb4199679)

build() {
    cd ${pkgname}-${pkgver}

    local meson_args=(
        -D package-name="GStreamer (Flarebird Linux)"
        -D package-origin="https://flarebirdos.github.io"
    )

    ${meson_options} "${meson_args[@]}"

    ${meson_build}
}

package() {
    cd ${pkgname}-${pkgver}

    ${meson_install} ${pkgdir}
}
