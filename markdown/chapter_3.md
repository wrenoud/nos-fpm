Chapter 3
===========
Data Acquisition
================

3.1 Sensor Risk Management
---------------------------

NOAA field units deploy valuable oceanographic sensors in the water when conducting hydrographic surveys.
The sensors are typically deployed in a variety of ways including: mounted directly on the hull of the survey
vessel, suspended in the water by mounting them to a rigid retractable pole, towed via a cable, and temporarily
installed on shore.


### 3.1.1 Best practices for preventing loss of equipment

The utmost care should be taken to prevent the loss of a hydrographic sensor prior to its deployment. This is
accomplished through regular inspection of all key components of survey systems, proper preventative
maintenance, safe operation procedures, and adequate precautionary measures to aid in recovery if a loss does
occur.

All mounting hardware should be inspected regularly (weekly inspections are recommended) for defects or
potential loosening. It is useful to mark mounting hardware, such as screws and bolts, with a reference mark to
indicate whether the fasteners are backing out and becoming loose. Components that are susceptible to degradation
in marine environments such as rubber isolation mounts or metal fasteners prone to oxidation should be checked
regularly for material condition. Routine inspection of mounting hardware and components for any sensor system
should have an established inspection schedule that is determine by the likelihood of system loss. A period of no
more than 1 week between inspections is recommended.

If available, safety devices designed to prevent the loss of a sensor (i.e. a safety cable attachment) or aid in the
recovery of a sensor (i.e. a pinging locator beacon) should be used at all times. These devices and associated
components should be checked regularly (weekly inspections are recommended) for material defect, damage, or
disengagement of fastening components. In the case of a system that is deployed over the side and is not statically
mounted, the safety system should be checked before every deployment of the sensor. Fixed mounted sensor’s
safety systems should be checked on a regular basis in the same manner as the mounting hardware.

If possible, the sensors should be stowed for transit (i.e. SSS tow-fish secured on deck, swing arm multibeam in
the retracted position, etc.) when not in use.

Whenever the launch is operating with sensors in the water (which may be at all times in the case of a fixed mount
sensor array) the sensors should be operating and the vessel’s navigation system should be recording data. If the
sensor is not operational and not being actively monitored, the loss could occur without being noticed. Additionally,
an accurate position for the vessel at the time of loss is extremely important in locating the sensor if a loss should
occur.

*Page 63*

------------------------------------------------------------------------------------------------------------------------

Dual frequency GPS base stations may be installed for up to 30 days in a variety of locations. Once installed it is
important to ensure that the antennae are not disturbed or moved for the duration of deployment. Antennae should
be secured in such a way that wind and rain or snow events will not move the antennae. GPS receivers as well as
batteries and radio electronics should be enclosed in a weather proof, locking case. Care should be taken to stage
this equipment in secured areas (whenever possible) to prevent vandalism or theft. If the base station is installed
in a remote location, the user should be aware of natural conditions (such as wildlife) that may disturb the
installation and take action to prevent damage or loss.


### 3.1.2 Best practices for recovery of lost equipment

While the guidance outlined in section above are intended to prevent sensor loss, a loss may still occur. In the
event of a sensor loss, the probability of recovery can be maximized by (1) rapidly informing the ship of the
potential loss, (2) determining if the sensor might still be connected to the launch, (3) determining an accurate and
precise location where the loss occurred, and (4) utilizing all available search and recovery means to locate the
sensor as soon as possible. Details for each item are below.

Once a loss is suspected, the entire survey crew should be informed so that appropriate action can be taken. The
ship should be notified immediately as they can provide additional guidance on the proper course of action and
dispatch assistance. The loss of a sensor with mountings that go through the hull could represent a catastrophic
failure in hull integrity. It is important that other vessels be made aware of the situation so that response can begin
immediately.

The vessel should immediately come to a gentle stop as the sensor may still be attached by a safety tether or
electrical cabling. The vessel should avoid transiting at speed until it is confirmed that the sensor is not still
attached. If possible, divers should enter the water and examine the sensor mounting to determine if the sensor is
still attached by any means. If the sensor is held in place by cabling or a safety tether, it should obviously be
retrieved. However, if retrieval is not feasible (i.e. dangerous conditions, insufficient equipment, etc.) or is
determined to be too risky (i.e. launch is in water too deep for dive recovery if the sensor should become
disconnected) then the dive team should secure it as best as possible and the launch should make its way at slow
speed to a more appropriate recovery location (i.e. the ship or shallow water). If it is not possible to use divers to
investigate, the launch should transit at slow speed back to the ship or other area of safety, where an inspection of
the sensor mounting can be performed.

As soon as a loss is suspected, the position of the survey launch should by marked in the acquisition system if
possible or noted via GPS coordinates or, at the very least, roughly plotted on a chart. A successful recovery of the
sensor is dependent on having an accurate location to begin the search. Marking this location, even if approximate,
at the time of the loss will greatly increase the chances of locating the sensor subsequent to its loss.
Alternately, if the navigation data was logged, the position for loss can likely be determined through analysis of
the data. For instance, logging POS data throughout the day will allow post processing in the POSPac software
suite to generate a smooth best estimate of trajectory (SBET) for the launch, which will provide an extremely
accurate track-line. If the sensor package was recording at the time of loss, the exact time of disconnection should
be easily determined and coupling this time with the accurate track-line data for the launch will result in an exact
position for sensor loss. If the sensor was not recording when lost, it is still possible to determine the approximate
time of loss by examining the HYPACK log file, which will generate an error message when the data string from
the sensor is lost. There is approximately an 8 second time lag between disconnection of a sensor from HYPACK
and the data timeout error being entered in the log (note that this timing latency may vary with different sensors).
If you are unsure of the timing latency and a similar instrument set-up is available, it may be useful to experiment
with error log time to determine the latency.

*Page 64*

------------------------------------------------------------------------------------------------------------------------

Once a position for the loss is determined, the search and recovery operation for the sensor should begin. It is
imperative to begin the search operation as soon as possible after the loss to increase the probability of locating
the sensor. All available means should be used to conduct the search. If located, the likelihood of recovery is good.
Search mechanism should be determined based on depth of search area and bottom type. Multibeam is of limited
use in locating objects smaller than a meter, unless in relatively shallow water. A side scan tow fish may provide
the best chance of detecting the sensor. If other survey vessels are operating in the area it could be possible to
immediately survey the area with multibeam or side scan sonar for any indication of the lost sensor. A diver search
and recovery is the best way to locate and recover the sensor. In water where diving is not possible or practical,
an ROV can be very useful for locating small objects, such as a sensor.

3.2 Bathymetry Acquisition
---------------------------

NOAA hydrographic field units primarily use two types of echosounders to acquire bathymetry data:, multibeam
echosounders (MBES) and vertical beam echosounders (VBES). This section is dedicated to operating echosounder
systems and recording sonar data using common software packages.


### 3.2.1 Lead Line Data

A lead line can be used to measure depths in areas too shallow for echosounders, to verify least depths over
dangers to navigation or shoals, and to calibrate echosounders. Lead line soundings should be acquired at slack
current, if possible, to ensure that readings are true vertical measurements of depth. All lead line soundings should
be clearly identified as such in the survey records. The hydrographer shall also, at a minimum, record the lead line
number, geographic position, and time of measurement for each sounding. Water level correctors must be applied
to lead line data during post-processing.


### 3.2.2 Sounding Pole Data

Sounding poles can be used to acquire data in near shore areas where depths are less than 4 meters. Sounding
poles should be carefully deployed so that a significant amount of sediment penetration does not occur and a true
vertical measurement of depth is obtained. Each pole sounding should be clearly identified as such in the survey
records. The hydrographer shall also, at a minimum, record the sounding pole number or identifier, geographic
position, and time of measurement for each sounding. Water level corrections must be applied to sounding pole
data during post-processing.


### 3.2.3 Vertical Beam Echosounder (VBES) Data

Vertical beam echosounder systems may vary among NOAA hydrographic field units. Most OCS systems are dual
frequency, using both a high and a low frequency, with beamwidths between three and eight degrees for high
frequency, larger for low frequency (20-30 degrees). Provided the magnitude of vessel roll and pitch is less than
the sonar beamwidth, these attitude characteristics will have little effect on sounding accuracy and their application
to VBES data is not required by OCS. However, to maintain data quality in sea states where vessel roll and pitch
angles exceed sonar beam width, OCS recommends that an external sensor be used to record heave data for
application during post-processing. If a heave sensor is not employed, the VBES system should be used only
when conditions are favorable for minimizing heave bias and data must be scanned for heave artifacts during postprocessing. Data acquisition should be suspended if the heave signature exceeds 0.5 meters and a heave sensor is
not being used.

*Page 65*

------------------------------------------------------------------------------------------------------------------------

Many VBES systems output calculated depth values rather than the two-way travel time of each sonar ping. To
facilitate internal depth calculations, these types of VBES systems must be configured with an estimated value for
the speed of sound through the water column. When necessary, hydrographic field units shall configure VBES
systems using 1500 m/s, the standard estimate for the speed of sound in sea water. VBES data shall then be
corrected using a full sound speed profile during post-processing.

Note: Sonar manufacturers often suggest applying real-time attitude, sound speed, and other corrections during
data acquisition. It is OCS’s standard policy to apply such data corrections during post-processing if possible.
The HYPACK software package is commonly used by NOAA hydrographic field units to acquire VBES data.
OCS guidelines for using HYPACK with VBES systems are described below. Users should also refer to the
HYPACK systems incompatible with HYPACK should consult the appropriate user’s manuals and/or contact the
regional HSTP Field Support Liaison for guidance.


#### 3.2.3.1 HYPACK

HYPACK is produced by HYPACK, Inc. This software is compatible with most types of VBES systems and can
also be used for MBES data acquisition, as discussed in section 3.2.4.1 In addition to recording bathymetry data,
HYPACK includes capabilities for completing the following tasks:
* Survey preparation and line planning.

* Precise survey line navigation.

* Recording of supporting sensor data such as position, heading, and attitude.

* GPS coordinated time-tagging of sonar and supporting data.

* Display of geo-referenced images as background files during acquisition.


##### 3.2.3.1.1 System Setup

To record, or “log,” data using HYPACK, a Project must first be created. Separate HYPACK Projects are typically
created either for each survey or for each data type to be acquired. Be certain to save each newly created Project
with a unique name, or all changes will be lost when another Project is loaded. Critical steps for Project creation
are described below. Once saved, Projects can be loaded and changed as necessary.


###### 3.2.3.1.1.1 Device Setup

For each Project, the hydrographer should assign a default Device Setup that includes drivers and recording
settings for each sensor. Since data formats can vary drastically and HYPACK manages data for numerous sensors,
it is critical that the correct Device Setup be loaded for each type of sensor being used. If a Project’s default
Device Setup is incorrect for the systems being used, a different Device Setup can be loaded after the Project has
been opened. Although creating a Project for each survey seems well organized, having a Project for each data
type may better ensure that the correct Device Setup is used for data acquisition if multiple configurations will be
needed for a single survey. OCS recommends that master Device Setups for each system configuration be backedup to a removable disk and maintained by the FOO or equivalent.

*Page 66*

------------------------------------------------------------------------------------------------------------------------

As a general rule, no offsets should be entered in the HYPACK Device Setup. It is OCS’s policy to record survey
data in the most “raw” form possible, then apply corrections and offsets during post-processing. One exception to
this rule is transducer offsets. Transducer offsets entered in HYPACK will not be applied to recorded data.
However, they will affect the displayed data and may be desirable for precise line-steering, particularly if offsets
are large as with a side-mounted system.


###### 3.2.3.1.1.2 Geodesy

Default geodesy parameters should be set for each Project. All OCS hydrographic survey data shall be acquired
in the North American Datum of 1983 (NAD83). This is accomplished in HYPACK by selecting the GRS80
ellipsoid and appropriate UTM zone.


###### 3.2.3.1.1.3 Line and Background Files

Planned survey line files and any associated background files, such as charts and limits, should be loaded for each
Project. HYPACK is capable of reading these files from any local computer directory as well as across a network.
However, it is recommended that all Project files be stored within the local HYPACK Project directory. This file
management strategy is easily implemented by using the File &gt; Add File and Copy option when initially loading
Project files, which will automatically copy each file to the current HYPACK Project directory.


##### 3.2.3.1.2 Recording Data

Prior to recording survey data in HYPACK, certain critical system settings and operations should be verified.
These quick system checks are highly recommended by OCS, as they can prevent errors that require extensive
editing or complete reacquisition of data.


###### 3.2.3.1.2.1 Time Synchronization

Through the Kinematic.dll device driver, HYPACK uses an internal timing algorithm called “Veritime” to time
stamp data during acquisition. Veritime synchronizes the time recorded in the raw data to UTC time from the GPS
system, and will also automatically reset the acquisition computer clock to UTC time. By default, Veritime will
determine UTC time from the GPS receiver’s NMEA0183 ZDA message. Thus, the hydrographer must ensure
that this ZDA message is being output by the GPS unit. Note: HYPACK provides an option to “Sync clock on
other sentences than ZDA.” This option is not recommended by OCS and should not be used for OCS survey data
without first contacting the regional HSTP Field Support Liaison. Time is a critical component of survey data, and
it is recommended that the hydrographer periodically verify that time stamps are being applied correctly to logged
data.


###### 3.2.3.1.2.2 Devices Test

Once all survey sensors are operating, the user should test that sensor data are being properly received by HYPACK.
By navigating through the HYPACK Hardware program, the user can “Test All” devices. This function opens a
new window for each sensor in the current Device Setup. Data strings being received by HYPACK will be
displayed for each device. Although data strings can be complex, the expected data from each sensor should be
easily identifiable somewhere in the datagram. Two common problem indicators during this test are either no data

*Page 67*

