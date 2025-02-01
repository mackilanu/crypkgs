BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME$PKGVER
tar -xf $SRCDIR-src.tar.gz

cd $SRCDIR

cd unix
./configure --prefix=/usr           \
            --mandir=/usr/share/man \
            --disable-rpath



TMPSRCDIR=$(pwd)
make

sed -e "s|$TMPSRCDIR/unix|/usr/lib|" \
    -e "s|$TMPSRCDIR|/usr/include|"  \
    -i tclConfig.sh

sed -e "s|$TMPSRCDIR/unix/pkgs/tdbc1.1.7|/usr/lib/tdbc1.1.7|" \
    -e "s|$TMPSRCDIR/pkgs/tdbc1.1.7/generic|/usr/include|"    \
    -e "s|$TMPSRCDIR/pkgs/tdbc1.1.7/library|/usr/lib/tcl8.6|" \
    -e "s|$TMPSRCDIR/pkgs/tdbc1.1.7|/usr/include|"            \
    -i pkgs/tdbc1.1.7/tdbcConfig.sh

sed -e "s|$TMPSRCDIR/unix/pkgs/itcl4.2.4|/usr/lib/itcl4.2.4|" \
    -e "s|$TMPSRCDIR/pkgs/itcl4.2.4/generic|/usr/include|"    \
    -e "s|$TMPSRCDIR/pkgs/itcl4.2.4|/usr/include|"            \
    -i pkgs/itcl4.2.4/itclConfig.sh

unset TMPSRCDIR
make DESTDIR=$BD install

chmod -v u+w $BD/usr/lib/libtcl8.6.so

make DESTDIR=$BD install-private-headers

ln -sfv tclsh8.6 $BD/usr/bin/tclsh
mv $BD/usr/share/man/man3/{Thread,Tcl_Thread}.3
