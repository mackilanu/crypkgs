BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

CC=gcc ./configure --prefix=/usr -G -O3 -r
make
make DESTDIR=$BD install
