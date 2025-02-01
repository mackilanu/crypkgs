BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR
sed -i 's:\\\${:\\\$\\{:' intltool-update.in
./configure --prefix=/usr

make
make DESTDIR=$BD install

install -v -Dm644 doc/I18N-HOWTO $BD/usr/share/doc/intltool-0.51.0/I18N-HOWTO