------------------------------------------------------------------------------------------------------------------------

or a string of gibberish being displayed. No data being displayed is often indicative of sensor or cable failure,
while gibberish frequently means that the sensor output baud rate does not agree with the receiving baud rate
setting in HYPACK.


###### 3.2.3.1.2.3 Logged Data Paths

By default, HYPACK will log survey line data under the active HYPACK Project directory in a folder named
“Raw”, and target files will be recorded to a file in the format mmddyyyy.tgt created in the Project directory.
However, each field unit will have a standard directory structure to which data and targets should be logged. It is
important for the user to check “Override Project Path” (in SURVEY mode under Options &gt; Project Information)
and select the appropriate folder for both survey line data and target file data prior to beginning daily data
acquisition. Using this option, survey and target data may be logged anywhere on the local system or across a
network.

Additional point data can be appended to a target file by pre-loading an existing target file. Pre-loading is
accomplished in the primary HYPACK window by copying files into the “Target Files” folder, a process similar
to loading planned survey line files. Target files can also be loaded as Chart Files (background data) in SURVEY
mode, but these targets will be simply displayed on the screen, i.e., it will not be possible to select a target and see
a range and bearing to it for use in navigation.


###### 3.2.3.1.2.4 File Extensions

Unless otherwise specified, VBES data will be automatically recorded with the file extension *.raw. However, it
is OCS standard policy to log HYPACK VBES data with a Day of Year (DOY) file extension. Note: HYPACK
erroneously terms the DOY format as “Julian Day”. In SURVEY mode, the “Julian Day as Extension” option
should be chosen under the Options &gt; Project Information menu to create files with DOY extensions.


### 3.2.4 Multibeam Echosounder Data

NOAA hydrographic field units typically use swath systems which produce multiple acoustic beams from a single
transducer and measure both the angle and two-way travel time of the acoustic signals. The frequency of the
signal varies from system to system and typically ranges between 12 and 455 kHz. During each sonar ping, a
projector transmits a swath of acoustic energy into the water and reflected energy returns to the transducer where
it is detected by a hydrophone.

Swath MBES systems may be capable of two different scanning modes: (1) Equidistant and (2) Equiangular.
The equidistant mode electronically forms the center of each footprint at a uniform distance from each other
across the swath width. This even sampling across the swath width reduces the amount of overlapping coverage
and intensity of returns in the inner half of the swath in effort to improve resolution in the outer beams. This is not
recommended for hazard investigation surveys because of weak, lower resolution inner beams. Another
disadvantage of this mode is that it reduces the received signal aperture of the outer beams thus reducing the
possibility of detecting distant returns.

*Page 68*

------------------------------------------------------------------------------------------------------------------------

The equiangular mode electronically forms the receiving beams in equal angles. This means in the outer beams
the beam footprint increases in length across-track providing bottom coverage across the entire swath width. The
advantage of this mode is the overlapping coverage of the inner half of the swath, excellent for hazard investigation
surveys where precise measurements of small targets are necessary. The primary disadvantage is the lower
resolution in the outer beams. To maintain equal resolution across an entire survey area, survey lines must be
planned for at 100% overlap (outer beam matching the nadir of the adjacent lines).

NOAA hydrographic field units have mounted MBES systems using a variety of methods, but these configurations
can be classified into one of two basic types: hull-mounts and pole-mounts. Each type of sonar mount has inherent
benefits and potential problems that should be considered during data acquisition.

A hull-mounted system is generally very stable, producing data with minimal noise due to vibration. A hullmounted
configuration can be accomplished by notching the vessel keel and installing the sonar head along the keel line,
attaching a mounting plate for the sonar head to the vessel hull, or cutting a box into the hull and creating a
retractable mount for the sonar head. The flow of water along a vessel hull can create air bubbles, which may
cause noise in a hull-mounted system. This problem should be considered when designing a hull-mount system.
Note: The aforementioned retractable mounting system is essentially a hybrid of a hull-mount and a polemount.
Benefits and drawbacks associated with each type of configuration should be considered when designing and
installing such a system.

A pole-mounted system is often the quickest and least intrusive mounting configuration. In its simplest form, the
sonar head is mounted to a large pole that can be pivoted into the water during data acquisition, then pivoted back
out and secured to minimize drag during transits. When using a pole-mounted system, it is critical that the sonar
can be both reliably deployed to a repeatable position (with respect to the vessel reference frame) and adequately
stabilized during data acquisition. Pins or guy-wires are often used to help with system stabilization. Noise due to
vibration of the mounting pole at certain vessel speeds is a common problem with pole-mounted systems.
Many MBES systems are capable of recording acoustic back-scatter data. Multibeam backscatter is intensity data
that can be processed to create low resolution imagery. Backscatter is co-registered with the bathymetry data and
is often used to assist with bathymetric data interpretation and post-processing. To optimize a system for backscatter
data quality, refer to the manufacturer’s documentation. However, the hydrographer should be cognizant that
adjusting a MBES system to enhance backscatter data may detrimentally affect bathymetry data
quality.

Auxiliary sensors are normally used for acquiring data to correct MBES soundings for vessel attitude, position,
and sound speed. Time synchronization of all sensor inputs is critical when acquiring MBES data, and there are
several methods which can be used to accomplish this. If using a flat-faced MBES transducer array, it is also
critical that sound speed be measured at the face of the transducer for beam forming and beam steering. For this
type of system, a surface sound speed measuring instrument should be mounted at the sonar head, and its data
input directly to the sonar processing unit.

The HYPACK/ HYSWEEP software package is commonly used by NOAA hydrographic field units to acquire
MBES data. OCS guidelines for using HYPACK/HYSWEEP with MBES systems are described below. Users
should also refer to the HYPACK User’s Manual which can be found on the Hydrosoft website. Field units
equipped with alternate software or systems incompatible with this software package should consult the appropriate
user’s manuals and/or contact the regional HSTP Field Support Liaison for guidance.

*Page 69*

------------------------------------------------------------------------------------------------------------------------


#### 3.2.4.1 HYPACK / HYSWEEP

HYSWEEP is an additional module available for the HYPACK software package discussed in section 3.2.3.1 of
this manual. HYSWEEP enables the hydrographer to record both MBES and SSS data, and runs simultaneously
with HYPACK. The HYPACK base program enables precise survey line navigation for MBES operations. Many
of the procedures required for VBES data acquisition in HYPACK also apply to MBES and SSS data acquisition
using HYSWEEP.

Basic information for using the HYSWEEP software module is provided in this manual. For more detailed
information about the HYSWEEP program, refer to the HYSWEEP User’s Manual, which can be found on the
Hydrosoft website.


##### 3.2.4.1.1 System Setup

System setup for HYSWEEP consists of adding MBES system devices in the HYSWEEP Hardware configuration
to enable communication with the sonar system and the HYPACK parent program. Note: HYSWEEP software
can not be used to manipulate the sonar system settings. Any sonar setting changes must be performed using the
sonar manufacturer’s software interface. The HYSWEEP Hardware menu is accessible through the HYPACK
Hardware menu. No vessel or hardware offsets should be entered in HYSWEEP, as it is OCS’s policy to apply
corrections and offsets to data during post-processing. Additional devices may also be added to the HYPACK
hardware configuration for displaying multibeam data (nadir depth and matrix data) in the HYPACK survey
window. Refer to Appendix 3 for detailed instructions for the standard setup of HYPACK and HYSWEEP devices
(HYSWEEP Device Setup SOP.pdf).

To record data using HYSWEEP, a Project must exist in HYPACK. HYPACK Project creation is discussed in
section 3.2.3.1.1 . Be certain to save each newly created Project with a unique name, or all changes will be lost
when another Project is loaded. HYSWEEP files will be recorded to the same directory selected in HYPACK.


##### 3.2.4.1.2 Recording Data

Recording data using the HYSWEEP module of HYPACK is nearly identical to logging data directly in HYPACK,
as described in section 3.2.3.1.2 . Typically both programs are run simultaneously. Data logging can be controlled
in either the HYPACK or the HYSWEEP program using the same commands and keyboard shortcuts. The two
survey programs will begin/end logging simultaneously when a record or stop recording command is given in
either one.

For OCS hydrographic surveys, HYSWEEP data shall be logged in ASCII HSX (HYSWEEP Survey Extension)
format. While logging data, the HYSWEEP main survey window should be used to monitor logging and device
alarms. MBES or SSS data can be displayed and monitored in real-time using windows selected under the View
menu. Range scales for depth and beam width are accessed under the View &gt; Options menu, and must be set to
the appropriate values according to expected water depth or data will not be displayed in the survey windows
(though it will still be logged). Multibeam display options, quality control tests, coverage map settings, and heave,
pitch, and roll correction options are also accessed under View &gt; Options menu. Note: the option to “Apply
Heave, Pitch, and Roll Corrections” is used for display purposes only, and will not affect the raw recorded data.

*Page 70*

------------------------------------------------------------------------------------------------------------------------


### 3.2.5 Diver Least Depth Gauge (DLDG) Data

A Diver Least Depth Gauge can be used by NOAA hydrographic field units to determine or verify the least depth
of a feature. Depth is determined by comparing a pressure value at a feature’s least depth to a surface pressure and
correlating this difference to water depth based on the local water density. For more detailed DLDG information,
refer to the document DLDG.pdf in Appendix 3.

At each dive site, a surface DLDG pressure must be recorded. OCS recommends taking a surface reading both
before and after the dive, then averaging the two surface values for post-processing. Divers should survey the
entire feature to identify the point of least depth. Once the least depth point is located, the DLDG should be placed
level with this point and a pressure reading determined. Pressure values will vary with surface sea action, so a
value eye averaged over a period of a few seconds should be recorded. A buoy marker should then be moved to
the point of least depth so that a DGPS position can be obtained from the surface. If time permits and the item is
complex, it is beneficial to record dimensions and make a quick sketch, noting the point of least depth. At the
conclusion of the dive, a sound speed profile must be conducted in the vicinity using a Sea-Bird SEACAT profiler
to determine local water density. Using a SEACAT system enables the DLDG pressures to be processed with
Velocipy software.

3.3 Acoustic Backscatter Acquisition
-------------------------------------

NOAA hydrographic field units use a variety of sonar systems to acquire acoustic backscatter data. Side scan
sonars (SSS) collect backscatter imagery and are preferred for their object detection capabilities. MBES systems
can record seafloor acoustic backscatter data that are collocated with their range and angle measurements. Although
acquisition of seafloor acoustic backscatter may be required in the project instructions and processed MBES
backscatter may assist with determination of seabed characteristics when planning bottom sample operations, it
does not meet OCS object detection criteria for hydrographic surveys. While it is also possible to collect water
column backscatter with MBES, collection of this data is not expected or discussed further.


### 3.3.1 Side Scan Sonar (SSS) Data

Side scan sonar systems and configurations vary among NOAA hydrographic field units. Traditional SSS
operations consist of a sonar body, or “towfish,” which is towed behind a vessel via a cable and winch system.
During operations, transducers located on each side of the towfish emit an acoustic signal that ensonifies a wide
swath of seabed. The frequency of the signal varies from system to system, typically ranging between 100 and 500
kHz. Lower frequencies will increase the maximum range scale of a SSS, but imagery quality and resolution
increases with higher frequencies. The amplitude of returning echoes from the seafloor are recorded and georeferenced based on the return time series. The intensity of the SSS return signal will also be affected by the
acoustic reflectivity of the sea floor. For example, rock and metal objects are better reflectors than sand or mud. If
the seafloor is flat, the return signal will include amplitude values at regular intervals along the entire range scale.
However, if a scour is present or an object is elevated from the sea floor, a portion of the return signal will be
irregularly spaced in time. This interruption causes an acoustic shadow, or a lack of return signal, along a portion
of the range scale. This basic side scan sonar theory of operation is illustrated in Figure 3.1.

*Page 71*

------------------------------------------------------------------------------------------------------------------------

Figure 3.1: Basic side scan sonar theory of operation
Side scan systems are typically towed at depth to increase sonar grazing angles and object detection capability.
For optimum object detection, OCS requires maintaining a towfish height of 8-20% of the operating range scale.
NOAA’s hydrographic field units effectively use both towed and hull-mounted SSS configurations. Each type of
configuration has inherent benefits and potential problems that should be considered during data acquisition.
In towed configurations, towfish height is controlled by a combination of vessel speed and cable out. Although a
towed configuration will maximize object detection abilities in various water depths, a certain amount of
positioning error is inherent in any towed system. Because of this additional error source, SSS data are rarely used
for final positioning of a feature. For hull-mounted configurations, position data are more accurate and operations
can be conducted safely and effectively in shallow waters. However, since a hard-mounted system can not be
lowered into the water column, sonar grazing angles will be directly affected by the water depth. As depth
increases, object detection capabilities will decrease. It may not be possible to meet object detection criteria in
deeper waters with a hull-mounted configuration.

Note: When operating a towed SSS system, towfish height should be carefully monitored. If a sonar grounding is
imminent, increasing vessel speed will typically raise the towfish.

SonarPro software is commonly used by NOAA hydrographic field units to acquire SSS data. OCS guidelines for
using SonarPro is described below. Users should also refer to the SonarPro Operation Manual, which can be found
on the Hydrosoft website. Field units equipped with alternate software/systems incompatible with this software
package should consult the appropriate user’s manuals and/or contact the regional HSTP Field Support Liaison
for guidance.


#### 3.3.1.1 SonarPro

SonarPro, is a comprehensive software package compatible with the Klein 5000 Multibeam & Klein 3000 Dual
Frequency SSS systems. In addition to display and recording of SSS data, SonarPro includes a capability for
managing sonar targets which is useful when performing emergency response surveys. Detailed information
about SonarPro can be found in the SonarPro Operation Manual.

*Page 72*

