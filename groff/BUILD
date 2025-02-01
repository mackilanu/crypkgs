BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

PAGE=A4 ./configure --prefix=/usr
make
make DESTDIR=$BD install
