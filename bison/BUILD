BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

./configure --prefix=/usr --docdir=/usr/share/doc/bison-3.8.2
make
make DESTDIR=$BD install
