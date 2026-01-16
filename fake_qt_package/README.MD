# Fake qt5-default Package for IQmol 2.15 on Ubuntu 24.04 LTS

This directory contains a **fake `qt5-default` Debian package** required to allow **IQmol 2.15** to work correctly on **Ubuntu 24.04 LTS**.

Recent Ubuntu releases no longer provide the `qt5-default` package. However, IQmol still expects this dependency to be present. To resolve this issue **without downgrading or modifying system Qt libraries**, a fake package can be created using `equivs`.

A pre-built `.deb` package is already included in this directory and can be installed directly.

---

## Purpose

The purpose of this package is to:

- Satisfy the `qt5-default` dependency required by IQmol 2.15
- Avoid changes to system Qt installations
- Ensure compatibility with Ubuntu 24.04 LTS

---

## Included Package

The following Debian package is included in this directory:

!sentinella
qt5-default_5.99.99+fake-13ubuntu37_all.deb
!sentinella

---

## Installation

To install the fake package, run:


```bash
sudo apt install ./qt5-default_5.99.99+fake-13ubuntu37_all.deb
```


After installation, IQmol can be installed or executed normally.

---

## Package Creation (Documentation)

For documentation purposes, the fake `qt5-default` package was created using `equivs`.
Rebuilding the package is **not required** if you use the included `.deb` file.

The following steps describe how the package was generated:

```bash
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
sudo apt-get update
```
---

## Reference

This workaround is inspired by the discussion available at:

- https://askubuntu.com/questions/1335184/qt5-default-not-in-ubuntu-21-04

---

## Notes

- This package does **not** install actual Qt binaries.
- It only satisfies dependency checks expecting `qt5-default`.
- Use with caution on production systems.



