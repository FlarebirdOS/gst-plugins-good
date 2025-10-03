pkgname=gst-plugins-good
pkgver=1.27.2
pkgrel=2
pkgdesc="Multimedia graph framework - good plugins"
arch=('x86_64')
url="https://gstreamer.freedesktop.org/"
license=('LGPL-2.1-or-later')
depends=(
    'bzip2'
    'cairo'
    'flac'
    'gcc-libs'
    'gdk-pixbuf'
    'glib2'
    'glibc'
    "gst-plugins-base-libs>=${pkgver}"
    "gstreamer>=${pkgver}"
    'lame'
    'libgudev'
    'libjpeg-turbo'
    'libpng'
    'libpulse'
    'libshout'
    'libsoup'
    'libvpx'
    'libx11'
    'libxdamage'
    'libxext'
    'libxfixes'
    'libxml2'
    'libxtst'
    'mpg123'
    'nettle'
    'orc'
    'qt6-qtwayland'
    'speex'
    'taglib'
    'twolame'
    'v4l-utils'
    'wavpack'
    'zlib'
)

makedepends=(
    'glib2-devel'
    'meson'
    'nasm'
    'qt6-qttools'
    'qt6-qtshadertools'
    'valgrind'
    'wayland'
)
source=(https://gstreamer.freedesktop.org/src/gst-plugins-good/${pkgname}-${pkgver}.tar.xz)
sha256sums=(4f047416d71b102998db4cc513925cb317d87a3409d0ffae3ba218765b0f1ce5)

build() {
    cd ${pkgname}-${pkgver}

    local meson_args=(
        -D package-name="GStreamer (Flarebird Linux)"
        -D package-origin="https://flarebirdos.github.io"
        -D doc=disabled
        -D asm=enabled
        -D orc=enabled
        -D monoscope=disabled
        -D aalib=disabled
        -D libcaca=disabled
        -D rpicamsrc=disabled
        -D amrnb=disabled
        -D amrwbdec=disabled
        -D jack=disabled
        -D dv=disabled
        -D dv1394=disabled
        -D qt-egl=disabled
        -D qt6=enabled
    )

    ${meson_options} "${meson_args[@]}"

    ${meson_build}
}


package() {
    cd ${pkgname}-${pkgver}

    ${meson_install} ${pkgdir}
}
