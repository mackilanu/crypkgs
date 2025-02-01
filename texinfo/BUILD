BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

./configure --prefix=/usr
make
make DESTDIR=$BD install
make DESTDIR=$BD TEXMF=/usr/share/texmf install-tex

pushd $BD/usr/share/info
  rm -v dir
  for f in *
    do install-info $f dir 2>/dev/null
  done
popd


