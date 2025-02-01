
BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

# POSIX requires that programs from Coreutils recognize character boundaries correctly even in multibyte locales. The following patch fixes this non-compliance and other internationalization-related bugs. 
patch -Np1 -i ../coreutils-9.5-i18n-2.patch


autoreconf -fiv
FORCE_UNSAFE_CONFIGURE=1 ./configure \
            --prefix=/usr            \
            --enable-no-install-program=kill,uptime

make
make DESTDIR=$BD install

# Move programs to the locations specified by the FHS
mkdir -pv $BD/usr/share/man/man8
mkdir -pv $BD/usr/sbin
mv -v $BD/usr/bin/chroot $BD/usr/sbin
mv -v $BD/usr/share/man/man1/chroot.1 $BD/usr/share/man/man8/chroot.8
sed -i 's/"1"/"8"/' $BD/usr/share/man/man8/chroot.8


