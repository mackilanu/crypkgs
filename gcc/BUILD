BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER

tar -xf $SRCDIR.tar.xz

cd $SRCDIR

sed -e '/m64=/s/lib64/lib/' \
    -i.orig gcc/config/i386/t-linux64

mkdir -v build
cd build
../configure --prefix=/usr            \
             LD=ld                    \
              --with-ld=/usr/bin/ld    \
             --enable-languages=c,c++ \
             --enable-default-pie     \
             --enable-default-ssp     \
             --enable-host-pie        \
             --disable-multilib       \
             --disable-bootstrap      \
             --disable-fixincludes    \
             --with-system-zlib

make
make DESTDIR=$BD install


ln -sv gcc $BD/usr/bin/cc


ln -svr $BD/usr/bin/cpp $BD/usr/lib/

ln -sv gcc.1 $BD/usr/share/man/man1/cc.1

ln -sfv ../../libexec/gcc/$(gcc -dumpmachine)/14.2.0/liblto_plugin.so \
        $BD/usr/lib/bfd-plugins/

mkdir -pv $BD/usr/share/gdb/auto-load/usr/lib
mv -v $BD/usr/lib/*gdb.py ../../$BUILDDIR/usr/share/gdb/auto-load/usr/lib


