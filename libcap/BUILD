BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz
cd $SRCDIR

sed -i '/install -m.*STA/d' libcap/Makefile

make prefix=/usr lib=lib
make prefix=/usr DESTDIR=$BD lib=lib install
