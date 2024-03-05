# Multiwfn
Multiwfn is a powerful wavefunction analysis program, it supports almost all of the most important wavefunction analysis methods. Multiwfn is free, open-source, high-efficient, very user-friendly and flexible. 
# Citing 
If Multiwfn is used in your research, at least this paper must be cited in main text:
```
Tian Lu, Feiwu Chen, Multiwfn: A Multifunctional Wavefunction Analyzer, J. Comput.
Chem. 33, 580-592 (2012) DOI: 10.1002/jcc.22885
```
## Installation for Linux
-Uncompress the Multiwfn binary package
-Make sure that you have installed motif package, which provides libXm.so.4, full version of
-Multiwfn cannot boot up without this file. 
-The motif is freely available at 'https://motif.ics.com/motif/downloads'. 
-If you are an Ubuntu user, run sudo apt-get install libxm4 libgl1 to install it, or download deb package (e.g. libmotif4_2.3.4-1_amd64.deb) and manually install it.
Add below lines to ~/.bashrc file (using e.g. vi ~/.bashrc command)
export OMP_STACKSIZE=200M
ulimit -s unlimited
-These lines mean removing limitation on stacksize memory, and defining stacksize of 200MB for each thread during parallel calculations.

## Input files that are supported::
   Currently, a wide variety of quantum chemistry packages, such as Molpro, Molcas, ORCA, Q-Chem, CFour, Turbomole, PSI4,MRCC and NWChem, as well as a first-principle code CP2K, are able to produce input file of
  1) Molden visualization program.
     This type of file records atomic coordinates, basis set definition, information of all occupied and virtual orbitals (including expansion coefficient of basis functions, occupation number, spin, energy and symmetry), meanwhile there is no information only specific for Molden. So in fact, Molden input file can be regarded as a standard and general file format for exchanging wavefunction information. Fo
   This can be generated from ORCA easily.
```
/home/Lib/ORCA_504/orca_2mkl hcho_nto -molden
```
where hcho is the basename of the gbw file

## Plotting the MOs 
After converting to molden , open Multiwfn, then select the file, then select 0 for plotting orbitals.
The Mos for formaldehyde plotted in the same manner.
'https://github.com/atreyeem99/Multiwfn/blob/main/multiwfn_mo_comparison.pdf'

## Plotting NTOs:
For that as we open the filename.molden.input , we select 18 for Electron excitation analysis , then select 6 for NTOs then give the path for the output file, and then save the file as mwfn.
After that, we choose singlet or triplet to plot and follow the commands accordingly.

## Density distributions of hole and electron
Sr is preferred as its graphical effect is better
##
3 Functions
64
##  Setting up grid, plane and plotting region

- When program asking you to input the number of grid points in both dimensions, you can input such as 100,150, which means in dimensions 1 and 2 the number of grid points are 100 and 150, respectively, so total number is 100*150=15000, they   are evenly distributed in the plotting region.
- For “Relief map”, “Shaded relief map” and “Shaded relief map with projection”, commonly I recommend 100,100; if this value is exceeded, the lines in the graph will look too crowd. For other graph types I recommend 200,200. Of course the picture will become more pretty and smoother if you set the value larger, but you have to wait more time for calculation. Bear in mind that total ESP calculation is very time-consuming, you’d better use less grid points, for previewing purpose I recommend 80,80 or less.
# Measuring CT length of electron
18 is for electron excitation analysis
4 to calculate to CT index (delta r)
1-5 is for analysing all 5 excited states
y
4 is for 4th excited state
y
0.01 is the printing threshold


# calculation of orbital overlap integral
## Sr wave function integral
18 is for electron excitation analysis
14 is for calculating lambda index
1-5 is for analysing all 5 excited states
y
4 is for 4th excited state
y
0.01 is the printing threshold
# Plotting heat map of charge transfer matrix to intuitively understand nature of electron excitation
18 is for electron excitation analysis
8
1 for heat map

# Calculation of Mulliken atomic transition charges
18
12: Mulliken
3: transition fron GS to 3rd ES
