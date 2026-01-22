# Molden Installation Guide


Source code download 
- (https://www.theochem.ru.nl/molden/)

The source code is contained in the archive you download. After extraction, the relevant files are located in the `src/` directory.

This README describes the full procedure to compile, install, and run Molden from source on a Unix-like system (Linux or macOS).

A working Fortran compiler (e.g. gfortran) and `make` are required (see package list)

First, download and extract the source archive. Move into the main project directory.

Edit the main `Makefile` and add the following flags to **every uncommented `FFLAG`**:
-w -fallow-argument-mismatch

Then edit the Makefile located in:

```bash
vi src/ambfor/Makefile
```

and add the same flags (`-w -fallow-argument-mismatch`) to all active `FFLAG` entries there as well.

Once both Makefiles have been updated, compile the program by running the following command from the parent directory:

```bash
make
```

After successful compilation, make the generated binaries executable:

```bash
chmod u+x bin/molden
chmod u+x bin/gmolden
```

Test the installation by running the programs directly from the command line:

```bash
./bin/molden
./bin/gmolden
```

If the programs start correctly, the installation was successful.

For maximum convenience, you can add the `bin/` directory to your shell environment so that the executables can be called from anywhere. For example, add the following line to your `.bashrc`, `.bash_profile`, or `.zshrc` file:

```bash
export PATH=$PATH:/path/to/molden/bin
```

Reload your shell configuration or open a new terminal session.

Enjoy using Molden and have fun!


## Acknowledgement

The installation procedure described in this README is not originally mine.  
It is based on the instructions available at the following link, which I adapted and collected here for convenience:

- [reddit.com](https://www.reddit.com/r/comp_chem/comments/v7865d/tutorial_compiling_molden_from_source_on_debian/)


