BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR
./configure --prefix=/usr --docdir=/usr/share/doc/automake-1.17

make
make DESTDIR=$BD install
