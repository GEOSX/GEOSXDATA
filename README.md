# GEOSXDATA

_Repository for large datasets to be kept out of main GEOSX repository._

In order to keep the size and history of the GEOSX repository manageable, larger input datasets should be kept separate from the main repository.  A good use case is the [SPE Comparative Solution Project](http://www.spe.org/web/csp/index.html), which provides a few well defined input datasets and problem descriptions.  These benchmark problems are widely used for testing reservoir simulation algorithms, but the provided porosity and permeability files are quite large.  We want to avoid keeping large files like this in the main GEOSX repository.  

Instead, example simulations could be organized as follows:

```
GEOSX/
  examples/
     spe10_model1_example/
        model1.xml
        description.rst
     spe10_model2_example/
        model2.xml 
        description.rst
        
GEOSXDATA/
   data/
     spe10/
       set1/
         permeability.dat
         description.rst
       set2/
         porosity.dat
         permeability.dat
         description.rst
```

Here, the user has created two example problems (model1.xml and model2.xml) in the main GEOSX repository, as well as some documentation describing the test problems.  The .xml files then point to large porosity and permeability datasets kept in GEOSXDATA.  These files have their own documentation describing the .dat file format.

This strategy keeps the parameter files small.  It also means that we can create multiple test problems for a given dataset, all pointing to one common data location.  Here, we have focused on property data, but other types of data (like large mesh files or comparison monitoring data) can go here as well.

