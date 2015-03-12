# Introduction #

The core of ADORE is written in bash. Therefore it is expandable by functions, scripts and external executables. This document explains what an Adore function/script is and how they are different from external executables.

## Internal ADORE Commands ##
These are bash scripts that use variables defined in ADORE environment. Therefore these commands will not work outside ADORE. They are sourced not executed.

These commands are usually located inside the folder: ${ADOREFOLDER}/scr/fun

### Examples for Internal ADORE Commands ###
check, dem, dem2slant2h, exclude, initialize, mask, raster, saveas, scenes, settings, and undo.

## External ADORE Commands ##
These are command line executables that are used in ADORE. Some of them are scripts and programs that were written before ADORE for DORIS processing, and some of them are executables from other researchers.

These commands receive all their inputs from the commandline, and they do not use any variables defined in ADORE environment. Therefore these commands can run outside ADORE.

These commands are usually located inside the folder: ${ADOREFOLDER}/scr

### Examples for External ADORE Commands ###
boundingBox.sh, km2deg.sh, lsprocess, modifyRes.sh, pn2rs, readDrs.sh, readRes.sh, rs2pn, setinterfarea.sh

## ADORE Functions ##
ADORE functions are bash functions that are defined in ADORE environment. These functions can only be used inside ADORE. Functions are generally used in ADORE scripts and internal ADORE commands, and can return multiple values.

These functions reside inside ${ADOREFOLDER}/scr/fun folder and generally have the .fun extension.

### Examples for the ADORE function files ###
functions, resfile.fun, plotting.fun

### Examples for ADORE functions ###
gnuplot\_baseline, dorisProcess2OutputFile, call, testFunction, strcmpi, getSystemEndianness, generateRandomString, canonicalPath, pp, p, s, checkInitialSettings, h

## ADORE Scripts ##
ADORE scripts are bash scripts that may require user modifications to work before they can be successfully executed. These are generally used for batch processing of interferograms with ADORE-DORIS. ADORE scripts have the .adr extension. These scripts generally use variables defined in ADORE environment, therefore they will not work outside ADORE.

These scripts can be found in the folder: ${ADOREFOLDER}/templates

Users will probably want to copy these files in their project folder before they make any changes.

### Examples for ADORE Scripts ###
baselines.adr, multiplePairs\_Parallel.adr, preparePsiInput.adr, singleMasterStack.adr, singleMasterStack\_Parallel.adr