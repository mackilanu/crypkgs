BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

./configure --prefix=/usr          \
            --disable-static       \
            --with-gcc-arch=native


make
make DESTDIR=$BD install