------------------------------------------------------------------------------------------------------------------------


##### 3.3.1.1.1 System Setup

Since SonarPro is specifically designed to operate with Klein System 5000 and 3000 side scan sonars, system
setup requirements are minimal. Klein System 5000 and 3000 sonars must be booted using a program called
vxWorks. (OCS recommends that the boot process be monitored using a HyperTerminal connection between the
acquisition computer and Klein TPU.) The vxWorks program will differ depending on which sonar system is
being used (5000 or 3000), allowing SonarPro to automatically detect and configure for the type of system to
which it is connecting.

Note: If using both 5000 and 3000 systems on the same acquisition system, be certain that the vxWorks file
corresponding to the current system configuration is loaded in the “klein” directory before booting the sonar.


##### 3.3.1.1.2 Recording Data

Once the SSS has been booted, SonarPro software should be started (or if already running, select the towfish
button from the main SonarPro display window to connect to the sonar). The user will be prompted to enter the
Klein TPU Internet Protocol (IP) address to establish a connection between the acquisition computer and the
sonar system. After creating a connection to the TPU, a Survey Wizard window will open that can be used to set
up a data logging directory and target parameters. (The wizard may also be bypassed and accessed later from the
main tool bar.) SonarPro will automatically display a Sonar Viewer window with SSS waterfall and towfish
controls allowing the operator to start and stop the sonar from pinging. Once the operator is satisfied with the
primary system setting choices, he/she should save the session by executing the Save State-Registry option under
the Sessions menu. Saving State-Registry will cause SonarPro to open in this configuration the next time the
software is opened.


###### 3.3.1.1.2.1 Towfish Setup

Towfish setup is accessed through the Towfish button in the Sonar Viewer window. OCS recommended setup
values are listed in Table 3.1. When conducting standard OCS hydrographic surveys, the most efficient SSS range
scale should be used, as described in section 2.5.3.1.2 . SonarPro will automatically select an optimal pulse length
for the user defined range scale.

Sonar Setting

High Frequency

Low Frequency

Sonar Range

Set for maximum efficiency according
to depth

Set for Maximum efficiency according to
depth

Pulse Length
Despeckle Sonar Image
Sonar Resolution
Side Scan System State
TPU Responder Control
Responder Frequency
Towfish Speed
Speed of Sound

Default
Default
Off
Off
Normal
Normal
Default
Default
Off
Off
28.5
28.5
Determine by GPS
Determine by GPS
150000 cm/s
150000 cm/s
Table 3.1: Recommended Towfish Setup

*Page 73*

------------------------------------------------------------------------------------------------------------------------


###### 3.3.1.1.2.2 Cable Out and Layback

The Cable Out window is accessed either using the Cable Out button or from inside the Layback window by
selecting the External Cable Out Source button. Cable out values can be entered manually or automatically
through external cable out sources.

Note: When entering manual cable out, new values will not take effect until the user clicks the “Apply” button.
The cable out source and settings will vary depending on the system configuration. The operator should verify that
Sonar Pro is reading the correct cable out values before logging data.

The hydrographer may want to enter vessel layback parameters (i.e., offsets from the navigation source to the
sheave) so that SonarPro can generate accurate real-time positions for targets. Entering these offset values is
important when investigating targets on the fly, such as during emergency response surveys. Vessel layback
parameters are accessed through the Layback button in the SonarPro window. Save and apply the layback
parameters by selecting the “Store Layback Parameters” button.

Note: Entering layback offset values will only affect the calculated positions of targets selected during acquisition.
Logged vessel navigation will not be affected, and towfish position should be calculated during post-processing
in CARIS.


###### 3.3.1.1.2.3 Data Display

Individual data display windows can be selected from the Window tab of the main SonarPro screen. If using a
Klein 3000, separate SSS Sonar Viewer windows should be opened to display both low frequency (100 kHz) and
high frequency (500 kHz) data. Since high frequencies provide higher resolution data, this data should be viewed
in the primary display window. However, low frequency data should also be monitored as it may pick up features
missed by the high frequency.

The user may want to display charts in SonarPro for navigation purposes. For the navigation window to work
properly, the user must first copy the desired *.BSB and *.KAP raster chart files to the sub-folder designated for
charts (commonly labeled Maptech) during SonarPro installation. It is recommended that only the charts needed
for a given work area be maintained in the chart folder to minimize software loading time. Note: If attempting to
display multiple charts, the charts must all have the same projection. Skewed raster charts will not display in
SonarPro.

SonarPro provides two types of informational alarms, towfish altitude and towfish roll. It is strongly recommended
that the towfish altitude alarm be set to visually and (if possible) audibly alert the user when this value falls below
5 meters. Towfish roll is a less critical value, and this alarm can be used at the hydrographer’s discretion.


###### 3.3.1.1.2.4 Data Logging

SonarPro provides the option of logging SSS data in either *.XTF format or Klein’s proprietary Sensor Data
Format (*.SDF). OCS’s standard policy is to log SonarPro data using the *.SDF format. The *.SDF format logs
vessel position and cable out values, but not towfish position. A towfish position will be calculated during postprocessing in CARIS. To begin logging *.SDF data, select the Record SDF button in the Sonar Data Recorder
window. Maximum file size is set by specifying the maximum number of minutes per disk file in the data logging
window. A maximum file size between 30 and 45 minutes is recommended based on field unit experience.

*Page 74*

------------------------------------------------------------------------------------------------------------------------

Note: If using HYPACK software for vessel navigation and logging bathymetry data, HYPACK and SonarPro
must be started and stopped independently.


### 3.3.2 Multibeam Echosounder Seafloor Backscatter

The acquisition of multibeam echosounder seafloor backscatter may be required in the project instructions. MBES
backscatter may be used to supplement hydrographic data for non-charting purposes. See section 6.2 of the HSSD
for further instructions on MBES backscatter requirements in Appendices 4 for standard operating procedures on
processing MBES backscatter data.

3.4 Position and Attitude Data
-------------------------------

NOAA field units often measure position and attitude data using a single piece of equipment, the POS/MV
(Position and Orientation System for Marine Vessels), manufactured by Applanix. Alternately, a combination of
systems may be used to measure position, heading, and heave/pitch/roll individually.


### 3.4.1 Applanix POS/MV

The Applanix POS/MV is a GNSS-aided Inertial Navigation System. It consists of two dual-frequency GNSS
receivers, an Inertial Measurement Unit (IMU), and a POS Computer System (PCS). The IMU and GNSS receivers
are complementary sensors; data from one are used to filter and constrain errors from the other, resulting in high
accuracy position and heading data. AGNSS Azimuth Measurement Subsystem (GAMS) is used to aid the POS/
MV in determining heading. GAMS heading aiding increases the system’s achievable heading measurement
accuracy, independent of latitude or vessel maneuvers. Additionally, the IMU senses linear acceleration and
angular motion along the three major axes of the vessel to determine heave, pitch, and roll.

POS/MV Controller software allows the user to interact with the PCS for purposes such as performing calibrations
and monitoring data accuracy. When acquiring data for OCS hydrographic surveys, POS/MV User Accuracy
parameters shall be set such that the error values identified in Table 3.2 are not exceeded. If these User Accuracy
parameters can not be met, the field unit shall contact the regional HSTP Field Support Liaison for guidance.

Data Parameter
Maximum Allowable Error
Attitude (Roll/Pitch)
0.05 degrees
Heading
0.05 degrees
Position
2.5 meters at 1 sigma
Velocity
1.0 m/s
Table 3.2: Maximum Allowable POS/MV Error for OCS Surveys
The POS/MV Controller Program should be monitored continuously during survey data acquisition to ensure that
the system is functioning properly and accuracy parameters are not exceeded. Occasionally, GAMS will experience
difficulty determining heading parameters. Three common GAMS problems and corresponding solutions
recommended by Applanix are described in Table 3.3.

*Page 75*

------------------------------------------------------------------------------------------------------------------------

POS/MV Symptom

Cause of Problem

POS/MV heading is correct within
the User Accuracy parameters, but
the “Invalid Installation
Parameters” fault is red.

POS/MV has resolved the wrong
set of ambiguities for its GAMS
heading aiding

Heading Accuracy on the main
Controller screen reads 55° for
more than five minutes after
powering on system.

POS/MV was not able to obtain
an initial heading, a.k.a.

“resolving its quadrant.” This will
most likely occur if POS/MV is
powered on while the vessel is
stationary.

Recommended Solution
1. Select View &gt; GAMS Solution
and ensure PDOP is less than 3
and number of satellites is greater
than 5.

2. Select Settings &gt; Installation
&gt; GAMS Installation Parameters
and click “Apply.”
1. Cycle POS/MV power.

2. Temporarily turn off DGPS
corrections.

3. Power on POS/MV only while
underway.

Heading does not match known
vessel heading once quadrant is
POS/MV has resolved the wrong
Cycle system to “Standby” and
resolved. The “Invalid Installation
quadrant.

back to “Navigate”.

Parameters” fault is
red
Table 3.3: Common GAMS Problems and Recommended Fixes.

Refer to the appropriate Applanix POS/MV User’s Manual, found on the Hydrosoft website, for additional
information on the POS/MV system.


#### 3.4.1.1 Differential Correction

GPS accuracy is improved by applying correctors from land-based differential radio beacons. The POS/MV
system uses these differential corrections (RTCM SC-104 messages) when determining vessel position. However,
the POS/MV system does not include a differential receiver. A separate receiver must be serially integrated into
the POS/MV configuration to obtain these messages.

NOAA hydrographic field units should use differential corrections from the United States Coast Guard (USCG)
radio beacon closest in distance to the survey area, if possible. If a beacon receiver is capable of monitoring more
than one radio beacon frequency, the unit should be set such that only one beacon station will be used. Allowing
only one beacon frequency will prevent the receiver from switching to another beacon station without the
operator’s knowledge, which could cause erratic positioning and make determining the source of correctors
difficult. It may be necessary to use an alternate radio beacon station if the preferred beacon is not functioning
properly. In such cases, the use of this secondary differential beacon should be noted in the data acquisition log.


##### 3.4.1.1.1 Portable DGPS Reference Stations

If differential correctors are not available from a USCG radio beacon, a portable DGPS reference station can be
set up by a field unit. A DGPS Reference station (Figure 3.2) consists of an L1/L2 GPS receiver, a radio transmitter,
a radio receiver, a VHF antenna, tripods or light brackets, marine batteries, solar panels, a timer, and a laptop
computer.

*Page 76*

------------------------------------------------------------------------------------------------------------------------

