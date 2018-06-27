# GEOSXDATA

_Repository for large datasets to be kept out of main GEOSX repository._

In order to keep the size and history of the GEOSX repository manageable, larger input datasets should be kept separate from the main repository.  An example use case is the SPE10 benchmarks.  The SPE10 porosity and permeability fields are widely used for testing reservoir simulation algorithms, but the data files are quite large.  We want to avoid keep large files like this in the main GEOSX repository.  

Instead, an example simulation could be setup as follows:

```
GEOSX/
  Examples/
     SPE10Model2/
        parameters.xml 
        documentation.rst
        
GEOSXDATA/
   SPE10Model2Data/
     spe10_model2_porosity.dat
     spe10_model2_permeability.dat
     documentation.rst
```

Here, the user has created an example problem (parameters.xml) in the main GEOSX repository, as well as some documentation describing the test problem.  The .xml file then points to large porosity and permeability datasets kept in GEOSXDATA.  These files have their own documentation describing the .dat file format. 

This strategy keeps the example problem files small and specific.  It also means that we can create multiple test problems using the SPE10 fields, all pointing to one common data location.
