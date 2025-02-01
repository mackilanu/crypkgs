BD=../$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

./configure --prefix=/usr
make
make DESTDIR=$BD install

rm -fv $BD/usr/lib/libz.a
