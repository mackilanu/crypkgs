BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

./configure --prefix=/usr --disable-static
make
make DESTDIR=$BD docdir=/usr/share/doc/check-0.15.2 install
