# Linux Fixes Repository

This repository is organized to host different fixes and workarounds for specific issues encountered on Linux systems.

The `main` branch serves as an index and entry point, while each solution is maintained in its own dedicated directory (or branch, if needed in the future).

At the moment, only one fix is available.

---

## Available Fixes

### 1. IQmol 2.15 – Qt Issue on Ubuntu 24.04 LTS

This fix was created to address a compatibility problem between **IQmol 2.15** and **Qt libraries** on **Ubuntu 24.04 LTS**.

On this Ubuntu release, IQmol 2.15 may fail to start or show graphical issues due to changes in the Qt framework and library versions shipped with the system.

The solution provided here contains notes and files aimed at resolving or working around this Qt-related problem, allowing IQmol 2.15 to run correctly on Ubuntu 24.04 LTS.

This solution was inspired by information and suggestions discussed in the following reference:

- [Qt5 default not in Ubuntu 21.04 – Ask Ubuntu](https://askubuntu.com/questions/1335184/qt5-default-not-in-ubuntu-21-04)

---

---

### 2. Molden – Compilation on Modern Ubuntu Versions

This fix provides instructions and notes to **compile Molden from source** on modern Ubuntu systems (Ubuntu 22.04 and later), where precompiled binaries or legacy build configurations may no longer work out of the box.

Due to updates in modern Fortran compilers and stricter argument checking, the original build process may fail. The provided instructions describe how to modify the Makefiles and compile Molden successfully using recent compiler versions.

This section serves as an alternative visualization solution when **IQmol is not available or not functioning correctly** on newer Linux distributions.

The compilation approach is based on the official Molden source and adapted for modern systems.

This solution was inspired by information and suggestions discussed in the following reference:

- [reddit.com](https://www.reddit.com/r/comp_chem/comments/v7865d/tutorial_compiling_molden_from_source_on_debian/)
---


