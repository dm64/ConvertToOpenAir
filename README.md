# Convert To OpenAir Tool #
Tool to convert a file containing a set of GPS coordinates to an OpenAir airspace file.mark
It creates an OpenAir airspace file with one of the following configurations:

- **Block**: creates a block of airspace defined by the task. Closes the airspace by joining the last point to the first
- **Ribbon**: creates an airspace strip or ribbon that follows the task line. The task line makes up the right hand boundary of the airspace (in the direction of travel).
- **Markers**: creates a marker at each point in the file. The marker shape can be one of: bow, circle (default), diamond or star

## Steps ##

1. Load the file containing the points to be converted.
2. Fill in the various parameters or if you are happy with the default values then carry on to step 3.
3. Click one of the 'Create Block', 'Create Ribbon' or 'Create Markers' button
4. A '.txt' file will be saved to your Download folder with same name as the task file and with 'block', 'ribbon' or the marker type added to the front
5. The OpenAir text will be displayed in the Airspace section. It can be copied from here.

## Parameters ##
### Points File ###
The following file types are accepted (based on the file extension):

- **.xctsk**: XcTrack Task File
- **.tsk**: XcSoar Task File
- **.wpt**: CompeGPS Waypoint File (note: other .wpt file formats will not work)

### Airspace Name ###
If not provided, it defaults to the name of the Points File if creating a Block or Ribbon. Not used for Markers

### Class ###
Enter the airspace class. Defaults to 'W' which shows as green on XcTrack

### Floor/Ceiling ###
The airspace floor/ceiling can be a entered in a number of different formats. It defaults to 'SFC' if not populated
eg. SFC, 100, 100ft, 100 ft, 100 Agl, FL 100, UNLIM etc

### <u>Additional Parameters for Airspace Ribbon</u> ###
### Width (km) ###
This is the width of the airspace strip in km. Only used if creating an 'airspace ribbon'. Defaults to 10km

### <u>Additional Parameters for Airspace Markers</u> ###
### Name Prefix ###
If supplied, markers will be named using this prefix with a sequential number at the end

eg. if Name Prefix = TR then the markers will be named: TR1, TR2, TR3 ...
If the Name prefix is not provided, markers will take the name defined in the Points file if it exists, otherwise they will use a prefix based on the marker shape (bow = BO, circle = CI etc).
      
### Radius (m) ###
Radius of the markers in metres if converting to a set of airspace markers. For markers that are not circles, this is the radius of the circle the marker is contained in.
Defaults to the cylinder radius defined in the Points File or 400m if no cylinders defined.
      
### Shape ###
Shape of the marker. It can be one of: bow, circle (default), diamond or star
    
