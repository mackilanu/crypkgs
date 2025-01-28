SRCDIR=$PKGNAME-$PKGVER

tar -xf $SRCDIR.tar.xz

cd $SRCDIR

mkdir -pv build
cd build
../configure --prefix=/usr       \
             --sysconfdir=/etc   \
             --enable-gold       \
             --enable-ld=default \
             --enable-plugins    \
             --enable-shared     \
             --disable-werror    \
             --enable-64-bit-bfd \
             --enable-new-dtags  \
             --with-system-zlib  \
             --enable-default-hash-style=gnu



make -j 16
make install DESTDIR=$(pwd)/../../$BUILDDIR
rm -fv ../../$BUILDDIR/usr/lib/lib{bfd,ctf,ctf-nobfd,gprofng,opcodes,sframe}.a

