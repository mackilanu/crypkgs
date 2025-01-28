
SRCDIR=$PKGNAME-$PKGVER

tar -xf $SRCDIR.tar.xz

cd $SRCDIR

patch -Np1 -i ../glibc-2.40-fhs-1.patch

echo "rootsbindir=/usr/sbin" > $SRCDIR/configparms

mkdir -v build
cd build
../configure --prefix=/usr                            \
             --disable-werror                         \
             --enable-kernel=4.19                     \
             --enable-stack-protector=strong          \
             --disable-nscd                           \
             libc_cv_slibdir=/usr/lib

make -j16
make DESTDIR=$(pwd)/../../$BUILDDIR install

sed '/RTLDLIST=/s@/usr@@g' -i ../../$BUILDDIR/usr/bin/ldd