When choosing a site for DGPS reference station installation, the hydrographer should set it in a convenient place
with good VHF line of sight to survey area and clear view of GPS satellites overhead (substantially clear sky all
around from 10 degrees above horizon – see Appendix 3 (User’s Guide for GPS Observations.pdf for more
information). Effective ranges of Portable DGPS Reference Stations will be a factor of obstructions within the
line of sight and antennae height, nominally 15 km can be used as a rule of thumb. Consider in particular the
following locations:
* setup over tidal bench mark: provides connection between tidal and GPS correctors
* setup over other existing control mark: provides check with prior survey work
* least favorite: establish a new control mark (monumentation instructions available from NGS)
Find existing control marks using the “datasheets” link from National Geodetic Survey http://geodesy.noaa.gov/
If no accurate coordinates exist for your control mark, submit a survey data file to OPUS http://www.ngs.noaa.
gov/OPUS/. For maximum accuracy, submit two 6-hour files (see section 3.5.3 and average the resultant
coordinates (if OPUS results do not agree within 2cm, consult with NGS). Occasional repetition of this OPUS
solution is recommended to provide confidence checks. Note: OPUS will soon allow archiving of geodetic control
directly from the website. To allow this, record photos of the mark and a description of the mark location (see draft
requirements here: http://beta.ngs.noaa.gov/OPUS/ ).

Instructions for setting up the beacon are provided with the kit and will not be provided here.

Check the entire beacon system by placing a roving receiver in a stable spot and tracking the position for 24 hours
(see section 3.2.2. of the HSSD). If the resulting scatter plot (from the Trimble Pathfinder ProXRS or other
receiver software) shows that more than 5% of positions exceed 5 meters from the average, this is an indication
that there is a problem. Otherwise, save a screen shot of the scatter plot for your files. Both a one-time DGPS site
confirmation and a weekly position uncertainty check are required per section 3.2.2 and3.4 (resp.) of the HSSD.
The weekly QC procedure is detailed in section 3.4.1.1.3 below.

Figure 3.2: DGPS Reference Station

*Page 77*

------------------------------------------------------------------------------------------------------------------------


##### 3.4.1.1.2 WAAS-corrected GPS data

NOAA prefers all in-house and contract hydrographers to use USCG Differential GPS (DGPS) as the primary
means of positioning. However, there are some project areas for which reliable DGPS coverage is unavailable or
inadequate. In some case, coverage may be provided by the Federal Aviation Administration’s Wide Area
Augmentation System (WAAS). When working in inshore areas that are relatively close to WAAS reference
stations, WAAS may be able to replace DGPS as the primary means of positioning if prior permission is obtained
from the Chief of the Hydrographic Systems and Technology Program in NOAA’s Coast Survey Development
Laboratory. WAAS can be an option if it can be shown that WAAS meets the positioning accuracy requirements
listed in the HSSD. The procedures for discovering if WAAS may serve as the primary positioning method are
listed below.

* Identify a point ashore with position known to ~0.5m accuracy (either a point surveyed yourselves with
precision GPS methods, or retrieved from the NGS database at http://www.ngs.noaa.gov/OPUS/). This site
should be in close proximity to the survey area, and have a relatively unobstructed sky view to maximize the
available GPS constellation.

* Occupy the point with your WAAS-enabled receiver for at least 24 hours, logging position data at no less than
1 minute intervals.

* Assess WAAS position accuracy and precision by constructing a scatter plot of the 24-hour time series, and
computing the average WAAS position. 95% of the WAAS positions must fall within 5m of both the high
accuracy mark position and the average WAAS position.

* Before acquiring WAAS-corrected hydrographic data, a brief report describing methods, data, test results, and
your plans for quality control shall be submitted to the Chief of the Hydrographic Systems and Technology
Program in NOAA’s Coast Survey Development Laborator


##### 3.4.1.1.3 PPK/RTK Base Station Position Uncertainty Checks

If a PPK/RTK GNSS base station is maintained and used by the field unit to improve horizontal positioning and/
or survey to the ellipsoid, a weekly base station uncertainty check shall be performed (see section 3.4 of the
HSSD).

NOAA hydrographic units shall use the known location of the base station used during post processing/RTK
corrector generation as the “Known” location for the check. NGS OPUS shall be used to determine the Known
location position. A position uncertainty check shall be performed each week of occupation by submitting a 6
hour session file to OPUS and verifying the “Check” position against the Known position.

NOAA hydrographic units shall use the NGS program INVERS3D to perform the weekly position uncertainty
check of the base station. INVERS3D is available as either a free download or web based program from NGS
http://www.ngs.noaa.gov/PC_PROD/Inv_Fwd/. The procedure for performing the weekly check is listed below:

*Page 78*

------------------------------------------------------------------------------------------------------------------------

* Submit both the Known position and Check position GNSS session files to NGS OPUS
* Run INVERS3D from the downloadable executable or web based form
* Enter the First Station (Known position) coordinates as Geodetic coordinates

Figure 3.3: Base Station Known Coordinates
* Enter the Second Station (Check position) coordinates as Geodetic coordinates

Figure 3.4: Second Station Coordinates
* Save the output into a file using the naming convention Station ID_QC_Week Number of check.txt (ex.
9237_QC_33.txt)
* Give First Station name using the naming convention Station ID_Known (ex. 9237_Known)
* Give Second Station name using the naming convention Station ID_Check (ex. 9237_Check)

*Page 79*

------------------------------------------------------------------------------------------------------------------------

Figure 3.5: Base Station Naming
* Examine the results of the text file. The Mark-to-mark distance (D) shall be:

Figure 3.6: Base Stattion Uncertainty Check Results


#### 3.4.1.2 True Heave

Heave data is calculated using a double integration of acceleration over a period of time. When recording heave
in real-time, the calculation is performed using only past measurements of acceleration. An improved estimate of
vessel low-frequency heave can be calculated by performing the integration over a time period centered on the
time of interest, resulting in a “true heave” value (also referred to as “delayed heave”). POS/MV TrueHeave is
effective across long-period wave conditions (16- to 30-second period swell), whereas a real-time heave filter
tends to exhibit its most notable artifacts in such conditions (&gt;16 seconds).

Note: TrueHeave does not replace the need for dynamic draft corrections or water level corrections.
TrueHeave is logged using the POS/MV Controller software, via the Ethernet connection to the POS/MV PCS.
TrueHeave data logging must be controlled separately from the primary data acquisition software, but it can be
continuously recorded throughout the day. The TrueHeave filter requires a period of up to five (5) minutes after it
has been enabled to initialize. The filter uses vertical acceleration data three (3) minutes past real time; hence,
logging must continue for at least three (3) minutes past the ending time of survey line data acquisition. The time

*Page 80*

------------------------------------------------------------------------------------------------------------------------

base used for TrueHeave data, “Heave Time 1”, is user selectable in the POS/MV Controller software. For OCS
hydrographic surveys, UTC (default) should be selected, not GPS time. Refer to the POS MV with TrueHeave
document, found on the Hydrosoft website, for more information regarding the theory, operation, and setup of
TrueHeave.

TrueHeave files are applied to survey data during CARIS HIPS post-processing via the Load True Heave tool, as
discussed in section 4.2.3.5 .


#### 3.4.1.3 POSPac Files

The POS Controller (POS VIEW) program is used to log POS PCS files that contain all the files necessary for
IAPPK processing of SBET in POSPac. See Appendix 4 for (Ellipsoidally Referenced Survey SOP.pdf). Also,
refer to the appropriate Applanix POS/MV User’s Manual, found on the HydroSoft website, https://inside.nos.
noaa.gov/hydrosoft/welcome.html , for additional information on the POS/MV system.


### 3.4.2 Alternate Positioning Equipment


#### 3.4.2.1 Vessel-mounted DGPS Receivers

Numerous types of differential positioning systems are available on the open market, including terrestrial based
DGPS receivers as well as satellite based DGPS receivers. NOAA hydrographic field units planning to acquire
hydrographic survey data with a positioning system not identified in this manual should contact the regional
HSTP Field Support Liaison for guidance and review the system’s accuracies to confirm that survey specifications
can be met. DGPS receivers that can automatically switch DGPS stations based on signal strength or distance
from station should have these options disabled so that the receiver does not switch beacons while acquiring data.
This can lead to horizontal shifts in data.


##### 3.4.2.1.1 Global Satellite-Based Augmentation System (GSBAS) correction

In situations where USCG DGPS correctors are not available and it is not feasible to set up a portable DGPS
station, a field unit may choose to subscribe to a service such as NavCom Technologies StarFire network or C &
C Technologies C-Nav network. These services utilize NASA’s Jet Propulsion Laboratory’s Real-Time GIPSY
(RTG) Precise Point Positioning (PPP) technology to generate corrections and then broadcast them over L-Band
communication satellites.


#### 3.4.2.2 Portable GPS Units

In some situations, such as shoreline verification, it is more efficient for the field unit to position features using a
portable GPS unit. Various models of portable GPS units are available on the open market. Portable GPS units
shall meet the horizontal accuracy requirements as stated in section 3 of the HSSD.

These systems and survey techniques are discussed in section 3.5.3 – Position Uncertainty and Precision.

*Page 81*

------------------------------------------------------------------------------------------------------------------------


### 3.4.3 Alternate Heading Sensors


#### 3.4.3.1 Gyroscopic Compass

A gyroscopic (gyro) compass may be used to determine vessel heading. Gyro compasses use the effects of gravity
and the Earth’s rotation to produce a true north reference and may be mechanical by design or use fiber optic or
laser technology. Ideally, a gyro compass should be installed on the centerline of the ship. When a gyro compass
is used, the manufacturer’s information should be reviewed carefully to determine if the system requires any user
input such as vessel latitude and/or speed to achieve the specified heading accuracy and to identify approximately
how much time is required for the system to slew when first powered up.


#### 3.4.3.2 Course Over Ground (COG)

Vessel course over ground (COG) can be used to calculate a smoothed vessel heading. This technique will not be
appropriate when acquiring all types of hydrographic data. Generally, any system hard mounted to the vessel will
require an instantaneous heading. Since towed systems will not be affected by every slight motion of the vessel,
they can typically use a calculated COG heading without detrimentally affecting the survey data. It may be
possible to adjust the smoothing factor associated with COG heading data. Manipulating the smoothing factor
would allow the user to adjust the frequency with which heading is calculated or how many position points are
used to estimate the vessel course.

3.5 Ancillary Data
-------------------

Two basic types of ancillary data are acquired in conjunction with OCS hydrographic surveys. The first type is
used to correct sonar data and includes such measurements as sound speed and water levels, as well as horizontal
and vertical control data. The second type consists of information that supports survey analyses beyond basic
water depth measurements and object detection. Positions for aids to navigation (ATONs), bottom samples,
shoreline determination, and Coast Pilot reviews are included in this second category.


### 3.5.1 Sound Speed Data

Sound speed data are used by NOAA hydrographic field units for multiple purposes. Primarily, sound speed
profiles of the entire water column are used to correct sounding data for the effects of refraction and varying speed
of sound through water. Water column profiles are also used when processing absolute pressure data obtained by
a DLDG so that a water depth can be calculated. Additionally, flat arrays and to a lesser extent, the far off nadir
beams in curved arrays (of MBES systems) require a continual real time input of sound speed data at the sonar
head for proper beam forming and beam steering. It should be noted that using incorrect sound speed at the
transducer face in beam steering can seriously impact the proper computation of launch/receive angle of all offnadir beams on curved arrays.
When acquiring sound speed profiles to correct bathymetry, OCS recommends taking casts in the deepest portion
of the project area that best represents the surveyed area for which the profile will be applied. If data will be
processed using Velocipy software, the sound velocity speed profile can be extended up to 30% of the cast’s
overall depth (in water depths less than 300 meters), providing more flexibility for cast locations . In water depths
greater than 300 meters, the cast data will be extended to the maximum depth of historical data files loaded in the
Velocipy program. The required frequency of casts will be dependent on the survey area, but OCS strongly
recommends that a cast be performed at least every four hours during MBES data acquisition and once per week
for VBES data.

*Page 82*

------------------------------------------------------------------------------------------------------------------------

The Sea-Bird SEACAT conductivity, temperature, and depth profiler (CTD), Odom DigibarPro, and Rolls- Royce
Moving Vessel Profiler (MVP) are commonly used by NOAA hydrographic field units to acquire sound speed
data. Position information will be required by Velocipy software for data processing and the user must be certain
to record the most accurate GPS position possible. Data acquisition is briefly discussed for each of these systems
below.


#### 3.5.1.1 Sea-Bird SEACAT

The SEACAT is a portable, user-deployed, battery-operated instrument, typically housed in a protective cage. The
SEACAT records water salinity, temperature, and pressure (i.e., depth) during deployment and retrieval. Sampling
rate depends upon the CTD model being used, and is typically between 2-4 samples per second. These data are
processed using NOAA’s Velocipy software to calculate a sound speed profile for the water column. Prior to
performing a cast, OCS recommends that the SEACAT memory be cleared by performing a Pre-Cast Setup and
the instrument status be reviewed using Velocipy (see Velocipy Operation Manual, included on the Hydrosoft
website). If the SEACAT voltage is less than the following values listed below, the instrument batteries should be
changed:
* SBE 19plus: 9.5 volts
* SBE 19: 7 volts
In both cases, the user is told to inspect the battery cut-off value in the status message. The battery should, at the
very least, be one volt greater than the cut-off value.

When conducting SEACAT casts, using the SBE 19plus, the instrument should be lowered and held just below
the water’s surface for about 1 minute to flush air out of the salinity cell. After soaking the instrument beneath the
surface, the user should slowly lower the instrument through the water column.

When conducting SEACAT casts, using the SBE 19, the 3-2-1 rule of thumb must still be followed. The instrument
should be turned on and allowed to sit on deck for 3 minutes while the sensors settle and form baseline measurements.
Next, lower and hold the instrument just below the water’s surface for 2 minutes. Finally, deploy it at a rate of
approximately 1 meter of depth per second.

With either the SBE 19 or the SBE19plus, lowering the instrument too quickly may not provide enough data
points for an accurate water column profile. In areas with lenses of fresh water or other complex sound speed
variation near the surface, the instrument should be lowered slowly (in some cases, much less than 1 meter/
second) by hand through the first 5-10 meters of water in order to accurately sample the sound speed. After the
instrument has descended through the initial 5-10 meters, the user should proceed to drop it at a rate of about 1
meter/second.

Refer to the Sea-Bird SBE User’s Manuals, found on the Hydrosoft website, for additional operating instructions.


#### 3.5.1.2 Odom DigibarPro

The DigibarPro Profiling Sound Velocimeter is a portable, user-deployed instrument. The DigibarPro system
includes a high frequency “sing-around” transducer and a reflector precisely spaced to facilitate measuring the
speed of sound in water by continuously transmitting and receiving a signal across a known separation distance.
The sing-around frequency and associated depth information are recorded at a rate of 10 samples per second. In

*Page 83*

------------------------------------------------------------------------------------------------------------------------

many OCS applications, DigibarPro systems have been mounted to or near a MBES transducer to directly measure
sound speed at the sonar face; however, some units deploy this instrument to obtain full water column profiles.
Recorded DigibarPro sound speed profiles can be uploaded to a PC and processed using NOAA’s Velocipy
software. Refer to the DIGIBAR-PRO Profiling Sound Velocimeter Operation Manual, found on the Hydrosoft
website, for additional operating instructions.


#### 3.5.1.3 Rolls-Royce Moving Vessel Profiler (MVP)

The Moving Vessel Profiler (MVP) is an automated winch system that deploys various payloads such as a free fall
fish (FFF) that can be fitted with a sound speed sensor. The FFF is configured to “fly” at a specified depth until
deployed by use of a “messenger” on the cable. Once at the depth limit, the winch is stopped manually and the
drag forces on the FFF cause it to rise toward the surface due to the ship’s forward motion while the slack cable
is pulled in by the winch. For OCS operations, the messenger is set on the tow cable so that the FFF flies at survey
transducer depth while the vessel is moving at survey speed. The FFF can either be user-deployed or deployed
automatically by the computer at a defined time interval to a user-defined depth or a preset depth off bottom
(typically 10 meters). The FFF is automatically recovered to transducer depth, ready to be deployed again. Because
of the large number of casts that can be recorded by the MVP in a short time frame, it is convenient to batch
process the sound velocity profiles using Velocipy.

Note: Sound velocity profiles created by the MVP must be processed using Velocipy.

Refer to the MVP Operation and Maintenance Manual and the MVP Controller Software Manual, found on the
Hydrosoft website, for additional information on this system and to section 1.5.2.3 . .


#### 3.5.1.4 Reson SVP 70

The Reson SVP 70 is a portable sound velocity probe consisting of a 6.5 inch, 2.2 pound probe which connects to
a topside computer. The SVP 70 measures the sound speed up to 20 times per second in a direct measurement by
transmitting a sound pulse and detecting its time to travel a well-defined path length. The transmitted signal is
generated using waveform techniques that yield optimal conditions for timing the arrival of the returning signal,
which is digitized at high frequency and high resolution. The timing is established using a high-stability clock
oscillator.

The SVP 70 should be mounted at or near the head of a flat face MBES transducer to ensure that valid sound speed
data is being utilized during the beam forming process.


### 3.5.2 Vertical Datum Transformation Data

Tide and water level data are used by NOAA hydrographic field units to reduce bathymetric data to local “chart
datum”, most often mean lower low water (MLLW). The hydrographer should be aware of the difference between
tide data and water level data. Tides refer to the changes in water levels due to astronomical forces only. Tides are
the only water level changes that can be scientifically predicted. Water level data refer to the actual (i.e., observed)
changes in water level due to the combined effects of astronomical forces, wind, rain, freshwater runoff, and other
meteorological events. It should be noted that predicted tides may differ significantly from actual water levels.
Typically, inland water level stations are more susceptible to meteorological effects; thus, tide predictions for
coastal water level stations can be expected to more accurately represent actual water levels than those for inland
stations. Stations in relatively shallow water or with a small tidal range are also highly susceptible to meteorological
effects, making water levels difficult to accurately predict.

*Page 84*

------------------------------------------------------------------------------------------------------------------------

For projects involving ERS, the hydrographer shall utilize approved vertical datum transformation methods (e.g.
VDatum, ERZT, and Constant Value) in lieu of traditional water levels to reduce the bathymetric data to chart
datum. The accuracy of the vertical transformation process is highly dependent on Global Positioning Systems.
Therefore, it is important for the hydrographer to recognize potential satellite ephemeris and clock errors related
to variables such as orbital decay. These variables comprise and explain the components of orbital perturbations.
As a result, orbital perturbations can alter satellite trajectories from its predicted path. This “ephemeris error” is
the difference between the expected and actual orbital path. These deviations are corrected in post processing
using rapid or precise ephemerides.


#### 3.5.2.1 Water Level Station Installation

Although CO-OPS will install, operate, and maintain control water level stations, hydrographic field units may be
required to install subordinate stations. If an installation will be necessary for a project, it will be stated in the
Project Instructions. In such cases, CO-OPS will provide a recommended general area for the gauge. The field
unit is responsible for performing reconnaissance to determine if the recommended location is feasible. If the
initial location is determined to be unsuitable, the field unit shall recommend an alternate location for CO-OPS
approval. Gauge installation, operation, and removal shall be performed and documented in accordance with
section 4 of the HSSD and section 5.2.2.2.4 of this manual. A copy of CO-OPS’ (Standing Project Instructions
and Requirements For the Coastal and Great Lakes Water Level Stations) is included in Appendix 3.


#### 3.5.2.2 Bench Mark Recovery and Leveling

A bench mark is a fixed physical object or marker (monumentation) set for stability and used as a reference to the
vertical and/or horizontal datums. Bench marks in the vicinity of a water level station are used as the reference for
the local tidal datums derived from the water level data. The vertical relationship between the bench marks and
the water level sensor or tide staff is established by differential leveling. NOAA Hydrographic field units will
often be required to install and/or recover benchmarks and perform leveling operations for applicable water level
stations at the start and end of data acquisition for a project. Existing bench mark descriptions and locations can
be found under the Products menu of the CO-OPS website http://www.tidesandcurrents.noaa.gov.

Each water level station will have one bench mark, designated as the primary bench mark, that shall be leveled to
on every run. Levels must be run between the water level sensor or tide staff and the required number of bench
marks when the water level measurement station is installed, modified (e.g., water level sensor serviced, staff, or
orifice replaced), for time series bracketing purposes, or prior to removal. Levels are required at least every six
months during the station’s operation, and are recommended after severe storms, hurricanes, or earthquakes to
document stability. Levels run at subordinate stations operated for less than one-year shall be at least third-order.
Any requirements for higher order levels will be specified in the Project Instructions for the project. Bench mark
installation and gauge leveling shall be performed and documented in accordance with section 4 of the HSSD.
Bracketing levels to an appropriate number of marks (five for subordinate stations) are required (a) if a gauge is
in operations for more than 30 days but less than 12 months (b) if final tides are required, or (c)) every 6 months
for stations collecting data for long term hydrographic projects.

*Page 85*

------------------------------------------------------------------------------------------------------------------------


#### 3.5.2.3 Water Level Data Retrieval

Typically, predicted tides or preliminary water level data are applied to soundings during initial post-processing.
As verified or final water level data become available, the best quality data should be applied to bathymetry. Field
units can download six-minute preliminary water level data directly from the Products &gt; Tides section of the COOPS website http://www.tidesandcurrents.noaa.gov within hours of data acquisition. Verified water level data
should be available from the CO-OPS website within seven days if the station has been placed on the Hydro Hot
List. If a station is not on the Hydro Hot List, verified data may take up to a month to be posted. Final water levels
should be requested from CO-OPS, via a Request for Tides package that can be automatically generated using
Pydro software. Guidance for submitting a Request for Tides is included in section 5.2.2.3.3 .


##### 3.5.2.3.1 Hydro Hot List

CO-OPS maintains a list of water level stations that are currently providing data for OCS hydrographic surveys.
This list is referred to as the “Hydro Hot List.” If a water level station is on the Hydro Hot List, it is monitored by
CO-OPS’ Continuously Operating Real-Time Monitoring System (CORMS) and its data are given priority over
other gauge data for office processing. Field units shall notify CO-OPS by e-mailing: nos.coops.hpt@noaa.gov
and nos.coops.oetteam@noaa.gov when data acquisition begins for a new survey so that the associated water
level stations can be put on the Hydro Hot List. Include the following information in the email: project name and
number, start and end date, and the names of the required gauges. CO-OPS should also be advised when
hydrographic survey data acquisition has been completed in an area so that stations can be removed from this list.
The Hydro Hot List can be found at http://tidesandcurrents.noaa.gov/hydro.shtml.


##### 3.5.2.3.2 Fetchtides

Fetchtides is a procedural program which allows a user to retrieve tides data from a variety of sources including
data e-mailed from tidebot, data in local files, and live data available through CO-OPS’s Web Services. fetchtides
then provides a mechanism to store the imported data locally and then combine multiple days worth of data into
one CARIS readable tide file.

*Page 86*

------------------------------------------------------------------------------------------------------------------------


### 3.5.3 GPS Horizontal and Vertical Positioning

NOAA hydrography frequently requires GPS positioning of features in the survey area independent of depth
sounding operations. Field units have a range of equipment and techniques at their disposal to perform these
measurements. While each survey will have slightly different requirements, typical operations are summarized in
Table 3.4. The rationale for recommended or required durations of GPS observations is given in Table 3.5. Exact
requirements can be found in the NOS Hydrographic Surveys Specifications and Deliverables or the relevant
Project Instructions.

Accuracy Regime

Typical System

Sub-Meter horizontal and/
or vertical.

Dual-frequency
receiver;
constant height
tripod

0.5 - Meter Horizontal

1m @ 95% Confidence
Interval

Typical Technique

Two 6 hour occupations
OPUS
post-processing with
precise ephemeris

Single Frequency
Portable GPS
Receiver
(Trimble ProXRS
or similar)

5 minutes of static L1
GPS data and differential
correction

Single Frequency
Portable GPS Receiver
(Trimble ProXRS or
similar)

10 to15 minutes of static
occupation
Post-processed
differential correction
(Pathfinder Office utility
or similar)

Typical Applications
Water level station
geodetic benchmarks with
vertical accuracy of 2
cm @ 95% confidence*
portable DGPS Reference
Station Control Points
Horizontal Accuracy:
3rd Order or better (~1m
@ 95% confidence)
Range Markers
Horizontal: 0.1m @ 95%
confidence
Ground Control Point
Positioning by
Navigation Response
Teams for the
National Geodetic
Survey’s Remote
Sensing Division.

Fixed ATONs (beacons or
lights)
Mooring Facility features
used for zero
visibility docking

Survey Vessel DGPS or
Floating ATONs
5m @ 95%
Single Frequency
DP with offset, short
Confidence
Portable GPS Receiver
static occupation, or
General Shoreline
Interval
(Trimble ProXRS or
roving as appropriate
Features
similar)
Table 3.4: Typical GPS Positioning Scenarios
*Per requirements of the CO-OPS Users Guide for GPS Observations and NGS-58.

*Page 87*

------------------------------------------------------------------------------------------------------------------------

Recommended or Required
Duration of Observation

Explanation

For Horizontal or Vertical
Positioning

Due to advances in GPS technology,
sub-meter horizontal positioning is
5 Minutes
now possible with an observation
Horizontal Only
period of 5 minutes using the
parameters found in Table 3.6
Minimum recommended for OPUSRS which may be a preferred
alternative for much of your work.

15 Minutes
Horizontal and Vertical
Unfortunately, it doesn’t work in
most remote locations or far
offshore.

Minimum recommended for normal
2 Hours
OPUS and is fine for your accuracy
Horizontal and Vertical
needs.

Minimum required for OPUS
Horizontal and Vertical
4 Hours
database (at least for now).

May be considered overkill, but
preferred whenever practicable;
6 Hours
e.g., if the system is set up to
Horizontal and Vertical
automatically record unattended
and would be left set-up anywa
This is basic geodetic practice, but
probably won’t tell you much unless
you really try for an independent
2nd Observation
Horizontal and Vertical
observation with a new observer,
independent antenna setup and
measurement, etc.

Table 3.5: Rationale for recommended or required durations of GPS observations.

It should be noted that independent observations are the key to survey confidence. If the hydrographer is using the
same equipment, then it isn’t true independence but it will give at least different satellites, different atmosphere,
different ephemeris which could be an issue, at least theoretically. Whenever there is a convenient opportunity to
collect more observations, it is recommended to do so and prove from repeated consistent OPUS results that you
know where you are.

*Page 88*

------------------------------------------------------------------------------------------------------------------------


#### 3.5.3.1 Sub-Meter GPS Positioning


###### 3.5.3.1.1.1 Equipment for Static Positioning

Operations which require sub-meter accuracy measurements of horizontal and/or vertical position are generally
accomplished with the following equipment:
* Dual Frequency (L1/L2) GPS receiver with internal logging, and appropriate batteries.

* L1/L2 ground plane GPS antenna.

* Antenna cable less than 10m in length. Shorter is better, but if you have or need longer (to protect receiver
or observer), then use it. Cables should be treated gently to avoid lost or noisy signal which will decrease
accuracy.

* Tripod or light bracket for antenna mounting (Fixed-height Tripod for high accuracy vertical measurements).
The following additional equipment is typically needed to install the GPS equipment:
* Magnetic Compass (for antenna orientation).

* Observation Log (see HorCon_VerCon_Obs_Log.pdf in Appendix 3.

* Eyebolts, rock drill, rope/cable, etc. as required to secure antenna for long duration observation sessions.
* Digital Camera for site documentation.


##### 3.5.3.1.2 Observations for Static Positioning

Sub-meter GPS positioning requires concurrent observations at one or more Continually Operating Reference
Station (CORS) sites and/or other pre-existing control stations with accuracies of at least a 1st order triangulation
(for sub-meter horizontal measurements) as well as vertical control for accurate vertical measurements. For best
results, the control station should be within 75km of the measurement site. Longer distances may be unavoidable
in remote areas but may necessitate longer observation sessions to achieve the same order of accuracy. Both
CORS sites and supplemental reference station information is provided on the National Geodetic Survey CORS
website: http://www.ngs.noaa.gov/CORS/.

To perform GPS observations, first assemble the tripod or light bracket (for fixed lighted ATONs) over the point
for which a new position will be determined. Be certain that the antenna is plumb to the mark, oriented north, and
level to the earth. Accurately measure the height of the antenna reference point.

Once the antenna has been properly set up, connect the GPS receiver and check that it has the expected number
of satellites in view and is computing a position. If performing a vertical position measurement on the geodetic
benchmark of a water level station, ensure that the Vertical Dilution of Precision (VDOP) is less than 6.0 (as
required by the CO-OPS Users Guide for GPS Observations and NGS-58, included in Appendix 3). At sites with
poor satellite visibility, it may be necessary to use a GPS constellation prediction tool such as the Trimble Planning
software to schedule sessions for best available satellite geometry.

*Page 89*

------------------------------------------------------------------------------------------------------------------------

Configure the GPS receiver to record GPS pseudo ranges for the appropriate amount of time to meet both accuracy
specifications and post-processing requirements. There are several methods that can be used to postprocess GPS
data; however, NOAA hydrographic field units typically use NGS’s Online Positioning User’s Service (OPUS),
which utilizes data from three nearby CORS sites and is available at http://www.ngs.noaa.gov/OPUS. To ensure
that the data can be processed using OPUS, the following guidelines should be followed during data acquisition:
* Recording intervals on the GPS receiver(s) should be set to 15s or some multiple that coincides with the three
nearest CORS site sampling rates. Sampling rates for each CORS site may differ and can be reviewed on the
NGS CORS website.

* If using more than one receiver for an observation session, all of the receivers should be set to the same
recording interval, since there must be common data between all stations.

* Observation times should be a minimum of two hours. For a strong OPUS solution, at least two hours of good
data are needed. NGS recommends four hours of good data to achieve horizontal accuracy of 0.035 m. For
further information on positioning, refer to the following Users_Guide_for_GPS_Observations At Tide and
Water Level Station Bench Marks: http://tidesandcurrents.noaa.gov/pub.html
* OPUS can convert them to RINEX for most receivers. If not, before uploading GPS files to OPUS, convert
them to RINEX2 format using the RINEX Conversion module included with the receiver manufacturer’s
software.

* Monitor the position and positional dilution of precision (PDOP) information displayed on the GPS receiver.
PDOP is a unitless value that indicates the degree of position error in a measurement. Do not start logging data
until PDOP is below six. Maintaining a PDOP less than six will help ensure that the observation file contains
clean data that will not be rejected by quality control checks performed by OPUS. Note: Some systems will
automatically begin logging data when powered on. In such cases, the user may need to manually stop a
session once PDOP is below six, create a new session in the receiver, and start a new session so that data begin
logging under a new file name. The first file can be easily deleted after downloading data.

* An observation log for every setup shall be completed by the observer(s) on site. A blank HorCon/Vercon
Observation Log is included in Appendix 3 (HorCon_VerCon_Obs_Log.pdf).

Additional detail on processing GPS Observations with OPUS can be found in section 4.4.1 .


##### 3.5.3.1.3 Ellipsoidally Referenced Surveys

ERS vertical control is discussed in Appendix 4 of the FPM and in Chapter 9 of the HSSD.


#### 3.5.3.2 Meter-level GPS Positioning

While horizontal position to 1m accuracy can be accomplished with the same equipment described above for
higher accuracy measurements, it is often more efficient and convenient to utilize portable single frequency
logging GPS receivers for this purpose. The Trimble ProXRS receiver with TSCe data collector or notebook PC
is an example of this equipment commonly found in NOAA field unit inventories.

*Page 90*

------------------------------------------------------------------------------------------------------------------------

The Trimble Pathfinder ProXRS is a backpack GPS system which combines a GPS receiver and a beacon
differential receiver. Although a single frequency (L1) GPS receiver, the ProXRS is capable of logging carrier
phase data, which can be post processed to recover significantly improved positional accuracy. With the addition
of the TSCe data collector, this system can be used to acquire static point or roving line data, and immediately
assign object types and attributes based on the S-57 catalog. Static position accuracies of 1m or better can be
attained when the system is used to occupy a point for a minimum of approximately 10 minutes, and the resulting
data is post-processed with Trimble Pathfinder Office software.


##### 3.5.3.2.1 System Software

Two types of software are used to conduct operations with the Trimble Pathfinder unit. GPS Pathfinder Office
software is used to create an initial configuration file for the ProXRS receiver and allows field personnel to postprocess logged GPS data, including converting data into Shapefiles, which can be exported to Pydro. Trimble
TerraSync software runs on the TSCe data collector or notebook computer, and is used to control the ProXRS
receiver and log and attribute data. Refer to the TerraSync Operation Guide found on the Hydrosoft website for
specific information on this software.


##### 3.5.3.2.2 System Configuration

Prior to acquiring data with the Trimble Pathfinder system, a project and configuration file must be created. Both
of these tasks should be completed using GPS Pathfinder Office software, although field adjustments can be made
to the configuration file using TerraSync. Refer to the GPS Pathfinder Office Getting Started Guide, found on the
Hydrosoft website, for specific details on how to create a project and configuration file. Numerous parameters
must be entered in the configuration file. Those which have been recommended for use by OCS are listed in the
table below.

*Page 91*

------------------------------------------------------------------------------------------------------------------------

Configure Parameters
OCS Recommended Value
Log SuperCorrect Data
Yes
DOP Type
HDOP
HDOP Mask
2.5
PDOP Mask
6.0
SNR Mask

*Page 4*

------------------------------------------------------------------------------------------------------------------------

Elevation Mask
10 degrees
RTK Static Precision- Horizontal
5.0 cm
RTK Static Precision - Vertical
5.0 cm
TK Roving Precision- Horizontal
10.0 cm
RTK Roving Precision- Vertical
15.0 cm
RTCM Age Limit
20 s
Integrated Beacon Mode
Manual
Integrated Beacon Frequency
varies by area
Coordinate System
Latitude/Longitude
Datum Name
NAD83
Distance Units
Meters
Altitude Reference
HAE (height above ellipsoid)
Area Units
Square Meters
Table 3.6: Recommended Trimble Pathfinder Pro XRS Configuration Parameters
*Per NOAA Technical Memorandum NOS NGS 58, for observation sessions less than 30 minutes, data collected
below the 15° elevation mask angle should only be used if required to derive a successful GPS solution. OCS
recommends acquiring data at an elevation mask of 10°, and increasing the elevation angle to 15° during
postprocessing. If data will not be post-processed, a mask of 15° should be used during acquisition. A copy of
NOS NGS 58 is included in Appendix 3 (NGS-58.pdf).


##### 3.5.3.2.3 Data Dictionary

The Trimble Pathfinder Pro XRS uses a digital Data Dictionary to attribute data acquired with the unit. NOAA
hydrographic field units shall use the Data Dictionary as a base for acquiring S57 attributed data. The Data
Dictionary should be loaded into TerraSync on the GPS datalogger or PC being used to record data. Consult the
GPS Pathfinder Office Getting Started Guide, found on the Hydrosoft website for further information on editing
the Data Dictionary.


##### 3.5.3.2.4 Recording Data

The Trimble Pathfinder Pro XRS can record position data as points, lines, and areas. Recording procedures will
vary depending upon the position accuracy required. In general, a single geographic position with real-time
differential correctors applied should be accurate within 2-5 meters and adequate for positioning features such as
large shoreline features and bottom samples. The TerraSync acquisition software also includes options for applying
offsets to a position which can not be directly accessed. Position offsets can be defined by a distance and bearing
from a recorded point (distance/bearing), distances from two recorded points (distance/distance), bearings from

*Page 92*

------------------------------------------------------------------------------------------------------------------------

two recorded points (bearing/bearing), distances from three recorded points (triple distance), or bearings from
three recorded points (triple bearing). Distances and bearings can be either visually estimated or measured using
a laser range finder and compass. Of these options, triple distance offsets measured with a laser range finder will
provide the most accurate position, but this method may not always be feasible or necessary. The hydrographer
should use the most efficient method of positioning that will meet data specifications.

When recording line data, the operator can configure the Trimble Pathfinder Pro XRS to record positions at
specified time intervals. For positioning linear shoreline features such as piers, hydrographic field unit experience
has shown a 1 second recording interval to be sufficient in most cases. A shorter interval may be necessary for
more complex features, or multiple single points may more accurately portray a feature that requires indirect
routes between corner points such as a cluttered pier. Refer to the GPS Pathfinder Systems User Guide, found on
the Hydrosoft website, for detailed information on Trimble Pathfinder Pro XRS operating procedures.
Higher accuracy positioning can be obtained by static occupation of a site for multiple position measurements,
and/or post-processing ProXRS data with the Trimble Pathfinder Office software’s Differential Correction Utility.


#### 3.5.3.3 Special Instructions for Positioning Aids to Navigation (ATONs)

Positions and characteristics for all ATONs within a survey area shall be visually observed and compared to both
the largest scale chart and current USCG Light List information during survey operations.

Note: Any ATON that is not serving its intended purpose, off-station, damaged, otherwise compromised, or
uncharted and is determined by the field unit to present a hazard to navigation shall be immediately reported to
the local USCG district.

NOAA’s Update Service Branch (USB) will assign specific ATONs (fixed type only) which require positioning
based on NOAA’s Critical Corrections Database (CRIT) and/or USCG Integrated Aids to Navigation Information
System (IATONIS) database records. Information for assigned ATONs will be provided on the Project CD/DVD.
Additional ATONs may be positioned at the field unit’s discretion if determined to be navigationally significant.
Unless specific positioning methods or accuracies are assigned in the Project Instructions, ATONs throughout the
survey area shall be investigated, and positioned if necessary, in accordance with the following guidance:
* Assigned Charted Fixed ATONs – If possible, the field unit shall position each fixed ATON assigned by MCD.
Assigned ATONs shall be positioned to an accuracy of less than one meter, at a 95% confidence level, unless
otherwise specified - such as range markers, which shall be positioned to within 4 cm precision and reported
to one-thousandth of a second of latitude (0.001’). Many NOAA hydrographic field units meet this accuracy
criteria by performing static GPS observations for minimum a period of 10 to 15 minutes and post-processing
position data using correctors from the nearest CORS station (e.g., using the Differential Correction utility in
GPS Pathfinder Office software as described in 3.5.3.2.1 ). If obtaining this level of accuracy is unfeasible, but
the field unit is able to acquire a higher quality position than that in the current database record, an upgraded
position should be determined and included in the ATON Report (see section 5.2.2.3.4 . Acquisition methods
and limitations should be described in the comments section for that ATON.

* Unassigned Charted Fixed ATONs – Charted fixed ATONs will not be assigned if a position accurate to less
than one meter, at a 95% confidence level, has already been determined. If an unassigned fixed aid is observed
to be significantly off station based on the largest scale chart, the hydrographer should review the USCG Local
Notice to Mariners (LNM) for a discrepancy report on the aid. (Discrepancy reports are issued by the USCG
when an ATON is known to be off station, but the agency has not yet been able to repair the aid. These reports
are contained in section 2 of each LNM.) If no discrepancy report has been published, the local USCG district

*Page 93*

------------------------------------------------------------------------------------------------------------------------

should be contacted to determine whether the aid was compromised or intentionally relocated to serve its
intended purpose. Following USCG confirmation that the aid is correctly positioned or has been properly
relocated, the field unit should re-examine the aid. If it remains off station, this ATON should be positioned
and reported as if it was an assigned aid.

* Uncharted Fixed ATONs – This category of ATON is typically comprised of privately maintained aids, and
the field unit must determine if such an ATON is navigationally significant. If navigationally significant, a
position should be acquired and the ATON reported as if it was assigned. For private aids reported, the field
unit should specify both the apparent purpose and by whom the aid is maintained in the report.

* Charted Floating ATONs – The field unit shall visually verify positions and characteristics of charted floating
ATONs during survey operations. If a floating aid is significantly off station with both the scale of the chart
and scope of chain considered, the hydrographer should review the LNM for a discrepancy report on the aid.
Note: Temporary positions of aids relocated to facilitate dredging, construction, or similar activities are
typically not charted. If no discrepancy report has been published, the local USCG district should be contacted
to determine if the aid was compromised or intentionally relocated to serve its intended purpose. Following
USCG confirmation that the aid is correctly positioned or has been properly relocated, the field unit should
re-examine the aid. If it remains off station, acquire a detached position (DP) for the ATON and report this
item as if it was an assigned aid. Static GPS observations are not required when positioning floating aids.
* Uncharted Floating ATONs – The field unit shall determine if each uncharted floating ATON is navigationally
significant (e.g., a mooring buoy or full-size private buoy, typically not a small private float). If navigationally
significant, the field unit should acquire a DP for the ATON and report this item as if it was an assigned aid.
Static GPS observations are not required when positioning floating aids.

For each survey, the field unit shall digitally submit an ATON Report to MCD as described in section 5.2.2.3.4 .


### 3.5.4 Bottom Samples

Bottom samples are typically obtained and analyzed in accordance with section 2.5.4.2.1 of this manual and
section 7.1 of the HSSD, and then discarded. Several sizes of bottom samplers are used in the NOAA hydrographic
fleet. and the field unit shall use the most appropriately sized bottom sampler for the vessel and conditions. If the
bottom sampler is successfully deployed and tripped three times, yet no sediment sample is acquired, the station
shall be labeled ”unknown” unless additional knowledge is available to the hydrographer. If sediment samples are
to be retained for future analysis, guidelines will be provided in the Project Instructions.


### 3.5.5 Nearshore Hydrography and Shoreline

All modern NOAA hydrographic surveys are Navigable Area Surveys, unless explicitly stated otherwise in the
Project Instructions. The navigable area concept is defined in section 1.1.2 of the HSSD. Working near shore is
inherently dangerous, and all field units are reminded that safety shall always be the primary consideration when
conducting operations. Shoreline verification should not be attempted unless conditions are favorable. Even
though an initial assessment is made by the Chief-of-Party, conditions at the actual survey area may be different
or degrade as the day progresses. In such cases, the launch or skiff personnel shall not perform shoreline operations
until conditions are favorable.

*Page 94*

------------------------------------------------------------------------------------------------------------------------


#### 3.5.5.1 Source Shoreline Data

Unless otherwise specified in the project instructions, HSD Operations Branch/Navigation Response Branch shall
compile and provide a Composite Source File (CSF) and a Project Reference File (PRF) for all projects.
The composite source is an S-57 attributed dataset in .000 file format, compiled from one or a combination of the
following sources: largest scale ENCs, preliminary ENCs, GCs and/or Lidar junction surveys. During planning
the project planner reviews the sources listed above to ensure the shoreline files reflect the most recent data
coverage for the project area. The following list is a description of how each source is applied to the CSF:
* ENCs – the largest scale ENCs of an area are applied to the CSF. If ENCs of different scales overlap, the larger
scale ENC is used to “clip” (remove) the smaller scale ENC so there is only one instance of all features at the
largest scale for the area.

* Preliminary ENCs – Preliminary ENCs are ENCs which have had source applied (e.g. GC) but the ENC has
not been reviewed by MCD and released to the public. Preliminary ENCs are applied to the CSF in the same
manner as different scale ENCs. A preliminary ENC may be used to clip the ENC ensuring only one instance
of all features.

* GCs - GCs that have not been applied to the ENC will be applied to the CSF by clipping the existing ENC
shoreline (COALNE) and replacing it with the GC shoreline. All remaining GC features are added to the CSF.
There is no further clipping of other features. This may result in duplicate features such as rocks or piles in the
CSF which will need to be reconciled by the field unit during verification.

* Lidar Surveys – Lidar junction data is applied to the CSF by adding the approved Lidar features to the CSF.
No clipping occurs with the addition of Lidar features which may result in duplicate features which will need
to be reconciled by the field unit. (Note, HSD is currently not using shoreline (COALNE) from Lidar surveys)
The source of each feature is indicated in the SORDAT and SORIND attribute fields.

The project reference file is an S-57 attributed dataset containing reference layers (i.e. sheets, junctions,
recommended bottom sample positions) and features which are specifically targeted for further investigation,
such as items from the Automated Wreck and Obstruction Information Service (AWOIS) database, Maritime
Boundary, or those surveyed by Lidar but not fully resolved.

Reference Features
Investigation Items

S-57 Object
CRAINES

Description
AWOIS, Lidar, Maritime Boundary investigation
items
AWOIS Radii
ACHBRT
AWOIS Search Radius
Survey Sheets
TESARE
Outline of the survey sheet*
Junction Surveys
TWRTPT
Outline if junction survey
Bottom Samples
SPRING
Recommended bottom samples locations
Table 3.7: Features contained in the Project Reference File from Operations Branch
*Note: The inshore limit has been clipped at the 0.8 mm bufer. The buffer will no longer be supplied as a
seperate S-57 object.

For reference, prior survey features may be provided in S57 format on the project CD/DVD in the prior survey
folder.

*Page 95*

------------------------------------------------------------------------------------------------------------------------


#### 3.5.5.2 Types of Shoreline Verification

Hydrographic Survey Project Instructions will specify which shoreline source documents are to be verified as well
as the type of verification required, either “traditional” or “limited.” Shoreline source(s), chart scale(s), and local
vessel traffic patterns are among the factors used in determining which method is appropriate for the survey area.


##### 3.5.5.2.1 Traditional Verification

Traditional shoreline verification is the most thorough and complete method, requiring full examination of all
shoreline detail and features seaward of MHW. This technique is very rarely required, and is only necessary if the
Project Instructions explicitly call for it. The hydrographer should examine all near shore detail and features
seaward of the shoreline (MHW line) originating from composite source documents, NGS-verified remote sensing
shoreline data, prior hydrographic surveys, and nautical charts. All features shall be verified, changed, or disproved,
provided the operations can be conducted safely. Features located near the shoreline or some accurately plotted
reference point may be verified by visual inspection.


##### 3.5.5.2.2 Limited Verification

Typically, a limited verification will be assigned for OCS hydrographic surveys. When conducting limited
shoreline verification, the hydrographer shall examine all features seaward of the Navigable Area Limit Line
(NALL) as defined in section 1.1.2 of the HSSD. If there is no MHW adjacent to features and the area is not safe
to survey, then the area is determined to be foul. Features shall be examined in accordance with the following
direction:
* All ENC, RNC, Preliminary ENC’s, Geographic Cells, and contemporary LIDAR features in the composite
source file that are seaward of the NALL should be verified or disproved. If a feature is found within 2
millimeters at the survey scale of the composite source position, a revised field position is not required (This
2mm tolerance does not apply to fixed ATONs specifically assigned for updated positions. See section 3.5.3.3
for additional guidance on these features.). Heights/depths of all features seaward of the NALL should be
determined by the best means available given the sea conditions at the time of the survey
Chart Interval (milimeters)
Survey Scale
Ground Distance (meters)
2mm
1:5,000
10m
2mm
1:10,000
20m
2mm
1:20,000
40m
2mm
1:40,000
80m
2mm
1:80,000
160m
2mm
1:100,000
200m
Table 3.8: Common survey scale examples of the chart interval 2mm converted to ground distance.

* New features seaward of the NALL should be properly positioned.

* New point features and new area features where the high point may be used for a navigational landmark also
require a corresponding height/depth. Composite source features that are correctly charted do not require
corresponding height/depth verification.

*Page 96*

------------------------------------------------------------------------------------------------------------------------

* Features with any horizontal dimension greater than 1.0mm at survey scale should be treated as area features
and delineated appropriately. Features with lesser horizontal dimensions should be positioned and attributed
as point features.

* The hydrographer shall address blatant and obvious shoreline discrepancies between hydrography and
deconflicted features in the Composite Source File.

* Prior survey features are for reference only. There is no requirement for the hydrographer to address prior
survey features in the Descriptive Report.

It may be necessary to position, verify, or disprove some features inshore of the NALL, if they are both
navigationally significant and safe to approach. Examples of features which might meet this standard include:
* Aids to Navigation
* Natural or man-made features sufficiently conspicuous to be an obvious navigational landmark (e.g., piers,
pilings, or very large and isolated boulders or outcroppings)
Note: “Navigationally significant” is not easily and absolutely defined. As such, it makes up part of the “art” of
hydrography versus the more easily quantifiable “science” aspect of the profession. Navigational significance
depends on location, proximity to shore and/or other features and the marine traffic patterns/usage in the area.
Ideally the person making the determination of navigational significance will be one who has extensive experience
utilizing NOAA/NOS charts for navigation and can convey that perspective to the persons conducting the field
survey work. This is typically the NOAA vessel Commanding Officer (Chief-of-Party) or Field Operations Officer,
Hydrographer-in-Charge, or the contractor’s Lead Hydrographer.


#### 3.5.5.3 Conducting Shoreline Verification

Shoreline verification operations should be scheduled for daylight periods when the tide is less than 0.5m above
Mean Lower-low Water (chart datum). To maximize the shoreline “window”, it is usually advantageous to plan
for shoreline operations during spring tides when the extreme range allows for longer low water periods each day.
In some cases, ideal water level conditions may not be available while the field unit is in the project area. In these
cases, the Chief-of-Party should request further instructions from the Chief, HSD Operations Branch. Shoreline
verification should be performed prior to main scheme bathymetric data acquisition in nearshore areas to ensure
that submerged hazards have been identified to the fullest extent possible before launches with protruding
transducers operate in the area.

Shoreline verification is typically conducted from a small, maneuverable survey vessel such as a skiff or jet-drive
survey launch. The vessel should be equipped with survey-grade GPS and vertical beam or tilted multibeam
echosounder interfaced to an appropriate data acquisition computer and software. Multibeam echosounders which
are mounted perpendicular to the seafloor (i.e. not tilted) are not ideal for shoreline verification because of the
increased risk of damage to hull-mounted transducers when operating in unsurveyed nearshore areas.
The vessel’s data acquisition software should be loaded with the composite source and other applicable files
(ENC, RNC, and Project Reference File). In addition, it is often helpful to print a large “boat sheet” of the
composite source on a large format printer. This is useful for orientation and quickly recording field observations.

*Page 97*

------------------------------------------------------------------------------------------------------------------------

A common and effective method for conducting shoreline verification is to run a VBES survey line parallel to
shore, observing exposed features. In the case of Limited Shoreline Verification, this survey line should approximate
the NALL, allowing the hydrographers to focus most of their attention offshore of the vessel. This approximate
NALL can be used later to assist in planning the inshore extent of bathymetry. As features meeting the criteria
given in section 3.5.5.2 are encountered, the survey vessel should break off from following the NALL, investigate
the features as required, and return to following the NALL.

Note that not all features require or even warrant investigation at low water. To maximize efficient use of low
water windows, it may be best to skip these features on the initial pass, and return at a higher stage of tide. In
extreme cases, it may be possible and advantageous to acquire complete MBES coverage of features which are
exposed at low water.


#### 3.5.5.4 Recording Shoreline Data

Point features are generally positioned using Detached Positions with a range and bearing from the survey launch,
or by direct occupation with a portable GPS system. Line features or the extents of areas can be bounded by
recording data as the launch passes as close as possible to the feature, taking DPs at the extents of the feature, or
using a roving portable GPS to walk the extents ashore. In all cases, it may be prudent to take written notes on log
sheets and/or the boat sheet in addition to recording data digitally.

Accuracy requirements for point positions depend on the type of feature being located. If the feature is a wharf or
pier potentially to be used for zero-visibility docking, the horizontal position error should be 1.0 meter or less. For
features not critical to zero-visibility navigation or docking, accuracy for all points should meet the minimum
horizontal position accuracy requirement set forth in the HSSD. The method of positioning a feature to the
required accuracy is typically left to the discretion of the hydrographer, subject to the guidance in section 3.5.3 .
When recording line data, positions are logged at regular intervals small enough to facilitate a “connect the dots”
drawing of the area. Line data is a valuable tool for accurately delineating curved or irregular features. OCS
recommends that line data used to define such features be acquired with a data collection interval of one second.
All data should be acquired with S-57 and NOAA attribution collected at the times of acquisition. While many
S-57 object types and attributes are self-explanatory, the hydrographer should consult the S-57 catalog for further
guidance.


### 3.5.6 Maritime Boundary Delineation


#### 3.5.6.1 Background

OCS is responsible for depicting the Three Nautical Mile Line (old territorial sea), Territorial Sea at 12 nautical
miles, Contiguous Zone at 24 nautical miles, and Exclusive Economic Zone (EEZ) at 200 nautical miles on
NOAA nautical charts. These maritime zones, whose limits are measured using principles set forth in the United
Nations Convention on the Law of the Sea (UNCLOS), define areas of U.S. jurisdiction for a variety of regulations.
Noteworthy examples that highlight the importance of near-shore surveys include provisions of the Clean Water
Act and Oil Pollution Act, which are tied to the inner and outer extents of the old territorial sea at 3 nautical miles.
In addition, the Three Nautical Mile Line is often used by state and federal enforcement officials to police fisheries
and other laws.

*Page 98*

------------------------------------------------------------------------------------------------------------------------

Figure 3.7 highlights the breadth of offshore maritime and marine boundaries. Among a host of marine boundaries,
the U.S. maritime zones (in red) include the territorial sea (0-12nm), contiguous zone (12-24nm), and EEZ (12200nm). The U.S. also retains and charts a territorial sea at 3nm, which supports enforcement of the Clean Water
and Oil Pollution Acts. All of these zones are measured from the U.S. baseline, which is largely composed of the
charted low water line (at MLLW) as well as closing lines across legally-defined bays and rivers. Various federal,
state, and local governments reference the limits on NOAA nautical charts as well as best practices for defining
those limits to enforce their own regulations.

Figure 3.7: Breadth of Offshore Maritime and Marine Boundaries

Figure 3.8: Normal baseline with projected envelope of arcs
(from “Shore and Sea Boundaries byShalowitz)
In accordance with customary international law and UNCLOS, the U.S. maritime zones are measured from what
is referred to as the “normal baseline.” Simply stated the normal baseline is composed of features that are dry at
mean lower low water (MLLW). This includes naturally-formed offshore rocks awash and harbor structures, such
as groins, jetties, and breakwaters (not recreational fishing piers). The maritime zones are measured from the
baseline using a method called “envelope of arcs” (see Figure 3.8). Using this method, only the most seaward
features influence the outer limits of the U.S. maritime zones.

*Page 99*

------------------------------------------------------------------------------------------------------------------------

Arcs generated from these salient baseline points are blended together to form continuous limit lines at 3, 12, 24,
or 200 nautical miles. Finally, the U.S. baseline as well as the maritime zones are reviewed and approved by an
inter-agency federal group called the U.S. Baseline Committee, which was established in 1970 and is chaired by
the Department of State.

Figure 3.9: Near-shore Feature Impacts to Offshore Limits
Figure 3.9 highlights how near-shore features can impact the offshore limits. Occasionally and depending upon
segment length and orientation, closing lines across legally-defined bays and rivers (another component of the
U.S. baseline) will influence the outer limits of the U.S. maritime zones. The territorial sea is measured from a
normal baseline, which generally consists of the mainland low-water line and offshore islands (A), plus any
closing lines across the mouths of rivers or legal bays (B), the outermost points of permanent harbor works (C),
and low-tide elevations wholly situated at a distance not exceeding the breadth of the territorial sea from the
mainland (D). Contributing baseline points, which are used to generate the maritime limits, are denoted as red Xs.
Determining the exact nature of charted low-water features is not always straightforward, and to aid enforcement
of the U.S. maritime zones, U.S. policy is to refrain from using uncertain features in the baseline. The most
controversial feature is the charted rock awash because many times compilation of older surveys to the nautical
chart did not include height information. In addition, the rock awash symbol is compiled through different
standards with east coast (includes Gulf of Mexico), west coast and Great Lakes surveys. The standards for
compiling rocks and islets to the nautical chart can be found in the HSSD Appendix 8: Rock Attribution and in
excerpts from MCD’s Nautical Chart Manual sections 4.9.1 and 4.9.2.


#### 3.5.6.2 Procedures

The maritime boundary verification requests are compiled by HSD OPS and delivered to the field units in the
Project Instructions. The point features are included in the Project Reference File (PRF) as the S-57 Object
CRANES and are distinguished by the NOAA Extended Attribute “Special Feature Type” (sftype) populated with
MARITIME BOUNDARY. The hydrographer is responsible for verifying the existence of the furthest offshore
fea- ture that is dry at MLLW recognizing that the furthest offshore feature may not be the feature within close
proximity to the Maritime Boundary investigation point.

*Page 100*

------------------------------------------------------------------------------------------------------------------------

See sections 7.3 Investigation Items and 8.2 S-57 Soundings and Feature Deliverables of the HSSD for further
information on Maritime Boundary point requirements and attribution.

Note, if MBES was used for verification the hydrographer should not delineate the linear MLLW on the field
deliverable as this is performed by cartographers at the branches.


##### 3.5.6.2.1 Processing & Deliverables

Maritime boundary features are flagged in the processing software as Maritime Boundary features. The field notes
are updated in the Remarks attribute and digital photographs are labeled and correlated to the Maritime Boundary
item. If MBES was used for verification the hydrographer should not delineate the linear MLLW on the field
deliverable as this is performed by cartographers at the branches. Point features covered by MBES should follow
the standard procedures as described above.


### 3.5.7 Coast Pilot Data

A Coast Pilot Review shall be conducted for each assigned survey area. The review consists of downloading the
appropriate Coast Pilot section for verification and updates. In addition, reviewing the information relating to
general operations in the area such as frequent transited areas and facilities utilized. See section 7.4 of the HSSD
for further information on requirements and the sections below for procedures.

*Page 101*

------------------------------------------------------------------------------------------------------------------------


#### 3.5.7.1 Performing a Coast Pilot Review

When determining what information is pertinent for the Coast Pilot, the size, type, and number of vessels using
each waterway must be taken into account. The requirements of the deep-draft navigator, yachtsman, and fisherman
must all be kept in mind. Allowance must also be made for the thoroughness with which the region has been
surveyed and charted. If the surveys of the area are incomplete, if the harbor charts are on too small a scale, or if
the harbor has grown in importance, more detail will be required in the Coast Pilot. If possible, digital photographs
should be submitted for significant Coast Pilot features in accordance with section 3.5.7.2.

If additional information is necessary to address a Coast Pilot item, a wide variety of locally knowledgeable
people can be used. However, information from outside sources should be verified by the reviewer. The source of
the report should be given so that the report’s value may be weighed against conflicting information that may be
received by NOAA’s Marine Chart Division. The following is a list of the principal organizations and officials
who can be interviewed for the purpose of obtaining local information: Coast Guard stations and other aids to
navigation units, buoy tenders and other cutters, patrol craft, and Marine Safety Offices
* Corps of Engineers district offices or other Federal field offices such as Customs Service
* Pilot associations, port authorities, harbormasters, and harbor police
* Other NOAA field parties operating in the area
* Operators of repair yards and marine service stations
* Captains of towboats, ferries, and coastwise vessels operating in the area
* Individuals very familiar with the area such as fishermen and longtime residents
* Yacht clubs
The following sections describe categories of information that should be addressed during a Coast Pilot Review.
The majority of this information is best obtained during field operations and is thus considered a part of data
acquisition.


##### 3.5.7.1.1 Aids to Navigation

Every effort should be made to ensure that aids to navigation referenced in the Coast Pilot are correctly identified
and in agreement with both the chart and the Light List. Information regarding significant new aids to navigation
(e.g., buoys/lights marking specific dangers to navigation) should be added.


##### 3.5.7.1.2 Anchorages

Attempt to obtain information on both charted and uncharted anchorage areas. The adequacy and accuracy of
anchorage information in the Coast Pilot should be checked, and new reliable information should be added when
possible. Anchorage information is one of the most difficult types of information to obtain and check, since it must
come from actual anchoring experience. Good judgment must be exercised by field personnel in obtaining such
information. A particular location is not a good anchorage simply because someone has anchored there.

*Page 102*

------------------------------------------------------------------------------------------------------------------------


##### 3.5.7.1.3 Bridges

Note bridges that are in the process of renovation (to the extent that type of bridge, vertical clearance, horizontal
clearance, or other description normally mentioned in the Coast Pilot is affected), bridges that have been newly
constructed, and/or bridges that have been removed in whole or in part. Confirm proper names of bridges as
included in the Coast Pilot or shown on the charts. Obtain new names as appropriate. Confirm or obtain VHF radio
frequencies/channels monitored, hailing protocols used by local traffic and telephone contacts related to bridge
operations, if applicable.


##### 3.5.7.1.4 Channels

Text referring to privately maintained channels and basins, natural channels, and federally maintained channels
within the assigned survey area should be reviewed and updated as necessary.


##### 3.5.7.1.5 Dangers to Navigation

Review and update as necessary any Coast Pilot text addressing charted rocks, shoals, reefs, wrecks, piles, snags,
and other objects dangerous to navigation within the survey area.


##### 3.5.7.1.6 Depths and Sounding Data

Once present survey soundings have been processed and compared to charted depths, any Coast Pilot text
referencing specific depths within the survey area should be reviewed and updated as necessary. Note: The
hydrographer should be certain that final water level correctors have been applied to sounding data prior to
reporting specific depths in the Coast Pilot Review.

If new depth information is received for an area outside of the assigned survey, but can not be verified by approved
NOAA hydrographic survey methods, this information can be included in the Coast Pilot as “reported.” Reported
information should be avoided unless deemed critical for safe navigation. If reported information is used, it must
be qualified as such, giving the date and the source of information. Reported depths are published in the Coast
Pilot as shown in the following example: “In June 2004, the channel had a reported controlling depth of 3 feet.”


##### 3.5.7.1.7 Ferries, Cable Ferries, and Pontoon Bridges

Report the locations of new ferry terminals and routes and/or the abandonment of old ones. If applicable, include
information about VHF radio frequencies monitored, hailing protocol, and telephone contacts. Cable ferries and
pontoon bridges pose a potential hazard to mariners. Obtain detailed information on their operations. Information
regarding operational peculiarities of any other movable bridges encountered should be included.


##### 3.5.7.1.8 Landmarks

Landmarks shall be inspected from seaward insofar as practicable. New landmarks considered to be significant
for vessel navigation should be positioned with DGPS, if possible. Describe each landmark, including position,
height, color and any other distinctive features that will aid in identification. Give the shape of objects that may
not be generally recognized by the name alone, such as “the large white dish of the charted radiotelescope.”

*Page 103*

------------------------------------------------------------------------------------------------------------------------


##### 3.5.7.1.9 Locks, Canals, and Hurricane Gates

Operational peculiarities of locks, canals, hurricane gates, and other navigation projects should be noted. Include
information about traffic signals, VHF radio frequencies/ channels monitored, hailing protocol, and telephone
contacts, if applicable.


##### 3.5.7.1.10 Overhead Cables

Make note of overhead cables that are not charted and/or not mentioned in the Coast Pilot. Attempt to ascertain
the following about the owner of the new cable: name of the company, address, telephone number, and name of a
cognizant individual in the company. This information is necessary in order to obtain copies of the cable permits
from the local District Engineer staff of the Corps of Engineers.


##### 3.5.7.1.11 Major Deep Draft Ports

Coast Pilot information pertaining to major ports, shipping terminals, and wharves within the survey area should
be reviewed and confirmed to whatever extent practicable via sounding data and reconnaissance during survey
operations. Particular attention should be paid to depth information stated in the text.

If at all possible, the local pilot association should be contacted. Pilotage information is one of the most important
items in the Coast Pilot. Pilots should be requested to read the pilotage section in the Coast Pilot and point out any
errors and/or new information that should be added. Be sure to address where vessels are boarded or anchored for
quarantine, and whether inspections are made by any U.S. Government agency.

Additional information, such as low altitude oblique photographs, may be obtained from a variety of sources such
as the local port authority, harbormaster, harbor police, and customs, immigration, public health, and agriculture
officials at the port. Information on repair facilities can be obtained from shipyards and boatyards. Local towboat
companies are often a good source of information, not only regarding the size and type of tugs available, but also
for other information such as local peculiarities of winds and currents, the routes followed by tugs and barges, etc.


##### 3.5.7.1.12 Small Deep Draft Ports

Coast Pilot information pertaining to smaller deep-draft ports, shipping terminals, and wharves within the survey
area should be reviewed and confirmed to whatever extent practicable via sounding data and reconnaissance
during survey operations. Particular attention should be paid to depth information stated in the text. Although
small deep-draft ports do not typically have large port authority staffs, additional information may be available
from the port’s general manager.


##### 3.5.7.1.13 Small Craft Harbors

Coast Pilot information pertaining to small craft harbors within the survey area should be reviewed and confirmed
to whatever extent practicable via sounding data and reconnaissance during survey operations. Additional
information may be available by contacting either the harbormaster or harbor patrol personnel, as well as operators
of towboats, boatyards, marinas, and state and federal agencies. Local yachtsmen and fishermen can be consulted
when appropriate.

*Page 104*

------------------------------------------------------------------------------------------------------------------------


##### 3.5.7.1.14 Radar and Radio Information

If possible, obtain information on the best radar targets and the approximate maximum range at which they can
be positively identified and used. The VHF radio frequencies/ channels used in port areas for different types of
communications between various private and public concerns should be ascertained. Where a radio watch is
maintained by pilots, harbormasters, bridge tenders, lockmasters, and other parties significant to the mariner,
confirm guarding schedules, VHF radio frequencies, hailing protocol, and telephone contacts, if applicable.


##### 3.5.7.1.15 Shoreline Changes

Coast Pilot information pertaining to shoreline within the survey area should be reviewed and confirmed to
whatever extent practicable via sounding data and reconnaissance during survey operations. Note condition,
additions, and deletions of wharves, piers, and other waterfront structures. If a pier or other shoreline structure has
been removed, note whether piles or ruins remain as a navigational hazard. Assume the existence of submerged
ruins unless there is contrary evidence. Also report significant shoreline changes, whether caused by dredging
and/or filling or by natural events.

If Coast Pilot information pertaining to shoreline outside of the survey area (e.g., areas frequently transited or
facilities utilized during inports) can be verified or updated during survey operations, this information should be
addressed in the Coast Pilot Review.


##### 3.5.7.1.16 Wrecks

If numerous wrecks are found to exist in a specific location, an attempt should be made to ascertain the causes
from survey data and/or local sources. If a specific hazard is determined, suitable highlighting of the situation
should be verified or added in the Coast Pilot.

In addition to the above categories of information, any anomalous conditions that may affect safe navigation
should be addressed.


#### 3.5.7.2 Digital Photographs

When possible, digital photographs portraying significant Coast Pilot features should be acquired. Sea level
photos should be taken from seaward, from as high a vantage point as possible and close enough so that principal
landmarks can be identified. Photos taken successively from 2 miles out or less, typically upon entering or
departing a harbor, may be useful in identifying the harbor approach or specific landmarks. If a single photo will
not adequately cover the view of a harbor with sufficient detail, a panoramic series of photos can be submitted.
Digital photos submitted to the Coast Pilot Branch may be included in subsequent editions of the publication. To
ensure photographs are of sufficient quality for publication, the following criteria should be met:
* The camera should have a resolution capability of 4 megapixels or better.

* A digital zoom feature should not be used. A camera with minimum optical zoom capability from wide angle
(35mm) to a mild zoom (out to 105mm) is recommended. (Ideally, the camera would accept lenses of different
focal lengths, such as wide angle, normal, and zoom.) * Photographs should be taken using an ISO setting of
100 (preferred) or less, but in no case higher than 200.

*Page 105*

------------------------------------------------------------------------------------------------------------------------

* Shutter speed should be set to at least 1/100th of a second.

* The photograph should be taken using a pixel setting of approximately 2300 x 1700 or better.

* JPEG (*.jpg) format is required for submission. Use of any other format should be cleared by the Coast Pilot
Branch. Select “JPEG (EXIF)” if that choice is given. EXIF is a standard metadata format that embeds
information about the camera and its settings such as focal length, shutter speed, lighting condition, and other
valuable information about the photograph into the file.


### 3.5.8 Electronic Navigational Chart (ENC) Verification

Verifications of ENC data are primarily performed by the NRTs. If ENC verification is required in conjunction
with a standard NOAA hydrographic survey, it will be stated in the Project Instructions. Information regarding
ENC shoreline and offshore features is given below.


#### 3.5.8.1 ENC Shoreline Features


##### 3.5.8.1.1 Aids to Navigation

Unless specifically assigned, aids to navigation to be located are left to the discretion of the hydrographer. Range
lights, channel lights, and major pier lights are priorities and should be positioned using static GPS whenever
possible, unless an acceptable (Third-order, Class I or higher) published position is available. Other federally
maintained aids such as day beacons and buoys, as well as privately maintained aids may be located using
hydrographic positioning methods. Refer to section 7.2 of the HSSD for further guidance.


##### 3.5.8.1.2 Structures

On features directly affecting vessel docking, obtain one-meter accuracy DGPS positions on all critical points.
Other points on the same feature may be surveyed to five-meter accuracy and/or derived from the imagery/
shoreline files, provided they are accurate to five meters or less. All other structures may be surveyed to five-meter
accuracy. Enter all relevant information; i.e., name, status, condition, etc., in the “Remarks” column.


##### 3.5.8.1.3 Works in Progress

Determine the status of construction for the identified marine facility or other chartable shoreline construction.
Obtain as-built plan drawings if possible. When as-built drawings are obtained, ensure that they have a coordinate
system on them. If they don’t, the NRT should obtain reference positions for the drawings using a GIS data
collection and data maintenance system. Use the “Remarks” column to report the name, status, condition, or other
relevant information.

*Page 106*

------------------------------------------------------------------------------------------------------------------------


##### 3.5.8.1.4 ENC Offshore Features


###### 3.5.8.1.4.1 Bridges

The appropriate NSD Navigation Manager will attempt to get as-built drawings for project area bridges before the
NRT arrives. If as-built drawings have been supplied, then the NRT will position the ends or other identifiable
points of the bridge to provide geo-reference points for the drawing.

When no drawings are supplied and no DGPS interference is experienced, one-meter accuracy DGPS positions
are required, to delineate clearances between bridge pier fenders facing commercial vessel traffic. Bridge pier
fender points not facing commercial vessel traffic may be surveyed to five-meter accuracy depending on the
relative importance to be determined by the hydrographer. When acquiring data points around obstructions such
as bridges, differential correctors from the USCG beacons should be used. The Trimble Pathfinder Pro XRS has
multi-path rejection technology that works best when using USCG correctors. Use the “Remarks” column in
MapInfo Final Field Sheet table to report the name, status, condition, or other relevant information.
When a drawing is not available and DGPS interference is experienced, then the NRT will attempt to obtain
positions over the supports that separate the commercial channel. NRB will not acquire positions on bridge
fenders where the bridge structure causes DGPS interference.


###### 3.5.8.1.4.2 Channel Depths

Where applicable, inquire with facility owners/managers about the status of privately maintained channels to
update charted notations. Provide documentation in the Descriptive Report or Chart Letter and submit diagrams
or survey copies when possible. In some cases (at the discretion of the Team Leader) a survey of the channel will
be required to obtain the current operating depths.
