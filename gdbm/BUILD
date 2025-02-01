BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

./configure --prefix=/usr    \
            --disable-static \
            --enable-libgdbm-compat
make
make DESTDIR=$BD install
