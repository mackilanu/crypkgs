BD=$(pwd)/$BUILDDIR
SRCDIR=Python-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

./configure --prefix=/usr        \
            --enable-shared      \
            --with-system-expat  \
            --enable-optimizations
make
make DESTDIR=$BD install


mkdir -pv $BD/etc
cat > $BD/etc/pip.conf << EOF
[global]
root-user-action = ignore
disable-pip-version-check = true
EOF

