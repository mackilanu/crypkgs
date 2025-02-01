BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

# Remove a warning about using egrep and fgrep that makes tests on some packages fail
sed -i "s/echo/#echo/" src/egrep.sh

./configure --prefix=/usr
make
make DESTDIR=$BD install
