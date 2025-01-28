
SRCDIR=$PKGNAME-$PKGVER

tar -xf $SRCDIR.tar.xz

cd $SRCDIR

./configure --prefix=/usr                           \
            --disable-static                        \
            --with-openssl                          \
            --enable-threaded-resolver              \
            --with-ca-path=/etc/ssl/certs &&
make -j16

make install DESTDIR=$(pwd)/../$BUILDDIR

cd ..
