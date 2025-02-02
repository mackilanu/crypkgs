BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

make DESTDIR=$BD install &&
install -vdm755 $BD/etc/ssl/local
