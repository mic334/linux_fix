# Fake qt5-default Package for IQmol on Ubuntu 24.04 LTS

This directory contains a fake `qt5-default` Debian package required to allow IQmol 2.15 to work correctly on Ubuntu 24.04 LTS.

Recent Ubuntu releases no longer provide the `qt5-default` package. However, IQmol still expects this dependency to be present. To resolve this issue without downgrading or modifying the system Qt libraries, a fake package can be created using `equivs`.

The pre-built `.deb` package is already included in this directory and can be installed directly.

The purpose of this package is to satisfy the `qt5-default` dependency required by IQmol 2.15, avoid changes to system Qt installations, and ensure compatibility with Ubuntu 24.04 LTS.

The following Debian package is included:

qt5-default_5.99.99+fake-13ubuntu37_all.deb

To install the package, run:

sudo apt install ./qt5-default_5.99.99+fake-13ubuntu37_all.deb

After installation, IQmol can be installed or executed normally.

For documentation purposes, the fake `qt5-default` package was created using `equivs` with the following steps:

sudo apt-get update
sudo apt-get install equivs

cd ~/Downloads
cat <<EOF > qt5-default-control
Package: qt5-default
Source: qtbase-opensource-src
Version: 5.99.99+fake-13ubuntu37
Architecture: all
Depends: qtbase5-dev, qtchooser
Suggests: qt5-qmake, qtbase5-dev-tools
Conflicts: qt4-default
Section: libdevel
Priority: optional
Homepage: http://qt-project.org/
Description: Qt 5 development defaults fake package
EOF

equivs-build qt5-default-control

These commands are provided for reference only and rebuilding the package is not required if the included `.deb` file is used.

This workaround is inspired by the discussion available at the following link:

https://askubuntu.com/questions/1335184/qt5-default-not-in-ubuntu-21-04

This package does not install actual Qt binaries and only satisfies dependency checks expecting `qt5-default`. Use with caution on production systems.
