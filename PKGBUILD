pkgname=opensoundmeter
pkgver=1.3
pkgrel=1
pkgdesc="Sound measurement application for tuning audio systems in real-time."
arch=( x86_64 )
url="https://opensoundmeter.com/"
pkgfqn="${pkgname}-${pkgver}-${pkgrel}"
license=( "GPL" )

depends=(alsa-lib icu libglvnd libx11 qt5-base qt5-declarative qt5-quickcontrols2 systemd-libs)
makedepends=( gcc )

source=(
    "git+https://github.com/psmokotnin/osm#commit=0a858c53672c008788854740397b92012d1d68f2"
    fix_project.patch
    fix_desktop_icon.patch
)

sha256sums=(
	'SKIP'
	6a24826eaf162611643d91ca499297ca43a31d787c9485a046d5830fec76a827
	812b2813b0e2bf7367d7caf0aafaf6f3b6d90c422954fbc4b2d33968e3ba36c7
)

prepare() {
	cd osm
	patch <../fix_project.patch
	patch <../fix_desktop_icon.patch
}


build() {
	cd osm
	qmake
	make -j4
}

package() {
	install -D -m755 "osm/OpenSoundMeter" "$pkgdir/usr/bin/OpenSoundMeter"
	install -D -m755 "osm/OpenSoundMeter.desktop" "$pkgdir/usr/share/applications/OpenSoundMeter.desktop"
	install -D -m644 "osm/icons/white.png" "$pkgdir/usr/share/icons/hicolor/1024x1024/apps/OpenSoundMeter.png"
}
