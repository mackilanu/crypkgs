BD=$(pwd)/$BUILDDIR

SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

./configure --prefix=/usr             \
            --without-bash-malloc     \
            --with-installed-readline \
            bash_cv_strtold_broken=no \
            --docdir=/usr/share/doc/bash-5.2.32 \

make
make DESTDIR=$BD install

mkdir -pv $BD/bin
ln -s bash "$BD/usr/bin/sh"
