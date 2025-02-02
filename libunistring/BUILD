BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

./configure --prefix=/usr    \
            --disable-static \
            --docdir=/usr/share/doc/libunistring-1.2 &&
make
make DESTDIR=$BD install
