# In your case, copying files to /etc
mkdir -pv ${BUILDDIR}/{etc,var} 
mkdir -pv ${BUILDDIR}/usr/{bin,lib,sbin}

for i in bin lib sbin; do
  ln -sv ${BUILDDIR}/usr/$i ${BUILDDIR}/$i
done

mkdir -pv ${BUILDDIR}/lib64

