BD=../$BUILDDIR
SRCDIR=linux-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

make headers
find usr/include -type f ! -name '*.h' -delete

mkdir -pv $BD/usr
cp -rv usr/include $BD/usr

