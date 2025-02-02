BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.xz

cd $SRCDIR

sed '20,$ d' -i trust/trust-extract-compat &&

cat >> trust/trust-extract-compat << "EOF"
# Copy existing anchor modifications to /etc/ssl/local
/usr/libexec/make-ca/copy-trust-modifications

# Update trust stores
/usr/sbin/make-ca -r
EOF


mkdir p11-build &&
cd    p11-build &&

meson setup ..            \
      --prefix=/usr       \
      --buildtype=release \
      -D trust_paths=/etc/pki/anchors &&
ninja


DESTDIR=$BD ninja install &&
ln -sfv $BD/usr/libexec/p11-kit/trust-extract-compat \
        $BD/usr/bin/update-ca-certificates

