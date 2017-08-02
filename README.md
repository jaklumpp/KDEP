# KDEP

Description:

The two zipped directories contain code which is identical except for the I/O subroutines. KDEP uses an I/O subroutine which relies on variable-length strings. This results in code which is easier to read and write. However, it is not supported by the open-source Fortran compilers. The developers of the code compiled it using the Intel Fortran compiler.

KDEP1 uses a different I/O subroutine which is compatible with older version of Fortran. It should compile using open-source Fortran compilers such as GNU.

It seems that some compilers may have recently changed to a more restrictive Fortran standard for I/O, because some people have had problems compiling the routine for reading and writing CSV files (my colleague and I have compiled these routines on 3 separate computers with gfortran and the Intel compiler). So, depending on what compiler you are using you may need to do some tinkering in order to compile from the source. If you should encounter this problem and solve it, please let me know and I'll post your solution with due credit - the problem is nearly impossible for me to debug since I can't reproduce it!

This code is publicly available and is intended for unlimited use, modification, and distribution. Updates and/or bug reports can be posted here.

Use:

To run, unzip either the KDEP or KDEP1 folder anywhere on your computer. In the kdep directory, there is a subdirectory called InputFiles. That contains input.csv and sizes.csv, which you can open with Excel or Notepad. Input.csv is where you specify the characteristics of the aerosol and the person breathing it. Sizes.csv is where you specify the particle sizes for which you want deposition fractions calculated. Once you have the parameters you want, run kdep.exe in the main directory (KDEP). The output will then be written to kdep.csv, also in the main directory. The code also writes 'compKDEP.csv,' which shows the ratio between the calculated results and the results in the comparison file (specified in input.csv). 

For a test case, you can calculate values for an adult worker and compare to the published ICRP130 values. In input.csv, confirm that monodispursed is set to T, nose breather to F, subject to 1 (adult male), activity to 5 (standard worker), rho to 3, shape factor to 1.5, U to 1, P to 76, Chronic to T, ICRP130 to T, and Comp File to icrp130.csv. This last instructs KDEP to create a table showing the ratio between its calculated values and those published in ICRP130 for the standard worker. These should be the default values anyway, so you shouldn't have to change anything. Similarly, the values in sizes.csv are the same as those sizes published by ICRP. Then run kdep.exe and open compKDEP.csv. This will contain the ratio between the calculated values and those published in ICRP130. You can compare the output against any file in the CompFiles directory.

Disclaimer:

THE MATERIAL EMBODIED IN THIS SOFTWARE IS PROVIDED TO YOU "AS-IS" AND WITHOUT WARRANTY OF ANY KIND, EXPRESS, IMPLIED OR OTHERWISE, INCLUDING WITHOUT LIMITATION, ANY WARRANTY OF FITNESS FOR A PARTICULAR PURPOSE. IN NO EVENT SHALL LOS ALAMOS NATIONAL SECURITY (LANS) OR THE UNITED STATES (U.S.) GOVERNMENT BE LIABLE TO YOU OR ANYONE ELSE FOR ANY DIRECT, SPECIAL, INCIDENTAL, INDIRECT OR CONSEQUENTIAL DAMAGES OF ANY KIND, OR ANY DAMAGES WHATSOEVER, INCLUDING WITHOUT LIMITATION, LOSS OF PROFIT, LOSS OF USE, SAVINGS OR REVENUE, OR THE CLAIMS OF THIRD PARTIES, WHETHER OR NOT LANS OR THE U.S. GOVERNMENT HAS BEEN ADVISED OF THE POSSIBILITY OF SUCH LOSS, HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, ARISING OUT OF OR IN CONNECTION WITH THE POSSESSION, USE OR PERFORMANCE OF THIS SOFTWARE. 
