BD=../$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

./configure --prefix=/usr
make
make html

make DESTDIR=$BD install

mkdir -pv $BD/usr/share/doc
install -d -m755           $BD/usr/share/doc/sed-4.9
install -m644 doc/sed.html $BD/usr/share/doc/sed-4.9
