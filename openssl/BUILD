BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

./config --prefix=/usr         \
         --openssldir=/etc/ssl \
         --libdir=lib          \
         shared                \
         zlib-dynamic

make
sed -i '/INSTALL_LIBS/s/libcrypto.a libssl.a//' Makefile
make DESTDIR=$BD MANSUFFIX=ssl install

mkdir -pv $BD/usr/share/doc
mv -v $BD/usr/share/doc/openssl $BD/usr/share/doc/openssl-3.3.1
