BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

./configure --prefix=/usr --sysconfdir=/etc
make
make DESTDIR=$BD install
