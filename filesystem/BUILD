# In your case, copying files to /etc
mkdir -pv ${BUILDDIR}/{etc,var} 
mkdir -pv ${BUILDDIR}/usr/{bin,lib,sbin}


cd $BUILDDIR
for i in bin lib sbin; do
  ln -sv usr/$i $i
done
cd ..
mkdir -pv ${BUILDDIR}/lib64

