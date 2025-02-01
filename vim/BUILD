BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

echo '#define SYS_VIMRC_FILE "/etc/vimrc"' >> src/feature.h
./configure --prefix=/usr

make
make DESTDIR=$BD install


mkdir -pv $BD/usr/share/doc
ln -sv ../vim/vim91/doc $BD/usr/share/doc/vim-9.1.0660

mkdir -pv $BD/etc
cp ../vimrc > $BD/etc
