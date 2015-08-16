# Contributer: BeholdMyGlory <larvid@gmail.com>
pkgname=mupen64plus-audio-sdl-hg
pkgver=107
pkgrel=1
pkgdesc="Audio plugin for Mupen64Plus v2.0, a Nintendo 64 emulator, using SDL. Latest hg pull."
url="http://bitbucket.org/richard42/mupen64plus-audio-sdl"
license=("GPL")
arch=(i686 x86_64)
groups=(mupen64plus-hg)
depends=(mupen64plus-core-hg libsamplerate)
makedepends=(mercurial)
source=("hg+http://bitbucket.org/richard42/mupen64plus-audio-sdl")
md5sums=('SKIP')

pkgver() {
	cd $srcdir/${pkgname%-*}
	echo $(hg identify -n)
}

build() {
	cd "${srcdir}/${pkgname%-*}"
	make -C projects/unix all NO_RESAMP=0
}

package() {
	cd "${srcdir}/${pkgname%-*}"
	make -C projects/unix PREFIX=/usr DESTDIR=${pkgdir} install
}
