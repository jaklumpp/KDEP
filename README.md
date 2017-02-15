# KDEP

The two zipped directories contain code which identical except for the I/O subroutines. KDEP uses an I/O subroutine which relies on variable-length strings. This results in code which is easier to read and write. However, it is not supported by the open-source Fortran compilers. The developers of the code compiled it using the Intel Fortran compiler.

KDEP1 uses a different I/O subroutine which is compatible with older version of Fortran. It should compile using open-source Fortran compilers such as GNU.

This code is publicly available and is intended for unlimited use, modification, and distribution. Updates and/or bug reports can be posted here.
