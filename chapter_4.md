Chapter 4
===========
Data Processing and Analysis
The purpose of this chapter is to provide the information necessary to clean, finalize, and analyze data for OCS
hydrographic surveys. The following types of data are addressed separately in this chapter.

•	 Bathymetry (VBES and MBES data)
•	 Imagery (SSS data)
•	 Features (bathymetry and imagery contacts, detached positions, AWOIS items, geographic positions)
Relevant steps regarding the post-processing of inertially-aided GPS data are mentioned in this section but full
details are discussed in the Ellipsoidally Referenced Survey SOP.pdf in Appendix 4. For additional guidelines
consult the HSSD Chapter 9 Ellipsoidally-Referenced Surveys.



4.1 Preparation for Data Processing
------------------------------------

Data processing for OCS hydrographic survey data is typically performed using CARIS HIPS and SIPS software.
HIPS tools are used to process bathymetry data, and SIPS tools are used with imagery data. To begin processing
data in CARIS HIPS and SIPS, a “Project” must be created. A CARIS Project consists of a data filing system,
structured according to a tree of project/vessel/day/line (PVDL) folders, where “vessel” refers to a particular vessel
configuration file, known as a HIPS Vessel File (HVF).

The HVF establishes, in HIPS and SIPS, the relationship between survey sensors as logged by the acquisition
software. The HVF must reflect any corrections or compensation of logged sensor data performed during
acquisition. Some sonar systems require, or perform in a superior fashion, if real-time corrections (e.g., refraction)
are used. Any real-time corrections included in the logged data must be accounted for when creating the HVF. The
HVF also includes information essential for estimating sounding measurement errors (see section 4.2.3.8). Depth
and position errors will be introduced if data are processed using an incorrect HVF.

Proper setup of HVFs is critical for accurate survey data, and this process is usually completed under the direction
of senior survey personnel. These files are typically created at the beginning of a field season, but they will need to
be amended if configurations change. Guidelines for creating an HVF are described in section 4.1.1. Refer to the
CARIS HIPS and SIPS User’s Manual, found on the Hydrosoft website, for addition information.

Once HVF files have been created, the HIPS and SIPS New Project Wizard can be used to specify a Project name,
associated vessels, and days for which data was acquired. The “day” name is formatted as YYYY-DOY (year + day
of year). Day of year (DOY) refers to a sequential number starting with 001 on January 1 of each year and ending
with 365, or 366 in leap years, on December 31 of that year.



*Page 108*

------------------------------------------------------------------------------------------------------------------------


Note: DOY is not synonymous with Julian Day Number and should not be referred to as such. The Julian Day
numbering system refers to the number of days since noon on January 1, 4713 BC, a system widely used by
astronomers.


### 4.1.1 Creating HIPS Vessel Files (HVFs)

A new HVF is created using the HIPS and SIPS Vessel Wizard, part of the Vessel Editor tool. As the user works
through the Vessel Wizard, HVF options must be chosen based on survey systems and configuration. Once the
initial HVF is created, additional parameters such as offsets and error corrections must be entered for each
individual sensor.


#### 4.1.1.1 HIPS and SIPS Vessel Wizard

The Vessel Wizard will first prompt the user to enter a name for a new HVF file. HVF naming conventions have
been standardized throughout the NOAA hydrographic fleet. The following naming convention shall be used for
NOAA hydrographic vessel HVF files:
<ship/field unit abbreviation>_<vessel hull number>_<data type + category>.hvf
Table 4.1 contains a list of common data types acquired during OCS hydrographic surveys and example HVF
names for each. Note that the field season year is not included in the name; rather, timestamp entries within the
HVF are used to track application dates. Only a reference to the principal echosounder or side scan sonar type
should be included in the last portion of the HVF name. More detailed equipment specifications and information
are recorded within the HVF. For HVFs associated with MBES and SSS data, include the sensor model; for vertical
beam echosounder data, use the suffix “VB.”
Once an HVF name is entered, the user will be asked to enter specifications for the applicable sonar system, such
as sonar type, number of transducers, number of beams, etc. The information requested is typically either based
on the physical system configuration or can be located in the sonar user’s manual.



*Page 109*

------------------------------------------------------------------------------------------------------------------------


Data Type
Multibeam Echosounder

HVF Name Examples
“FA_2806_Reson7125” - NOAA Ship
FAIRWEATHER launch 1010, Reson 7125
multibeam

Main-scheme Survey Lines or Investigation Lines

“BH_S5501_Reson7125” - BAY
HYDROGRAPHER, Reson 7125 multibeam
“RA_S221_VB” - NOAA Ship RAINIER, vertical
beam

Vertical Beam Echosounder
Main-scheme Survey Lines or
Investigation Lines

“NRT2_1210_VB” - Navigational Response Team
2, boat 1210 vertical beam
“TJ_S222_Klein5000” - NOAA Ship THOMAS
JEFFERSON, Klein 5000 100-percent side scan
sonar

Towed Side Scan Sonar - 100%
and 200% Coverage
Other Coverage (e.g., additional
investigations, buffer lines)

“NRT2_1210_Klein3000HF” - Navigation
Response Team 2, boat 1210, Klein 3000 high
frequency 100-percent side scan sonar
“TJ_3101_Klein5000Hull” - NOAA Ship THOMAS
JEFFERSON, launch 3101, hull-mounted Klein
5000, non-100/200 coverage

Hull-mounted Side Scan Sonar 100% and 200% Coverage
Other Coverage
Echosounder Point Observations

“NRT2_1210_EchosounderDP” - Navigation
Response Team 2, boat 1210, echosounder DPs

Depth “Detached Positions”
(DPs)

“RA_2801_EchosounderDP” - NOAA Ship
RAINIER, launch 2801, echosounder DPs
“RA_2801_ShorelineDP” - NOAA Ship RAINIER,
launch 2801, Shoreline DPs

Non-Echosounder Point
Observations
Diver Least Depth DPs
Shoreline DPs

“TJ_3101_DiverDP” - NOAA Ship THOMAS
JEFFERSON, launch 3101, Diver DPs

Table 4.1: Example HVF naming conventions for NOAA hydrographic vessels.



##### 4.1.1.1.1 Motion Sensor Options

