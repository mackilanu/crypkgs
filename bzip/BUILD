BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

patch -Np1 -i ../bzip2-1.0.8-install_docs-1.patch
sed -i 's@\(ln -s -f \)$(PREFIX)/bin/@\1@' Makefile
sed -i "s@(PREFIX)/man@(PREFIX)/share/man@g" Makefile

make -f Makefile-libbz2_so
make clean

make
make PREFIX=$BD/usr install

cp -av libbz2.so.* $BD/usr/lib
ln -sv libbz2.so.1.0.8 $BD/usr/lib/libbz2.so

cp -v bzip2-shared $BD/usr/bin/bzip2
for i in $BD/usr/bin/{bzcat,bunzip2}; do
  ln -sfv bzip2 $i
done

rm -fv $BD/usr/lib/libbz2.h
