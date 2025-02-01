
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR


mkdir build
pushd build
  ../configure
  make -C include
  make -C progs tic
popd

./configure --prefix=/usr           \
            --mandir=/usr/share/man \
            --with-shared           \
            --without-debug         \
            --without-normal        \
            --with-cxx-shared       \
            --enable-pc-files       \
            --with-pkg-config-libdir=/usr/lib/pkgconfig

make

make DESTDIR=$PWD/dest install
install -vm755 dest/usr/lib/libncursesw.so.6.5 /usr/lib
rm -v  dest/usr/lib/libncursesw.so.6.5
sed -e 's/^#if.*XOPEN.*$/#if 1/' \
    -i dest/usr/include/curses.h
cp -av dest/* ../$BUILDDIR


#  Many applications still expect the linker to be able to find non-wide-character Ncurses libraries. Trick such applications into linking with wide-character libraries by means of symlinks (note that the .so links are only safe with curses.h edited to always use the wide-character ABI): 
for lib in ncurses form panel menu ; do
    ln -sfv lib${lib}w.so ../$BUILDDIR/usr/lib/lib${lib}.so
    ln -sfv ${lib}w.pc    ../$BUILDDIR/usr/lib/pkgconfig/${lib}.pc
done


#make sure that old applications that look for -lcurses at build time are still buildable: 
ln -sfv libncursesw.so ../$BUILDDIR/usr/lib/libcurses.so


mkdir -pv ../$BUILDDIR/usr/share/doc
cp -v -R doc -T ../$BUILDDIR/usr/share/doc/ncurses-6.5
