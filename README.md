# PCB Drilling Optimizer
A script that optimizes the order of drilling holes on a PCB, so the this task will be faster

If you use a CNC machine to build your circuit board, you may end with the CNC machine taking so much time to drill the holes on the PCB because the order of the holes are not the best.

This script takes a drilling plan file (Created by your PCB layout software), and use some algorithm to define a better path for the CNC machine. It will save a new version of the drilling file, so you can keep using the same tools you already use.

Check this example of how this optimzation will save you time by removing useless movements from the CNC job

![Optimization example](https://raw.githubusercontent.com/aporto/pcb_drilling_optimizer/master/drill_optimize.jpg)

This script supports two algorithms for optimization, by solving the Traveling Salesman Problem:
* "fast" algorithm takes just a few seconds to create a good sequence of the holes
* "opt-2" algorithm may take several minutes to create a better sequence

In order to use the script, use the following command line
python drill_optimize <FULL_PATH_TO_DRILL_FILE> [ALGORITHM]

Where [ALGORITHM] is an optional argument, containing one of the previously referred algorithms. If no algorithm is defined, "fast" will be used

# Limitations of the current version
* Only supports Excellon file formats (Which are also supported by most PCB layout programs)
* Ignores different hole diameters (Different tools). All holes will be saved using the same tool (diameter)
