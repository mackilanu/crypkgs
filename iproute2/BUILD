BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

sed -i /ARPD/d Makefile
rm -fv man/man8/arpd.8

make NETNS_RUN_DIR=/run/netns
make DESTDIR=$BD SBINDIR=/usr/sbin install


mkdir -pv             $BD/usr/share/doc/iproute2-6.10.0
cp -v COPYING README* $BD/usr/share/doc/iproute2-6.10.0
