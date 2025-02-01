
SRCDIR=$PKGNAME-$PKGVER

tar -xf $SRCDIR.tar.gz

cd $SRCDIR

./configure --prefix=/usr

make
make DESTDIR=../$BUILDDIR install
