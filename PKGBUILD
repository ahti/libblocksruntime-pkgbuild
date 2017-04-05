# This is an example PKGBUILD file. Use this as a start to creating your own,
# and remove these comments. For more information, see 'man PKGBUILD'.
# NOTE: Please fill out the license field for your package! If it is unknown,
# then please put 'unknown'.

# The following guidelines are specific to BZR, GIT, HG and SVN packages.
# Other VCS sources are not natively supported by makepkg yet.

# Maintainer: Your Name <youremail@domain.com>
pkgname=libblocksruntime # '-bzr', '-git', '-hg' or '-svn'
pkgver=r4475.b5c5274da
pkgrel=1
pkgdesc="BlocksRuntime lib from llvm compiler-rt"
arch=(x86_64)
url=""
license=('MIT')
groups=()
depends=()
makedepends=('git') # 'bzr', 'git', 'mercurial' or 'subversion'
provides=("${pkgname%-VCS}")
conflicts=("${pkgname%-VCS}")
replaces=()
backup=()
options=()
install=
source=('blocksruntime::git+https://github.com/mackyle/blocksruntime.git')
noextract=()
md5sums=('SKIP')

# Please refer to the 'USING VCS SOURCES' section of the PKGBUILD man page for
# a description of each element in the source array.

pkgver() {
	cd "$srcdir/blocksruntime"
	printf "r%s.%s" "$(git rev-list --count HEAD)" "$(git rev-parse --short HEAD)"
}

prepare() {
	cd "$srcdir/blocksruntime"
}

build() {
	cd "$srcdir/blocksruntime"
    CFLAGS=-fPIC ./buildlib
}

package() {
	cd "$srcdir/blocksruntime"
    mkdir -p $pkgdir/usr
    prefix=$pkgdir/usr ./installlib
}
