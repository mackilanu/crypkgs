BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

./configure --prefix=/usr --docdir=/usr/share/doc/gperf-3.1
make
make DESTDIR=$BD install
