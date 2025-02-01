BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

mkdir -v build
cd       build



../configure --prefix=/usr           \
             --sysconfdir=/etc       \
             --enable-elf-shlibs     \
             --disable-libblkid      \
             --disable-libuuid       \
             --disable-uuidd         \
             --disable-fsck

make
make DESTDIR=$BD install

rm -fv $BD/usr/lib/{libcom_err,libe2p,libext2fs,libss}.a


gunzip -v $BD/usr/share/info/libext2fs.info.gz
mkdir -pv $BD/usr/share/info
install-info --dir-file=$BD/usr/share/info/dir $DB/usr/share/info/libext2fs.info
