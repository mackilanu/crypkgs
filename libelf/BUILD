BD=$(pwd)/$BUILDDIR
SRCDIR=elfutils-$PKGVER
tar -xf $SRCDIR.tar.bz2

cd $SRCDIR

./configure --prefix=/usr                \
            --disable-debuginfod         \
            --enable-libdebuginfod=dummy
make
make DESTDIR=$BD -C libelf install
install -vm644 config/libelf.pc $BD/usr/lib/pkgconfig
rm $BD/usr/lib/libelf.a