HIPS and SIPS Vessel Wizard will prompt the user to enter what vessel motion data (i.e., attitude data) will be
recorded and whether these data should be applied during post-processing. The meaning of “apply in postprocessing” for heave is straightforward. If survey data were not logged with heave corrections applied during data
acquisition, and heave data (either real-time values or true heave, as discussed in section 3.4.1.2 were recorded
separately, then apply this correction in post-processing. The standard practice for OCS hydrography is to not
correct survey data for heave during data acquisition; hence, “apply in post-processing” is usually enabled for this
sensor in the HVF.

The application of roll and pitch is a bit more complicated than applying heave. The user must keep in mind that
options to apply roll and pitch will affect any remote heave calculations. (Remote heave is defined as changes in

*Page 110*

------------------------------------------------------------------------------------------------------------------------


vertical position of the transducer due to roll and pitch acting over a non-zero moment arm between the heave
sensor and the transducer). If remote heave compensation is to be performed in HIPS, the vessel coordinate
system reference point (RP) entered in the HVF will be treated as the center of rotation and, therefore, should be
established as close to the vessel’s center of motion as possible.

Many MBES sensors can be configured to acquire bathymetry using roll or pitch beam steering. In these cases, the
HVF apply roll & pitch options should be set according to the data acquisition configuration. If roll steering was
enabled during acquisition, do not apply roll in post- processing. If roll steering was not enabled, the HVF option
to apply roll in post-processing should be checked. Likewise, if pitch steering was enabled during acquisition, do
not apply pitch in post-processing. If pitch steering was not used, the HVF option to apply pitch in post-processing
should be checked.


##### 4.1.1.1.2 Configuration Options

The Vessel Wizard configuration options enable the user to enter offset parameters for “sound velocity” corrections
(more appropriately, sound speed corrections as explained in section 4.2.3.6 , a dynamic draft table, and “waterline”
value for the vessel. Typically, bathymetry data will require sound speed (i.e., refraction) correction during postprocessing and the option to “define parameters for sound velocity corrections” should be checked. If this option
is checked, the hydrographer will also be prompted to enter any mounting offsets for the sonar transducer. Only
large mounting offsets should be entered here. Small offsets will be accounted for during the patch test. However,
some MBES systems correct for refraction during data acquisition. If refraction correction has been performed in
real-time during data acquisition, it can be performed again during post processing with more flexibility in how
the sound speed correctors are applied to the data. Typically imagery data will not require sound speed correction
either, and “defining parameters for sound velocity corrections” is unnecessary for HVFs used only to process data
that will not be sound speed corrected during post-processing.

Dynamic draft refers to changes in draft induced by the flow effects of a vessel moving through the water. Corrections
for this effect can be applied during post-processing via either a Dynamic Draft table of speed-versus-draft values
entered in the HVF or from a “delta draft” time series that is loaded during post-processing. The OCS standard
practice is to enter a speed-versus-draft table that is applied in post-processing. Thus, in most cases the option to
“create a Dynamic Draft table or speed vs. draft values” should be checked and values manually entered into this
table by the hydrographer.

The term “waterline height”, as defined by CARIS, refers to the measured vertical difference between the vessel
waterline and the established origin of the local vessel reference frame (RP). This value will be positive if the vessel
waterline is below the RP, and negative if the vessel waterline is above the RP. Variations in static draft of the
transducer should be accounted for by adjusting the waterline height in the HVF, thus the HVF option to “define
vessel waterline height variations” should be checked and the waterline value applied in post-processing.
Note: Some sonar systems must be configured such that depths are reported relative to the waterline, rather than
the transducer. In such cases, the value entered for waterline may not be as defined above, and the hydrographer
should verify that the combination of values entered in the HVF for transducer vertical offset and waterline do not
cause an erroneous vertical correction.


#### 4.1.1.2 HIPS and SIPS Vessel Editor

Once a new HVF has been created with the Vessel Wizard, sensor offsets and additional sensors, such as CARIS
“TPU values,” can be activated using the CARIS HIPS and SIPS Vessel Editor. It should be noted that HVFs use a

*Page 111*

------------------------------------------------------------------------------------------------------------------------


left-handed coordinate system, as summarized in Table 4.2. (Be aware that despite the fact that the +Z axis is down,
when recording vessel motion positive heave action is up.) The user should verify that offset values determined
during the vessel survey adhere to the same coordinate system as the HVF. If this is not the case, surveyed offset
values will need to be converted so that the vessel configuration is accurately represented in the HVF.
Coordinate System Component
Direction
+X axis
Starboard
+Y axis
Forward (toward bow)
+ Z axis
Down (into the water)
+Pitch
Bow down
+Roll
Starboard up
+Heave
Up (out of the water)
Table 4.2: CARIS HVF coordinate system (a left handed coordinate system).

Note: Coordinate systems vary among NOAA survey systems and software. This information should be verified in
the appropriate user’s manual prior to entering offsets into any software or equipment configuration. Coordinate
systems for common OCS survey systems are described in Appendix 1, (Coordinate_Systems.pdf).

The hydrographer may find it useful to create a three-dimensional Vessel Shape when entering sensor offsets.
This image, created using Vessel Editor’s Edit > Vessel Shape menu, shows the relative location of sensors as entered
in the HVF and can provide the hydrographer with a quick verification that offsets have been entered correctly.
The field unit shall ensure that the vessel offsets, entered in the HVF are fully consistent with those, listed in the
DAPR (see section 8.1.5.1 of HSSD). Any inconsistencies shall be addressed in the DR (see section 8.1.4 of HSSD).

### 4.1.2 Creating CARIS Projects

CARIS Projects shall be created for each survey and include only the survey registry number (e.g. H12345, or
F00123). New Projects are created using the CARIS New Project Wizard. When adding a new project, the wizard
will request the following data:
•	 Description – Provide a brief summary of the purpose of the Project and any significant survey-specific
information. The bulk of the description can be extracted from the Introduction, Location, and Priority
sections of the Project Instructions. Note: Entering a description is important because this is one of the few
places in HIPS and SIPS where external metadata can be attached to digital data.

•	 Owner – List the assigned ship or field party, as well as the Lead Hydrographer (Commanding Officer or
Chief-of-Party) and Survey Manager.

•	 Map Projection – Map Projection establishes the coordinate system to be used for the Project view in HIPS/
SIPS. If AUTO_UTM is specified, the coordinate system of the Project view will be based on the ellipsoid
manually entered in the HVF. The AUTO_UTM option can be used, provided a Universal Transverse Mercator
(UTM) projection on the North American Datum of 1983 (NAD83) has been entered for all HVF files
associated with the survey.

•	 Project Extent – Enter the basic boundaries of the survey area. Project Extent is expressed as a regular (i.e.,
non-rotated) rectangle. Project Extent should completely cover the assigned survey limits. Note that data

*Page 112*

------------------------------------------------------------------------------------------------------------------------


brought into a CARIS Project are not automatically clipped to this area; the clipping function is optional and
requires user activation. If activated, the default clipping boundary will be the Project Extent, but this may be
modified by the user. Refer to the CARIS HIPS and SIPS User’s Manual for additional information on clipping
data.



4.2 Bathymetry Processing
--------------------------

NOAA hydrographic field units typically acquire bathymetric data using VBES, MBES, or a combination of both.
VBES depths are processed using the CARIS HIPS Single Beam Editor tool to review and edit data anomalies.
MBES data may be edited in two different ways: using CARIS HIPS Swath Editor tool to edit data in a time-series
mode, or using the CARIS HIPS Subset Editor tool to edit data in a spatial mode. In both instances, Bathymetry
Associated with Statistical Error (BASE) methods are used to generate, using one or more different algorithms, a
digital seafloor model that contains depth and uncertainty information at each model node. In addition to the
basic bathymetric layer, auxiliary information layers such as standard deviation of soundings, sounding density,
shoal depth, source identification, hypothesis count, and hypothesis strength will be generated depending upon
the algorithm used to construct the BASE surface. These BASE surface layers are used to guide the hydrographer
to areas that require further examination and/or editing. This concept is explained in greater detail in section 4.2.1
.

Unlike VBES and MBES data, depth measurements acquired by leadline, sounding pole and/or diver least depth
gauge are positioned using a type of target file referred to as a detached position (DP) and depth data is entered
manually in CARIS Notebook or Pydro. Since target files are more frequently used to locate point features such as
shoreline items and bottom samples than these types of depth measurements, processing details have been included
in section
4.4.1.2 .


### 4.2.1 The BASE Surface Concept

A BASE surface represents bathymetry as a dense grid of statistically derived depth estimates. Various products
can be derived from BASE surfaces, including a shoal-biased set of depth estimates for safe vessel navigation. The
BASE surface paradigm discussed herein is specifically designed for MBES data, which typically has a high
sounding density. Nevertheless, VBES data can also be assimilated into the BASE surface model. The Survey
Manager should consult, through his/her chain-of-command, OCS’s Hydrographic Surveys Division for the most
current guidance on incorporating VBES data into BASE surface data.


#### 4.2.1.1 Base Surface Methods

There are two different algorithms used by NOAA hydrographic field units for creating BASE surfaces: uncertainty
weighted grids and the Combined Uncertainty and Bathymetric Estimator (CUBE) method and uncertainty
weighted grids. The preferred method shall be the CUBE method, but uncertainty weighted grids will be allowed.
Their use shall be documented in the Descriptive Report. Each of these methodologies is described below.


*Page 113*

------------------------------------------------------------------------------------------------------------------------



##### 4.2.1.1.1 Combined Uncertainty and Bathymetric Estimator (CUBE)

CUBE is a gridding algorithm developed at the University of New Hampshire (UNH)/NOAA Center for Coastal
and Ocean Mapping Joint Hydrographic Center by Dr. Brian Calder. Its primary advantage over uncertainty
weighted grids is that it is less susceptible to noise. CUBE works in two stages:
Integration of Soundings into Hypotheses - During the first stage, all soundings in the area are grouped into
internally consistent depth hypotheses, using the uncertainty of the soundings as a threshold.

Disambiguation - After all soundings are integrated, a second stage determines which hypothesis at each node is
the most likely to be the seafloor. There are four disambiguation methods available:
	

(a) The density option selects the hypothesis with the greatest number of sounding samples.


	
	

(b) The locale option selects the hypothesis that is most consistent with its surrounding nodes that has 		
only one hypothesis.


	
	

(c) The density and locale option selects the hypothesis with the greatest number of soundings and is
consistent with neighboring nodes.


	
	

(d) The initialization option selects the hypothesis that is closest to an initialization surface created 	
previously.


	

The CARIS HIPS integration of CUBE is well documented in the CARIS HIPS and SIPS User’s Manual. This
manual should be referenced for details on the workings of the algorithm and explanations of the user interface.
When editing a CUBE surface, the user may opt to edit soundings or to edit hypotheses. For NOAA hydrographic
survey data, it is critical that only sounding edits be used to correct gridding problems. This is primarily because
hypothesis edits exist only in the context of a single grid, and will be lost if that grid is recomputed.

###### 4.2.1.1.1.1 CUBE Parameters

There is a small parameter file called “CUBEParams.xml” that is referenced in the HIPS environment. The values
in this file control the behavior of the CUBE gridding and disambiguation processes. The default CUBE parameters
are not authorized for NOAA surveys. Instead, field units shall use the CUBEParams_NOAA.xml file. Each of the
following grid resolutions has its own CUBE parameter set: 0.5m, 1m, 2m, 4m, 8m, 16m, and 32m. Field units shall
use the parameter set corresponding to the appropriate resolution(s) and depth ranges of their survey data as
specified in section 5.2.2 of the HSSD. A description of each parameter and its default value and allowable range
of values can be found in the header of the XML file.

Three parameters have been modified from the CARIS default values: Capture Distance Scale, Capture Distance
Minimum, and Horizontal Error Scalar.

The Capture Distance Scale value is a percentage of depth used to limit the radius of influence a sounding may have
on the grid. The system default value is 5.0. However, for all grid resolutions in the NOAA parameters file, the
value has been set to 0.5. Setting the value this low disables the function and forces the Capture Distance Minimum
to be used instead over the range of applicable grid resolutions. This fixes the Capture Distance to the grid resolution.
A value of 0.5 was determined to be low enough for all grid resolutions, since they grow with depth.

*Page 114*

------------------------------------------------------------------------------------------------------------------------


The Horizontal Error Scaler value is used to scale the horizontal error of each sounding when used in the radius of
influence computation. It affects the propagated uncertainty of each sounding and how it is combined into each
hypothesis. The system default value is 2.95. However, based on discussions with Dr. Calder, the value has been set
to 1.96, for all grid resolutions in the NOAA parameters file.

The Capture Distance Minimum value is minimum distance that the CUBE algorithm will search for soundings to
contribute to a node. It is used in conjunction with the Capture Distance Scale to limit the radius or influence of a
sounding. The system default value is 0.5. The Capture Distance Minimum is the only parameter that varies
between the grid resolutions in the NOAA parameters file.

The minimum capture distance radius is specified in sections 5.2.2.1 and 5.2.2.2 of the HSSD and is limited to
(0.707*grid resolution), or

This value defines the capture distance to ensure that the radius of influence touches the outer corners of the grid
resolution but not farther. With this capture distance, no sounding is ever “lost” to the algorithm, but there is not
an oversampling of data from areas significantly further than the grid resolution. Because all of the soundings are
in close proximity to the node, the grid most accurately depicts the seafloor in that area without losing any
soundings.


##### 4.2.1.1.2 Uncertainty Weighted Grids

In order to generate uncertainty-weighted BASE surfaces, TPU must be calculated for each sounding. TPU
accounts for either the priori estimate or sensor recorded horizontal and vertical components of uncertainty
associated with each sounding measurement. TPU is formulated from the summation of the modeled uncertainties
for all sub-systems included in the overall hydrographic survey system (e.g., water levels, tide zoning, attitude
sensor error, navigation sensor horizontal position error, sound velocity profile error, sonar bottom detection
method, etc.). The sources of uncertainty values include (or may be combination of) manufacturer specifications,
theoretical values, and empirical observations from the field. A priori estimates values are entered into the HVF
while sensor recorded values are applied from the recorded data during the Compute TPU process.

OCS-recommended a priori uncertainty values are contained in the CARIS HVF Uncertainty Values document in
Appendix 4. The uncertainty values described in the appendix are provided as guidance for use in standard NOAA
hydrographic surveys. These values do not cover the breadth of operations encountered by all field parties, nor do
they cover the range of equipment configurations possible for any particular vessel. As such, these values should
serve a starting point in developing a vessel’s error model. Any deviation from the attached values should be
completely described in the applicable Descriptive Reports and DAPR.

In general, soundings (observation points) do not coincide with grid nodes (BASE surface estimation points). To
account for this, the vertical component of a sounding’s TPU is propagated to a grid node according to a power law
that models the increase in uncertainty as a function of three variables: distance between sounding and node, the
sounding’s horizontal component of TPU, and grid node resolution. The amount of weight an observation exerts
on a given BASE estimation point is inversely proportional to the propagated vertical uncertainty of the observation.
See Figure 4.1 .


*Page 115*

------------------------------------------------------------------------------------------------------------------------


Figure 4.1: Model for propagated uncertainty in depth
Where V and H are the vertical and horizontal components of TPU (resp.), SH is a scale factor representing the
worst case error that horizontal TPU can contribute, xi and nj are the location of the sounding and estimation
node (resp.), x and y are the two-dimensional spacing of grid nodes, and the exponent is a heuristic to control
overall growth of propagated uncertainty, P . The HIPS BASE surface algorithm uses a value of 1.0 (HIPS has
already scaled H by 1.96, for a 95% confidence interval) and a value of 2.0.

Theoretically, every sounding can affect every node in a BASE surface encompassing a survey area. For computational
efficiency, HIPS limits a sounding’s radius of influence on surrounding nodes through the following “spreading
conditions.” (1) At a minimum, each sounding affects all nodes within a radius of 0.707 times the grid resolution
of its position; i.e., within half the distance of the diagonal on a regular (square) grid. Hence, a given sounding will
affect at least two to four nodes, depending on where it is situated with respect to the nodes. (2) Each sounding will
propagate at most a distance determined by a user-specified threshold of propagated vertical uncertainty. The
uncertainty threshold is expressed in HIPS according to an IHO sounding error model (see Figure 4.2 ); that is, an
estimate of all constant errors (a) and depth-dependent errors (b times d) are summed in quadrature as shown in
Figure 4.3.


Figure 4.3: Generalized uncertainty growth curve with respect to sounding radius influence (d).

OCS requirements for the accuracy of measured depths, as set forth in the HSSD, are adapted from IHO S-44,
Standards for Hydrographic Surveys, 5th Edition, which defines Special Order (a=0.25 meters, b=0.0075), Order
1 (a=0.5 meters, b=0.013 or 1.3% of depth), and Order 2 (a=1.0 meters, b=0.023 or 2.3% of depth) standards. OCS
specifies that the total sounding error in a measured depth at the 95 percent confidence level, after systematic and
system specific errors have been removed, shall not exceed the IHO Order 1 standard in depths up to 100 meters
and shall not exceed the IHO Order 2 standard in deeper waters. If either an IHO Special Order standard or a userdefined accuracy is required for a survey, these requirements will be stated in the Project Instructions.


*Page 116*

------------------------------------------------------------------------------------------------------------------------



##### 4.2.1.1.3 Other BASE Weighting Methods in HIPS

CARIS HIPS allows BASE surfaces to be generated using either swath-angle weighting, uncertainty weighting, or
CUBE discussed in the previous section. Swath-angle weighted BASE surface nodes do not incorporate TPU and,
hence, node “uncertainty” is not available therein. Unless specifically stated to the contrary, use of the term “BASE
surface” in conjunction with OCS hydrographic surveys refers to those surfaces generated using the uncertainty
weighting method or CUBE.


#### 4.2.1.2 BASE Node Attributes

The depth at a given BASE surface grid node, n, is the mean depth (weighted by propagated depth uncertainty) of
the set of N soundings whose domain, Di, contains n. Likewise, the uncertainty at a given node is the mean
uncertainty (weighted by propagated depth uncertainty) of all the soundings contained in set N. See Figure 4.4
Note that the depth at grid node n is the weighted mean of soundings 1, 2, and 3. Sounding 4 is not included
because its radius of influence does not encompass grid node n.


Figure 4.4: Formulation of Base surface nodes from soundings.



*Page 117*

------------------------------------------------------------------------------------------------------------------------


In addition to depth and uncertainty, users can include five additional attributes in the BASE surface nodal data.
The definitions of the seven nodal attributes are summarized below. Note that all node statistics are computed
from the set of surrounding soundings whose propagated vertical uncertainty passes a user-supplied threshold
(IHO Order):
•	 Depth - weighted-mean depth of soundings that contribute to a node; weighting is inversely proportional to
the propagated vertical uncertainty of the soundings.

•	 Uncertainty - weighted-mean vertical component of TPU of soundings that contribute to a node; weighting
is inversely proportional to the propagated vertical uncertainty of the soundings.

•	 Density - number of soundings that contribute to a node.

•	 Std_Dev - standard deviation of soundings that contributed to the selected hypothesis at the 68%CI
•	 Node_Std_Dev – standard deviation of the soundings that contributed to the current grid node at the
68%CI
•	 Shoal - shoalest sounding from the set of soundings that contribute to a node.

•	 Mean - sample mean of the set of soundings that contribute to a node.

•	 Deep - deepest sounding from the set of soundings that contribute to a node.


### 4.2.2 Bathymetry Processing Diagrams


Figure 4.5: Processing flow diagram for VBES data.



*Page 118*

------------------------------------------------------------------------------------------------------------------------


Figure 4.6: Processing flow diagram for MBES data.


### 4.2.3 Daily Batch Processing

A number of processing tasks need to be performed on “raw” bathymetry data (i.e., unaltered data in the format
recorded by the acquisition software) before any detailed analysis and evaluation can occur. Some of these daily
tasks are interdependent, and the specific sequence is critical. The relevant daily batch processing tasks are listed
below. Refer to the Bathymetry Processing Flow Diagram 4.6 for the appropriate ordering of steps.
	

1. Conversion (Section 4.2.3.1 )

	

2. Load Attitude/Navigation (Section 4.2.3.2 )

	

3. Load Error Data (Section 4.2.3.3

	

4. Load Delayed Heave (Section 4.2.3.5)

	

5. Load Tides or Compute GPS Tides (Section 4.2.3.4

	

6. Sound Speed Correction (Section 4.2.3.6 )

	

7. Merge (Section 4.2.3.7 )

	

8. Compute TPU (Section 4.2.3.8

	

9. Filter (Section 4.2.3.9 )

	

10. Add to Coverage BASE Surface (Section 4.2.3.10


*Page 119*

------------------------------------------------------------------------------------------------------------------------


Most of the tasks above can be semi-automated using the HIPS “Batch Processor” tool. Data format dictates how
specific batch processing actions should be configured; thus, a separate HIPS Batch Processing File (.hbp) is needed
for each raw data format type.

In general, all of the aforementioned tasks should be completed for any type of echosounder data. A basic set of
batch processing files can be specified for each data type and reused on the appropriate set of survey lines acquired
each day. In some circumstances, either creation of custom batch processing files or manual processing of one or
more tasks, line-by-line, in non-batch mode may be necessary. For example, conversion and filtering options may
need to be customized to reflect changes in echosounder performance as weather conditions varied throughout a
survey day.


#### 4.2.3.1 Conversion

CARIS HIPS supports numerous different data formats that can be used to record bathymetry. During conversion,
HIPS uses the raw data to create a single, proprietary data format that will be used in subsequent CARIS processing
routines. These files in CARIS HIPS format are referred to as “HIPS files” or “HDCS files”.

Depending upon the system type and setup, recorded raw data may have been corrected for factors such as vertical
(depth or height) offsets, vessel motion, or acoustic refraction during acquisition. It is critical that HVFs account
for any real-time corrections performed, so that “double corrections” do not occur during post-processing.
If an HVF error is discovered subsequent to post-processing, it may be necessary to reapply certain correctors and
re-merge. Depending upon the error, a re-conversion may be required; however, most HVF settings do not impact
the HIPS data conversion process. (HVF settings that can directly affect the data conversion process include VBES
draft and MBES beam numbering.) Data processors should not automatically resort to time-consuming
reconversion and re-processing of a significant amount of data upon discovering an HVF error. If unsure whether
data repairs are necessary, the Survey Manager should consult, through his/her chain-of-command, the
Hydrographic Systems and Technology Program for assistance.

The following sections contain guidance for converting common raw bathymetry data formats used by OCS into
HDCS files. Relevant background information is provided, followed by a table of guidelines for specific HIPS and
SIPS Conversion Wizard settings related to each raw bathymetry format.

Note: HIPS uses the same Conversion Wizard as SIPS for a given raw data format. Options related to conversion
of sonar imagery stored in raw MBES data are not addressed in this section; see section 4.3.2.1 for imagery
conversion details.


##### 4.2.3.1.1 HYPACK

HYPACK is the standard data format used by NOAA hydrographic field units to log VBES and MBES data.
HYPACK software is used to store data from a variety of MBES systems via an additional software module called
HYSWEEP. For OCS hydrographic survey data, HYPACK VBES files should be recorded using a DOY (erroneously
termed “Julian Date” in the HYPACK software) file extension. MBES data, recorded using HYSWEEP should be
logged as ASCII *.HSX (HYSWEEP Survey Extension) files.

Within the raw HYPACK file, data recorded from each sensor in the acquisition system is assigned a “device
number.” This numbering scheme will vary according to the specific hardware configuration used to record the
data. During conversion, device numbers can be specified to correlate each sensor’s data string with a specific type

*Page 120*

------------------------------------------------------------------------------------------------------------------------


of data (e.g., echosounder, heading, navigation, etc.). If no device numbers are specified, the converter will look for
sensor data using known NMEA device strings. Specifying device numbers during conversion ensures that HIPS
does not incorrectly identify a data string. Device numbers can be verified by reviewing a raw HYPACK line file in
a text editor, such as WordPad, in which each device number will be listed adjacent to its respective device name.

###### 4.2.3.1.1.1 VBES Data

When logging VBES data, HYPACK records depth values directly from the echosounder, rather than two-way
acoustic travel times. For OCS hydrographic survey data, field units must recalculate VBES depths using an actual
measured sound speed profile during post-processing. HIPS will assume an estimated sound speed of 1500 m/s
was applied to data during acquisition and uses that value to determine a two-way acoustic travel time for each
sounding. HIPS can than recalculate VBES depths using a measured sound speed profile.

Note: If using a VBES system in which the speed of sound through water can be manually entered, the hydrographer
must enter 1500 m/s to facilitate the above HIPS process, as noted in section 3.2.3 .

If dual-frequency VBES data are being converted, high- and low-frequency soundings are stored side-by-side in
the HYPACK raw data record. During conversion, each sounding will be flagged as either “Primary” or “Secondary”
in the order in which it appears in the datagram. For example, if the high frequency depth is listed first in the
record and the user chooses “Primary, Secondary” for conversion, the high frequency depth will be flagged Primary
and the low frequency depth will be flagged Secondary. Primary soundings are also flagged “Selected” by default
in HIPS, and only Selected depths will be carried through to final processing. Users may override the Primary/
Secondary flagging assigned during conversion to force a depth into, or remove one from, the set of Selected
depths.

Note: In dual frequency systems, the low frequency beam width will be wider than the high frequency beam width.
If the low frequency return shows a shoaler depth than the high frequency, it often indicates a feature offset from
the vessel trackline. The least depth of such a feature may not have been captured by the low frequency signal; thus,
the hydrographer should note the feature’s position and perform a development.


###### 4.2.3.1.1.2 MBES Data

Converting HYSWEEP MBES data is nearly identical to converting HYPACK VBES data. The primary differences
are that the user must select raw *.HSX files for conversion and choose the “Multibeam” option for soundings,
rather than Single Frequency or Dual Frequency as would be required for converting VBES data. Device numbers
should still be specified as described in the beginning of this section.



*Page 121*

------------------------------------------------------------------------------------------------------------------------


Options

Dual Frequency

OCS Guidelines
If Single Frequency VBES data is being converted, it
will automatically be classified as “Primary”.

The OCS standard is to read in high frequency as
“Primary and low frequency as “Secondary”.


Multibeam

For HYSWEEP MBES data, simply choose the
multibeam option.


Single Frequency

Typically, static draft should not be applied during
conversion. The OCS standard is for sensors to be
Static Draft
referenced to a vessel RP and static draft to be accounted
Apply during conversion
for via a “waterline” correction entered in the HVF.

Refer to section 4.1.1.1.2.

If the hardware setup in HYPACK is unambiguous,
then blank device numbers may work fine; OCS
Device Numbers
recommends explicitly stating the device numbers
during conversion.

Data acquired for OCS hydrographic surveys shall be
corrected for sound speed using actual measured sound
Sound Velocity
speed profiles. For HYPACK data, this process is
performed in HIPS.

Table 4.3: OCS guidelines for converting HYPACK data.


##### 4.2.3.1.2 Simrad

The Simrad data converter is designed for use with data from Kongsberg Simrad multibeam systems, such as the
EM 710, EM1002 and/or EM3000. Two notable options are available when converting Simrad data, shortening
line names and decimating attitude data.

Simrad generated survey line names can be quite long. During conversion, the user can opt to modify raw line file
names into 12-character HIPS line names using the format YYDDD_HHMMSS (2-digit year + DOY + integer
hour, minute, second, based on the starting date and time of the line data).

To reduce file size, attitude data can be decimated during conversion. Often, the output rate of attitude sensors
used during multibeam data acquisition can be unnecessarily large (e.g., higher than 25 Hz), creating very large
attitude data files in HIPS. The attitude data decimation factor determines the ratio of attitude data that is converted.
For example, using a factor of 1 converts all data; a value of 10 converts every tenth attitude record.
Options

OCS Guidelines
Shorten Line Names
OCS recommends shortening line names.

A minimum attitude sample rate of 25 Hz is
recommended by OCS. Do not decimate attitude data
Attitude Data Decimation Factor
deyond this value, e.g. if attitude sample rate is 100 Hz,
do not decimate attitude data by a factor greater than 4.

Table 4.4: Guidelines for converting Simrad data.


*Page 122*

------------------------------------------------------------------------------------------------------------------------



##### 4.2.3.1.3 Generic Sensor Format (GSF)

Generic Sensor Format (GSF) may be used to store data from a variety of VBES and MBES system configurations.
GSF is particularly well suited for storing data that have been subject to real-time corrections during acquisition.
As noted in section [sec:Preparation-for-Data], any real-time corrections in the logged data must be accounted for
when creating the HVF. Real-time corrections may also affect processing decisions made in HIPS.

As compared to the Daily Batch Processing steps presented in section [sub:Daily-Batch-Processing-SSS], the state
of a given GSF dataset may range from raw (i.e., no corrections applied) to a condition where steps 2, 3, and 4 have
already been completed. The options for converting GSF data into HDCS files are fairly simple because much of
the behavior of the converter cannot be manipulated by the user. The GSF format includes a standard ping flag
definition to indicate whether data are “on line” (e.g., data from a planned survey line) or “off line” (e.g., data in
between lines, during turns, transits, etc.). The only choice a user must make during HIPS conversion of GSF data
is how to treat these off-line data.


##### 4.2.3.1.4 Extended Triton Format (XTF)

The eXtended Triton Format (XTF), created by Triton Imaging, may be used to store data from a variety of MBES
systems. (Imagery data can also be acquired in the XTF format, as discussed in section 4.3.2.1.3 ) XTF datagrams
are comprised of a Triton-defined “header” attached to an optional manufacturer-specific sensor data packet. In
the past, XTF was a common data format within OCS, primarily due to the widespread use of Triton Imaging’s
IsisSonar data acquisition software. However, since ISIS has been replaced by HYSWEEP on NOAA hydrographic
field units, MBES data is generally no longer acquired in XTF.


#### 4.2.3.2 Load Attitude/Navigation

For ERS based projects, the processed Smoothed Best Estimate of Trajectory (SBET) files are loaded using the
CARIS/HIPS Load Attitude/Navigation tool. Load Attitude/Navigation will overwrite any previously converted
real-time attitude and navigation data. The hydrographer can review/edit the attitude and navigation time series
data using HIPS editors. For additional information regarding ERS see the Ellipsoidally Referenced Survey SOP.
pdf in Appendix 4.


#### 4.2.3.3 Load Error Data

The CARIS/HIPS Load Error Data tool is used to override HVF TPU values with observed/computed uncertainty
time-series values. For non-ERS projects the observed uncertainty time series in the POS PCS files (.000) is used.
For ERS-based projects, the processed error metrics file that accompanies the SBET file (smrmsg) is used in the
CARIS/HIPS Load Error tool. During the CARIS/HIPS Compute TPU step (4.2.3.9 ) the hydrographer can indicate
the uncertainty source: (HVF) Vessel Settings, Realtime Data or a Custom mix of uncertainty sources. For
additional information regarding ERS see the Ellipsoidally Referenced Survey SOP.pdf in Appendix 4.

#### 4.2.3.4 Load Tides

For NOAA charting purposes, hydrographic sounding data must be merged with water level observations relative
to the local “chart datum,” typically mean lower-low water (MLLW). The HIPS Load Tide tool creates a water level
height time series in each survey line directory that is appropriate for the position and time of each line.

*Page 123*

------------------------------------------------------------------------------------------------------------------------


If tidal effects throughout a survey area are complex or if multiple water level stations are located nearby, an
optional zone definition file (.zdf) can be used to express how the amplitude and phase of the tide within a given
area is related to available water level station data. For each zone, a reference water level station, time corrector, and
range corrector will be provided. This technique called discrete tidal zoning does not account for the effects of
spatially varying harmonic and non-harmonic effects on the water levels. The accuracies achieved by this method
may be inconsistent from one survey area and/or time periods to others, and the resulting uncertainties may be
difficult to quantify.

A tide or water level file must be loaded prior to merging data in HIPS, but actual water level data may not yet be
available. Thus for daily data processing, a zero or predicted tide file will often be used. If survey data were
compensated for water level variances during acquisition or if water level measurements are not necessary for the
survey area (e.g., some non-tidal rivers or lakes), a “zero tide” file must still be loaded to enable the HIPS merge
process.

Note: Non-tidal areas are still subject to water level variances due to factors such as wind, rain, barometric pressure
changes, and freshwater runoff.

If preliminary or verified water levels are available, the most accurate of these data should be applied (see section
4.2.5.1.1 ).

Note: HIPS currently supports a “weighted averaging” option for zoned tides. This option applies data from
multiple water level stations by weighting observed water level measurements based on the inverse of the station
to- vessel distance. OCS does not recommend using HIPS “weighed averaging,” because the two-dimensional
character of the survey area is not taken into account (i.e., the station-to-vessel distance vector may cut through
land).


##### 4.2.3.4.1 Tidal Constituent and Residual Interpolation (TCARI)

Tidal Constituent and Residual Interpolation (TCARI) was designed for total water levels relative to Mean Lower
Low Water (MLLW) at selected hydrographic survey areas along the coast by the spatial interpolation of tidal data.
The model spatially interpolates the harmonic constants (used to predict the astronomic tide), tidal datums, and
residual water levels (i.e., the non-tidal component or the difference between the astronomically predicted tide and
the observed water level) using the values at a combination of operational and historical stations. The method
works best in regions where there is an abundance of high quality tidal data surrounding the survey area. TCARI
methodology has the potential to yield water level correctors with increased accuracy and reduced uncertainty.
The use of TCARI, just as in discrete tidal zoning, requires the hydrographer to evaluate and understand the tidal
characteristics of the survey areas. Success in either method requires information from historical tide stations and
other sources. Gaps in information limit both methodologies. And both methodologies require tide stations to be
in operation during survey operations. TCARI first requires the development of a model grid to cover the survey
areas and then requires a spatial field of harmonic constants from historical stations for the interpolation instead
of just the average time and range of tide required by tidal zoning. Finally, TCARI planning requires an analysis of
the non-tidal residual across the survey area to determine the location and number of stations to be in operation
during the survey. TCARI grid files, interpolation weighting functions, and harmonic constant files are created
during planning and sent to the survey platform. Survey vessels must obtain the observed data from the specified
tide stations during the survey so that TCARI can apply the interpolated water level residuals in the process.


*Page 124*

------------------------------------------------------------------------------------------------------------------------


Both TCARI and traditional tidal zoning will be used and the applicable tool will be determined by CO-OPS in the
planning stage on a survey by survey basis. CO-OPS will either send TCARI program files or discrete zoning to the
field but not both. Field units receiving a TCARI grid from CO-OPS can load it into Pydro with water level data to
create tidal reducers for the survey’s bathymetry. Once TCARI has created the tide files, the data can be merged in
CARIS (loading tides option is not necessary, you will not need a .zdf file).

For final tide correctors, the survey vessel should generate and submit a request for Final tides, stating on the
request that TCARI was used for that particular survey.

CO-OPS will review and quality control the TCARI grid sent to the survey vessel and if no discrepancies or
problems are found, will send the vessel a note stating that the preliminary grid can be used for final tidal correctors.
If CO-OPS finds discrepancies or problems, then CO-OPS will re-evaluate and determine the best solution.

##### 4.2.3.4.2 Compute GPS Tide

For ERS based projects, the CARIS HIPS Compute GPS Tide function creates the HDCS GPSTide file using the
SBET converted GPSHeight and the loaded Ellipsoid to chart datum Separation Model (SEP, if any). An Ellipsoid
to chart-datum model may consist of one of the alternate models described in Section 9.2 in the HSSDM. Computing
GPSTide with a ”zero” separation is used to maintain merged soundings relative to the Ellipsoid and a vertical
datum transformation is applied during grid processing. Additional details regarding the application of GPS Tide
can be found in the Ellipsoidally Referenced Survey SOP.pdf in Appendix 4.


#### 4.2.3.5 Load Delayed Heave

If POS MV TrueHeave was logged during data acquisition, these files should be loaded using the HIPS Load
Delayed Heave tool. Loading TrueHeave files will not overwrite real-time heave values that are automatically
recorded in a raw file. However, once TrueHeave files have been loaded, CARIS will automatically apply True
Heave unless the user manually deletes the TrueHeave files from the PVDL directory. The hydrographer can
review/edit the TrueHeave time series data using HIPS Attitude Editor. TrueHeave data will be applied to survey
soundings during either HIPS SV Correct (if performed) or Merge, provided the “apply in post-processing” option
for heave has been checked in the HVF.

Note: Simrad data is typically compensated for real-time heave during acquisition. To avoid a double-correction,
the Simrad-based TrueHeave algorithm in HIPS applies a vertical adjustment equal to the difference between
TrueHeave and real-time heave.


#### 4.2.3.6 SV Correct

Correcting sonar data for the speed of sound (through water) actually refers to performing a refraction correction
based on a sound speed profile of the water column. Variations in the speed of sound (primarily due to water
temperature variations, or thermocline) result in refraction (bending) of sonar beams. The speed of sound through
water will decrease as water temperature lowers, causing a sonar beam to bend downward and creating depth and
position errors in any measurement calculated based on travel time and an assumed linear travel path of the sonar
beam. Figure 4.7 illustrates the effect of refraction. The sound wave striking the thermocline at point B slows down,
while point A on the same sound wave continues at the original speed until it strikes the thermocline at C. As a
result, the sonar beam bends downward.


*Page 125*

------------------------------------------------------------------------------------------------------------------------


Figure 4.7: Sonar refraction due to thermocline.

Note: Although often referred to as sound velocity correction, bathymetry data are actually corrected for sound
speed, as only the scalar magnitude of velocity (i.e., speed) is used by HIPS. However, when referring to a specific
manufacturer’s process, the manufacturer’s terminology will be used in this manual, e.g., CARIS’ terminology
(sound velocity or SV) will be used when referring the CARIS procedure “SV Correct”.

If sound speed corrections have not been applied in real-time during data acquisition, a HIPS Sound Velocity
Correction must be performed using the SV Correct tool. Two stages of sound speed processing are possible in
HIPS: (1) Adjustment of sonar beam (reported) launch angle through flat face refraction (FFR), which is not
applicable for all MBES systems, and (2) adjustment of sounding horizontal position and depth through geometric
beam ray-tracing. During HIPS SV Correct, survey line “ObservedDepths” data (alongtrack/acrosstrack position
and depth with respect to the vessel RP) are recalculated from “SLRange” data (beam launch angle, one-way travel
time) and corrected for acoustic refraction as well as (if indicated in the HVF) waterline, dynamic draft, heave, roll,
and pitch.

Note: the “Apply” box in the HVF must be checked for waterline, dynamic draft, and each attitude sensor for these
data to be applied.

If any sensor smoothing was performed during post-processing, the user may choose to apply the smoothed heave,
roll, and pitch sensor values during SV Correct.

Note: Choosing the smooth sensor option will not affect survey data if smoothed coefficient data are not present.
The unsmoothed sensor data will be applied by default.

FFR is very important to the beam forming process for MBES systems that use flat-faced transducers, and OCS
recommends this process be performed during data acquisition. However, for certain Simrad flat-faced multibeam
transducer types, HIPS is capable of performing FFR during post-processing.

For Simrad, FFR can be performed in HIPS if beam range and beam angle datagrams are present in the raw data.
(Simrad EM data logged in Simrad Merlin/SIS RAW.ALL format includes the necessary datagrams; EM data logged
in HYPACK HYSWEEP format does not.) A check box in the HIPS SV Correct dialog to “Perform an additional
recomputation of the steered beam angles based on a new surface sound speed that will be interpolated from the
sound velocity profile” controls whether or not HIPS will attempt FFR.


*Page 126*

------------------------------------------------------------------------------------------------------------------------


If data quality issues dictate that FFR be performed during SV Correct, any SSP files present in the HDCS data
must first be manually deleted.

Beam ray-tracing is performed on all MBES data during HIPS SV Correct, regardless of echosounder type. Starting
from the initial launch angle (reported or otherwise FFR-corrected), each sonar beam within a given survey line is
processed as a ray refracting through the loaded sound speed profile and tracing a non-linear path. The distance
of this path is assumed equivalent to the measured one-way travel time for the beam. By calculating a more precise
one-way travel time, a more accurate beam position and depth can be determined.

Typically, a concatenated SVP file (generated by NOAA’s Velocipy software) that contains multiple sound speed
profiles, complete with metadata to indicate when and where observations took place, will be applied to survey
data. In such cases, the user will need to choose a method for selecting how individual sound speed profiles are
applied. HIPS SV Correct provides four options: previous in time, nearest in time, nearest in distance, nearest in
distance within time. The method selected should be whichever will most accurately represent survey area
conditions.


#### 4.2.3.7 Merge

The HIPS Merge process calculates “Processed Depths” (latitude, longitude, depth) by compensating “Observed
Depths” (alongtrack/acrosstrack position and depth with respect to the vessel RP) for heading, navigation, and
tide data. Merge will also apply vessel attitude, waterline, and dynamic draft if the data were not previously
processed with SV Correct.

Note: the “Apply” box must be checked for waterline, dynamic draft, and each attitude sensor in the HVF for these
data to be applied.

The HIPS Merge tool can determine what corrections have been applied during SV Correct and will not perform
a double correction for these sensors.

If any sensor smoothing was performed during post-processing, the user may choose to apply smoothed sensor
values during Merge.

Note: Choosing the smooth sensor option will not affect survey data if smoothed coefficient data are not present.
The unsmoothed sensor data will be applied by default.

For ERS based projects, use the “Apply GPSTide” option in the merge dialogue to select the GPSTide file computed
in section 4.2.4.3.2 .


#### 4.2.3.8 Compute TPU (Total Propagated Uncertainty)

Prior to data processing, vessel offsets and total propagated uncertainty values based on uncertainty estimates for
survey equipment should have been entered into the corresponding HVF (see CARIS HVF Uncertainty Values
document in Appendix 4).

For the most part, uncertainty estimates entered into the HVF file are static over a field season or in the absence of
changes to the vessel configuration. Some HVF uncertainty estimate values may need to be adjusted on a case-bycase basis to account for any un-modeled uncertainty in a given component of the sounding. For example, in areas
with strong currents, uncertainty in vessel speed can be adjusted in the sensor TPU section of the HVF to

*Page 127*

------------------------------------------------------------------------------------------------------------------------


compensate for appreciable differences between speed-over-ground and speed-through-water. Another critical
example of TPU values that may need to be updated in the CARIS HVF is depth uncertainty introduced by heave
in singlebeam data acquired on vessels without an attitude sensor. Survey days with substantial heave introduce a
larger depth uncertainty than calm days, and require a larger TPU value in the heave section of the HVF. An
estimation of uncertainty introduced by heave can be calculated by multiplying the heave amplitude (1/2 the wave
height) by 0.707. (This formula is equal to 1 sigma of a sinusoidal wave).

Most of the uncertainty estimates that are entered into a CARIS HVF are straightforward and are based on direct
measurement techniques or manufacturer provided information. The estimation of the uncertainty value associated
with MRU alignment is an exception. There is no direct method to measure or estimate MRU alignment uncertainty.
One method to estimate these values is to calculate the standard deviation of a large sample of angular bias values
resolved with a patch test. The sample size can be created either by a number of people resolving the angular biases
or a couple of people resolving the values numerous times. Angular bias values resolved in a patch test are actually
a measurement of the angular bias that exists between the transducer reference frame and the MRU reference
frame. Therefore, any uncertainty values derived from the patch test angular biases are based on the same
relationship. As it is the angle between the MRU and the transducer that we are measuring, rather than the absolute
alignments of both the MRU and the transducer to a vessel reference frame, we can assign this uncertainty to
either the MRU alignment or the transducer alignment. CARIS expects this value to be entered into the MRU
alignment uncertainty field.

Note: All changes made to HVFs used to process OCS hydrographic survey data shall be approved by the field
unit’s Chief-of-Party and completely described in the Descriptive Report. Provided the TPU sensor values in the
HVF do not require modification as noted above, TPU computation for specific survey lines is completed by
selecting a set of survey lines and choosing the Compute TPU process in HIPS. Once the process has been selected,
uncertainty values that change on a survey-by-survey basis, such as tide and sound speed, are entered into the
Compute TPU dialog box (see below regarding Tide zoning uncertainty values for TCARI tides).

CARIS allows for only one sound speed and one tide value to be entered per survey area, on a survey-wide basis
(at BASE surface creation) in the Compute TPU dialog box. HSTP is working with CARIS to adapt a statistical
approach which will allow for multiple values per survey.

Certain error values in the HIPS vessel file (HVF) may be overridden with real-time or post-processed error
values. Prior to computing TPU, use HIPS Load Error Data from the Applanix POS PCS raw file (.000) or the
Applanix POSPac post-processed RMS file (smrmsg ).

Refer to Appendix 4 for an example of the CARIS Compute TPU Dialog menu.



*Page 128*

------------------------------------------------------------------------------------------------------------------------


Tide zoning uncertainty values at the 95% confidence level for discrete zoning are provided by CO-OPS in the tide
requirements document on the project CD. All error value components entered in CARIS for TPE calculation are
assumed to be 1 sigma; therefore, the value provided by CO-OPS should be divided by 1.96.

Tide zoning uncertainty values for TCARI tides are loaded on a line-by-line basis using NOAA’s Pydro-TCARI
software. Pydro’s Tides->CARIS TCARI Tide->”Load TCARI Tide in HIPS PVDLs” is used in place of CARIS
HIPS Process->Load Tide. This operation in Pydro-TCARI loads both tide corrector and tide uncertainty data
(HDCS “Tide” and “TideErrorFile”, respectively) into a given survey line.

For ERS based projects, if a SEP has been used in the HIPS Compute GPSTide step (processed depths relative to
MLLW), the associated vertical datum transformation uncertainty is currently entered in place of the tide values
in the Compute TPU dialogue. The VDATUM transformation uncertainty is based on the modeled maximum
combined uncertainty (MCU) and will be provided by HSD. Additional details regarding the application of Load
Error Data and Compute TPU can be found in the Ellipsoidally Referenced Survey SOP.pdf in Appendix 4.
The sound speed component of total propagated uncertainty is a function of environmental variability with respect
to space and time and instrument/calibration uncertainty. Of the two, environmental variability has the greatest
influence. Sound speed has a complicated dependence on salinity, temperature and pressure with the greatest
change in acoustic propagation speed occurring with the change in temperature between the surface and the lower
limit of the thermocline.

HSD has determined that the measured sound speed uncertainty may range from 0.5 to 4 m/s. This range depends
on the spatial and temporal environmental variability and the frequency at which sound speed casts are taken.
Casts taken at a high frequency (i.e. every 15 minutes or less) will capture the spatial variability better and lower
the uncertainty values. HSD requires platforms to use the measured uncertainty values (i.e. TPU) for sound speed
listed in the CARIS HVF Uncertainty Values document in the Appendix 4.

Field Units should note the 4 m/s uncertainty estimate (listed in the table from HTD-2 and HTD-10) for traditional
sound speed casts is a conservative estimated variability value determined via Velocipy. Hydrographers can lower
this uncertainty by increasing the number of casts for a given areas. Thus, field units are strongly encouraged to
utilize a high frequency cast system (e.g., MVP) whenever possible and especially in highly variable areas.
Sound speed uncertainty is the subject of continuing research and investigation at UNH CCOM/JHC. Velocipy
has incorporated some of this research such as the Uncertainty Wedge Analysis (UWA) and statistically estimating
sound speed uncertainty (ESS). See the Velocipy Operations Manual (included on the Hydrosoft website)for more
information. Future research is underway to create an algorithm to estimate the sound speed uncertainty value
more accurately using temporal and spatial separation between the sound speed profiles and soundings. . Field
units which have not been trained in the proper use of the UWA and ESS within the Velocipy software should use
the uncertainty values listed in the CARIS HVF Uncertainty Values document in the Appendix 4 but are welcome
to test out the program.

The TPU values associated with surface sound speed have a smaller range and magnitude than measured sound
speed (0.2 m/s to 2 m/s) because sound speed is continually measured at the transducer. The sound speed
uncertainty, therefore, is dictated by the sound speed gradient at the velocimeter’s sensor head.
If field units wish to deviate from the sound speed uncertainty values listed here, a review of the variability in the
surface sound speed will be necessary to estimate the sound speed uncertainty for a given survey. If the field unit
can prove through detailed documentation and calculation that their calculated uncertainty is lower than those
stated in the CARIS HVF Uncertainty Values document in Appendix 4), then the lower value may be used. As with
any deviation from procedures specified in the HTD’s, FPM or the HSSD, methods for estimating uncertainty, and

*Page 129*

------------------------------------------------------------------------------------------------------------------------


justification for this deviation, should be clearly described in the Descriptive Report as well as the Data Acquisition
and Processing Report. The field should be aware, however, that if the processing branches disagree with the
method used, any corresponding surveys using these uncertainty values may be returned to the vessel. Therefore,
HSD strongly recommends that field units communicate to the branch their proposed approach. If the branch feels
the method is adequate, a detailed description of the method, corresponding calculations and data will need to be
sent to HSD for verification (and dissemination to other field units if approved). NOAA does not currently conduct
sweep surveys, and the lower section of the TPU dialog box is not utilized.

The TPU values for each sounding ( ˆV andˆH , see propagated uncertainty equation in Figure 4.1) will be computed
at the 95% confidence interval.


#### 4.2.3.9 Filter

Depending upon data quality, the hydrographer may choose to filter a dataset during post-processing. HIPS
provides several filtering tools that can be used to automatically flag data as rejected or accepted. Filtering methods
commonly used for processing OCS hydrographic survey data include TPU (see section 4.2.3.8 ), sonar quality
flags, angle from nadir, and depth threshold. The TPU filtering option can be used to expeditiously reject soundings
with uncertainty values that fall outside limits set for either an IHO order survey or some user-defined parameter.
However, the hydrographer should keep in mind that it is the grid node depth that must meet survey specifications,
not each individual sounding. Thus, the TPU filtering tool may over clean data. MBES data can be filtered based
on sonar quality flags and/or angle from nadir. Although filtering by sonar quality flags is not recommended by
OCS, filtering based on angle from nadir may be useful when external conditions cause outer beams to degrade to
the point of being unusable. Both MBES and VBES data may be filtered based on depth threshold. This method
can be used to eliminate anomalous soundings resulting from double-echoes or near-surface reflection such as
propeller wash, entrained air, and marine life. Consult the CARIS HIPS and SIPS User’s Manual for more
information on filtering methods.


#### 4.2.3.10 Add to Coverage BASE Surface

A BASE surface model should be created to demonstrate data coverage in accordance with section 5.2.2 of the
HSSD. Each day, newly acquired data should be added to this surface for a quick coverage assessment and planning
of the next day’s surveying operations. The hydrographer is reminded that AWOIS radii that extend beyond the
basic survey limits must be entirely covered with 200% side scan, complete or object detection multibeam, or a
combination thereof to be disproved by sonar data. These radii should be considered when evaluating survey
coverage.

Coverage requirements will vary based on the classification of MBES data assigned in the Project Instructions.
Three general classifications for NOAA hydrography are Complete Multibeam, Object Detection, and Set Line
Spacing. Typically when a BASE Surface is created to evaluate coverage, that day’s bathymetric data have not yet
been analyzed using directed-editing processes. Thus, the coverage BASE surface may need to be re-gridded
periodically to verify that subsequent editing did not affect data coverage.


### 4.2.4 Boat-day Processing

“Boat-day Processing” as described in this chapter refers to that portion of hydrographic data processing that is
performed on a single vessel’s data that were acquired during a single day of data acquisition. Prior to commencing
Boat-day Processing, all of the Daily Batch Processing tasks ( see section 4.3.3 should have been performed. For
ships and launches, Boat-day Processing is typically accomplished during a “night processing” shift. For field
parties, this processing step is often saved for foul weather days or is accomplished by a shore party member in

*Page 130*

------------------------------------------------------------------------------------------------------------------------


charge of daily data processing. For ERS based projects, boat-day processing includes generating POSPac SBET’s
for all survey vessels. Additional details regarding POSPac SBET processing can be found in the Ellipsoidally
Referenced Survey SOP.pdf in Appendix 4.

Boat-day Processing is based on the natural interpretive power of the human eye to evaluate a BASE surface for
anomalous bathymetry, directing attention to areas that require review and/or editing (i.e., “directed editing”) by
an experienced hydrographer. Vertical exaggeration is a very useful tool to accentuate bathymetric features and
artifacts on a “sun-illuminated” BASE surface. However, extreme depth scaling can make small features seem
significant and/or make acceptable multibeam data appear riddled with problems. Scaling sun-illuminated depth
layers by a multiplier of three to five is generally a good choice for initial data review. If artifacts are perceived, the
hydrographer can measure the vertical distance of the artifact (peak-to-trough) and compare this distance to the
allowable vertical error for the survey to determine if the data is acceptable. If major data artifacts or issues are
observed, the CST, FOO, or Team Lead should be informed in order to identify and resolve the issue.
Note: In navigationally significant areas where no supporting imagery data exist (see section 4.3), special emphasis
should be placed on the review and interpretation of bathymetry data and, as needed, supporting sensor time
series data.

In most cases, data anomalies can be easily evaluated and edited using HIPS Subset Editor . However, complex
areas may require additional line-by-line evaluation and editing via HIPS Swath Editor (see section 4.2.4.3.2 ).
Once data are merged, the hydrographer should review attitude and navigation time series data as described in
sections 4.2.4.3.3 and 4.2.4.3.4 , then use the HIPS Single Beam Editor tool to review bathymetry data. Following
this review, the most accurate water level data available should be applied (see section 4.2.5.1.1), and then the
VBES data can be inserted directly into Pydro.


#### 4.2.4.1 Create Boat-day BASE Surface

The first step in Boat-day processing is to create a CARIS BASE surface of the vessel’s daily data using final gridded
data specifications as defined in section 5.2.1 of the HSSD. Initially the Boat-day BASE surface is used to direct the
editing process (see section 4.2.4.3 ). Once editing and the appropriate checks are complete the Boat-day BASE
surface can be regridded and added to a Survey-wide BASE surface that will, ultimately, be finalized and submitted.
An option exists in the HIPS BASE surface creation process to add comments. These comments are included in the
metadata stored in an XML companion file with every BASE surface. In addition to having metadata in a separate
file, it is helpful to include some descriptive information in the BASE surface file name. The following BASE file
naming convention is an effective way to keep track of Boat-day surfaces:
Registry Number_Vessel Number_Day-of-Year_Resolution_<Lettered Index>
For example, the names for two Boat-day BASE surfaces created at a 2 meter resolution using RAINIER launch #4
data from day number 152 might look like: “H12345_RA04_152_2m_a” and “H12345_RA04_152_2m_b.”

#### 4.2.4.2 Review Boat-day BASE Surface

Once a Boat-day BASE surface has been created, it should be investigated for indications of data problems (artifacts)
and features. A bathymetric feature is any object that may be of importance for nautical charting, such as a wreck,
shoal, or other item that may need further investigation. Typically, the depth and standard deviation BASE surface

*Page 131*

------------------------------------------------------------------------------------------------------------------------


layers are most useful for identifying data anomalies (see list of BASE attributes in section 4.2.1.2 ).
The Properties Window can be used to assist the hydrographer with BASE surface review. This window allows the
user to customize a BASE surface color map and adjust the azimuth and elevation of simulated sun illumination.
Varying these settings helps highlight artifacts and features that may be hidden when viewed using only one set of
display parameters. The hydrographer should systematically inspect all BASE surfaces at least four times, moving
the azimuth of the virtual sun 90° each time while maintaining a moderate to low elevation. For example, azimuth
values of 045°, 135°, 225°, and 315° (northeast, southeast, southwest, and northwest) with a fixed elevation of 45°
is a common, and usually effective, series of settings.

Note: If plotting BASE surfaces, a sun elevation of 45° and azimuth of 315° generally presents artifacts and features
most accurately. A particular pixel-color can also be set as transparent. Choosing a transparent pixel of “0” will
make the otherwise white background of the image transparent so that underlying data (charts, orthographic
photographs, etc.) will be revealed.

Problems that may be encountered in a MBES data set can generally be broken down into the following seven
categories: refraction, attitude, position, heading, sonar, environmental, and tide. Each of these data problems is
described below. For further guidance on which tools should be used to edit various data problems, see section
4.2.4.3 .


##### 4.2.4.2.1 Refraction

Acoustic refraction-induced errors are caused when the speed of sound through the water column is not adequately
modeled over time or space. When viewing data with refraction errors in the acrosstrack direction, the hydrographer
will notice a “smiling” or “frowning” characteristic as shown in Figure 4.9 .


Figure 4.9: HIPS Subset Editor view (bottom) of acoustic refraction-induced bathymetry errors, using BASE
surface standard deviation image for reference.

Depending upon the cause of this artifact, it may indicate a need for additional sound speed profiles each day or
more profiles spatially over the survey area. Typically, the amount of time required to obtain additional sound
speed profiles is far less than that required to edit, or otherwise “fix”, data afflicted with acoustic refraction artifacts.
HIPS Refraction Editor, a tool in Swath Editor, may be used to assist with troubleshooting refraction errors.
Refraction Editor allows the user to enter a step sound speed correction at a specified water depth. As sound speed
corrections are entered, the effect is reflected in the swath edit display by increasing or decreasing the curvature
(smiling or frowning) of the swath.

Note: HIPS does not account for TPU (see section 4.2.3.8 ) introduced by using Refraction Editor; thus, Refraction
Editor is not approved for use in OCS hydrographic surveys and shall not be used for deliverable products.

*Page 132*

------------------------------------------------------------------------------------------------------------------------



##### 4.2.4.2.2 Attitude

Vessel motion artifacts may arise due to a failing accelerometer within the heave/pitch/roll sensor, a gap occurring
in data transmission or recording, an inaccurate patch test (e.g., conducted in insufficiently deep water for the
given survey area), or unaccounted latency within the data acquisition system. An example of a gap in the recorded
attitude time series is illustrated in Figure 4.10.


Figure 4.10: BASE surface standard deviation layer (left) of a survey line with data in
attitude time series (right).

If a specific cause of vessel motion artifacts can be determined, it may be possible to repair the data. For example,
a new patch test could be run, or data could be reprocessed to account for a known latency. In other cases, data
may need to be either smoothed to minimize the artifact or rejected entirely. If systematic errors are found in a
vessel’s attitude data, the time spent trouble shooting the source of the problem will typically far outweigh the time
required to continually edit data.


##### 4.2.4.2.3 Position

Gross horizontal positioning errors are uncommon when using modern surveying equipment. Inertially-aided
GPS navigation equipment, such as the Applanix POS/MV, uses Kalman filtering to constrain vessel speed,
acceleration, and displacement, eliminating the majority of potential positioning errors. The most common cause
of error in an inertially-aided system is when the GPS portion of the position solution fails.

Note: Due to the horizontal position accuracies required for OCS hydrographic surveys, loss of differential GPS
corrections should also be considered GPS failure. The effects of temporarily losing differential corrections are
illustrated in Figure 4.11.


Figure 4.11: HIPS Navigation Editor time-series showing positioning error caused by
temporary loss of differential corrections.


*Page 133*

------------------------------------------------------------------------------------------------------------------------


During a GPS failure, inertial navigation systems can dead reckon for approximately 30 seconds before errors
accumulate to a level that produces unacceptable positioning. The hardware/software interface for an inertial
navigation system should be configured to alert the user of failure events so that data acquisition can be suspended
if position data becomes unacceptable.

Positioning “problems” associated with horizontal uncertainty may be seen on areas of extreme slopes. For example,
if the horizontal accuracy is approximately 4 meters, the vertical depth error on a slope of 60° would be almost 7
meters. Inconsistencies will be observed from swath to swath in these areas due to the horizontal positioning error.
Keep in mind that horizontal uncertainty is factored into the BASE node uncertainty calculation, and may
adequately account for what appears to be positioning errors on steep slopes (see section 4.2.1.1 ).

##### 4.2.4.2.4 Heading

Heading errors can be induced by a faulty sensor or an incorrect heading alignment correction entered in the HVF.
This problem can be easily identified as a break in continuity of linear features from one swath to the next.
During data acquisition, heading values are sometimes included in datagrams from sensors other than the primary
navigation system. However, the accuracy of heading data will vary depending upon its source. If heading errors
are discovered, it may be possible to re-process the data using heading information from another source. The field
unit’s FOO or equivalent should be notified if an alternate heading source (e.g., calculated course-over-ground) is
used to process survey data, as TPU (see section 4.2.3.8 values in the HVF may require editing.


##### 4.2.4.2.5 Sonar

Sonar-induced data problems are typically caused by inappropriate settings in the sonar system. These may include
unoptimized power, gain, and threshold settings, as well as improper range settings for the depth of water. Any of
these circumstances could prevent the sonar from accurately representing the sea floor. The best way to minimize
sonar-induced errors is by having a well-trained and attentive operator during data acquisition.


##### 4.2.4.2.6 Environmental

Environmental data problems are those caused by objects or disturbances in the water column, such as marine life,
vegetation, entrained air from passing vessels, or weather-induced disturbances from heavy seas or rain. Figure
4.12 shows an example of environmental noise which occurred near the transducer face.


Figure 4.12: HIPS Swath Editor view (left) and BASE surface standard deviation layer
view (right) showing water column noise near transducer.


*Page 134*

------------------------------------------------------------------------------------------------------------------------


As with all data problems, environmental data issues are most effectively addressed during the acquisition stage
rather than during processing. Depending upon the severity of data problems, acquisition may need to be
suspended until environmental conditions have improved.


##### 4.2.4.2.7 Tide

Tide errors can result from inaccuracies in any of the source data used in the vertical datum transformation
algorithm, such as inaccuracies in the water level observations, tide zoning model, or navigation. This type of error
is often identified by a measurable vertical offset visible when data are viewed in the acrosstrack direction, as
shown in Figure 4.13 .


Figure 4.13: HIPS Subset Editor view of tide-induced bathymetry errors (bottom),
using BASE surface standard deviation image for reference (top).

If tide errors are identified, the hydrographer should ensure that the correct water level data have been loaded for
the suspect dataset. Keep in mind that predicted tide files do not account for water level effects due to nonastronomical forces. Thus, what appears to be a data problem may correct itself once observed water level data are
applied. However, the varying accuracies and unquantified uncertainty of tide correctors resulting from discrete
zoning have the potential to result in tide-induced bathymetry errors even when using actual tide gauge data
rather than predictions. If there are no other hydrographic sources of this error, this would indicate that either the
tide gauge locations are inadequate and/or the method of discrete tidal zoning cannot account for the complex
hydrodynamics of this survey area.


##### 4.2.4.2.8 ERS SBET Height Errors

This type of error may be identified by a measurable vertical offset visible when data are viewed in the across track
direction, similar to a tide error. Additional details regarding ERS SBET quality control can be found in the
Ellipsoidally Referenced Survey SOP.pdf in Appendix 4.


#### 4.2.4.3 Directed Editing from Boat-day BASE Surface

One or more of the HIPS data “editors” can be used to analyze data artifacts and features of interest that are
identified on the Boat-day BASE surface. With the exception of VBES data, depth values cannot be directly edited
or changed in HIPS; rather, soundings can be flagged with various attributes, including “rejected” which will
suppress a sounding from further processing steps. Daily review and flagging of features is strongly recommended
to maintain an organized and complete survey. Supporting sensor data can also be flagged as being rejected, either
with or without interpolation.


*Page 135*

------------------------------------------------------------------------------------------------------------------------


Subset Editor is the most frequently used HIPS editing tool and allows the most flexibility in addressing a problem
that is concentrated in one geographic area. OCS recommends the use of “Subset Tiles” with 10% overlap to track
editing progress in Subset Editor. Once defined, subset tiles may be flagged as either “Complete” (green), “Partially
Complete” (yellow), or “Incomplete” (red) to identify areas that have been investigated, need a second review, or
have not yet been edited, respectively.

In some cases, it may be beneficial to review individual sonar pings in a specific line of survey data. This type of
line-by-line editing can be performed in HIPS Swath Editor. If potential problems in either attitude or position
data are noticed, the Attitude Editor or Navigation Editor tool can be used to review individual sensor time series
data. Each of these four data editing tools is described in greater detail below. Refer to the CARIS HIPS and SIPS
User’s Manual for further information on any of these tools.


##### 4.2.4.3.1 Subset Editor

Subset Editor enables the hydrographer to review and edit a “subset” of the entire sounding dataset, and
corresponding BASE surface data, by geographic area. Subsets are rectangular in shape and will contain all
soundings acquired within the geographic boundaries of the subset. Subsets can be created in a north-south or a
rotated orientation. Rotating a subset can be useful to obtain a profile view when inspecting data along slopes or
dredged channels.

When using Subset Editor, the hydrographer should be aware of the data display settings, particularly vertical
exaggeration and whether rejected soundings are displayed. If vertical exaggeration is set to “Auto,” then the display
will rescale as soundings are edited. This feature creates a potential for the user to become focused on very fine
details in the seafloor and essentially edit data to create a smooth bottom, which rarely exists. The hydrographer
must take care not to “over clean” data in this fashion. Displaying rejected soundings allows the user to see data
that has been previously rejected, typically by a filtering routine in Swath Editor or editing by another hydrographer.
Viewing rejected data is often valuable when investigating the validity of a possible feature.

•	 Individual soundings or groups of soundings may be selected and flagged in Subset Editor. Available data flags
and each flag’s purpose with respect to OCS hydrography are as follows:
•	 Reject - Flag anomalous soundings as “rejected” to suppress them from being included in subsequent processing
steps, such as in the calculation of BASE surface grids.

•	 Reject Swath - This flag sets the “rejected” flag for all soundings in a selected swath. Use this function to reject
a single ping or a continuous section of flawed sonar pings.

•	 Outstanding - This flag may be set for any data point that holds particular hydrographic significance. Typically,
if the identity, extent, or validity of a feature is uncertain, it should be flagged as “outstanding.” NOAA Pydro
software treats soundings flagged “outstanding” in HIPS as bathymetry features. Pydro establishes a connection
to the HDCS data for all “outstanding” soundings and will automatically update the HDCS data for any
subsequent flag changes made in Pydro during feature processing (see section 4.4 ).

•	 Examined - This flag does not currently have a defined meaning for OCS hydrographic survey data; however,
it can be used by the surveyor as a means of marking a sounding for future reference. This flag can also be used
to separate a group of soundings for non-standard data analyses.

•	 Designate - Applying the “Designate” flag to a sounding will force the BASE surface grid node closest to that

*Page 136*

------------------------------------------------------------------------------------------------------------------------


sounding to assume the exact depth value of the designated sounding, ignoring all other soundings within the
area of influence of this node. Pydro regards soundings flagged “designated” in HIPS as “designated” bathymetry
features in Pydro. Pydro establishes a connection to the HDCS data for all “designated” soundings, and
subsequent flag changes or edits made to the bathymetry feature in Pydro will automatically be reflected in the
HDCS data.


##### 4.2.4.3.2 Swath Editor

Swath Editor enables the hydrographer to review and edit a single swath of data from four orthogonal directions
as well as from a three dimensional perspective.

Note: Data viewed in Swath Editor are not geo-referenced, but displayed with respect to acrosstrack and alongtrack
distances from the transducer.

Data problems that appear to be limited to the extent of a single line of data are often best addressed using Swath
Editor. As when using Subset Editor, individual soundings or groups of soundings may be selected and flagged in
Swath Editor. HIPS data flags and their purpose in OCS hydrography.

Note: “Outstanding” and “Examined” flags can not be applied using Swath Editor.

Swath Editor also allows the user to view amplitude (i.e., backscatter or side scan) data from a multibeam
echosounder. Amplitude data can provide valuable insight for determining if a particular sounding or group of
soundings is a real feature.


##### 4.2.4.3.3 Attitude Editor

Attitude Editor allows the hydrographer to review and edit heading (gyro), heave, pitch, and roll data. Attitude
Editor displays each sensor’s time series data for a single survey line. HIPS provides three means of editing attitude
data, rejecting (with or without interpolation), filtering, and smoothing.

For data problems of limited extents in time, rejecting is generally the preferred editing method. There are two
options for rejecting attitude data: “Reject-with interpolation” and “Reject-break interpolation.” Rejecting data
with interpolation will fit a straight line from the last good data point before the segment rejected to the first good
data point after the segment rejected. Caution should be exercised when using this tool. Rejecting and interpolating
sections of attitude data across the peaks of a signal will result in distorting the maximum observed amplitude at
that time, as illustrated in Figure 4.14 .


Figure 4.14: interpolation across region ‘A’ will most likely create an artifact of its own, whereas
interpolation across region ‘B’ will not adversely impact the sounding data.

Rejecting without interpolation should be used to edit attitude data corruption occurring over an extended period
of time. A general rule of thumb is to divide the allowable data gap distance for the survey by the vessel speed in
meters-per-second to determine when to begin breaking interpolation. For example, if a 5 meter resolution grid is
required to demonstrate adequate data coverage and the vessel speed is 5 m/s (~10 knots), regions of bogus data

*Page 137*

------------------------------------------------------------------------------------------------------------------------


greater than or equal to 1 second (5 m ÷ 5 m/s = 1 s) should be rejected without interpolation. The Hydrographer
should note that breaking interpolation will create a gap in the data. When the files are merged, this option rejects
all sounding data recorded during the time period in which sensor data were rejected, thus leaving a holiday in
data coverage.

For attitude data problems that are systematic throughout the time series, filtering or smoothing is typically the
best editing approach. The hydrographer is cautioned that filters are powerful tools and should be used sparingly
and with great care. Attitude Editor provides two filtering options: “Moving Average” and “Fast Fourier.” The
Moving Average option calculates a mean for each data point according to a user-specified number of neighboring
data points (in time or number) or “box size.” The Fast Fourier method performs low-pass filtering on the sensor
data according to a user specified signal period (in time or number-of-points).


##### 4.2.4.3.4 Navigation Editor

Navigation Editor allows the hydrographer to review and edit the vessel’s navigation time series. The navigation
time series can be edited in HIPS using rejection with or without interpolation. When rejecting data, the Navigation
Editor tool offers two interpolation methods: Linear and Bezier. Linear interpolation is suitable if the majority of
navigation positions are clean and do not deviate significantly from neighboring positions. Bezier interpolation is
suitable if the original data is noisy. Linear interpolation simply calculates new positions over the rejected segment
by connecting bounding positions with a straight line. Bezier interpolation calculates new positions over the
rejected segment by fitting a Bezier curve through bounding positions, producing a resultant curve that may not
necessarily connect or pass through all navigation positions on the line.

To help expedite data inspection, Navigation Editor provides “spike detection.” This tool will search the navigation
time series for user-defined “jumps” in speed and time. Each jump will be highlighted so that the hydrographer
can decide how best to edit the data. Large jumps in speed, calculated as distance traveled divided by time between
fixes, can detrimentally affect the vessel’s dynamic draft computation. Data artifacts due to speed jumps will be
more pronounced if the slope of the vessel’s speed versus dynamic draft is steep. A general rule-of-thumb is to
interpolate speed jumps if they exceed the TPU (see section 4.2.3.8 modeled for vessel speed in the HVF, but this
becomes less critical if a vessel’s speed versus dynamic draft slope is small. Since speed and time jumps are directly
related and speed is used to determine dynamic draft, it is not necessary to separately edit time jumps.

#### 4.2.4.4 Update Survey-wide BASE Surface

Once directed editing has been completed, the Boat-day BASE surface should be recomputed to verify that all edits
were successful. If no further editing is necessary, the Survey-wide BASE surface should be updated, using final
gridding parameters, to reflect the current survey status.

For ERS based projects, if no SEP has been used in the HIPS Compute GPSTide step (processed depths relative to
the Ellipsoid), then boat day and survey-wide BASE surfaces must be transformed to chart datum for sounding
review and the determination of DTON’s. See section 4.2.5.1.2 for guidance.


### 4.2.5 Survey-wide Processing

“Survey-wide Processing” includes many of the steps and skills discussed previously in this chapter. The difference
is the context in which these steps are accomplished. During Boat-day processing, a single “boat-day’s” worth of
bathymetric data is being viewed, edited, and flagged for internal consistency, gross errors, and any features that

*Page 138*

------------------------------------------------------------------------------------------------------------------------


warrant further investigation. During Survey-wide processing, survey bathymetry and imagery data are examined
in context with existing chart information and any additional supporting data available. Survey wide data analysis
can be performed relative to Ellipsoid or chart datum as most appropriate.

Many of the steps involved in processing hydrographic surveys are iterative and may be conducted in parallel with
each other. Efficiency can be increased by conducting many of the Survey-wide processing steps concurrently with
Boat-day processing for global quality control and general survey completeness. These processes would include
verifying adequate investigation of charted features within the survey sheet limits, reviewing the data for DTONs,
and verifying that data coverage meets the assigned specifications. Reviewing these points on a daily basis will help
to ensure a complete survey and a timely submission.


#### 4.2.5.1 Vertical Datum Transformation


##### 4.2.5.1.1 Apply Water Level Correctors (non-ERS)

Preliminary water levels are 6-minute water level measurements that have undergone rudimentary data consistency
checks in the CO-OPS Data Processing and Analysis System (DPAS). Any gaps in data coverage will remain in
these preliminary data, and measurements may, or may not, have been reduced to the local MLLW datum.
Preliminary water levels should be available within hours, if not minutes, of data acquisition. Verified water levels
have gone through CO-OPS’ processing, analysis and quality assurance processes, and any gaps in data have been
recovered or interpolated through a process which utilizes nearby gauge data. After a preliminary or accepted
datum has been computed, 6-minute verified water levels are made available referenced to MLLW.

Note: Field units shall submit, via email, a request for final tides to final.tides@noaa.gov within 24-hours of
completing data acquisition for a survey (see section “5.2.2.3.3).

Once a request for tides is received, CO-OPS will review the survey tide requirements to determine if adjustments
or corrections are required. If CO-OPS needs to make any modifications, they will provide final water level
correctors to the field unit. If no changes are required, CO-OPS will provide the field unit with an official final tide
note stating that preliminary zoning, (and associated .zdf file) will be accepted as the final zoning; thus, verified
water levels applied using preliminary zoning will be equivalent to final water level correctors. CO-OPS should
respond to the field unit within two weeks of receiving a Request for Tides. Verified 6-minute water levels and final
water level correctors should be applied as soon as these data are available. See sections 4.2.3.2/ and 4.2.3.5 for
details regarding the application of water levels in HIPS.


##### 4.2.5.1.2 Apply Ellipsoid to Chart Datum Separation Model (SEP)

For the 2014 field season, the processes and tools for applying SEP to CARIS processed bathymetry grids are being
developed. The process will involve the following basic steps:
	

1. Ellipsoidally referenced grid surfaces are read from CARIS.


	
	

2. Grid math is performed (currently outside of CARIS) to apply the project SEP model (VDATUM or 		
ERZT) datum and datum uncertainty.


	
	

3. The adjusted surface data is read back into CARIS now referenced to chart datum (MLLW) with 		
appropriate vertical datum transformation uncertainty applied.


*Page 139*

------------------------------------------------------------------------------------------------------------------------



#### 4.2.5.2 Assess Bathymetry Features

Throughout the survey process, bathymetric contacts should be periodically assessed and a determination made
as to whether “development” is necessary. Developing a bathymetric contact typically refers to acquiring additional
MBES data over the feature to increase sounding density and determine, or verify, a least depth. However, other
methods of obtaining a least depth may be used, such as VBES or DLDG.

Bathymetric contacts are often easily identified and corresponding HDCS data can be flagged during examination
of the BASE surface depth or standard deviation layers. Soundings flagged “examined”, “outstanding”, or “designated”
can then be highlighted using the HIPS “Display Critical Soundings” command. However, bathymetric features
should also be assessed in Pydro, which enables the hydrographer to analyze each item in context with other
available data sources such as the chart, imagery data, DPs, and AWOIS records/search radii. (Refer to section 4.4
for additional details.) Within Pydro, the hydrographer can easily evaluate bathymetric features to determine if
any are DTONs. Comparisons should also be made between sounding data and existing charted depths. If survey
soundings indicate deeper water than the charted depth(s), the charted depth should be treated as a feature and
additional data acquired, as necessary, to verify that the charted depth is incorrect. (This process is often referred
to as a charted sounding investigation.) Bathymetric features should be evaluated for significance and data coverage
and, if appropriate, flagged within Pydro for “investigation,” as detailed in section 4.4 .


#### 4.2.5.3 Review Survey-wide BASE Layers

The final Survey-wide BASE surface to be submitted shall be created in accordance with section 5.2.1 and 5.2.2 of
the HSSD. Prior to finalization, BASE layers should be reviewed to ensure that the gridded surface truly reflects the
conditions in the survey area, meets specifications assigned in the Project Instructions and that all features have
been adequately investigated. Both mainscheme lines and crosslines should be included in the final BASE surface.

### 4.2.6 Finalize Bathymetry Data

For survey submission, BASE surfaces must be finalized in HIPS. This process is explained in detail in the CARIS
HIPS and SIPS User’s Manual. Finalizing BASE surfaces serves three purposes:
•	 To apply Designated soundings: In some instances, due to the nature of the weighting algorithm, a BASE
surface does not accurately represent the least depth of a navigationally significant feature (typically a fine item
such as a tall, narrow coral head or a shipwreck’s mast). In such cases, a sounding can be flagged as Designated
to force the nearest BASE surface grid node to honor the depth of the designated sounding. Refer to the
following subsection for guidance on selecting Designated soundings. Designated soundings are applied to the
BASE surface during the Finalize step in CARIS by checking the “Apply designated soundings” option.
•	 To assign grid nodes a final uncertainty: A grid node’s final uncertainty can be assigned as one of three options:
1) that node’s a priori uncertainty-weighted uncertainty, i.e., predicted error, 2) the grid node’s standard
deviation scaled to a 95% confidence interval, i.e., observed error, or 3) the greater of the two. For OCS
hydrographic survey data, the “greater of the two” option shall be used to maintain a conservative uncertainty
estimate.

•	 Define depth thresholds: A single-resolution grid will generally not be appropriate for an entire survey area. To
maintain the optimal resolution for a given depth range, the finalize process filters out a desired depth range
for each different grid resolution created.


*Page 140*

------------------------------------------------------------------------------------------------------------------------



#### 4.2.6.1 Designate Bathy Features

Since the calculated depth at each grid node of a BASE surface is influenced by multiple soundings, the least depth
of a feature may not always be accurately represented in the gridded data. Prior to creating a finalized BASE surface
collection, the hydrographer must systematically review significant feature least depths to ensure they are accurately
portrayed by the BASE surface.

If a specific least depth sounding is preferred over the weighted mean-depth calculation for the associated BASE
surface grid node, that sounding should be flagged Designated. The Designated flag can be applied in either HIPS
or Pydro. If a sounding is made Designated in one software package, this flag will automatically carry through to
the other application. Designated soundings shall be selected in accordance with section 5.2.1 and 5.2.2 of the
HSSD.

A common area of confusion is the preferred spatial density of designated soundings. It is easy to lose ones sense
of scale when viewing data in subset editor. Sand ripples can look like mountains and small rocks appear like house
sized boulders. The hydrographer shall take a holistic view of the surrounding bathymetry to help determine the
hydrographic significance of a feature before designating a sounding. When there are a group of features near each
other (e.g. they would be shown as a single sounding or charted feature at the scale of the survey), only the shoalest
sounding on the feature with the most representative shoal depth shall be selected.

As discussed in the Specifications and Deliverables section 5.2.1.2, the hydrographer should use discretion in
designating soundings on features. In the example below, the pile of rocks on the left hand side of the image would
only require one designated sounding although there are two ‘peaks’ in the rock pile. The single designated
sounding would be adequate to chart the least depth of the group of features. The next feature to the right (a
submerged piling) would have a designated sounding at the least depth. The buoy, anchor chain, and buoy block
should have no designated soundings. The pair of pilings which are exposed and charted as pilings would not have
designated soundings, they are not features that would be charted with a sounding. The pilings on the pier on the
far right would not have any designated soundings, nor would any objects under the pier as they would not be
charted.


Figure 4.15: Designated Bathy Feature


4.3 Imagery Processing
-----------------------

NOAA hydrographic field units typically acquire three types of imagery data: side scan sonar (SSS), MBES
backscatter, and MBES “side scan” which is available as an option on some systems. True side scan sonars produce
superior imagery for object detection purposes and are used to meet object detection requirements for OCS
hydrographic surveys.


*Page 141*

------------------------------------------------------------------------------------------------------------------------


Note: Backscatter data and side scan imagery acquired in conjunction with MBES bathymetry, is often processed
as an aid for data analyses but is not approved by OCS for meeting hydrographic survey object detection
requirements.

The procedures outlined in this section are required only for SSS imagery being used to meet OCS object detection
criteria, and are not applicable to MBES imagery data unless noted as pertaining to a specific MBES system or
“backscatter” data.


### 4.3.1 Imagery Object Detection

Imagery data are acquired and processed with the purpose of detecting objects that may be of navigational
significance. This determination is typically based on contact type, position, and height above the sea floor
estimated from the item’s acoustic shadow on the SSS record. Imagery data acquired for OCS hydrographic surveys
are geographically referenced; thus, a position can be determined for each contact identified. The accuracy of this
position will vary depending on whether the sonar was towed or hull-mounted, but either method should be
sufficient to locate the item for further investigation. If a contact is determined to be significant, a “development”
should be conducted to determine the item’s least depth and a more accurate position for charting.

Figure 4.16: Basic data processing flow chart for SSS data.


### 4.3.2 Daily Batch Processing

Several processing tasks need to be performed on “raw” imagery data (i.e., unaltered data in the format generated
by the acquisition software) before any detailed analysis and evaluation can occur. Some of these daily tasks are
interdependent, and the specific sequence is critical. The recommended ordering of daily batch processing tasks is
as follows:
	

1. Conversion 4.3.3.1

	

2. Filter, if applicable 4.3.3.2

*Page 142*

------------------------------------------------------------------------------------------------------------------------


	

3. Recompute Towfish Navigation 4.3.3.3

	

4. Slant Range Correction 4.3.3.4

	

5. Add to Mosaic 4.3.3.5

Most of the tasks above can be semi-automated in HIPS/SIPS using the “Batch Processor” tool. Data format
determines how specific processing actions need to be configured; as such, a separate Batch Processing File (.hbp)
is needed for each raw data format type.

In general, all of the aforementioned tasks should be completed for any type of imagery data being used to meet
OCS hydrographic survey specifications. A basic set of batch processing files can be specified for each sonar type
and reused on the appropriate set of survey lines acquired each day. In some circumstances, either creation of
custom batch processing files or manual processing of one or more tasks, line-by-line, in non-batch mode may be
necessary. For example, conversion and filtering options may need to be customized to reflect changes in sonar
performance as weather conditions varied throughout a survey day.


#### 4.3.2.1 Conversion

CARIS SIPS supports many different data formats that may be used to record imagery. During conversion, SIPS
uses raw data to create files in CARIS’ proprietary format which will be used in subsequent CARIS processing
routines. These files in CARIS SIPS format are referred to as “SIPS files” or “HDCS files.”
For towed SSS configurations, a calculated “towfish position” may have been recorded in the raw data depending
upon the acquisition software being used. This calculation requires cable out and towfish depth (or water depth
minus towfish altitude). If cable out and either towfish depth or water depth and towfish altitude were logged
during acquisition, towfish position can be re-calculated during post-processing via SIPS Recompute Towfish
Navigation (see section 4.3.2.3 . Either method of positioning should be adequate for standard SSS operations.
However if recomputing towfish navigation, the hydrographer should first review and edit, if necessary, cable out
and towfish depth. For hull-mounted configurations, sonar offsets should be accounted for in the HVF as vessel
RP-to-towpoint values.

Note: Recompute Towfish Navigation must be performed for vessel RP-to-towpoint to be applied. For hullmounted
configurations (i.e., no cable out data recorded), towfish navigation will be recomputed using a cable out value of
zero.

If an error is discovered in the HVF during SSS post-processing, re-conversion may not be required to correct the
data. If unsure whether data repairs are necessary, the Survey Manager should consult, through his/her chain-ofcommand, the Hydrographic Systems and Technology Program for guidance.
The following sections contain guidance for converting common raw imagery data formats used by OCS into
HDCS files. Relevant background information is provided, followed by a table of guidelines for specific Conversion
Wizard settings related to each raw imagery format.



*Page 143*

------------------------------------------------------------------------------------------------------------------------



##### 4.3.2.1.1 Sensor Data Format (SDF)

Sensor Data Format (SDF) may be used to store data from Klein System 3000 or Klein System 5000 side scan sonar
systems. Conversion parameters will vary slightly depending upon the SSS system used to acquire the data. The
SDF data format is generated by Klein Associates’ proprietary software package SonarPro.

If data were acquired using a Klein 3000 dual frequency (100 kHz and 500 kHz) side scan sonar, the user must
choose which frequency to convert. Choose the “high” option to convert 500 kHz data and “low” to convert 100
kHz data. Typically, higher frequency data will provide better imagery resolution, while lower frequencies travel
further and can be used at larger range scales.

If data were acquired using a Klein 5000 dynamically focused multibeam side scan sonar, the user must choose
whether or not to convert hidden beams. There are five beams on each channel (port and starboard) of the Klein
5000. Based on range scale and towfish speed, the system will determine the number of beams necessary to achieve
100% coverage. Typical range scales and speeds used for hydrographic surveying require that 3 - 4 beams be used.
Selecting “convert hidden” forces all 5 beams to be converted and may improve imagery in high yaw-rate conditions
(e.g., in turns or for hull-mount configurations) or aid in detection of very small objects during activities such as
search and recovery. However, for the purposes of a basic OCS hydrographic survey, converting hidden beams is
not necessary to meet survey specifications and can introduce data management problems by significantly
increasing file sizes.

Towfish depth is used to calculate towfish navigation in SIPS. Both the Klein 3000 and 5000 systems are equipped
with a pressure sensor installed in the towfish body to determine towfish depth. Each towfish will have a pressure
sensor rated for 100, 300, or 1000 psi, depending on the anticipated operating depths. The hydrographer must
know the pressure sensor rating for the specific towfish used to acquire data.

Both the Klein System 3000 and System 5000 towfish are equipped with a magnetic-based heading sensor. This
sensor’s data are logged as SSGyro. Typically, a magnetic compass does not indicate true headings and must be
corrected for magnetic declination (variation) and deviation to obtain a true heading. Electrical interference could
also contribute to a loss of both accuracy and precision of the SSGyro. Due to these inaccuracies, OCS does not
recommend using towfish heading sensor values (SSGyro) for processing survey data.

Various side scan sonar systems may record imagery at different resolutions. Both Klein System 3000 and System
5000 imagery data are recorded at a resolution of 12 bits. When converting SDF files, choosing an 8-bit conversion
will reduce the data resolution. Even though the recorded resolution is 12 bits, choosing the option to “Preserve
16-bit” will retain the original resolution.

Options

OCS Guidelines

Klein 3000 Frequency
- High or Low

High frequency data should be
used unless range scale
requirements are such that the
higher frequency is ineffective.

Do not convert hidden beams as a
standard practice.

Choose the pressure sensor rating
for the specific towfish used to
acquire data being converted.


Convert Hidden
Pressure Sensor
- 100, 300, or 1000 psi


*Page 144*

------------------------------------------------------------------------------------------------------------------------


Convert SSGyro

Do not convert SSGyro

16-bit Sonar Conversion
Choose to “Preserve 16-bit”
- Preserve 16-bit
resolution.

- Convert to 8-bit: Scale or Shift
Table 4.5: OCS guidelines for converting SDF data.


##### 4.3.2.1.2 Simrad

Kongsberg Simrad multibeam systems, such as the EM1002 or EM3000, used for bathymetric data acquisition as
discussed in section 4.2.3.1.2 , are also capable of recording backscatter data. Simrad backscatter imagery is not an
acceptable object detection method for OCS hydrographic surveys. However, these backscatter data may be useful
for verifying objects detected in bathymetry data or identifying changes in seafloor texture to guide bottom
sampling operations.

Converting Simrad angle-dependent backscatter imagery into HDCS files is simple. When converting the Simrad
bathymetry data in HIPS, the user simply makes a choice whether or not to “Convert Side Scan/Backscatter” data.
No other choices are associated with imagery conversion.

Options
OCS Guidelines
Convert Side Scan / Backscatter
Choose this option and convert imagery data.

Table 4.6: OCS guidelines for converting Simrad data.


##### 4.3.2.1.3 Extended Triton Format (XTF)

The eXtended Triton Format (XTF) can be used to store data from a variety of side scan systems. Both imagery and
bathymetry data from MBES systems can also be acquired in the XTF format (although this is uncommon on
NOAA hydrographic field units), and the same CARIS XTF converter is used for all three data types. XTF datagrams
are comprised of a Triton-defined “header” attached to an optional manufacturer-specific sensor data packet.
NOAA hydrographic field units acquiring SSS data with a Klein 5000 dynamically focused multibeam side scan
sonar will typically log data in XTF format. Since the CARIS converter accommodates an extensive variety of sonar
systems capable of logging XTF data, the user is required to make multiple decisions so that this raw sonar data is
properly interpreted by CARIS. Each critical conversion choice is discussed below, with OCS guidance summarized
in section 4.3.2.1.3.2 .


###### 4.3.2.1.3.1 Convert Side Scan

Some SSS systems, such as the Klein 3000, will simultaneously log data from multiple frequencies. During
conversion, each frequency will be associated with a pair of sonar channels and the user must indicate which
channels are to be processed. If the SSS operates on only one frequency, the data will always be associated with
sonar channels 1 and 2.

Navigation data can be recorded in two separate datafields (“ship” navigation and “sensor” navigation) within the
XTF side scan datagram. The primary difference between the “ship” and “sensor” fields is how the data is time
stamped. “Ship” navigation is associated with the time logged in the XTF header, while each “sensor” navigation
string is individually time stamped. Applying “Sensor” navigation is recommended to avoid potential timing
errors.


*Page 145*

------------------------------------------------------------------------------------------------------------------------


Heading (gyro) data can not only be logged in multiple datagrams within the XTF record, but may also be recorded
in multiple locations within the side scan datagram. While this sensor data may appear redundant, sources and
data quality can vary. Typically, NOAA hydrographic field units will apply heading data stored in the “ship” field
of the side scan datagram, which will correspond to the vessel’s instantaneous heading. Heading data from the
attitude packet will also correspond to the vessel’s instantaneous heading, but the logging rate for attitude data is
often set much higher than the update rate for heading. Thus, using attitude packet heading data will be effective
but could be considered “overkill”. If vessel crab angle is large and the SSS is being towed, the hydrographer should
remember that a towed body will not be experiencing the same crabbing effect. In this scenario, course-madegood (CMG) from navigation often provides the best imagery. This option uses an interpolated heading value
based on recorded vessel position fixes. If acceptable towfish navigation was logged, “CMG from SSSNavigation”
should provide similar results. OCS does not recommend using heading data from the “sensor” field. This data is
logged from the towfish’s magnetic compass, which is subject to both magnetic variation and electrical interference.
If data were acquired using a Klein 5000 dynamically focused multibeam side scan sonar, the user must choose
whether or not to convert hidden beams. There are five beams on each channel (port and starboard) of the Klein
5000. Based on range scale and towfish speed, the system will determine the number of beams necessary to achieve
100% coverage. Typical range scales and speeds used for hydrographic surveying require that 3 - 4 beams be used.
Selecting “convert hidden” forces all 5 beams to be converted and may improve imagery in high yaw-rate conditions
(e.g., in turns or for hull-mount configurations) or aid in detection of very small objects during activities such as
search and recovery. However, for the purposes of a basic OCS hydrographic survey, converting hidden beams is
not necessary to meet survey specifications and can introduce data management problems by significantly
increasing file sizes.

Various side scan sonar systems may record imagery at different resolutions. Both Klein System 3000 and System
5000 imagery data are recorded at a resolution of 12 bits. When converting XTF files, choosing an 8-bit conversion
will reduce the data resolution. Even though the recorded resolution is 12 bits, choosing the option to “Preserve
16-bit” will retain the original resolution.


###### 4.3.2.1.3.2 Convert Layback/CableOut Data

NOAA hydrographic field units typically record cable out during towed SSS acquisition to facilitate recomputing
navigation, if necessary. The XTF format provides two datafields (“cableout” and “layback”) in which this
information can be stored. The primary difference in these fields is that “cableout” will only accept integers, while
a decimal number can be logged in the “layback” field. To preserve decimeter accuracy for cable out values, the
field unit may use one of the two following options:
•	 Configure the vessel’s cable counter to output values in decimeters and log an integer value to the “cableout”
field. However, SIPS assumes cable out data is in meters when recomputing. During conversion, the user can
enter a “multiplier” of 0.1 to the “cableout” data that would reconvert the values to meters. For example, if
acquiring SSS data with 10.6 meters of cable out, a cable counter integer output of 106 (decimeters) would be
stored in the XTF “cableout” field. When converting the data in SIPS, the “cableout” value would be multiplied
by 0.1 to recreate a value of 10.6 that SIPS assumes is in meters.

•	 Configure the acquisition system to log cable out, in meters and decimal meters, to the XTF “layback” field. In
this scenario, the user must remember to convert data from the “layback” field, even though the data are
actually values for cable out. SIPS will assume data from either datafield is cable out if towfish sensor depths
are non-zero. (Similarly, if no towfish depths are converted, SIPS will interpret this as a zero sensor depth and
assume data from either datafield are layback values.)

*Page 146*

------------------------------------------------------------------------------------------------------------------------


To determine towfish depth, both the Klein 3000 and Klein 5000 SSS systems calculate a value from an integrated
pressure sensor. If the hydrographer intends to use cable out to recompute navigation for a SSS system that does
not have a pressure sensor, the towfish depth will need to be calculated based on water depth logged to an AUX
field and towfish altitude. Typically, NOAA hydrographic field units will not need to calculate a sensor depth in
this fashion.

Options
Convert Side Scan
- Sonar channels (1,2 or 3,4)
- Navigation Datafield (ship or sensor)
- Gyro Datafield (ship, sensor, attitude packet, CMG
from navigation, CMG from [sss] navigation)
- Convert Hidden Data
- Apply image enhancement
- Convert single beam from AUX field num

OCS Guidelines
For single frequency systems, convert channels 1 and 2.

When using multiple frequency systems, the user must
determine which channel pair corresponds to the
frequency they wish to convert.

Use navigation data stored in the “sensor” datafield to
avoid potential timing problems.

Typically, use heading data from the “ship” datafield. If
vessel crab angle is large, CMG may provide better
imagery. Do not apply heading from the “sensor”
datafield
Do not convert hidden beams as a standard practice.

Do not apply image enhancement as a standard
practice.

Logging VBES data to an AUX field is not
recommended. Thus, this option is not checked as a
standard practice.


- 16 bit sonar conversion (preserve 16 bit, convert to 8
Choose to “Preserve 16-bit” resolution.

bit (scale or shift))
Convert cable out data from either field, depending
Convert Layback/CableOut data
upon the acquisition system configuration. If
- From layback field
converting from the Cableout field, apply a multiplier
- From cableout field (multiplier)
to preserve decimeter accuracy.

This option is necessary only if recomputing
- Calculate sensor depth using AUX field
navigation for a system that does not have a pressure
sensor.


#### 4.3.2.2 Filter

SIPS does not provide filtering tools to automatically flag/reject “bad” imagery data. However, as when processing
bathymetry, filtering can be performed on attitude and navigation data. Refer to sections 4.2.4.3.3 and 4.2.4.3.4
for details on Attitude Editor and Navigation Editor. Time-series data for gyro (heading), cable out, and sensor
depth, as well as bottom tracking must be reviewed line-by-line and edited as necessary. If the SSS system is
configured to calculate sensor depth based on sensor height and an auxiliary VBES depth, these sensors will also
need to be reviewed.


#### 4.3.2.3 Recompute Towfish Navigation

OCS typically uses one of two side scan sonar configurations, a towed sonar body or a hull-mounted sonar body.
Regardless of system configuration, the hydrographer has the option of either computing the sensor position

*Page 147*

------------------------------------------------------------------------------------------------------------------------


during data acquisition or recomputing towfish navigation during SIPS processing. If a towfish position is computed
during acquisition and stored in the raw data format, this information can be converted directly into the SIPS
towfish navigation data structure. If, in addition to ship navigation, either cable out and towfish depth or horizontal
layback is recorded, the side scan sensor position can be calculated in SIPS via Recompute Towfish Navigation.
OCS strongly recommends recomputing towfish navigation using cable out and towfish depth to determine towed
sensor position. This process enables the hydrographer to review and edit, if necessary, the ship position data, cable
counter data, and towfish depth or bottom tracking (if used to determine towfish depth) prior to calculating a
towfish position.

Note: If horizontal layback or tow cable length data are not available or if the Recompute Towfish Navigation step
is not executed, then the towfish navigation data recorded during acquisition will be used to georeference imagery.
If, additionally, towfish navigation was not recorded during data acquisition, then the side scan sensor position
data are assumed to be the same as the ship navigation data.

When using a hull-mounted configuration, navigation data for the sensor is typically determined by using ship
navigation data and entering the vessel RP-to-towfish offset in the towpoint section of the HVF. However, SIPS will
only apply the towpoint offset when navigation is recomputed. For this type of configuration, Recompute Towfish
Navigation must be performed with a cable out value of zero.

Note: If no cable out data was converted, SIPS will assume cable out to be zero.


#### 4.3.2.4 Slant Range Correction

Side scan sonar is initially logged as a series of time-indexed intensity values for each ping, i.e., the acrosstrack axis
represents time. These data are considered “raw” side scan and are displayed with the central portion of the image
representing the water column and a digital line along either the port or starboard leading edge indicating the
logged bottom track. Some sonar systems will track bottom very accurately, while others require that these data be
edited or redigitized. Any errors in bottom track should be edited prior to slant range correcting, as these data
determine sonar height during the slant range correction process.

When data are slant range corrected, an estimate of the speed of sound through sea water is applied to the two-way
travel time for each intensity value. This produces an estimated ray length that, when combined with the known
sonar height (from the digitized or logged bottom), is used to produce the acrosstrack distance to a pixel using
simple trigonometry. Slant range corrected data are displayed with the water column removed and the acrosstrack
scale representing distance from nadir. It should be noted that this method presupposes that the bottom is flat
across the ping and can result in the acrosstrack misplacement of objects over varied or steeply sloping terrain. If
available, SIPS can use a BASE Surface, grid, or tile in the slant range correction operation to supply depth values
and improve the acrosstrack positioning of pixels. This process is explained in detail in the CARIS HIPS and SIPS
User’s Manual.

During the process of slant range correction, the resolution value will default to the minimum value appropriate
for the sonar system. If this resolution is not feasible, it will default to 0.10 meters. Resolution may be manually
increased, but keep in mind that increased resolution means a larger file size. The hydrographer will be required to
make some arbitrary decisions regarding beam pattern correction and despeckling. The “Beam Pattern” function
attempts to equalize the differences in pixel intensity from nadir to the outer ranges of the sonar swath. The
“Despeckle” function detects isolated bright spots and streaks in the raw sonar file and smooths them by averaging
the neighboring pixels. Applying these options will produce a more attractive mosaic when creating constituent
products, and should not hide small contacts during data processing. If SSS data were converted using the “Preserve
16-bit” option, the user can choose to “Create 8-Bit Processed Side Scan” to generate a slant range file requiring less

*Page 148*

------------------------------------------------------------------------------------------------------------------------


storage space, if necessary. When slant-range correcting 16-bit data to create 8-bit side scan, a shift factor should
be applied to spread out the histogram and improve imagery. The user can apply either the 16-bit shift factor stored
with each line or a single bit shift factor to be applied to all lines. Generally, the bit shift factor stored with each line
is a good choice.


#### 4.3.2.5 Add to Mosaic

A survey-wide side scan mosaic should be created and maintained during Daily Batch Processing to evaluate data
coverage, identify any gross systematic errors, and plan future data acquisition.

Note: If a 200% side scan survey is being conducted, a separate mosaic should be created to demonstrate coverage
for each hundred percent.

In addition to planning future SSS acquisition, the first 100% mosaic can be used to delineate areas of high contact
density where complete MBES coverage is more appropriate than 200% SSS. The hydrographer is reminded that
AWOIS radii that extend beyond the basic survey limits must be entirely covered with 200% side scan, complete
or object detection multibeam, or a combination thereof to be disproved by sonar data. These radii should be
considered when evaluating survey coverage.

When creating a mosaic, the hydrographer will be prompted for several pieces of information. In accordance with
section 5.2.2 of the HSSD, resolution shall be 1m by 1m or less. Maximum acrosstrack and altitude ratios can be
used to systematically remove areas of poor quality data from the mosaic, such as when outer edges are affected by
thermocline. Note: These features will not actually reject the imagery data, but they will remove portions indicated
for all lines in the mosaic.

Options such as interpolation and shine-thru may be used at the hydrographer’s discretion. These features may
enhance the overall mosaic and can be desirable for creating constituent products.


### 4.3.3 Boat-day Processing

Boat-day Processing” as described in this chapter refers to that portion of the hydrographic data processing that is
performed on a single vessel’s data that were acquired during a single day of data acquisition. It is assumed that all
the processes described in section 4.3.2 of this chapter have already been performed. For ships and launches, this
portion of the processing is typically accomplished during the “night processing” shift. For field parties, this
processing step may be either saved for foul weather days or accomplished by a shore party member in charge of
their unit’s daily data processing.

The goal of imagery Boat-day Processing is to identify contacts that warrant further investigation and record these
contacts in the digital data. This process is completed using SIPS Side Scan Editor.


#### 4.3.3.1 Side Scan Editor

Imagery data should be reviewed twice using CARIS SIPS Side Scan Editor. The initial review process is referred
to as “scanning” the data. The second review is performed by a different person and is called “check scanning.” The
initial reviewer should identify any object that warrants further investigation, often referred to as a “significant
contact”, and record these items into the digital data. The second review serves as a quality control, and should add
any significant contacts that were overlooked during the initial check. SIPS provides several tools to assist in
determining if a contact is significant. Two of the most frequently used are “Measure Shadow” and “Measure
Distance.”

*Page 149*

------------------------------------------------------------------------------------------------------------------------


“Measure Shadow” can be used to determine the height of an object by measuring its acoustic shadow and
calculating the object’s approximate elevation off the seafloor. This tool can only be used when viewing data in slant
range corrected mode. “Measure Distance” is used to measure the distance between two points. This tool is helpful
in determining the overall size of contacts, which may determine significance. For example, a very large item, even
if it does not protrude significantly from the seafloor, may be listed in the AWOIS database and should therefore
be investigated. The Measure Distance tool can be used when viewing both “raw” (i.e., not slant range corrected)
and slant range corrected data.

All significant contacts should be recorded in the digital data by creating a contact in SIPS. (Refer to the CARIS
HIPS and SIPS Users Guide for detailed information on how to create a contact.) The general OCS practice for
determining significance of an imagery contact is stated in the HSSD.

The hydrographer must always consider the location of a contact when determining significance. For example, in
a major channel where vessels transit with minimal underkeel clearance, a contact less than one meter high could
be significant.

When a contact is recorded in SIPS, the item is geo-coded and attributes are attached to it in the Side Scan Editor.
Each contact should be attributed as thoroughly as possible. A contact file is created for each survey line and is
stored in the line folder within the Project directory structure.


### 4.3.4 Survey-wide Processing

“Survey-wide Processing” for imagery data consists of evaluating total coverage and assessing side scan contacts in
NOAA’s Pydro software to determine which items warrant further investigation or development, and attributing
each contact accordingly in Pydro. Efficiency can be increased by conducting many of the survey-wide processing
steps concurrently with Boat-day processing for global quality control and general survey completeness. These
processes would include verifying adequate investigation of charted features and assigned AWOIS items within (or
partially within) the survey sheet limits, reviewing the data for Dangers to Navigation (DTONs), and verifying that
data coverage meets the assigned specifications. Reviewing these points on a daily basis will help to ensure a
complete survey and a timely submission.


#### 4.3.4.1 Review Survey-wide Mosaic

Survey-wide mosaics are typically reviewed during Boat-day processing to assess coverage and insure that no
significant data gaps, referred to as “holidays,” are present in the imagery. Once 100% side scan coverage has been
attained and demonstrated via the survey-wide mosaic, this “final mosaic” should be saved as a CARIS Fieldsheet
and exported as a GeoTiff in UTM NAD 83 format. Both the Fieldsheet and GeoTiff image should be digitally filed
for submission with the completed survey data. If the survey requires 200% side scan coverage, a separate final
mosaic should be created for each hundred percent.


#### 4.3.4.2 Assess Imagery Features

Throughout the survey process, imagery contacts should be periodically assessed and a determination made as to
whether “development” is necessary. Developing an imagery contact typically refers to investigating the item with
MBES to determine a least depth. However, other methods of obtaining a least depth may be used, such as VBES
or DLDG. Some types of side scan sonar systems are able to acquire co-located imagery and bathymetry data.
However, these systems are a developing technology, and SSS bathymetry has not yet been approved for OCS
hydrographic surveys.


*Page 150*

------------------------------------------------------------------------------------------------------------------------


Imagery contacts should be assessed using either CARIS Notebook or Pydro, which enables the hydrographer to
analyze each contact in context with other available data sources such as correlating contacts, the chart, bathymetry,
DPs, and AWOIS records/search radii. Contacts should be evaluated and, if confirmed to be significant, flagged for
“investigation” within Pydro. This flag enables the user to export that item to MapInfo MIF/MID and HYPACK
TGT formats to plan for further investigation or development. (Once a contact has been exported, its Pydro record
will indicate this via the “Tgt Exported” flag.) If correlating contacts or features exist, the image which best
represents the contact should be flagged “Primary”, and all correlating contacts, AWOIS items, or charted features
should be flagged “Secondary”.

Note: Any significant contact suspected to be a Danger to Navigation, as described in section 4.4.2.1 , shall be
expedited through the investigation/development process and a DTON report submitted, if necessary.
Contacts which, upon further analysis, are determined not to be significant should be flagged “Resolved” and a
note added to the Remarks tab of the Editor’s Notebook stating that the item is considered insignificant. Any
contact which was erroneously inserted into the survey data, and can not be efficiently removed, should be flagged
“Rejected” and an explanation entered in the Remarks tab. For additional information on analyzing and flagging
contacts in Pydro, refer to section 4.4
The determination whether or not to develop an item from imagery data is considered a preliminary assessment
of contacts. Once this decision has been made, significant contacts are considered imagery “features” and should
be further processed as described in section 4.4 This preliminary contact evaluation should not be confused with
finalization of imagery data, where the goal is to verify that all contacts have been addressed and flagged either
“resolved” or “rejected.”

#### 4.3.4.3 Finalize Imagery Survey Data

Once all significant contacts have been developed, analyzed, and flagged in accordance with section 4.4 the
hydrographer should verify that no “Unresolved” imagery features remain in the Pydro PSS and a final mosaic,
created in accordance with section 8.3.1 of the HSSD, has been generated and digitally filed for each 100% SSS data
acquired.



4.4 Feature Processing and Analysis
------------------------------------

In OCS surveys, a feature is an object that merits individual attention distinct from the bathymetric model of the
sea floor.

In a general sense, the bathymetric model of the sea floor will be represented on the chart using soundings and
contoured depth areas. Everything else: buoys, rocks, wrecks, piles, docks, etc. are features. During the acquisition
of a hydrographic survey, the hydrographer will encounter many objects that may merit individual attention and
treatment.

In some cases, this object will be of significant navigational interest and will eventually be portrayed as a distinct
cartographic symbol on a chart. An example of this type of feature is a prominent wreck. Once discovered, the
wreck will likely require further investigation. This may involve high resolution multibeam, side scan sonar, or
diver investigation. This additional information is collected together and used to fully describe and categorize the
wreck. Once processed, this information is passed to the Atlantic and Pacific Hydrographic branches and
cartographers using formatted reports and digital data files. These data will aid the cartographer in correctly
charting the feature.


*Page 151*

------------------------------------------------------------------------------------------------------------------------


In other cases, further investigation may indicate that the feature is not navigationally significant, and should not
be charted as a distinct cartographic symbol. An example of this type of feature might be an object detected with
side scan sonar that subsequent multibeam coverage found to be not of navigational concern (a patch of gravel
perhaps). This feature would still be handled through the same methods as the wreck described above. This process
serves as a record that the hydrographer properly inspected and handled all indications of an item of potential
navigational significance.

In some other cases, the hydrographer may wish to call out an object for individual cartographic treatment even if
the depth of the object is well represented in the bathymetric data set. For example, a large glacial erratic boulder
on an otherwise flat and featureless sandy bottom may be of particular navigational significance, especially if there
is a bottom trawl fishing fleet in the area. This object may be selected by the hydrographer and recommended for
charting as an isolated feature rather than simply through soundings and contours.

We can see from these examples that the feature processing pipeline is used to: (1) gather together information on
features that may eventually be added to the chart, (2) aid in assessing the feature’s navigational significance, and
(3) provide a mechanism for reporting this feature analysis to the Atlantic and Pacific Hydrographic branches.
Five basic sources of feature information must be analyzed and resolved when processing an OCS hydrographic
survey: Bathymetry, side scan imagery, detached positions (DPs), AWOIS items, and geographic positions (GPs).
The ability to resolve a feature depends heavily on viewing data in its full context. GIS (Geographic Information
System) software can be used to spatially correlate a set of features both within the contemporary survey data and
from other (prior) data sources, enabling the hydrographer to quickly identify redundant data on a single “real
world” feature. Correlating information allows the hydrographer to confidently determine a feature’s significance
with respect to marine safety and nautical charting. The most important features that can be identified in a survey
are those that pose a danger to navigation (DTON). Data should be reviewed daily to identify items that are
DTONs, as described in section 4.4.2.1 DTON processing shall be expedited to the greatest extent possible.
Non-DTON features should be evaluated and classified periodically as the survey progresses toward completion.
Ultimately, all features should be evaluated, classified, developed (if necessary), and resolved.
NOAA hydrographic field units shall use NOAA’s Pydro software package, CARIS Notebook, CARIS Bathy
DataBASE (BDB), and/or HYPACK ENC EDITOR to analyze and document survey features. CARIS BDB and
Pydro are generally used for feature correlation for side scan sonar (SSS) contacts. Pydro is also used for generating
survey reports for DTONS and the Final Request for Tides. All four software packages can be used to process
S-57 features and populate their attributes. The user may switch between software by importing and exporting
S-57 .000 files. The capabilities of these software packages are described further in section 4.4.1.
The feature processing workflow is illustrated in figure 4.17.below:


*Page 152*

------------------------------------------------------------------------------------------------------------------------


Figure 4.17: Feature Processing Workflow

### 4.4.1 Processing Software


#### 4.4.1.1 NOAA Pydro Software

NOAA’s Pydro software package is used to bring the various source data for potential features, (side scan Sonar
contacts, designated soundings, detached positions etc.) together in a georeferenced interface. In most cases, Pydro
maintains links to the source data which results in certain flags and edits applied in Pydro being automatically
written into the source dataset. Similarly, some types of editing performed in the raw data processing program (i.e.,
CARIS HIPS/SIPS) will be automatically carried through to Pydro.

Note: Some edits performed in CARIS, such as rejecting/accepting sounding data or imagery contacts, will require
that the source data be re-inserted into Pydro.

•	 Pydro has the ability to read several data types, including the following:
•	 Side scan imagery contacts created in CARIS SIPS.

•	 Bathymetry features in CARIS HIPS; i.e., soundings flagged “outstanding” and/or “designated”.

•	 Bathymetry soundings in CARIS HIPS; shoal-biased binned line-by-line.

	

•	 Gridded bathymetry data created in CARIS HIPS; BASE surfaces (.csar) or weighted grids (.def/.sum/.		
weight) files.

•	 Target files from HYPACK (.tgt), Trimble Pathfinder (.mdb, etc.), and other generic data sources.
•	 The AWOIS database, in MS Access format.



*Page 153*

------------------------------------------------------------------------------------------------------------------------


•	 ENC (.000 files).

•	 Other “generic” geographic position data in many database formats, such as ESRI Shapefiles (.shp), 		
	 MapInfo Interchange Files (MIF/MID), MS Excel, dBase (.dbf), ASCII, etc.

•	 ENC S-57 base cells (.000) rendered according to S-52 and various raster formats for background data, 		
	 including GeoTIFF (.tif), MrSID (.sdf), and NOAA/BSB raster nautical charts (.kap)
•	 Once these data are imported into Pydro for a specific survey, the combined data package is referred to as 	
	 a Pydro Survey Session (PSS).

Note: The Pydro PSS is not to be confused with the historical “preliminary smooth sheet”, which was a plotted
presentation of survey data formerly required for submission.

Within the PSS, items can be marked with digital notes, various flags, and attributes to aid in decision making and
reporting. Items are automatically correlated according to a user-specified radius or can be manually recorrelated
and grouped to form sets of observations that represent the same physical item. The best data for reporting a
feature, e.g., the most accurate least depth observation from the available bathymetry and/or most descriptive
picture from the available imagery, is designated via a defined flagging schema.

Pydro is also the mechanism for creating reports such as DTONs and Requests for Tides. These reports are
automatically generated from the digital data which eliminates error prone “cut and paste” actions and standardizes
report formats which maintains quality control throughout the hydrographic data pipeline.

PSS files from Pydro are interoperable with CARIS Notebook, BDB, and HYPACK by importing and exporting
S-57 .000 files.


#### 4.4.1.2 CARIS Software

CARIS Notebook and Bathy DataBASE (BDB) are used to bring together various data types, including features,
images and bathymetry into a georeferenced user interface. CARIS Notebook and BDB are good tools for managing
line and area features such as reefs, foul areas, piers etc. Notebook also has GPS logging and tide correction
capabilities for point features. The GPS logging enables the user to digitize point and line features from a launch or
backpack in real time. The tide correction enables the user to tide correct all features in Notebook instead of HIPS
& SIPS.

Notebook and BDB have the ability to read several data types, including the following:
•	 ENCs, or other S-57 databases (.hob, .000)
•	 Raster displays: (.kap, .tif)
•	 Vector files (.shp, .dxf, .des)
•	 Gridded CARIS Surfaces (.csar)


*Page 154*

------------------------------------------------------------------------------------------------------------------------


•	 Pydro .000 files
•	 Pydro XML files (Notebook only)
•	 CARIS Mosaics
•	 CARIS Contours
•	 CARIS Sounding Plots
Once these data are imported into Notebook or BDB for a specific survey, they are saved into a Notebook or Bathy
DataBASE session, which can be opened as a cohesive unit.

Within each Session, there can be numerous types of information to assist in processing and analyzing potential
features. Charts, georeferenced images, CARIS HIPS and SIPS generated data products etc. assist in feature analysis
while the features themselves are housed in non-standard .000 files called HOB files. Each feature within a HOB
file follows the S-57 encoding specifications and has extended attributes to provide further flexibility in processing
and to support data interoperability between the various workflows that may be used in the field.
HOB files from CARIS Notebook and BDB are interoperable with Pydro and HYPACK by importing and exporting
S-57 .000 files.


#### 4.4.1.3 HYPACK Software

HYPACK contains a module that is embedded into the main HYPACK Shell called HYPACK ENC Editor. This
software is capable of making direct edits to the S-57 .000 file and takes advantage of the NOAA extended attributes
to support data interoperability between the various workflows that may be used in the field. The field may utilize
this option to perform feature verification in the field as well as adding new features to the .000 file (similar to
Notebook’s GPS logging function). Edits in the extended attribution are retained in the .000 file. HYPACK target
files (tgt) acquired as features can also be imported into ENC Editor and translated into S-57 objects.
HYPACK ENC Editor has the ability to read several data types, including the following:
ENCs (.000)
Raster displays: (.kap, .tif)
Vector files (.shp, .dxf, .dgn, .tgt)
S-57 .000 files from HYPACK are interoperable with Pydro and CARIS by importing and exporting S-57 .000 files.


*Page 155*

------------------------------------------------------------------------------------------------------------------------



### 4.4.2 Significant Features


#### 4.4.2.1 Dangers to Navigation (DTONs)

The most important features to identify in a survey are Dangers to Navigation (DTON). A DTON is defined as any
uncharted or incorrectly charted natural feature (e.g., shoal, boulder, reef, rock outcropping) or cultural feature
(e.g., wreck, obstruction, pile, wellhead) that poses an immediate threat to surface navigation. General chart
discrepancies can be addressed at the conclusion of a survey, but items that meet DTON criteria should be reported
as soon as practicable after discovery.

The primary characteristic of a DTON is navigational significance. When reviewing survey data for potential
DTONs, the hydrographer must consider the types of vessels operating in the area as well as vessel routes, both
typical and seasonal. Much of the final selection of DTONs is subjective and requires a bit of cartographic
interpretation as well as a navigational perspective of the chart. Examination of newly acquired survey data for
potential DTONs should be performed on a daily basis.

The following guidelines can be used to identify potential DTONs; however, each item should be further evaluated
for significance within that specific geographical area.


##### 4.4.2.1.1 Water Depth

Historically, selection of DTONs has been concentrated in areas with water depths of 20 meters or less. While this
remains a good rule of thumb, this depth range should be evaluated in the context of vessel traffic and typical
routes through the area. For example, features in water deeper than 20 meters may be DTONs along routes for
supertankers.


##### 4.4.2.1.2 Potential DTON Height

Typically, survey features and soundings indicating a depth discrepancy of 1 meter or greater are first evaluated for
DTON potential. Again, this guideline should not be followed blindly. Vessel traffic must be considered. If vessels
transit the area with minimal underkeel clearance, a discrepancy of only 1/3 meter could be critical; or, if a deep
inland bay or harbor is accessible only by shoaler restricted channels, a large feature within the deep water area
may not be a hazard since only small vessels could access the area. Figure 4.18 illustrates a potential DTON located
within a channel. If the channel’s tabulated depth is listed as 40 feet for the right outside quarter, then this charting
discrepancy would only be 1 foot. Typically, a 1-foot discrepancy would not be considered a DTON. However, the
hydrographer must consider what type of vessels transit the area and how much water they draw. This channel
might be the entrance to a major port facility where vessels drawing 40 feet arrive on the rising tide. In such a case,
this 1-foot difference is critical, particularly if the item is a rock or cultural feature as opposed to a sandy shoal.
Figure 4.19 shows a small bay with depth discrepancies of 2 fathoms (12 feet). Although this depth difference is
significant, the bay is accessible only by passing through a 5 or 6 fathom channel. Thus, the 7 fathom sounding
inside the bay is insignificant, i.e., not a DTON. Similarly, a very large object identified in a river accessible only
by small craft may not be a DTON. Figure 4.19 shows a potential DTON located in a deep section of a small river.
The object in question protrudes over 10 meters from the seafloor. However, this river happens to be accessible
only by small craft, due to a shoal at its mouth. Despite this large depth discrepancy, the item is navigationally
insignificant when the hydrographer considers the draft of vessels capable of operating in the area.


*Page 156*

------------------------------------------------------------------------------------------------------------------------


Figure 4.18:
Potential DTON in Channel

Figure 4.19:
Potential DTON in small bay


##### 4.4.2.1.3 Proximity to Existing Features

Many new or uncharted features are potential DTONs. The hydrographer must consider each new item’s proximity
to existing features (rocks, reefs, fish havens, shoreline, foul areas, etc.) and the item’s significance with respect to
these adjacent features. Figure 4.20 illustrates a case where an existing feature (Fish Haven with an authorized
minimum of 15 feet) affects the significance of a potential DTON. In this example, an item intended for the fish
haven may have been erroneously deposited outside the haven’s geographical bounds, a very realistic scenario.
Despite the discrepancy with regard to the charted 43 foot depth, the adjacent Fish Haven to the south/southwest
and shoal to the east would deter prudent mariners from approaching the area. Likewise, a large depth discrepancy
adjacent to a reef or foul area would quite possibly not be a DTON, again, as a prudent mariner would operate in
the area only with extreme caution.


Figure 4:20:
Potential DTON adjacent to fish
haven.


##### 4.4.2.1.4 Dense Groups of DTONs

The density of DTONs reported should not exceed what can be legibly portrayed on the largest scale chart of the
area. If numerous DTON candidates are identified in close proximity, the hydrographer could report either the
most significant item or the group of DTONs as an area feature, e.g., designate the entire area “foul.” When
determining the most significant DTON in a group, the item having the shoalest least depth will typically be
chosen. However, this may not be the case if, for example, the item is located on a slope. Typically, if two potential
DTON are adjacent on a slope, the most seaward sounding will be selected for submission. The prudent mariner

*Page 157*

------------------------------------------------------------------------------------------------------------------------


will assume that depths will decrease as shore is approached. An example of this exception is shown in Figure 4.21.
The 2 fathom sounding is shoaler, but the 4 fathom sounding extends further offshore. In this case, the 4 fathom
sounding would be submitted. Although both soundings would supersede the 5¾ fathom charted depth, it can be
reasonably inferred that there is a continuous slope toward shore, therefore depths shoaler than 4 fathoms would
be expected.


Figure 4.21:
Two potential DTON’s located on close
proximity.



##### 4.4.2.1.5 Charted Feature Removal Request

A Charted Feature Removal Request, often referred to as an “anti-DTON,” is used to expeditiously remove charted
features that are hindering operations in major shipping corridors and have been adequately disproved. Only
navigationally critical items should be submitted as Charted Feature Removal Requests. These requests should be
submitted using the same procedure indicated for DTONs in this manual.


##### 4.4.2.1.6 DTON Submission (see section 8.1.3 of HSSD)

Typically, DTON selections should be reviewed by the Chief-of-Party prior to submission. If approved, DTONs
must be flagged properly in Pydro, which can then generate a DTON report. Note: All Pydro PSS Metadata should
be completed prior to generating a DTON report so that this information will be included in the report. Additionally,
the DTON must be stamped with the actual ping time and not the time they were discovered in boat or office
processing. The Pydro DTON report is generated in a Zip archive which contains an Adobe *.pdf text report, an
*.xml file containing the survey data for that feature, and a DTONImages folder containing all the relevant report
images and chartlets (if applicable). The Zip archive should be submitted to NOAA’s Marine Chart Division (MCD)
via email (ocs.ndb@noaa.gov), with courtesy copies to the Chief of OPS and to the Chief of the appropriate
hydrographic branch.

Chartlets are not a required deliverable. However if applicable, field units may use either Pydro or ESRI to generate
a chartlet for the DTON report. If the chartlet is generated externally to Pydro, users must add those chartlets to
the *.pdf report manually. Note: The Pydro report includes a zip file of the *.pdf so field units must make sure the
report to MCD is updated before submittal if the HydroMI chartlet is going to be used.

Additional actions, as noted below, are required when reporting DTONs in the following two cases.
1.	 If the potential DTON will directly impact commercial shipping routes and/or is located within an area of
Army Corps of Engineers’ authority, the appropriate NOAA Navigation Manager shall be consulted prior to
submitting the DTON. If the Nautical Data Branch of MCD discovers a DTON located in a Corps of Engineers’
authority that has not been submitted to the Navigation Manager, then NDB personnel will cease processing
the DTON and recommend that the submitting party inform the Navigation Manager.


*Page 158*

------------------------------------------------------------------------------------------------------------------------


2.	 If a DTON report includes a potentially historically-significant wreck, the field unit shall provide a courtesy
copy of the report sections pertaining to that specific feature to the corresponding NOAA Navigation Manager
and State Historic Preservation Officer. If a potentially historically-significant wreck is identified outside of
state waters, notify the current Sanctuaries Historical/Archaeological contact.

Once submitted, all DTONs will be expedited through MCD to the Coast Guard for publication in the Local
Notice to Mariners. Within three days of DTON report submission, MCD’s Nautical Data Branch (NDB) will send
an email to the field unit confirming that DTON data has been received and processed. If a DTON submission is
not confirmed by NDB within one week, the hydrographer should promptly contact MCD (via an inquiry email to
ocs.ndb@noaa.gov) to verify that the report has been received and processed. MCD will also notify the submitting
party of any changes made to the Dangers to Navigation Report by return e-mail. For additional reference and
guidance, refer to section 8.1.3 Dangers to Navigation in the HSSD.


#### 4.4.2.2 AWOIS

Automated Wreck and Obstruction Information System is a database of wrecks and obstructions in the coastal
waters of the United States. These items have been found during previous hydrographic surveys or have been
reported by miscellaneous sources. The HSD OPS Project Manager or the NRB Technical Assistant will assign
AWOIS items to the field unit for investigation. The hydrographer shall investigate the items and document the
results according to the AWOIS requirements. For further information on AWOIS see sections 7.3 of the 	H S S D
and 2.2.2.2 of the FPM.


#### 4.4.2.3 Maritime Boundary Points

OCS is responsible for depicting the Three Nautical Mile Line (old territorial sea), Territorial Sea at 12 nautical
miles, Contiguous Zone at 24 nautical miles, and Exclusive Economic Zone (EEZ) at 200 nautical miles on NOAA
nautical charts. These maritime zones, defined by Maritime Boundary “baseline points”, define areas of U.S.
jurisdiction for a variety of regulations. The HSD OPS Project Manager or the NRB Technical Assistant will assign
Maritime Boundary rocks to the field unit for investigation. The hydrographer shall investigate the items and
document the results according to the Maritime Boundary requirements. For further information on Maritime
Boundary see sections 7.3 of the HSSD and 3.5.6 of the FPM.


#### 4.4.2.4 Cultural or Historical Submerged Features

In the course of acquiring or processing hydrographic data, features on the seafloor may be discovered which are
of potential cultural or historical significance. These include wrecks of ships or aircraft, the recognizable debris
from wrecks, or other items which may appear anthropogenic in origin and have some associated cultural or
historical significance.

Chiefs-of-Party must always promptly assess the discovery of any features for significance to local surface navigation
and report these accordingly. Any feature determined to be a Danger to Navigation shall be immediately reported
through the standard DTON reporting process (see section 4.4.2.1.

It is Marine Chart Division (MCD) policy that all features recommended for charting by the Chief-of-Party be
applied to the appropriate nautical charts. Chiefs-of-Party must continue to recommend for charting all features
determined to be significant to surface navigation, as well as features determined to be significant or hazardous to
other marine chart users engaged in activities such as fishing or trawling. This includes features which may have

*Page 159*

------------------------------------------------------------------------------------------------------------------------


potential cultural or historical significance. This policy is unchanged and in accordance with the MCD Nautical
Charting Manual.

All features which appear to be of cultural or historical significance, and appear anthropogenic in origin, do require
special consideration during the hydrographic surveying process. Data and information from these features must
always be protected and may only be released in accordance with OCS policies and procedures. Unless specified
by the Project Instructions (or other written instructions from OCS):
1.	 Do not attempt to determine the cultural or historic significance of any features. And, do not expend any
operational effort toward identification beyond what is necessary for assessment as a Danger to Navigation.
2.	 Do not speculate about a known or newly discovered feature’s potential cultural or historical significance,
either publicly or in writing.

3.	 Do not identify by name or otherwise associate with a name, any cultural or historical feature in the Descriptive
Report (DR) or any part of the survey’s data.

4.	 DO include an image, SSS or bathymetry, of the feature in the Pydro feature report for recognition by a historian
or preservation official.

OCS, as a unit of a federal agency, has responsibilities under section 106 of the National Historic Preservation Act
(NHPA, 16 U.S.C. 470 et seq.) to take into account the effects of its undertakings on historic properties. The
process for federal agencies in complying with the NHPA is laid out in 36 C.F.R. Part 800, which prescribes
consultation with the State Historic Preservation Officer (SHPO). In addition, OCS may also consult with other
NOAA offices or governmental agencies.

OCS consultations for hydrographic projects provide information about planned survey activities, and about
survey outcomes. A pre- or post-survey consult will allow these Historic Preservation Points of Contact (HPPOCs)
at least 30 days to respond. In general, NOAA field units are not required to submit any data to a HPPOC. All
consultations will be conducted by OCS.


##### 4.4.2.4.1 Pre-survey Consultation

A pre-survey consult will be initiated during the project planning process by OCS HSD Operations Branch or NSD
Navigation Response Branch. Any responses or special handling that may be required of a NOAA field unit will be
provided in the Project Instructions.

A pre-survey consultation may be anticipated to result in one of three general outcomes:
1.	 No Response – No special data handling is required.

2.	 Informational response – Information received from the HPPOC is provided without any restriction for public
release. No special data handling is required.

3.	 Actionable response – Specific information received from the HPPOC may prevent the public release of all or
part of the survey data or products. The specific information will be evaluated by HSD OPS, and clear
instructions for data handling will be provided will be provided in the PIs.



*Page 160*

------------------------------------------------------------------------------------------------------------------------



##### 4.4.2.4.2 Post-survey Consultation

A post-survey consult will be initiated by HSD’s Atlantic Hydrographic Branch (AHB) or Pacific Hydrographic
Branch (PHB). No additional action should be required by the Field Unit.


### 4.4.3 Survey Feature Management and Analysis


#### 4.4.3.1 Pre-acquisition

HSD Operations provides the field units with a Composite Source File (CSF) and Project Reference File (PRF) on
the Project CD for field verification. The CSF is in a .000 format and consists of all of the source features (i.e. ENCs,
Preliminary ENCs and GCs if applicable). The hydrographer clips the project CSF to the size of the survey and this
file is renamed to Final Feature File where all updates occur. The Final Feature File is one of the final deliverables
to the processing branch.

The PRF is in a .000 format and consists of survey reference items such as: survey limits, investigations items
(AWOIS and Maritime Boundary), bottom sample targets, and junction survey outlines. The PRF is clipped to the
size of the survey to support survey analysis and processing. The PRF is for reference only and is not one of the
final deliverables to the processing branch.


#### 4.4.3.2 Post-acquisition


###### 4.4.3.2.1. GPS Data Post-Processing

As described in section 3.5.3 , high accuracy GPS positioning frequently requires that the data acquired be post
processed to apply all available corrections. This must be accomplished before the resulting feature positions are
imported into the feature management environment for attribution and analysis. Most NOAA GPS post processing
is accomplished by one of the following two methods.


###### 4.4.3.2.1.1 OPUS GPS Processing

The National Geodetic Survey’s Online User Positioning Service (OPUS) is the most commonly used tool for postprocessing dual frequency GPS data for positions requiring sub-meter accuracy. OPUS allows the surveyor to
submit GPS data files in receiver-independent exchange (RINEX) format to NGS via the internet. The data are
post-processed, using NGS’s PAGES software, with respect to three Continuously Operating Reference Stations
(CORS). OPUS will try to select the three sites nearest to the user’s location but will expand the search based on
data availability and quality. Positions computed by OPUS are usually emailed to the user within a few minutes.
Currently, OPUS can only process one position at a time, so multiple sessions must be submitted individually. A
good solution will have an overall root mean square (RMS) value below 0.03m, using 90% of the observations, with
over 50% of the ambiguities fixed.

The performance of precise orbits generally yields marginal improvements in accuracy than its rapid orbit
counterpart. Therefore rapid orbits can be used extensively during time challenged surveys.

Additional information and specific instructions for OPUS processing are included in the Users Guide for GPS
Observations in Appendix 3 and on the OPUS web page http://geodesy.noaa.gov/OPUS/.


*Page 161*

------------------------------------------------------------------------------------------------------------------------



###### 4.4.3.2.1.2 Tremble Pathfinder Office

Trimble Pathfinder Office includes a Differential Correction Utility which is used by many field units equipped
with the Trimble ProXRS backpack GPS receiver. This utility makes use of the carrier phase data logged by the
ProXRS and the NGS CORS network to produce positions of meter-level accuracy or better.


##### 4.4.3.2.2 Target File Processing

Several types of survey data, such as shoreline features, manually measured depths, and bottom samples, are
positioned using target files. These files can not be read directly into CARIS; thus, Pydro has been developed to
handle the bulk of target file processing. A HYPACK target file can be easily inserted into Pydro via Data > Insert
> HYPACK DPs. Pydro’s Data > Insert > Trimble/Pathfinder Database GPs+DPs imports a Microsoft Access
database (.mdb) according to a specific, S-57 based Pathfinder data dictionary format developed in conjunction
with NOAA Ship FAIRWEATHER. Separate tables are used in this Pathfinder database for separate S-57 object
classes and geometry. For example, “OBSTRN_P”, “OBSTRN_L”, and “OBSTRN_A” tables may be present in a
given database file for point-, line-, and area-geometry obstructions acquired in the field. And both GPs and DPs
may be present in a given table; the “Tide – DP/GP” field is used by Pydro to segregate those observational types.
Other “generic” target files can be read into Pydro via Data > Insert > Generic GPs/DPs, wherein users may
configure a template for importing other data sources on a routine basis. Once inserted into Pydro the DP
observational data can be edited, and the various attributes present in Pydro are added. Pydro automatically writes
or “converts” (in the same sense of the term used by CARIS HIPS) DP datasets to CARIS HDCS data during data
save operations. See section 4.4.2.1 for more information.

Once a target file is written to the HDCS data, it can be opened in CARIS to continue processing DPs which
correspond to depths. In CARIS, a tide file and, if necessary (i.e., for echosounder determined depths) a sound
speed profile can be applied to DP data. The DPs must then be merged as per standard HIPS processing to create
processed depths. If any subsequent edits to DP position or depth values are performed in Pydro and saved, the
standard CARIS HIPS “outdated” status is active and data will need to be re-SV Corrected and re-merged in HIPS.

##### 4.4.3.2.3 Water Level Correction (for features only)

Preliminary and final water levels for tidally affected features such as rocks or piles are applied in either Pydro or
CARIS Notebook. To apply tides in Pydro insert DPs and load appropriate tide file (i.e. TCARI or Zoned). To
apply tides in CARIS Notebook select the feature(s) and load appropriate tide file (i.e. TCARI or Zoned).

##### 4.4.3.2.4 Attribution and Geometry


###### 4.4.3.2.4.1 S-57 Standard

S 57 is shorthand for the International Hydrographic Organization (IHO) Special Publication No. 57, “IHO
Transfer Standard for Digital Hydrographic Data”. S-57 standard details what S-57 objects and related attributes
and geometry are permissible for official navigational charts produced by hydrographic offices around the world
allowing hydrographic data to be transferred seamlessly from one user to another. The primary final product of
S-57 data within NOAA is the Electronic Navigational Chart (ENC).

An S-57 file is a database of feature object classes and associated attributes that utilize a 6-letter acronym naming
convention. For example a buoy (BOYLAT) is the feature object class and the description such as color (COLOUR)

*Page 162*

------------------------------------------------------------------------------------------------------------------------


are the associated attributes. Multiple object class “instances” are often required to describe a single real-world
feature. For example, a lighted lateral buoy with a horn is described with three object classes in S-57: BOYLAT
(buoy, lateral), LIGHTS (lights), and FOGSIG (fog signal).

Attribute types under each object class are used to indicate the specific makeup of the feature; e.g., COLOUR
(colors), COLPAT (color pattern; applicable if dealing with more than one color), CATFOG (category of fog
signal), etc.


####### 4.4.3.2.4.1.1 S-57 Objects

S-57 feature designation and attribution are assigned in HYPACK, CARIS Notebook and BDB through the feature
editing function. In CARIS select the feature type (i.e. point, line, area) on the Feature Creation menu. Select the
appropriate feature object class in the Object Acronym list. The details of the object class are displayed below in the
Dictionary Information. The S-57 attributes are in upper case, the extended attributes are in lower case, and the
mandatory attributes are distinguished with red color (Note: this is only true if the hydrographer is using the
NOAA customized extended attribute files for CARIS which include the mandatory attribute settings). Certain
attributes do not require manual editing; instead, the attribute is linked to the digital data present in the CARIS
feature data (e.g. VALSOU - value of sounding - is associated with the depth).

In HYPACK select the feature type (i.e. node, chain, and region) and appropriate feature object class. The HYPACK
Object Catalog uses whole words instead of acronyms (e.g. to create a PILPNT, you select PILE). The S-57
mandatory attributes are distinguished with a “M”.

In Pydro S-57 features are designated and attributed via an S-57 Editor dialog. Only the primary item requires
flags and attributes because they are propagated through to the flags of all Secondary items. Select an object in
the ”Object Classes” list by checking the box adjacent to the desired object class description. The corresponding
6-digit acronym for any highlighted class name in the list is shown in the mouse pointer tooltip while hovering
over the “Object Classes” button; and, clicking on the button opens up a help file detailing the meaning of the
object class. The mandatory and additional attributes per the ENC Product Specification are shown on separate
notebook pages in the Pydro S-57 Editor. Certain attributes do not require manual editing; instead, the attribute is
linked to the digital data present in the Pydro XML feature data (manual editing for such attributes is in fact
disabled). For example, if the S-57 attribute VALSOU (value of sounding) is associated with the feature, the Pydro
XML <depth> element value will automatically appear in the depth editing box. Fill out the other boxes on the
Additional Attributes notebook page in the S-57 Editor dialog according to your field observation.

####### 4.4.3.2.4.1.2 S-57 Attribution

S-57 feature attribution is required for features to be compiled to an ENC. S- 57 feature attribution is required for
all new and updated items that represent a real-world feature recommendation for inclusion on the official
navigational chart. The hydrographer should edit the S 57 object/attribute instances to describe each real world
feature as completely as possible.

In addition to S-57 Attribution, NOAA requires customized flags and attribution to support H-Cell (preliminary
ENC) compilation by the cartographers and to highlight features that need to be included in the appropriate
reports. These extended attributes and flags are mirrored through all three processing software applications
allowing for interoperability between the software using .000 files.

Refer to the S-57 and NOAA Attribution Guidance.pdf, Attributing and Flagging for Automated Feature Reports.
pdf, and Customized Attribute Equivalencies.pdf in Appendix 4 of the FPM for more information.


*Page 163*

------------------------------------------------------------------------------------------------------------------------



###### 4.4.3.2.4.2 New Features and Feature Geometry Modification

The most appropriate tools for creating and modifying line and area features are CARIS Notebook, BDB, and
HYPACK ENC Editor. Notebook and HYPACK ENC Editor have the ability to digitize data in real time with
the GPS logging functionality. Features can also be created or modified during post processing. BDB updates
must occur during post processing as BDB does not have the GPS logging functionality.

New features are added as S-57 attributed objects through the feature editing function. The feature geometry
shape and extents of existing features), such as ledges, foul areas etc, can also be modified using the same function.
Line or area objects that require modification may be delivered as points or lines of the new extents.
All additions and modifications require specific attributes which are described in detail in the S-57 and NOAA
Attribution Guidance.pdf in Appendix 4section 8.2 of the HSSD.

All new and modified features.are submitted in the Final Feature file. See section 4.4.4 for details.

###### 4.4.3.2.4.3 Attributing and Flagging

Features must be attributed/flagged correctly in the processing software for the processing branch cartographers
to compile the survey to an HCell and create the Feature Report Appendices of the DR. For processing and QC
the hydrographer may use the Query functions in CARIS BDB and Notebook or the *treetemplates files in Pydro.
Refer to section 8.2 of the HSSD for attribution requirements.


####### 4.4.3.2.4.3.1 Additional Attribute/Flagging Definitions & Examples


######## 4.4.3.2.4.3.1.1 Pydro Combination Flag Definition

The following subsections describe the most common Pydro flagging combinations for survey items, grouped by
data acquisition type: items from bathymetry (HIPS processed depths flagged Outstanding and/or Designated),
imagery (SIPS contacts), DPs, AWOIS, and other geographical positions (GPs). Note that all descriptions listed
below are for Primary items. The Primary attribute/flag is no longer mandatory. In addition, the term “Feature
Report” refers to the feature report created at the processing branch.

1. Items from Bathymetry
•	 Resolved - This indicates any bathymetry feature that is not intended for the feature report (note the absence
of the Report flag). This should be used for all designated soundings that were selected to force the uncertainty
surface to honor the true sea floor—but not otherwise elevated to the level of desire for an explicit feature
symbology on the chart.

•	 Chart, Resolved - This flag combination indicates any bathymetry feature that is included as an explicit feature
on the PSS, but not intended for the feature report (note the absence of the Report flag). This flag combination
is uncommon, but sometimes used when depicting complex shoreline with a series of DPs. Further information
and reasoning should be detailed in the item’s Remarks tab.

•	 Chart, Report, Resolved - This flag combination indicates any bathymetry feature that is included as an explicit
feature on the PSS and is intended for the feature report. Further information and reasoning should be detailed
in the item’s Remarks tab.


*Page 164*

------------------------------------------------------------------------------------------------------------------------


•	 Chart, DTON, Report, Submitted, Resolved - This flag combination indicates any bathymetry feature that is
included as an explicit feature on the PSS, is specifically intended for the feature report, and has been submitted
to MCD as a DTON. Further information and reasoning should be detailed in the item’s Remarks tab.
2. Items from Imagery
•	 Resolved - This flag combination indicates any insignificant contact that was not developed (otherwise imagery
item should be Secondary to a bathymetry-based feature). Further information and reasoning should be
detailed in the item’s Remarks tab. This flag combination often indicates a contact that, after further evaluation,
was determined to be insignificant.

•	 Tgt Exported, Resolved - This flag combination denotes a contact that was exported, presumably for subsequent
investigation, and found to be insignificant (otherwise imagery item would be Secondary to a bathymetrybased item). The item is not intended for the feature report. Further information and reasoning should be
detailed in the item’s Remarks tab.

•	 Chart, Report, Resolved - This flag combination indicates any imagery item that was determined to be a
significant contact, but was not investigated. The item is intended for the feature report. Further information
and reasoning should be detailed in the item’s Remarks tab. Imagery items should typically not be flagged
Chart since they do not provide an accurate depth for charting. Except in extenuating circumstances,
significant items from imagery should always be Secondary to a (Primary) bathymetry-based item. An example
of when this flagging scenario could be used is when the field unit acquired SSS imagery, but left the area
before a significant contact could be developed with bathymetry or diver investigation. This scenario is not
common, but is sometimes unavoidable.

3. Detached Positions (DPs)
•	 Rejected, Resolved - This flag combination indicates any detached positions that the hydrographer does not
want to be part of the survey. Further information and reasoning as to why it was rejected, such as because it
was a blunder or a DP on an unassigned AWOIS item, should be added in the feature’s Remarks tab.

•	 Resolved - This flag indicates any detached positions included for informational purposes only, which are not
intended for the feature report. Further information and reasoning should be detailed in the item’s Remarks
tab.

•	 Chart, Resolved -This flag combination indicates any detached positions that are depicted on the PSS as
features but not intended for the feature report. Some examples of when this flagging scenario might be used
are as follows: (i) recording bottom sample locations, (ii) positioning shoreline features, and (iii) verifying
positions of aids to navigation.

•	 Chart, Report, Resolved - This flag combination indicates any detached positions that are depicted on the PSS
as features and are intended for the feature report. Some examples of when this flagging scenario might be
used are as follows: (i) least depths determined by DLDG that either do not have supporting echosounder
bathymetry or any correlating echosounder bathymetry is flagged Secondary, and (ii) portraying complex
shoreline, including issues such as changes to MHW and shoreline feature disprovals.

4. AWOIS Items
•	 Resolved - This flag indicates an AWOIS item that was disproved using one of the investigation methods

*Page 165*

------------------------------------------------------------------------------------------------------------------------


assigned in the database record. It can also be used to indicate an AWOIS item that does not fall directly into
a survey area, but whose search radius partially falls within the survey area, and has been or will be addressed
by an adjoining survey. Further information should be added to the item’s Remarks tab.

•	 Secondary—to [Primary] Bathymetry Item or DP (see section 4.4.4 for information on correlation) - This flag
combination indicates any AWOIS item that was located/verified during the survey.

•	 Geographic Positions (GPs)- GPs are any point data that do not fit into another feature category. As Secondary
items, they can be used to convey information that is outside the scope of standard features in Pydro. GPs may
be either inserted into Pydro from some “generic” ASCII or database format or manually digitized via the
context menu in a Pydro Chart Window. GPs can optionally be assigned under the sub-categories “ChartGPs”
and “Checkpoints”. An explicit function exists in Pydro to insert S-57 ENC features as ChartGPs into the PSS
for evaluation of survey items in context with the (official) chart.

•	 Secondary ChartGPs are used to indicate the connection of the associated Primary item to an existing charted
feature. Such a relationship instructs Pydro’s DR document builder to file a Report feature under the “Charted
Features” chapter; absence of a Secondary ChartGP (and no Secondary AWOIS) directs a Report feature to
the “New Features” chapter.

•	 Checkpoint GPs can be created in Pydro if survey features do not exist at desired comparison locations 		
	 for (say) a Pydro Points/Surface Stats Report.

	
	
	

•	 GPs can be created as placeholders for the information necessary to disprove a feature, without the need 	
for an item to be explicitly logged during data acquisition. Photographs and other details about the 		
techniques used to disprove a feature (e.g., search radius and method) are important pieces of 			
information to include with such a disproval GP.



######## 4.4.3.2.4.3.1.2 Examples of Feature Attribution Using the NOAA Customized Attributes

Assigned Features – Not Addressed descrp=5
Features that were “Assigned” in the CSF but not addressed. The reasoning should be detailed in the item’s
Remarks attribute. These features maintain the original SORDAT and SORIND.

Example 1: An obstruction area was Assigned but not addressed due to high sea state making the area unsafe for
operations. The feature is attributed as Not Addressed and an explanatory statement is included in the Remark
field.

Example 2: A charted rock was Assigned but not addressed due to the feature being inshore of the navigable area
limit line of the survey. The feature is attributed as Not Addressed and an explanatory statement is included in the
Remark field, such as “inshore NALL”.

Addressed Features with No Attribution Change descrp = 4
Features that were addressed and not edited in any way, maintain the original SORDAT and SORIND. Descriptive
attribution of Retain along with a explanatory Remark should be added. This will alert the processing branch to
either retain the charted feature or that the feature is depicted accurately if from another source.
Example: A GC rock is Assigned and investigated during shoreline verification, it was found to correctly portray
the feature. No existing attribution, such as height is changed. The feature is given descriptive attribution of
Retain and a Remark .


*Page 166*

------------------------------------------------------------------------------------------------------------------------


New Features descrp=1
New features that are identified are given a descriptive attribution of New along with an explanatory Remark and
the SORDAT and SORIND populated with current survey entries.

Example: A charted rock is found to be the high point of a large new navigationally significant reef. A SBDARE
line (NATSUR = Rock) is digitized into the Final Feature File using the observed reef extents as a guide, assigned
the new SORDAT and SORIND, given a Remark and the descriptive term New. The processing branch will create
an area object of the SBDARE line.

Updated Features descrp=2
Updated features are comprised of features that have a change in Attribute or Object class, but do not have a
change in position. The field modified something about the feature without moving it. Examples of the two main
update types are below:
Update Feature, Attribute Change:
Example 1: A height measurement is taken for a GC rock. The rock is retained in the Final Feature File, VALSOU
field populated, the feature is assigned the new SORDAT and SORIND and given the descriptive term Update. A
Remark is included to note the addition of the height attribution.

Example 2 : The color of a mooring buoy is found to be orange rather than the yellow shown on the chart. The
COLOUR attribute is changed for the MORFAC feature, and the feature assigned the new SORDAT and SORIND
and given the descriptive term Update. A Remark is included to note the change of the color attribution.
Updated Feature, Object Class Changed (geographic primitive unchanged)
Example: A charted pile is found to be a dolphin. The PILPNT designation is changed to MORFAC, dolphin, and
the new SORIND and SORDAT are assigned to the new feature. The feature object change is noted in Remarks
and the feature is attributed with the descriptive term Update.

Re-positioning features, changing a Geographic Primitive and altering or adding to the extents of an area
feature:
The above scenarios all require two sets of features, one with a descrp =1 for the new position/primitive/extents,
and the other with a descrp = 3, for the old position/primitive/extents. This indicates to the cartographer/ reviewer
what has changed. The following are examples of these changes.

Repositioned Features – Altering Geographic Position or Shape descrp= 1 for feature at new position, descrp=3
for feature at old position
For features that were repositioned or the geographic position or shape is altered, the original feature that
has a position error is attributed with the descriptive term Delete, maintaining the original SORDAT and SORIND,
given an appropriate Remark and Recommendation. The repositioned feature in the Fi- nal Feature File is assigned
the new SORDAT and SORIND, will contain a Remark stating that it was repositioned and be given the descriptive
term New.

Example: A charted pile is discovered to be a dolphin 200 m to the west of the charted position. The new dolphin
is digitized and given the new SORDAT and SORIND, a Remark, and descriptive attribution of New; the pile is

*Page 167*

------------------------------------------------------------------------------------------------------------------------


given the descriptive term Delete and it maintains the original SORDAT and SORIND, and the Remarks field is
populated regarding the disproval of the pile. Because it is a charted feature a Recommendation is also required
Geographic Primitive Altered (i.e. from point to area, or area to point)
descrp= 1 for feature with new geographic primitive, descrp= 3 for feature with old geometry
In any case where the geographic primitive is altered (i.e., point feature modified to a line; point modified to an
area, etc.), the feature with the new geometry contains the descriptive attribution New and the feature with the old
geometry is attributed with the descriptive term Delete.

Example 1 : A charted obstruction area with snags/stumps is discovered to be the intact wreck of the privateer
Black Pearl. The OBSTRN object is given the descriptive term Delete and it maintains its original SORDAT and
SORIND. It is given a Remark, and because it is a charted feature disproval, it is also given a Recommendation.
A new WRECKS point object is collected in the field or digitized to the Final Feature File, assigned the new
SORDAT and SORIND, given the descriptive term New and a Remark.

Example 2: A charted reef is found to be correctly positioned, but is determined to be a small islet rather than a
reef. A LNDARE point object is used to depict the islet, and height given using a LNDELV object. The LNDARE
and LNDELV objects are assigned a descriptor of New, are given a new SORDAT and SORIND and a Remark.
The original reef is attributed with the descriptive term Delete maintaining its original SORDAT and SORIND.
Because it is a charted feature disproval both a Remark and a Recommendation are added to the feature.
New or Adjusted Extents – Line or Area
descrp = 1 for new or adjusted extent, descrp = 3 for old extent
The Final Feature File includes line features digitized to define new or modified limits of kelp beds, foul or rocky
areas, ledges and reefs, where the extents were obtained using DPs, GPs, buffer lines, or surfaces from VBES and/
or MBES. The new SORDAT and SORIND are assigned and a Remark added, for instance “New ledge”.

Example 1 : The BASE Surface is used as a back drop to digitize the extents of a rocky seabed area using a
SBDARE line object. The SBDARE line object (which will be created as an area object during branch processing)
is included in the Final Feature File and assigned the new survey SORDAT and SORIND. Remarks are added to
the line feature and it is attributed as New.

Example 2: A maritime boundary MLLW water point is investigated, it is found to be at a more seaward location
of an already charted ledge. The new extents are digitized using a SBDARE line object. The SBDARE line object
is included in the Final Feature File and assigned the new survey SORDAT and SORIND. Remarks are added to
the line feature and it is attributed with a descriptor of New and a special feature type of Maritime Boundary. The
old extent of the ledge may need to be attributed as Delete and retains its original SORDAT and SORIND, and
includes a Remark and Recommendation.

Deconflicting Features
descrp= 4 best position feature, descrp= 3 for features determined to be at incorrect position
Where features from multiple sources are given in the composite source for deconfliction, the feature that is
selected as the best representation is attributed as Retain in the Final Feature File, maintaining its original
SORDAT and SORIND. A statement as to why the feature was selected to be retained and what methods were
used to make this determination is included in the Remarks field. The remaining features are attributed with the
descriptive term Delete. Each disproved feature keeps its original SORDAT and SORIND and a Remark. A
Recommendation must also accompany any currently charted features attributed with the descriptive term Delete.

*Page 168*

------------------------------------------------------------------------------------------------------------------------


Example 1: The composite source includes two features for deconfliction, one from the raster chart and one from
GC, positioned in close proximity to each other and to a prior survey feature included in a reference file. The prior
survey rock is found to be the best representation of the position of the rock. The prior survey rock is imported
into the Final Feature File and given the descriptive term Retain along with a Remark. The prior survey feature
maintains its original registry number and date for SORIND and SORDAT. The remaining two features, the GC
and chart rocks, are attributed as Delete. The features retain their original SORDATs and SORINDs. Remarks are
included for both, and a Recommendation accompanies the chart rock.

Example 2: Where a LIDAR item is found by the field to be a charted feature, choose the better representation of
the item and attribute it as Retain. If the LIDAR item is selected over a charted item, the LIDAR item remains in
the Final Feature File and the charted feature is attributed as Delete. If the charted item is selected over a LIDAR
item, the charted item remains in the Final Feature File and the LIDAR feature is attributed as Delete.
Disprovals descrp=3
Features from Composite Source that have been disproved should be attributed with the descriptive term Delete,
and should maintain the original SORDAT and SORIND. A Remark should indicate the reason for disproval.
Disproved chart features also require a Recommendation.

Example 1: A charted rock is disproved using MBES. The charted rock is given the descriptive term Delete where
it maintains the original SORDAT and SORIND, the Remarks field is populated regarding the method of disproval,
and a Recommendation to remove the feature from the chart is made.

Example 2: A charted pier in ruins is not seen in the SSS imagery or in the MBES data. The pier is given the
descriptive term Delete and should maintain the original SORDAT and SORIND. The remark field is populated
with information regarding the method of disproval and a Recommendation to remove the pier from the chart is
made.

Example 3: LIDAR coverage over a charted feature shows no indication of the charted feature. The feature has
subsequently been disproved using VBES, SWMB, etc. The charted feature is attributed as Delete and maintains
its original SORDAT and SORIND, and the method of Disproval is indicated in Remarks. A Recommendation is
also required for all Disprovals

###### 4.4.3.2.4.4 Feature Correlation

In a NOAA hydrographic survey new features can be automatically cor- related (i.e. associated or connected) with
existing data using Pydro software. or manually correlated with CARIS Notebook, BDB or HYPACK. The manual
correlation in CARIS and HYPACK is achieved through NOAA ex- tended attributes. For further information,
refer to section 8.2 of the HSSD
The existing data are typically classified in one of the following five categories:
•	 Items from Bathymetry – Sounding data (MBES or VBES) which has been identified as a measurement of a
least depth on a feature in CARIS HIPS or Pydro. ”Designated” soundings can also be selected to force the
gridded surface to honor the true depth of the seafloor.

•	 Items from Imagery – A potentially significant feature which has been identified in SSS data, chosen as a
contact in CARIS SIPS during post-processing, and to be evaluated for further investigation and/or development.

*Page 169*

------------------------------------------------------------------------------------------------------------------------


•	 Detached Positions (DP) – Detached positions are used to position point features such as shoreline items,
bottom sample locations, DLDG depth determinations, and lead line or pole soundings. DPs are subdivided
into echosounder and non-echosounder types. Echosounder DPs are used for data with a corresponding depth
determined by VBES, MBES, or another system which is referenced to a point other than the water’s surface
and require the application of vessel offsets. Non-echosounder DPs are used to provide positions for data
either with no associated depth information or referenced to the water’s surface, such as DLDG determined
depths and heights of shoreline features.

•	 AWOIS Items – AWOIS items represent features which have been previously reported or surveyed and are
generally included on the current chart. Specific AWOIS items within, or partially within, each survey area will
be assigned for investigation.

•	 Geographic Positions (GP) – Geographic positions refer to point data used for various purposes and not
otherwise classified. These points are typically uploaded from a portable GPS system, manually digitized in
CARIS, HYPACK, or Pydro, or created by inserting “generic” data into Pydro.

•	 Two sub-types of GPs exist in Pydro: “Chart GPs” and “Checkpoints”. The principal use of Chart GPs in Pydro
is to indicate those survey items which represent new observations on existing charted features, or otherwise
disprovals thereof. Checkpoints provide for a way to steer some comparison of survey data at discrete locations.
As each feature is evaluated, standard classification flags should be set. (A Pydro data flagging decision tree is
provided in Figure 4.22 to assist the hydrographer with this process.) The basic process involves systematically
reviewing survey data for features, by segregating correlating groups of items into a best- representative “Primary”
item + supporting “Secondary” item(s). This decision process involves examining survey items in context with all
supporting data available: any previously known items (AWOIS and other currently-charted features) and
bathymetry (current survey, prior survey, charted soundings, etc).

Note: An item from bathymetry representing the least depth of a navigationally significant real-world feature
should always be marked Primary.



*Page 170*

------------------------------------------------------------------------------------------------------------------------


Figure 4.22: Pydro data flagging decision tree.

For all the correlating items that represent the same feature as the Primary item, set the status flag to Secondary.
If an item has been automatically correlated to a Primary item, but does not appear to be the same feature, assign
it as Primary. That is, use the Primary item status to segregate features. If your survey makes use of side scan
sonar, this means you will often encounter disparate features through items from imagery before having supporting
item(s) from bathymetry. Set the status flag to Primary for such items, knowing that if they prove to be navigationally
significant, a bathy item will take precedence as the Primary item when available. If there are items that represent
a common feature that have not been automatically correlated by distance, use Pydro’s Group Features tool to
manually associate those items.

In Pydro only, certain subsequent flagging actions on a feature need only be carried out on the Primary item
because they are propagated through to the flags of all Secondary items. Each feature should be reviewed to
determine if it is significant based on either the NOAA contact height criteria or some other criteria determined
by the field unit. Other criteria include, but are not limited to, proximity to a maintained channel, predominant
ship/boat traffic in the area, proximity to other significant features etc. If so, check the “Significant” flag. If the
feature requires additional data acquisition to be resolved, also check the “Investigate” flag. The purpose of the
Investigate flag is to remind the field hydrographer that more information, possibly involving additional data
acquisition, is necessary to adequately resolve the least depth or nature of a feature. All items marked “Investigate”
may be exported to MapInfo Interchange Format files (MIF/MID), HYPACK Target files (.tgt), or HYPACK S-57

*Page 171*

------------------------------------------------------------------------------------------------------------------------


files (.000) to facilitate additional data acquisition; the “Tgt Exported” flag is set upon item export.

### 4.4.4 Deliverables

The following feature files shall be delivered with a survey. The hydrographer shall adhere to Appendix 12 of the
HSSD: Data Directory Structure for the proper directory structure:
1. Feature Data:
(a) Final Feature File in .000 format - (HXXXXX_Final_Features _File.000) - The .000 final features layer contains
the original source data with survey updates. This is the primary file the branch cartographer will use to compile
the survey to the HCell.

(b) Final Pydro File (if applicable) in a .pss format (HXXXXX_Final_Features _File.pss) – The .pss final features
layer contains the original source data with survey updates. The .pss is a supplemental file which may or may not
be used by the branch cartographer to compile the survey to the HCell.

2. Multimedia - Photographs and images are very helpful to the cartographers during compilation. Multimedia is
delivered with the final feature file in the Multimedia folder. The photographs and images are correlated or linked
(depending on software) to the features.

(a) Photographs – ex: new extents of piers, piles, rocks, etc.

(b) Images
	
	
	

i. MBES – ex: least depth on rock or wreck from CARIS 3-D viewer
ii. Side Scan Sonar Contact Images

Note: A copy of the Side scan sonar contact images shall be delivered in the CARIS HDCS line file.
3. Side Scan Sonar (SSS) Contacts in .000 format – All SSS contacts, both significant and insignificant, shall be
delivered in .000 format and submitted in the S-57 Features Folder. The side scan sonar contact points shall be
delivered as the S-57 feature object cartographic symbol ($CSYMB) with the attribution described above in
Section 8.2 of the HSSD.

•	 Example 1 : The BASE Surface is used as a back drop to digitize the extents of a rocky seabed area using a
SBDARE line object. The SBDARE line object (which will be created as an area object during branch processing)
is included in Final_Features and assigned the new survey SORDAT and SORIND. Remarks are added to the
line feature and it is attributed as New.

•	 Example 2: A maritime boundary MLLW water point is investigated, it is found to be at a more seaward
location of an already charted ledge. The new extents are digitized using a SBDARE line object. The SBDARE
line object is included in Final_Features and assigned the new survey SORDAT and SORIND. Remarks are
added to the line feature and it is attributed as New. The old extent of the ledge may need to be attributed as
Delete and retains its original SORDAT and SORIND, and includes a Remark and Recommendation.

Deconflicting Features
descrp= 4 best position feature, descrp= 3 for features determined to be at incorrect position

*Page 172*

------------------------------------------------------------------------------------------------------------------------


Where features from multiple sources are given in the composite source for deconfliction, the feature that is
selected as the best representation is attributed as Retain in Final_Features, maintaining its original SORDAT and
SORIND. A statement as to why the feature was selected to be retained and what methods were used to make this
determination is included in the Remarks field. The remaining features are attributed with the descriptive term
Delete. Each disproved feature keeps its original SORDAT and SORIND and is given a Remark. A Recommendation
must also accompany any currently charted features attributed with the descriptive term Delete.

•	 Example 1: The composite source includes two features for deconfliction, one from the raster chart and one
from GC, positioned in close proximity to each other and to a prior survey feature included in a reference file.
The prior survey rock is found to be the best representation of the position of the rock. The prior survey rock
is imported into the Final Feature layer and given the descriptive term Retain along with a Remark. The prior
survey feature maintains its original registry number and date for SORIND and SORDAT. The remaining two
features, the GC and chart rocks, are attributed as Delete. The features retain their original SORDATs and
SORINDs. Remarks are included for both, and a Recommendation accompanies the chart rock.

•	 Example 2: Where a LIDAR item is found by the field to be a charted feature, choose the better representation
of the item and attribute it as Retain. If the LIDAR item is selected over a charted item, the LIDAR item
remains in the Final_Features layer and the charted feature is attributed as Delete. If the charted item is selected
over a LIDAR item, the charted item remains in the Final_Features layer and the LIDAR feature is attributed
as Delete.

Disprovals descrp=3
Features from Composite Source that have been disproved should be attributed with the descriptive term Delete,
and should maintain the original SORDAT and SORIND. A Remark should indicate the reason for disproval.
Disproved chart features also require a Recommendation.

•	 Example 1: A charted rock is disproved using MBES. The charted rock is given the descriptive term Delete
where it maintains the original SORDAT and SORIND, the Remarks field is populated regarding the method
of disproval, and a Recommendation to remove the feature from the chart is made.

•	 Example 2: A charted pier in ruins is not seen in the SSS imagery or in the MBES data. The pier is given the
descriptive term Delete and should maintain the original SORDAT and SORIND. The remark field is populated
with information regarding the method of disproval and a Recommendation to remove the pier from the chart
is made.

•	 Example 3: LIDAR coverage over a charted feature shows no indication of the charted feature. The feature has
subsequently been disproved using VBES, SWMB, etc. The charted feature is attributed as Delete and maintains
its original SORDAT and SORIND, and the method of Disproval is indicated in Remarks. A Recommendation
is also required for all Disprovals.



4.5 Chart Comparison
---------------------

Compare each hydrographic survey to the latest versions or editions of the largest scale ENC’s and raster charts
that cover the project area. Conduct the comparison in accordance with section 8.1.4., D.1 of the HSSD. The
specific method of comparison is left to the discretion of the hydrographer, though the comparison is typically
done using Pydro, CARIS, or MapInfo software. When performing a chart comparison, the hydrographer shall use
the most current official charts available. If necessary or required by the Project Instructions, additional evaluation
methods such as junction survey comparisons or prior survey comparisons may also be used.


*Page 173*

------------------------------------------------------------------------------------------------------------------------



### 4.5.1 Obtaining and Identifying Current Charts

The hydrographer should keep in mind that the most current official charts may not be the ones provided on the
Project CD/DVD. Often, versions of raster and/or ENC charts used for vessel navigation will be more current.
Any chart corrections from the National Geospatial Intelligence Agency’s (NGA) Notice to Mariners (NTM), the
United States Coast Guard’s Local Notice to Mariners (LNM), and Canadian Hydrographic Service (CHS) that
have not yet been applied should also be considered. For additional chart correction information, the database of
NTM corrections can be queried online at: http://msi.nga.mil/NGAPortal/MSI.portal LNM corrections can be
reviewed online at: http://www.navcen.uscg.gov/

#### 4.5.1.1 Raster Navigational Charts (RNC)

Prior to chart comparisons, the most current RNC can be downloaded from MCD at http://www.charts.noaa.
gov/. For raster charts, the edition, corrections applied, and date of notices through which the chart has been
“cleared” will be included in the *.KAP file header information, which can be viewed using a text editor such as
WordPad. The term “cleared” means that all notices up to, and including, the one issued on the cleared date have
been reviewed and any corrections have been applied to that raster chart. Edition and correction information has
been identified in the example header file section in section 4.2.4 .


Figure 4.23: Section of a *.KAP file (opened in WordPad) identifying chart edition and corrections that have been
applied to the digital file. Note: CHS does not issue corrections for this chart area, so no cleared date is listed.
Note: Some of the chart information identified in Figure 4.24 is repeated in the header line beginning with “NTM.”
In this example, NE=10.56 refers to what the raster manufacturer calls the “Notice Edition.” It is the number of
digital patches (56) applied to that chart edition (10). ND refers to the “Notice Date,” and repeats the NGA NTM
cleared date. BD is the “Base Date” and repeats the chart edition date.


#### 4.5.1.2 Electronic Navigational Charts (ENC)

The most current ENC can be downloaded from MCD at http://www.charts.noaa.gov/.

The ENC Update Application Date is the date that the full ENC Cell was first posted or re-posted. This date is
similar to the Edition Date of a raster chart. ENC Cells are re-posted when the updates grow too large or a large
section of the Cell is re-built. The Issue Date identifies when the last correction was applied. All notices have been
applied through that date, similar to a “cleared” date for raster charts. If using an ECDIS system or viewer software
to read the ENC, these dates can be found in the ENC Cell properties.

Note: Some viewer manufacturers have erroneously reversed the Update Application Date and Issue Date. Since
an edition must exist before it can be corrected, the later of these two dates will always be the Issue Date.

*Page 174*

------------------------------------------------------------------------------------------------------------------------



### 4.5.2 Junction Survey Comparisons

If the designated limits for a survey junction with modern data from another survey, the area of overlap should be
compared and discussed in the Descriptive Report. OCS considers a standard junction comparison acceptable if
sounding variance is 1 meter or less between the present and junctioning surveys. Agreement is considered poor
if sounding variance is greater than 1 meter. In such cases, the hydrographer should attempt to determine the
cause(s) of significant discrepancies and explain these variances in the Descriptive Report.


### 4.5.3 Prior Survey Comparisons

Due to the advances in survey technology and data coverage capabilities, modern survey data will nearly always
supersede historical data. Thus, prior-survey comparisons are generally not required by field personnel, but may
be used at the discretion of the hydrographer for quality control purposes. If the present survey has numerous
conflicts with charted soundings and/or features, then the hydrographer should consider conducting a prior survey
comparison. If a prior survey comparison is performed, the reason it was deemed necessary should be discussed
in the Descriptive Report and the applicable prior survey(s) should be identified by registry number, date of
survey, and scale.



*Page 175*

------------------------------------------------------------------------------------------------------------------------


