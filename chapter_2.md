Chapter 2
===========
Pre-Survey Planning
Pre-survey planning is essential for any field unit to effectively and efficiently conduct hydrographic survey operations. When planning operations, the hydrographer must keep in mind the assigned survey specifications and
approved methods for meeting those criteria. This Chapter describes information that will be provided to a field
unit when a hydrographic survey is assigned and provides project preparation and survey planning guidance.

2.1

Crew & Vessel Safety

Above all, every member of the field party should understand that safety of the crew and vessel is the number one
priority. Safety shall be the foremost consideration in all aspects of Office of Coast Survey (OCS hydrographic
surveys, from the planning stages through data submission. It is the responsibility of the Chief-of-Party, as well
as vessel crew, to be aware of safety hazards and take steps necessary to ensure undue risks are avoided, even
if it means ceasing operations.

Good planning and information can minimize risks associated with hydrographic surveying. Recommended
practices to increase safety include, but are not limited to the following:
•	 Use historical weather information to prepare for seasonal patterns.

•	 Review the survey region for exposed areas, constricted areas, shallow areas, surf, etc. Plan on surveying
challenging areas when weather, tides, and currents are optimal.

•	 Review prior survey Descriptive Reports (DR) and smooth sheets for uncharted hazards. Often, the DR will
describe deficiencies, hazards, and challenges from prior surveys and field experience.

•	 Work progressively from safe water towards unknown, shallow, or potentially hazardous areas.

•	 Use daily survey information progressively in the field to minimize hazards. Communicate survey and safety
information to all personnel involved in operations. ‘
Read the Automated Wreck and Obstruction Information System (AWOIS) features included with the project
files descriptions to understand hazards and survey the feature project area safely.

Understand the limitations of charted and source information and approach features conservatively during initial
operations.



*Page 44*

------------------------------------------------------------------------------------------------------------------------



2.2 The Project CD/DVD
------------------------

When a hydrographic survey is assigned, the HSD Operations Branch (OPS), or the NSD Navigation Response
Branch (NRB) if the unit is an NRT, will generate and compile relevant project information onto a Project CD/
DVD. This information will include project instructions, as well as supporting information and data files to be used
during field operations and subsequent survey processing. Copies of the Project CD/DVD will be disseminated
to the appropriate field unit six weeks prior to the start of the project. The file structure illustrated in Figure 2.1
represents that of a typical Project CD/DVD. If a folder is intentionally left empty, the project planner will place
in a readme.txt file indicating as such.


Figure 2.1: Project DVD Structure


*Page 45*

------------------------------------------------------------------------------------------------------------------------



### 2.2.1 Hydrographic Survey Project Instructions

The Hydrographic Survey Project Instructions will identify specific requirements for a survey project. Project
Instructions will be included on the Project CD/DVD and can be equated to a Requirements Document or
Statement of Work. Field units shall acknowledge receipt of Project Instructions via email to the assigned OPS
Project Manager or the NRB Technical Assistant.


### 2.2.2 Supporting Project Information

Extensive supporting project information will be provided on the Project CD/DVD. The following items are
included: Consults folder containing relevant project correspondence, project GIS Files, Junction Surveys, Prior
Surveys, and preliminary tidal zoning files. The naming conventions for project information files generated at
OPS or NRB will reference the applicable project number or survey sheet number.


#### 2.2.2.1 Consults

OCS, as a unit of a federal agency, has responsibilities under section 106 of the National Historic Preservation
Act (NHPA, 16 U.S.C. 470 et seq.) to take into account the effects of its undertakings on historic properties. The
process for federal agencies in complying with the NHPA is laid out in 36 C.F.R. Part 800, which prescribes
consultation with the State Historic Preservation Officer (SHPO). In addition, OCS may consult with other NOAA
offices or governmental agencies, depending on jurisdiction. The Hydrographic Surveys Division is responsible
for conducting the entire consultation process. Correspondence and documentation relating to consultations with
these Historic Preservation Points of Contact (HPPOCs) will be included in the Consults folder as background
information for the field units.

Any additional relevant project correspondence will be included in this folder.


#### 2.2.2.2 GIS Files

This folder will include the Composite Source File, MapInfo Sheet Limits, Maritime Boundary Point(s) Document,
the Project Reference File, and Aids to Navogation Records.

The OPS Project Manager or NRB Technical Assistant will compile all available shoreline source files into
one “composite source” file (CSF) in S-57 .000 format. Shoreline source files include: ENC, RNC, Geographic
Cells (GCs – also labeled as DCFF ), and Lidar files. Compilation will include reviewing the CSF to determine
which shoreline features shall be verified by the field unit. Features requiring verification shall have the attribute
Assignment (asgnmt) populated with “Assigned”.

The MapInfo sheets .tab will be provided to identify the planned area of hydrography for each project.
Layouts for Field Examinations (FEs) will vary according to the item, feature, or area to be surveyed. Any
MapInfo tables created by the OPS Project Manager or NRB Technical Assistant will be projected in Universal
Transverse Mercator (UTM) using the North American Datum of 1983 (NAD83).

A Project Reference File (PRF) will also be delivered with the CSF. The PRF is an S-57 attributed dataset
containing reference layers such as survey limits, junctions, recommended bottom sample locations and features
which are specifically targeted for investigation such as AWOIS points or Maritime Boundary points.

*Page 46*

------------------------------------------------------------------------------------------------------------------------


The project wide AWOIS items are assigned to the field unit for investigation by the OPS Project Manager or
the NRB Technical Assistant. This subset of the master AWOIS database will contain all items falling within the
limits of the particular project, as well as any critical items in close proximity to the survey area.
AWOIS items are represented as placeholders by the S-57 Feature Object CRANES. The AWOIS radii are
represented by the S-57 Feature Object ACHBRT. The AWOIS search radii are assigned based upon extensive
research of historical documents and factors such as the original source of the feature and the quality of that
feature’s positioning.

Prescribed investigation requirements for each AWOIS item will be specified in the NOAA Extended Attributes
(see section 8.2 of HSSD for details).

All AWOIS items included in the project area are “assigned” for verification (asgnmt = “Assigned”). In addition,
the project planner may “assign” AWOIS items outside of the project area.

There are two types of AWOIS verification:
1.0 AWOIS items which have not been verified in the past (Item Status = “Assigned”, Search Type = “Full” or
“Limited”) – investigation includes verifying or disproving the item by covering the entire search radius regardless
of location with respect to survey limits.


2.0 AWOIS items which have been verified in prior surveys (Item Status = “Completed”, Search Type =
----------------------------------------------------------------------------------------------------

“Information”) – no search radius is required. Investigation includes verifying or disproving the feature just as any
other feature within the project area is verified or disproved. A search outside of the survey limits is not required
(i.e. items inshore of the NALL).

See section 7.3 of the HSSD for further information on AWOIS items.

If shoreline verification is not required, there will be no CSF however all projects will contain a PRF containing
a minimum of the survey limits.

NOAA’s Update Service Branch (USB) within the Marine Chart Division will review NOAA’s Critical Corrections
Database (CRIT) and/or USCG Integrated Aids to Navigation Information System (IATONIS) database to identify
ATONs within the survey area that require positioning. Records for each assigned ATON will be provided by USB
for inclusion on the Project CD/DVD. ATON records will include the current database position for each assigned
ATON, position accuracies or positioning methods that were used (if available), and any special positioning
requirements.


#### 2.2.2.3 Junction Surveys

Assigned surveys may include a junction with contemporary data from a recent field season and all field units are
required to ensure continuity in survey coverage and depth by evaluating junctioning or overlapping surveys. The
Project Instructions will indicate if a junctioning survey is in a projection and datum other than UTM NAD83 and
requires a datum conversion or reprojection.



*Page 47*

------------------------------------------------------------------------------------------------------------------------



##### 2.2.2.3.1 Junctioning with Light Detection and Ranging (Lidar) Surveys

Lidar junction data will be provided in S-57 (.000 or .HOB) format on the Project CD/DVD. Features found by the
Lidar survey will be added to the Composite Source File (CSF) as an existing feature. Lidar investigations will be
added to the Project Reference File (PRF). Field units should obtain the required coverage type to the Lidar extent
line or the Navigation Area Limit Line (NALL), whichever is further offshore. The standard practice for coverage
overlap between Lidar and MB surveys is to overlap one swath width inshore of the LGL. Verify or disprove all
Lidar investigation items seaward of the NALL.

The following files will be included on the Project CD/DVD for junctioning with Lidar data.

File Name

Description

Hxxxxx_LI_BASE_3m

3 meter resolution surface.


Table 2.2: CARIS file included on the Project CD/DVD for junctioning with Lidar data.

File Name
Description
Hxxxxx_DR.pdf
Descriptive report and Appendices.

Table 2.3: Other files included on Project CD/DVD for junctioning with Lidar
The following common attributes are used to define feature objects in the deliverables.

Attribute
Description
NINFOM
Remarks and description of the feature.

Table 2.5: Object attributes used in HOB files for junctioning with Lidar data.

For more information about the inclusion and treatment of Lidar items in the Composite Source, refer to section
2.2.1 and 3.5.5.1 .


#### 2.2.2.4 Prior Surveys

The Project CD/DVD will include the Descriptive Report raster images of the smooth sheet, features and soundings
(in .000 format) for all available prior surveys in the assigned area.


#### 2.2.2.5 Survey Request Information

The OPS Project Manager or the NRB Technical Assistant will include, if available, copies of documents from the
maritime community, research groups, or other entity requesting the survey on the Project CD/DVD.

#### 2.2.2.6 Tides

The Project CD/DVD will identify vertical control requirements for a project. Vertical Requirements which are
further explained in sections2.4.4 & 3.5.2 , could consist of traditional tidal zoning, TCARI, VDatum, constant
separation value, or ellipsoidally referenced zoned tides (ERZT). The Project Instructions will explicitly list any
required subordinate tide gauges. A VDatum or constant separation file to correct soundings from the ellipsoid to
chart datum will be provided on the project CD/DVD. For ERS vertical datum QC procedures, refer to chapter
9 of the HSSD.


*Page 48*

------------------------------------------------------------------------------------------------------------------------


The NOAA Center for Operational Oceanographic Products and Services (CO-OPS) provides three basic types of
water level data, “predicted tides,” “preliminary water levels” and “verified water levels” referenced to MLLW or
other appropriate chart datum. All of this data can be downloaded from the CO-OPS website. Typically, CO-OPS
posts preliminary water level data within a few hours of data acquisition. Stations included on the Hydro Hotlist
(see section 3.5.2.3.1 are processed weekly and verified water level data is typically available at the start of the
following work week. Verified tides can be downloaded from the CO-OPS Data Retrieval website:
http://opendap.co-ops.nos.noaa.gov/axis/text.html
The CO-OPS Hydro Planning Team (HPT) also supplies discrete zoning or TCARI to estimate water levels across
the entire survey area where the water level characteristics may vary from those where tide gauges are located.
Historical water level station information, including the location of each station site, benchmark description and
elevations, and historical datum references will also be provided if historical tide stations need to be reoccupied.
Predicted tides using 6-min format will be supplied on the Project CD/DVD.


#### 2.2.2.7 Orthoimagery

The hydrographer may request orthoimagery for a project if considered necessary to support pre-survey planning
and post processing. Examples may (but are not limited to) include areas where there are drastic differences from
the shoreline features in the CSF to the real world features. In these cases the hydrographer should contact the
project planner from HSD or NRB which is listed in the project instructions to request approved orthoimagery.
The project planner will work with the HSD OPS Team Lead and RSD to acquire the approved orthoimagery if
available. Note: Orthoimagery is for reference only and shall not be used as source for surveying (i.e. digitizing
features from orthoimagery is not allowed).



2.3 Additional Resources
-------------------------

Although the majority of information required to conduct an OCS hydrographic survey will be provided on the
Project CD/DVD, additional resources such as training or reference materials may be necessary throughout a field
unit’s operating season.


### 2.3.1 Hydrosoft Website

The Hydrosoft website, https://inside.nos.noaa.gov/hydrosoft/welcome.html, is maintained by OCS’s
Hydrographic Systems and Technology Program (HSTP) and provides an extensive amount of reference materials
to the field. A Site Download option will be made available at the beginning of each field season to download the
entire Hydrosoft website via a zip file. Additionally, the Recent Updates page lists all the changes that have been
made in reverse chronological order.



*Page 49*

------------------------------------------------------------------------------------------------------------------------


The following types of materials can be found on the Hydrosoft Website:
•	 Common survey software packages and applications, both commercial and in-house.

•	 Software and hardware manuals and guides.

•	 NOAA hydrographic training presentations and resources.

•	 Nautical and navigation reference materials (e.g., Bowditch, Coast Pilot, Chart 1).

•	 NOAA Hydrographic survey references (e.g., HSSD, FPM, IHO documents).



2.4 Project Preparation
------------------------

Once a field unit has received the Project CD/DVD, survey personnel should begin preparatory tasks such as
reviewing project information, establishing a data management plan, contacting constituents, and planning
horizontal and vertical control if necessary. These tasks are typically performed on a project-wide basis, prior to
individual survey planning.


### 2.4.1 Project Information and Instructions

As soon as practicable, the field unit should inventory files provided on the Project CD/DVD to verify that all
necessary information has been included. Once it has been confirmed that all files are present, project information
should be copied to the field unit’s computer systems in accordance with the unit’s standard data management
practices. The OPS Project Manager or the NRB Technical Assistant will deliver draft Project Instructions
approximately two months prior to the start of a project. The Field Operations Officer and Chief Hydrographic
Surveyor should review the draft Project Instructions to raise questions and concerns with HSD OPS or NRB
at this time. Once the final Project Instructions are delivered (approximately one month prior to the start of
a project) all appropriate hydrographers should review the Project Instructions and Project CD/DVD files to
become familiar with the project.


### 2.4.2 Data Management

Guidelines for effective field unit data management are described in the following sections.


#### 2.4.2.1 Digital Data Directory Structure

Data directory structures used during acquisition and processing may vary among field units. However, a standard
should be in place within each field unit. It is important to adhere to any field unit directory standards, as some
software configurations must reference specific directories. Refer to Appendix II for an example of a field unit
directory structure.



*Page 50*

------------------------------------------------------------------------------------------------------------------------



#### 2.4.2.2 Digital File Naming Conventions

It is important to follow file naming standards within the field unit. Maintaining these conventions greatly assists
AHB and PHB in identifying data records. Do not create data files with non-standard names that are unrelated to
the file content and will confuse others who must access that data. Additionally, any preliminary, temporary, or
extraneous files created by the field unit should not be included with data submitted to AHB or PHB.

### 2.4.3 Horizontal Control

Horizontal Control (HorCon) refers to the terrestrial network of geodetic marks that support two-dimensional
hydrographic positioning. Typically, NOAA field parties use USCG differential beacons to correct GPS for
hydrographic positioning. USCG differential correctors are subjected to an internal quality control process,
ensuring a stable meter-level service. Additionally, USCG differential beacons are precisely positioned; thus, it
is generally unnecessary for NOAA field units to establish horizontal control points when using this positioning
method.

In remote survey locations or confined areas such as a fjord, USCG differential correctors may be unavailable or
severely limited. For these areas, the field unit shall establish at least one horizontal control point where a portable
DGPS control station can be installed. A review of the survey area should be combined with local knowledge to
determine a feasible location. Keep in mind that public properties are usually preferred over private properties
because special permissions will typically not be necessary for future access. However, equipment security
must also be considered in populated areas which are easily accessible. Security measures may include locking
instruments, affixing owner identification to equipment, and choosing a discrete station location. After a suitable
location has been chosen, the field unit should obtain permission to access the property and install HorCon
equipment. If it is necessary to drill into rock during the installation, permits should be obtained for this purpose.
The Federal Aviation Administration’s Wide Area Augmentation System (WAAS) may be used provided a QC
procedure is followed as per Section 3.2.2 of the HSSDM.

HorCon techniques may also be used to determine high accuracy DGPS positions for ATONs. If OCS’s Update
Service Branch requires that an ATON be positioned using high accuracy HorCon methods, specifications will be
noted in the ATON information provided on the Project CD/DVD. Typically, higher order ATON positions will
be required for range lights.


### 2.4.4 Vertical Control

Vertical control refers to a network of geodetic marks that supports three-dimensional hydrographic positioning.
Vertical control activities are typically conducted to support water level gauge installations, water level
measurements, and ERS. Personnel from CO-OPS are responsible for all planning of tide and water level
requirements for OCS hydrographic surveys. CO-OPS will analyze historical data and tidal characteristics for
each project area, specify operational NOS control stations, specify general locations for subordinate water
level stations to be installed, and provide the tidal zoning (both preliminary and final) to be used during survey
operations.

Installation, operation, and maintenance of controlling water level stations is typically the responsibility of the
CO-OPS Field Operations Division (FOD). However, the hydrographic field unit may be required to install,
monitor, repair, and/or uninstall a control water level station under the instructions of the CO-OPS FOD. The
Project Instructions will state if installation, operation, and/or removal of subordinate water level stations is

*Page 51*

------------------------------------------------------------------------------------------------------------------------


required for a project. In such cases, FOD will work in collaboration with the field unit to complete these tasks.
The field unit will be responsible for ellipsoidal positioning of benchmarks near subordinate water level stations,
in accordance with section 4.2.5 of the HSSD.

To prepare for vertical control operations, the field unit should verify that all necessary equipment and tools have
been obtained from CO-OPS. The following manuals should occupy the equiptment received from CO-OPS FOD:
•	 Portable Tide Gauge Setup, Configuration, and Data Export Procedure
•	 9210B Xlite Data Logger Operations and Maintenance Manual
•	 Paros User’s Manual
•	 Satlink2 Operations and Maintenance Manual
•	 H-355 Pump User’s Manual
A sample equipment checklist for water level station installations is included in Appendix 2 (Wtr_Lvl_Statn_Equip_
Checklist.pdf). Several reference guides are available to assist the field unit with water level station procedures.
For reference, the following manuals can be found on the Hydrosoft website and can also be downloaded from
the CO-OPS website tidesandcurrents.noaa.gov/pub.html
•	 NOS User’s Guide for the Installation of Bench Marks and Leveling Requirements for Water Level Stations.
•	 Specifications and Deliverables for Installation, Operation, and Removal of Water Level Station
•	 CO-OPS User’s Guide for Electronic Levels
•	 CO-OPS User’s Guide for Writing Bench Mark Descriptions
•	 CO-OPS User’s Guide for GPS Observations
Additionally, the field unit should review any subordinate water level station locations specified in the Project
Instructions and, if necessary based on local knowledge, recommend alternate sites to CO-OPS. Keep in mind that
public properties are usually preferred over private properties because special permissions will typically not be
necessary for future access. However, equipment security must also be considered in populated areas which are
easily accessible. Security measures may include locking instruments, affixing owner identification to equipment,
and choosing a discrete station location. Once locations have been agreed upon, survey personnel should obtain
permission to access the property and install the staff, benchmarks, and gauge at the selected site.

### 2.4.5 Constituent Contact

The Project Instructions will list constituents who must be contacted at or near the beginning and end of field
operations to discuss survey objectives and accomplishments. It is mandatory that the field unit contact the
appropriate regional NOAA Navigation Manager as identified in the Project Instructions.

The Project Instructions will also list various local contacts for reference. These resources should not be overlooked
and can often provide local knowledge regarding AWOIS items, shoaling, marine activities, traffic patterns,

*Page 52*

------------------------------------------------------------------------------------------------------------------------


and other areas of concern. Local information sources include Port Authorities, Pilot Associations, local ferry
companies, fishermen, towing companies, U.S. Coast Guard, U.S. Army Corps of Engineers, and local and state
government agencies. Information regarding local survey requests or charting concerns that will not be addressed
during the current project should be conveyed to either the Chief of Operations or the Chief of NRB.

#### 2.4.5.1 Local Notice to Mariners Announcement

Prior to commencing survey operations for a project, the field unit shall submit an announcement to be included
in the USCG Local Notice to Mariners (LNM). At a minimum, this announcement should be submitted 2-weeks
prior to commencing operations and include information about the project work area, the type of work being
conducted, the field unit characteristics (e.g. size, color, markings of ship and launches), means of contacting
the field unit, and the start and end dates of the survey. These announcements can be submitted via e-mail to
the appropriate USCG District e-mail, which are listed in the LNM for each district (http://www.navcen.uscg.
gov/?pageName=lnmMain). See Appendix 2 for an example of a LNM announcement.


#### 2.4.5.2 Cultural or Historic Submerged Features

HSD Operations Branch will contact the State Historic Preservation Officer (SHPO), historical/archaeological
contact at NOAA’s Office of National Marine Sanctuaries (ONMS), or other relevant governmental agency during
preparation of Project Instructions to request information on any historically significant man-made features on the
seabed within the survey area. Information provided by these Historic Preservation Points of Contact (HPPOCs)
will be included in the Project Instructions. While the Project Instructions will also include contact information,
field units are generally not required to consult with the HPPOCs. Instead, the Hydrographic Processing Branches
are responsible for contacting the HPPOCs in the event of discovery of a potentially historically significant manmade feature, in accordance with section 4.4.3 .

#### 2.4.5.3 Potential for Lost or Damaged Fishing Gear

In many areas, particularly the Northeast United States, field units may encounter significant densities of fixed
or floating fishing gear; such as lobster pots, crab pots, fishing pots, long lines, gill nets, etc. NOAA field units
should always attempt to minimize the impact of hydrographic survey operations on the commercial fishing industry. There is an expectation that Coast Survey and all field units will make every effort to prevent damage or
interaction with fishing gear. However, if damage does occur, State agencies may not detain or prosecute a Federal employee for violation of State law. For example, it is a violation of Massachusetts law if someone destroys
any lobster or other fishing gear and can be punished through a fine or imprisonment; however, if they are engaging in an activity authorized by the Federal law (e.g. conducting survey operations), then they cannot be detained.
See Appendix 2 for a legal opinion from NOAA’s Office of General Counsel.

When operating in areas with high densities of fishing gear, field units should consider modifying survey operations to reduce the possibility of damaging fishing gear and survey equipment. Some steps that may be taken in
areas of dense fishing gear include:
•	
•	
•	
•	

Limiting survey operation to daylight hours.

Utilizing survey launches instead of the ship to conduct operations.

Utilizing hull-mounted sonar systems instead of towed survey gear.

Limiting use of towed sensors such as Moving Vessel Profilers


*Page 53*

------------------------------------------------------------------------------------------------------------------------


In an effort to be pro-active and incorporate better coordination, the Operations Branch will contact fishing and
lobster associations and organizations to inform them, prior to the field season, where a NOAA survey vessel
will be working and the approximate time frame. This notification will be completed via an official letter to the
association president or other point of contact. The Navigation Manager for the region and field unit should be
carbon copied on this letter. See Appendix 2 for an example of a notification letter.

A mandatory point of contact will be listed in the Project Instructions for projects which have the potential to significantly interfere with the work of local fishermen/lobstermen. In those cases, the field unit must use that point
of contact to solicit input and coordinate with the local fishermen/lobstermen in an effort to reduce possibility of
fishing gear interaction and better plan survey operations.

Additionally, the Navigation Manager or field unit will submit an announcement of the survey project for inclusion in the USCG (LNM) as early as is practicable (usually as soon as Project Instructions are received). See
section 2.4.5.1 for information on submitting announcements. These announcements should also be provided directly to the fishing or lobstermen association for distribution to their members and inclusion in their newsletters.
Notices should not only be sent to associations operating in the region the survey operations are being conducted,
but also adjacent associations, as they will likely have some overlap.

While field units will make every effort not to cause damage or otherwise interfere with fishing gear, some entanglements and other damage may occur. In instances where fishing gear has been damaged local fisherman or lobstermen may make a claim regarding lost or damaged fishing gear and request compensation. The claims process
for damaged fishing gear that may have been damaged by a NOAA hydrographic survey field unit is listed below:
1.	
	
	
	

Initial claims of gear interaction may be received from the fishermen by the field unit, the USCG, or the 		
State Marine Patrol. Claimants will typically be referred to the State Marine Patrol as the best point of 		
entry into the process. Note that NOAA hydrographic survey field units are not authorized to collect 		
sworn statements, so whenever possible claimants should be referred to a law enforcement agency.


2.	
	
	
	

State Marine Patrol and NMFS Office of Law Enforcement special agents will collaborate to collect 		
sworn statements from affected fishermen, depending on whether alleged loss occured in state or 			
federal waters. At a minimum, claims need to give the location of gear lost, estimate of when it 			
was lost, what was lost, and the fair market value.


3.	
	

All completed claims will be routed from NMFS OLE special agents to the regional NOAA Navigation 		
Manager.


4.	
	
	

The Navigation Manager will request route data from the field unit, and compare the positions and times 	
of the alleged loss with the unit’s activities. The Navigation Manager may request assistance from the 		
local NOAA Fisheries lab to determine if fair market value claimed for lost gear is reasonable.


5.	
	
	

The Navigation Manager will forward substantiated claims to NOAA Office of General Counsel for final 	
certification and payment. See Appendix 2 for an example letter for reimbursement. Unsubstantiated 		
claims will be referred back to the State Marine Patrol and NMFS OLE with supporting documentation.

6.	

OCS and OMAO leadership will determine how costs of any claims will be shared.



*Page 54*

------------------------------------------------------------------------------------------------------------------------



2.5 Survey Planning
---------------------

OCS recommends that systematic data acquisition plans be prepared prior to vessel operations.These plans may
consist of lines used directly for vessel navigation, polygons used to designate survey areas if the acquisition
software provides a real time coverage map, or target files used to mark pre-determined data acquisition points.
When creating data acquisition plans, many factors must be considered, including the scope of the survey, object
detection criteria, sheet layout with respect to surrounding features, available data acquisition systems, number
of features to be addressed, traffic patterns, local currents, tide stages, and prevailing weather and sea conditions.
Input from other survey personnel, particularly those who have previously operated in the area, can be invaluable
when creating data acquisition plans. Proposed plans should be reviewed by the FOO and/or Chief-of-Party prior
to vessel operations.


### 2.5.1 Survey Scope

The scope of an OCS hydrographic survey will be categorized as basic hydrographic, navigable area, field
examination, or special project. Survey requirements will vary according to this classification. The type of survey
to be conducted and any special requirements will be identified in the Project Instructions.

The type of specific hydrographic survey projects are created via an evaluation of known requirements and
priorities. Survey limits are based on these requirements and priorities as well as quantitative and qualitative
measures of shipping and boating in an area, the adequacy of existing survey information in the area, the rate of
change of the bathymetry, safety precautions and an assessment/weighting of benefit versus efficiency.

#### 2.5.1.1 Basic Hydrographic Surveys

A basic hydrographic survey must be able to stand alone, without supplementation by any other survey. The
basic survey must be adequate to supersede all prior surveys for charting purposes and meet all applicable survey
requirements specified in HSSD.


#### 2.5.1.2 Navigable Area Surveys

Navigable area surveys must meet the requirements of basic hydrographic surveys, but will have special survey
limits defined in the Project Instructions. Typically for this type of survey, the limits have been restricted to
omit areas that are not considered navigationally significant. Another scenario would be restricting the survey
to primary shipping traffic areas. Assigned survey limits may require adjustment based on safety and field unit
observations of local traffic patterns. Any significant survey limit adjustments shall be coordinated through the
Chief of OPS.


#### 2.5.1.3 Field Examinations

Field Examinations (FE) are item investigations or surveys that cover small areas of specific interest. These
surveys may be assigned to prove/disprove the existence of reported dangers or obstructions, to provide data for
harbor development, or to supplement prior surveys for construction of large-scale charts.



*Page 55*

------------------------------------------------------------------------------------------------------------------------



#### 2.5.1.4 Special Projects

Special Projects are surveys typically performed for purposes other than creating nautical charts, such as habitat
mapping, ocean exploration, or homeland security. The Project Instructions will define requirements for Special
Projects.

Note: Depending upon the type of project, data acquired for Special Projects may be subject to additional security
measures. Any required security practices will be defined in the Project Instructions. The field unit should use
discretion when handling Special Project data and contact the Chief of OPS or Chief of NRB if data security
requirements are in question.


#### 2.5.1.5 Homeland Security Surveys

Homeland security surveys may be assigned in response to requests by the US Naval Oceanographic Office
(NAVOCEANO) for hydrography to support Homeland Security in the nation’s coastal waterways. These
projects are typically 200% side scan sonar surveys conducted in accordance with NOS requirements for SSS
data acquisition and processing with minor modifications. Any additional project specific requirements will be
provided in the Project Instructions. In the event that it is not possible to adhere to the HLS specifications, Chief,
HSD Operations Branch should be contacted for further guidance.

Special attention should be given to setting up survey plans and file structures when a survey area contains a region
to be submitted for Homeland Security purposes. Careful advance planning will ensure that the relevant Homeland
Security survey data and associated ancillary files will be easily extractable for submission to NAVOCEANO.

### 2.5.2 Object Detection Criteria

Unless otherwise specified by the Project Instructions, all data acquisition shall be conducted to meet object
detection criteria as set forth in the HSSD; this may be accomplished with SSS, MBES, or a combination of the
two. Object detection capabilities are dependent upon the acoustical characteristics of the sonar system. Vessel
speed versus sonar pulse repetition rate (ping rate) must also be considered in order to meet coverage requirements
in the along track direction. Standards set by OCS for object detection vary depending on sonar technology and
requirements for each sonar type are discussed individually below.


#### 2.5.2.1 Side Scan Sonar (SSS)

The HSSD states that side scan sonar systems shall be operated such that a 1m x 1m x 1m object on the sea floor
can be detected from acoustic shadow measurements. OCS has determined that this object detection criteria can
be met by acquiring a minimum of 3 independent ensonifications (pings) per meter traveled in the along-track
direction. This criterion can be met by regulating vessel speed based on sonar range scale. Longer operating
ranges have slower pulse repetition rates, thus requiring that the vessel speed be slower to meet object detection
requirements. Refer to sections sections 6.1.2 and 6.1.3 of the HSSD for further guidance on side scan object
detection standards. Sonar ping rates should be defined in the operator’s manual or the manufacturer’s technical
documentation.



*Page 56*

------------------------------------------------------------------------------------------------------------------------



#### 2.5.2.2 Multibeam Echosounder (MBES)

Multibeam echosounder object detection criteria vary according to water depth. Adequate detection has been
defined by OCS as 3.2 beam footprints, center-to-center, per 3 meters (in depths of 40 meters or less) or a distance
equal to 10 percent of the depth (in depths greater than 40 meters). In the along track direction, this criterion can
be met by regulating vessel speed based on sonar range scale, which directly affects ping rate. Since the size of
MBES beam footprints will be greater as the angle from nadir increases, object detection capabilities should be
calculated based on outer beams. Field personnel should refer to section 5.2.2 of the HSSD for further guidance
on multibeam object detection standards. Sonar ping rates should be defined in the operator’s manual or the
manufacturer’s technical documentation.


### 2.5.3 Survey Line Planning

Before creating a line plan, the Project Instructions should be reviewed for any required methodology, line spacing,
or coverage requirements. Besides Project Instruction requirements, factors such as general bathymetry, traffic
patterns, shoreline features, currents, prevailing weather and sea states, and distance from GPS base stations
should also be considered during line plan creation. New features discovered during operations may warrant
additional adjustments to line plans as the survey progresses. It should be noted that survey limits are subject to
revision based upon command decision and/or requirements for safe vessel operation. Any significant survey limit
adjustments shall be coordinated through the Chief of HSD Operations Branch.

Safety should never be compromised for the sole purpose of following a line plan. Line plans used for data
acquisition can be classified into the following categories:
•	 Mainscheme (MBES, SSS, or VBES)
•	 Holidays (MBES, SSS or VBES)
•	 Crosslines (MBES or VBES)
•	 Developments (MBES or VBES)
•	 Target Files
•	 Special Circumstances
Acquisition requirements vary depending upon data category and the type of equipment used. OCS recommends
that field units standardize survey line numbering such that data classification can be determined based upon line
number. For example, use the 100 number series for the first 100% of side scan sonar lines; the 200 number series
for 200% side scan numbers; the 300 number series for side scan holidays lines; the 400 - 500 number series
for mainscheme multibeam lines; the 600 - 800 number series for development data; and the 900 number series
for crosslines. Specific line numbering standards have not been implemented by OCS; however, standardization
within each field unit is strongly recommended.

Line plan requirements and guidelines for each data category are discussed in the following sections. Keep in
mind that these guidelines are provided to help the field unit maximize survey efficiency, but they should not be
followed at the expense of personnel and vessel safety.



*Page 57*

------------------------------------------------------------------------------------------------------------------------



#### 2.5.3.1 Mainscheme

Mainscheme refers to the primary survey data that are systematically acquired to meet basic survey requirements.
Mainscheme data are typically comprised of complete or object detection MBES data or 200% SSS imagery
data acquired simultaneously with VBES bathymetry. However, in some circumstances variances such as a
combination of complete multibeam and 100% side scan data may be preferred.

When planning mainscheme lines, special consideration should be given to junction areas. For surveys that are
part of the same current project and from the same year, data overlap in junction areas shall be sufficient to ensure
continuous coverage. To adjoin with a non-contemporary survey from a different year and possibly conducted by
a different vessel, a 100-200 meter overlap of mainscheme data is required, unless the Project Instructions and
provided project limits indicate otherwise.


##### 2.5.3.1.1 Multibeam Echosounder (MBES)

When planning mainscheme MBES lines, the hydrographer must consider object detection requirements,
echosounder system, and water depth. If complete coverage is desired, line spacing will vary according to the
effective swath width. The available swath width will vary between systems, but object detection requirements
may require data filtering by swath angle or could even limit the types of sonars which may be used. Generally,
lines should be oriented parallel to depth contours for consistent swath widths and line spacing. The following
formula can be used as a general rule of thumb for determining swath width:
Available Swath Width = 2 x Water Depth x (tangent 1/2 swath angle)
The hydrographer should keep in mind that allowing for adequate data overlap when planning mainscheme lines
can significantly reduce the number of holidays created during acquisition. Based on the above formula and
collective OCS experience, mainscheme line spacing is commonly set at 3 x Water Depth to obtain complete
coverage.

In special cases, partial MBES coverage may be used for mainscheme survey data. This type of coverage might
be assigned if time is limited and existing survey data are fairly modern. In such cases, required line spacing will
be noted in the Project Instructions. For further information on MBES requirements for OCS surveys, see section
5.2.2 of the HSSD.


##### 2.5.3.1.2 Side Scan Sonar (SSS)

Typically, two-hundred percent coverage is required when using SSS as a mainscheme survey technique. One
hundred percent coverage is completed by acquiring data that meet the assigned object detection requirements
over the entire survey area one time. This process is performed a second time to obtain two-hundred percent
coverage. Side scan sonar data quality will, inherently, degrade both at nadir and at outer ranges. Because of this
characteristic, line plans for the second hundred percent should be either offset or oriented differently than the first
hundred percent. OCS recommends offsetting 200% lines by ½ of the line spacing for the first 100% coverage.
If possible, SSS data should be acquired by running lines perpendicular to depth contours to avoid imagery
distortion caused by slopes in the athwartships direction.

Note: Multibeam backscatter imagery is not considered equivalent to, or a replacement for, side scan sonar
imagery. Side scan sonar provides low grazing-angle imagery that enables identification of features not visible in
lower resolution, higher grazing angle MBES backscatter imagery.


*Page 58*

------------------------------------------------------------------------------------------------------------------------


The line spacing necessary to obtain 100% SSS coverage is dependent upon the effective range scale, achievable
positional accuracy, and any positioning errors inherent to a towed system. A good rule of thumb to obtain complete
coverage is to plan survey line spacing at 1.6 x Range Scale, allowing for an overlap of 40% of range scale (20%
of the total swath) between adjacent swaths. Note: Range Scale refers to the athwartships distance ensonified on
each side of the towfish. Thus, Range Scale equals one half of the total swath ensonified.

Generally, SSS range scale is chosen for maximum survey efficiency. The sonar should be maintained at an
altitude of 8 - 20% of range scale during acquisition; thus, water depth will determine an upper range scale limit
or a particular survey area. However, the hydrographer should also consider the system configuration and if a
minimum sonar depth will be necessary to avoid water column disturbances such as propeller wash. Based on
the chosen range scale’s corresponding ping rate, vessel speed should be adjusted to ensure that object detection
criteria are met (see section 2.5.2.1 ). If a specific range scale is required for a survey, it will be indicated in the
Project Instructions.


##### 2.5.3.1.3 Vertical Beam Echosounder (VBES)

Since complete coverage can not be efficiently completed using VBES alone, this will rarely be assigned as the
sole method for acquiring mainscheme survey data. Typically, VBES systems will be used to provide correlating
sounding data for SSS operations, define an inshore contour, or develop very shoal or foul areas where there is a
high probability of damaging either a MBES or SSS system.

If VBES has been assigned as a stand-alone mainscheme data acquisition method, the required line spacing will
be noted in the Project Instructions. If possible, VBES mainscheme data should be acquired by running lines
perpendicular to depth contours. This practice assists the hydrographer in accurately identifying contour intervals.
If extensive discrepancies are found between VBES sounding data and charted depths, the Chief of OPS or Chief
of NRB should be contacted to determine if a more extensive survey is warranted.


#### 2.5.3.2 Holidays

Holidays are defined as gaps in mainscheme data or areas where accuracy requirements have not been met.
Holidays may be caused by various events, such as vessel maneuvering, survey equipment problems, unexpected
shoals, or rejection of poor quality data during post-processing. Holiday line plans are typically developed to
address these data gaps as mainscheme acquisition progresses, rather than at the end of mainscheme operations.
This practice will minimize transit time required to revisit each area of the survey with a holiday and the time
required to acquire, process, and manage additional sound speed profiles. If the field unit uses a real-time coverage
map during mainscheme data acquisition, most holidays can be identified and addressed prior to ceasing operations
that day, thus increasing survey efficiency.


#### 2.5.3.3 Crosslines

Crossline data are used to identify any systematic data problems by comparing it to mainscheme data acquired at
different times, water levels, and line azimuths. Separate vessels may also be used for crossline data acquisition
to help identify any vessel to vessel system biases.

Ideally, crosslines should be acquired prior to mainscheme data, in areas of gently sloping bottom, and when water
levels are as close to survey datum (MLLW) as practicable. Crossline data may not agree well with mainscheme
soundings if acquired in areas of irregular submarine relief and/or if VBES systems are used. In rocky areas, large

*Page 59*

------------------------------------------------------------------------------------------------------------------------


depth differences may occur over small horizontal distances, making a small positioning error appear to be a large
depth error. This effect is often noted when using VBES systems due to the large beam footprint.


#### 2.5.3.4 Developments

A development is performed to either obtain a least depth over a known point feature or further define an area
based feature such as a shoal. Typically, dense MBES data are acquired for developments, although multiple
VBES lines may be more appropriate for defining very shoal area features due to the significant decrease of
MBES efficiency in such depths. If a VBES system is used to determine the least depth on a point feature, several
parallel lines should be run over the feature until the hydrographer is confident that the least depth is recorded. A
third method for determining a feature’s least depth is by diver investigation. The process of using a diver least
depth gauge is discussed in section 3.2.5 For additional information on feature investigation, refer to section 4.4.
Note: Conducting developments during high stages of tide will improve MBES efficiency and may also provide
increased vessel safety by maximizing underkeel clearance. If development lines are created to be run during a
specific tide range, the hydrographer must be certain to convey this information to the vessel crew that will be
acquiring the data.

When developing point features, least depths should be acquired using the center region of the MBES swath,
typically 45° or less off nadir. This section of the MBES swath will have less error due to refraction than the
outer beams. It is recommended that, during development acquisition, a confidence swath be run in an orthogonal
direction to the primary development lines. A common MBES development line plan may appear to be an
assortment of “H” or “+” patterns over numerous features.


### 2.5.4 Survey Polygon Planning

Most field units will be equipped with data acquisition software that allows the sonar operator and the coxswain
to view a real-time coverage DTM of the data being acquired. As an alternative to line planning, which is most
often redundant with this software capability, polygons that define areas to be covered are created by the sheet
manager. While the entire area could just be covered with a continuous line, polygons provide the hydrographer
with discreet sections to be covered assisting in better plans for survey timing and vessel efficiency. Most of the
guidance that applies to line plans also applies to polygon planning. The data should still be acquired with the boat
traveling parallel to the contours.

•	 Polygons should be planned such that the boat will be running offshore to nearshore. This is a safety tip!
Creating separate offshore and onshore polygons (those that can be run at any time vs. those that need a
specific tide window) is also helpful.

•	 Make polygons longer in the dimension the boat should run, providing a clear indication to the coxswain and
surveyor of the polygon’s directionality. (If running N to S will be most efficient with the contours, make your
polygon longer in the N to S dimension).

•	 If there is a MHW Buffer, a limit line that defines the shoal edge of the survey (survey to the 4 meter curve)
or a NALL established during shoreline verification, do not plan polygons inshore of these limits unless there
is a specific reason to do so.

•	 In a channel that could be filled in with one polygon (shore to shore), consider breaking it down into two
polygons such that there is a straight edge in the middle of the channel. This provides the vessel with a straight
baseline, and encourages running from offshore to nearshore.


*Page 60*

------------------------------------------------------------------------------------------------------------------------


•	 Set polygons up in such a way that turns are minimized and lines are of a manageable length for processing.
•	 Be aware of any possible sources of fresh water, or other factors that will affect the water column and make
smaller polygons in these areas.


#### 2.5.4.1 AWOIS Items

For all assigned AWOIS investigations, the entire search radius shall be investigated if possible, regardless
of its position relative to the survey limits. Specific investigation methods considered adequate for an item’s
disproval will be noted in the attributes of the placeholder AWOIS feature, CRANES. Often, AWOIS items can
be investigated in conjunction with mainscheme data acquisition.

Note: If the entire search radius is not investigated, it is nearly impossible to disprove an AWOIS item.

#### 2.5.4.2 Target Files

Target files refer to a collection of geographic positions designated for point data acquisition. These files are
typically created to designate specific positions for acquiring other types of data. For example, the hydrographer
may create a target file to show the specific position where a sound velocity profile is desired or specific locations
of items to be developed.


##### 2.5.4.2.1 Bottom Samples

Samples of bottom sediment throughout the survey area shall be obtained and analyzed in accordance with the
HSSD, if required by the Project Instructions. A bottom sample plan is compiled by the HSD Project Manager
and delivered to the field unit in the Project Reference File (PRF) using the S- 57 Object Class, ‘SPRING’. The
field unit should review the bottom sample plan to the survey data acquired (bathymetry and backscatter) to
determine if the bottom sample locations are appropriate. The survey data will often better differentiate varying
bottom characteristics within the survey compared to the bottom sample plan. The field unit should contact HSD
Operations Branch to discuss modifying the plan if needed.


#### 2.5.4.3 Special Circumstances


##### 2.5.4.3.1 Search Patterns

In emergency or accident situations, NOAA field units may be involved with wreck, obstruction, or debris searches.
When planning this type of operation, the direction of the search pattern should be oriented within 20° of the set of
any significant current present in the survey area. This arrangement will minimize towfish offset from the planned
tracks, increase position accuracy, and increase towfish stability by minimizing forces that are not aligned with the
longitudinal axis of the towfish. However, tracks run in the same direction as a very strong current may result in
an increased speed over ground, which could decrease object detection capabilities; thus, this parameter should be
monitored if searching for small objects. If strong currents exist in the area and running search tracks in a pattern
oriented normal to the current is unavoidable, the operations should be timed to coincide with periods of slack or
minimum current, if possible.


*Page 61*

------------------------------------------------------------------------------------------------------------------------



##### 2.5.4.3.2 Special Wreck Investigations

If a hydrographic field unit discovers a potentially significant historic wreck site, or conducts a special wreck
investigation through a contract from another NOAA program or a request from a NOAA Navigation Manager,
the field unit should make an effort to ensonify the wreck site and associated debris field with each type of sonar
system that is readily available. When conducting side scan sonar operations, run parallel tracks on either side
of the wreck, so that both sides are imaged, as well as two additional tracks orthogonal to the site. The imagery
and bathymetry data will provide clues to the wreck’s status and identity, identify any obstructions, and provide
researchers with an adequate baseline assessment with which to compare future surveys.


### 2.5.5 Survey Plan Finalization

Proposed survey acquisition plans should be reviewed by the FOO and/or Chief-of-Party and any necessary
adjustments made. Once approved by the Chief-of-Party, the plan should be converted from the format generated
by the GIS software used to design the plan to a format that can be read by the field unit’s survey navigation
software. Typically, acquisition plans will be designed using CARIS Notebook or Bathy DataBASE software
for polygon planning or MapInfo software for line planning. The MapInfo files are converted into a HYPACK
line file (*.lnw) or HYPACK target file (*.tgt) for vessel navigation. This specific conversion process can be
accomplished using the Hydro_MI.mbx MapBasic tool, which will also report the number and the total mileage
of the planned lines. Number and mileage statistics should be recorded and used to estimate the amount of time
required to complete the survey. These estimations are critical to overall project planning.


### 2.5.6 Preparing the Survey Crew

The Survey Manager will provide a boat sheet to the survey crew(s) with a plot depicting line plans, polygons,
and/or shoreline files overlaid on the largest scale chart with any uncharted hazards, lines planned for acquisition
during high tide or slack current, AWOIS items, contacts, and/or developments prior to each survey day.


*Page 62*

------------------------------------------------------------------------------------------------------------------------


