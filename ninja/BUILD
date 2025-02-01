BD=$(pwd)/$BUILDDIR
SRCDIR=$PKGNAME-$PKGVER
tar -xf $SRCDIR.tar.gz

cd $SRCDIR

python3 configure.py --bootstrap

mkdir -pv $BD/usr/bin
install -vm755 ninja $BD/usr/bin/
install -vDm644 misc/bash-completion $BD/usr/share/bash-completion/completions/ninja
install -vDm644 misc/zsh-completion  $BD/usr/share/zsh/site-functions/_ninja
