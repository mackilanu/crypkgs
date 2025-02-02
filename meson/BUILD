BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

./packaging/create_zipapp.py --outfile meson --interpreter '/usr/bin/env python3' .

mkdir -pv $BD/usr/bin
mv meson $BD/usr/bin
