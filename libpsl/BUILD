BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR
mkdir build &&
cd    build &&

meson setup --prefix=/usr --buildtype=release &&

ninja

DESTDIR=$BD ninja install
