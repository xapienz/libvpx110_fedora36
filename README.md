# What

This is RPM spec for older version libvpx 1.10 to build on Fedora 36.
Resulting libvpx_1.10 can be installed along with newer versions.

# How

```
# Prepare build sources:
sudo dnf builddep --spec ./libvpx.spec
mkdir -p ~/rpmbuild/SOURCES/
cp vpx_config.h ~/rpmbuild/SOURCES/
cp libvpx-1.7.0-leave-fortify-source-on.patch ~/rpmbuild/SOURCES/

# Build:
rpmbuild --undefine=_disable_source_fetch -bb ./libvpx.spec

# Install:
sudo rpm -i ~/rpmbuild/RPMS/x86_64/libvpx_1.10-1.10.0-2.fc36.x86_64.rpm
```
