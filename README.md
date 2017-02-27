This repository contain three Python 3 scripts that can be used to **export starred locations in Google Maps to other formats** that can be imported on 3rd party GPS navigation apps. The three scrips are:

* json2kml: this script converts the list of starred/saved places (a.k.a. POIs) from Google Maps into a KML file that can be imported into various GPS navigation applications (suchs as MAPS.ME).

* json2csv: this script converts the list of starred/saved places (a.k.a. POIs) from Google Maps into a CSV (*Comma Separated Values*) file that can be imported into some POI convertion tools or edited directly in Excel.

* json2sygic: this script converts the list of starred/saved places (a.k.a. POIs) from Google Maps into the internal format used by Sygic Android to save its favorites ("items.dat") file.


## json2kml

This script depends on “SIMPLEKML” library (https://simplekml.readthedocs.io/) and it can be installed via pip with the following command line:

pip install simplekml

After this, the following steps must be executed:

1.	Go to Google Takeout (https://takeout.google.com/settings/takeout). 
2.	Click “Select None” and then select “Maps (your places)”. Make sure this is the only option selected.
3.	Google will export a ZIP file. Open this file and extract the file “\Takeout\Maps (your places)\Saved Places.json” to a directory in our PC (do not change the file name).
4.	Download the “json2kml.py” script (https://raw.githubusercontent.com/dmrsouza/json2kml/master/json2kml.py) and save to the same directory where you saved "Saved Places.json".
5.	Opent a command prompt, change the current directory to where the above files were saved, and run the script with the command line “python json2kml.py”
6.	The script will run and will create the file “Saved Places.kml”.

## json2csv

Documentation in progress...

## json2sygic

Documentation in progress... Some notes:

* In Android devices, Sygic saves the favorites into file "items.dat". This file is located in folder "/Sygic/Res/db" if Sygic is configured to use internal storage or in folder "" if Sygic is configured to use external SD card.
* This script creates a new "items.dat" file with all saved places from Google. This file needs to be copied to one of the above foldres.
* **IMPORTANT**: when overwriting "items.dat" files, **all current Sygic favorites** will be lost. Keep this in mind.

