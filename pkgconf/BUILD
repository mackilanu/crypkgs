BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

./configure --prefix=/usr              \
            --disable-static           \
            --docdir=/usr/share/doc/pkgconf-2.3.0
make
make DESTDIR=$BD install

ln -sv pkgconf   $BD/usr/bin/pkg-config
ln -sv pkgconf.1 $BD/usr/share/man/man1/pkg-config.1
