BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR
make prefix=/usr
make prefix=/usr DESTDIR=$BD install
rm -v $BD/usr/lib/libzstd.a
