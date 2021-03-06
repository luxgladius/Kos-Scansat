# Kos-Scansat

## What is it?
This is an addon for kOS to access the data provided by SCANsat.

## Requirements

* kOS
* SCANsat

## How to install

Unpack the .zip file in the GameData folder


## kOS Addon Functions:
 
* Basepath is **addons:scansat** 
* **\<geoposition\>** is the structure returned my latlng or vessel:geoposition
* **\<body\>** ist the structure returned my SHIP:BODY or Mun,Duna ect. not a String.

### API

**:CURRENTBIOME**

Name of the Biome at the vessels position. If the vessel is manned or the probecore has KerbNet biome access and is connected, 
the name is returned, even the spot was not scanned before by SCANsat

**:GETBIOME(\<body\>,\<geoposition\>)**

returns the name of the biome, when a biome scan was performed. with no biome scan: "unknown" 

**:ELEVATION (\<body\>,\<geoposition\>)**

Returns the scanned altitude of the coordinates. 
Rounded to 500m steps, when only the low-resolution scan was perfomred.
-1 when It's not scanned. And no KerbNet access is possible, or the KerbNet of the current Vessel is out of the scanning FOV. 

**:SLOPE (\<body\>,\<geoposition\>)**

Returns a computed slope (in percent) with the best available data. the input data is the best scanned data. KerbNet can be used as a source for the active vessel.

**:ALLSCANTYPES**

Displays all (not blacklisted) scantypes.

**:COMPLETEDSCANS (\<body\>,\<geoposition\>)**

returns a list of all performed scantypes for that spot.

**:GETCOVERAGE(\<body\>,\<scantype\>)**

Returns the completed percentage of the scantype of the body.

**:ALLRESOURCES**

Returns a list of the valid resources, which are known to scansat and activated by other mods

**:RESOURCEAT (\<body\>,\<geoposition\>,\<scantype\>)**

Returns the value (as a double) of and given resource at the spot.

**:GETANOMALIES (\<body\>)**

Returns a list of discovered anomalies at the given body.

