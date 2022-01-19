# Fusion Eagle converter 
Convert Fusion 360 schematic and PCB file compatible to Eagle 9.6.2 

## Problem 
Some use Fusion 360 as their electronic design tool, while some stick to older version of Eagle, like version 9.6.2. When a file goes from low version to high verision, everything works fine, but not the other way around. Unfortunately Eagle has difficulty open schematic or PCB file generated from Fusion 360: 
1. The opened file has all the devices there (from Design Manager), but the color is pure white (in schematic), or pure black (in PCB), invisible in both cases. 
2. To make matters worse, the ratsnest feature would result in error and the file won't open.  

## Solution
1. Clone the repo;
2. Replace the schematic and PCB file in the folder;
3. run ``convert.py`` from command line, enter the file name requested;
Now compatible electronic design files with suffix "-convert" will be generated. Eagle can open both files, although still with a few warning, and the color and ratsnest are set up correctly.   

## How it works? 
The Python script finds all layer and polygon definitions that Eagle 9.6.2 cannot understand and replaces them with either default layer color setting and reverts labels to definitions in the old version. 
