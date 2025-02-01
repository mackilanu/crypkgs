BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME$PKGVER
tar -xf $PKGNAME$PKGVER.tar.gz

cd $SRCDIR

patch -Np1 -i ../expect-5.45.4-gcc14-1.patch

./configure --prefix=/usr           \
            --with-tcl=/usr/lib     \
            --enable-shared         \
            --disable-rpath         \
            --mandir=/usr/share/man \
            --with-tclinclude=/usr/include

make
make DESTDIR=$BD install

ln -svf expect5.45.4/libexpect5.45.4.so $BD/usr/lib
