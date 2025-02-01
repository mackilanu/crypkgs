BD=../../$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

FORCE_UNSAFE_CONFIGURE=1  \
  ./configure --prefix=/usr

make
make DESTDIR=$BD install

mkdir -pv $BD/usr/share/doc 
make -C doc install-html docdir=$BD/usr/share/doc/tar-1.35
