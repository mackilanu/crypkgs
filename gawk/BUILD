BD=../$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

sed -i 's/extras//' Makefile.in

./configure --prefix=/usr
make

rm -f $BD/usr/bin/gawk-5.3.0
make DESTDIR=$BD install

ln -sv gawk.1 $BD/usr/share/man/man1/awk.1

#install docs
mkdir -pv $BD/usr/share/doc
mkdir -pv                                   $BD/usr/share/doc/gawk-5.3.0
cp    -v doc/{awkforai.txt,*.{eps,pdf,jpg}} $BD/usr/share/doc/gawk-5.3.0
