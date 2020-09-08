# hfs_fit
A python fitting program for atomic emission lines with hyperfine structure.

----Python modules and the versions the codes are written with----:

-python 3.6.9
-astropy 3.0
-numpy 1.18.1
-matplotlib 3.1.3
-pandas 1.0.2
-xlrd 1.1.0

Should work with newer versions.


----Files and explanations----:

example.py - basic usage.

fitLog.xlsx - parameters saved here when desired.

hfs_fit.py - Main script that makes use of others, contains class for spectrum, contains fitting, plotting algorithms.

interpolation.py - used for cubic spline interpolation when specified in hfs_fit.py.

LU.py - LU decomposition for interpolation.py.

matrixmult.py - matrix multiplication for LU.py.

relInt.py - routine to calculate relative intensities of HFS components, used by hfs_fit.py.

spectrum.txt - a small portion of an UV Co II spectrum with 4 Co II lines.

fits - folder containing saved plots.


----Useful functions and Notes----:

-Can plot transition diagram with components using the LineFig() method in the hfs class. nInterp argument for this is the number of points to artificially add to make lines smooth if you wish, 1 for no interpolation (default). The spacing between things may not be perfect, most of the time the level label will overlap with a level line, can change this by changing the location of the texts from lines 678-681. 

-Can plot spectrum with components using the PlotSpec() method in the hfs class, put a wavenumber in the bracket and it will plot around that wavenumber.

-Use hjw() of hfs class to half all jumpwidths before Optimise(), this is convenient when performing the final optimisation of parameters, or if the initial guess is very good.

-Can always re-open the sliders plot with PlotGuess() method of the hfs class. If the sliders don't work, try closing and opening it up again (this happens sometimes in iPython).

-Can also add points for smoothing during fitting, to do this change the nInterp value in the WNRange() method of hfs and re-import hfs.

-HFS components are ploted by default, can turn this off using PlotGuess(components = False)

-The reset button of PlotGuess() doesn't seem to work in iPython.

-If the instrumental profile is negligible, put icut at the maximum value.

