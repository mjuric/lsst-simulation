# LSST Simulation Issues
Repository to collect feedback/issues for the simulates SolSys Products DB.


# Release notes SSPDB version 0.1

The Solar System Products Data Base (SSPDB) contains a full density simulation of Solar System Object observations during year one of the Legacy Survey of Space and Time (LSST) to be conducted at the Vera C. Rubin Observatory. 
The aim of the SSPDB is to give the Solar System Science Collaboration (SSSC) a preview of what LSST data 
catalogs will look like. 
This first relase of the SSPDB is intended to serve as a testing ground during the LSST SSSC sprint 2020. Future updates of the SSSPDB will add fidelity and include additional data in order to provide as complete a mock catalog of LSST Solar System observations as possible.

## DB Realization:
The SSPDB is currently realized as a MySQL database with three tables:

* DIASource
* MPCORB
* noise

The DIASource table contains information on individual observations of Solar System Objects (SSOs).
The MPCORB table contains orbit data for the SSO input populations.
The noise table contains false detections for every exposure composed of Difference Image Artifacts (FD) and CCD Noise (NS)
 
Schemata have been implemented as discussed with the SSSC according to the following templates:
https://docs.google.com/document/d/1DmS35IkbfyIYYIIHAcQAsUoxIDRmk4BAgqX8d8upIK0

As of this moment several columns are empty or NULL. Those will be filled over the course of the upcoming SSPDB updates.

## SSO Input Populations: 
Synthetic Solar System Model (S3M, Grav et al. 2011) 


## Survey Simulation: 
Operations Simulation (OpSim) run Feature Based Scheduler version 1.5 @ 
http://astro-lsst-01.astro.washington.edu:8081/

## Observation Simulator: 
Naidu et al. (JPL) @
https://github.com/AsteroidSurveySimulator/objectsInField

### Settings/features

* N-body propagation (perturbers: planets + Pluto/Charon)

* Actual LSST camera footprint (instead of statistical fill factor)

* Trailing losses

* “Fading”/statistical detection cutoff

* All SSOs have spectral types: S, C according to (Ivesić et al. 2001). Colors and filter transformations were taked from Vereš & Chesley (2017).

* False detections: DIA & CCD noise (Jones et al. 2017, Vereš & Chesley 2017)


## Accessing SSPDB

SSSC Jupyter Hub @
https://sssc.dirac.institute

MySQL Database @  
db.dirac.institute (accessible from within JupyterHub only)

## References


