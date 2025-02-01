BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

./configure --prefix=/usr \
            --docdir=/usr/share/doc/flex-2.6.4 \
            --disable-static

make
make DESTDIR=$BD install

ln -sv flex   $BD/usr/bin/lex
ln -sv flex.1 $BD/usr/share/man/man1/lex.1
