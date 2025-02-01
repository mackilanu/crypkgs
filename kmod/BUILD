BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

./configure --prefix=/usr     \
            --sysconfdir=/etc \
            --with-openssl    \
            --with-xz         \
            --with-zstd       \
            --with-zlib       \
            --disable-manpages
make
make DESTDIR=$BD install


mkdir -pv $BD/usr/sbin
for target in depmod insmod modinfo modprobe rmmod; do
  ln -sfv ../bin/kmod $BD/usr/sbin/$target
  rm -fv $BD/usr/bin/$target
done
