BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER

tar -xf $SRCDIR.tar.xz

cd $SRCDIR


mkdir -pv $BD/lib64

# This is just copied from the first build.
cp /lib64/ld-linux-x86-64.so.2 $BD/lib64/ld-linux-x86-64.so.2

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

make 

touch $BD/etc/ld.so.conf
sed '/test-installation/s@$(PERL)@echo not running@' -i ../Makefile
make DESTDIR=$BD install

sed '/RTLDLIST=/s@/usr@@g' -i $BD/usr/bin/ldd

#Install locale files
make DESTDIR=$BD objdir=$BD localedata/install-locales

