# Contributor: Xiao-Long Chen <chenxiaolong@cxl.epac.to>
# Contributor: Handy Menny <Handymenny[at]outlook[dot]com>
# Maintainer: Pablo Lezaeta <prflr88@gmail.com>

pkgname=xubuntu-artwork
pkgver=18.04
pkgrel=1
_uver=artful
pkgdesc="Xubuntu themes, artwork, icons"
arch=("any")
url="https://launchpad.net/xubuntu-artwork"
license=("gpl2" "gpl3" "custom:cc-by-sa-3.0")
conflicts=("elementary-xfce-icons")
#depends=("xfce-theme-albatross" "xfce-theme-bluebird" "xfce-theme-greybird" "shimmer-wallpapers")
makedepends=("zip")
optdepends=("plymouth: For the plymouth theme to work"
        "lightdm-gtk-greeter: For LightDM GTK Greeter theme to work"
        "shimmer-wallpapers: Wallpapers not included in the main package, or git version"
        "xfce-theme-albatross: Official theming, git or stable version"
        "xfce-theme-bluebird: Official theming, git or stable version"
        "xfce-theme-greybird: Official theming, git or stable version")
source=("https://launchpad.net/ubuntu/+archive/primary/+files/${pkgname}_${pkgver}.tar.xz"
	"CC-BY-SA-3.0.txt")

package() {
  #cd "${srcdir}/trunk"
  #cd "${srcdir}/${_uver}"
  cd "${srcdir}/${pkgname}"

  install -dm755 "${pkgdir}/usr/"

  msg2 "Install the rest of the files."
  cp -av usr/share/ "${pkgdir}/usr/share/"

  # Icons from package elementary-xfce-icons don't look so good
  # msg2 "Remove Elementary-Xfce bundled with this artwork, is hella outdated."
  # rm -frv "${pkgdir}"/usr/share/icons

  msg2 "Move backdrops to a better place for Xfce 4.12+."
  mkdir -p "${pkgdir}/usr/share/backgrounds/xfce"
  mv -v "${pkgdir}"/usr/share/xfce4/backdrops/* "${pkgdir}"/usr/share/backgrounds/xfce

  msg2 "Remove redundant and empty files."
  rm -frv "${pkgdir}"/usr/share/xfce4/backdrops

  install -D -m644 "${srcdir}/CC-BY-SA-3.0.txt" "${pkgdir}/usr/share/licenses/${pkgbase}/CC-BY-SA-3.0.txt"
}
# I use MD5 because is what "makepkg -g" give by default, blame Allan


md5sums=('6f6b6cc63f0630881a69c3aad08c21cc'
         'd55fbe17f8a79a738b1337f0b96aa064')
