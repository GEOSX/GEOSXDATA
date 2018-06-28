# GEOSXDATA

_Repository for large datasets to be kept out of the main GEOSX repository._

In order to keep the size and history of the GEOSX repository manageable, larger input datasets should be kept separate from the main repository.  A good use case is the [SPE Comparative Solution Project](http://www.spe.org/web/csp/index.html), which provides a few well defined input datasets and problem descriptions.  These benchmark problems are widely used for testing reservoir simulation algorithms, but the provided porosity and permeability files are quite large.  We want to avoid keeping large files like this in the main GEOSX repository.  

Instead, example simulations could be organized as follows:

```
GEOSX/
  examples/
     spe10_model1_example/
        description.rst
        model1.xml
     spe10_model2_example/
        description.rst
        model2.xml 
        
GEOSXDATA/
   data/
     spe10/
       set1/
         description.rst
         permeability.dat
       set2/
         description.rst
         permeability.dat
         porosity.dat
```

Here, the user has created two example problems (model1.xml and model2.xml) in the main GEOSX repository, as well as some documentation describing the test problems.  The .xml files then point to large porosity and permeability datasets kept in GEOSXDATA.  These files have their own documentation describing the .dat file format.

This strategy keeps the parameter files small.  It also means that we can create multiple test problems for a given dataset, all pointing to one common data location.  Here, we have focused on property data, but other types of data (like large mesh files or comparison monitoring data) can go here as well.

# FILE FORMATS #

Often, data will be received in a raw format that cannot be directly used by GEOSX.  In this case, we will often preprocess the data with a script to convert it to a usable format.  In this situation, we recommend committing both the original and processed data files to GEOSXDATA, with a description of the data provenance and processing that was done to it.  If the conversion script is generically useful, it should be added to the scripts directory in GEOSX.  A single-purpose script can be kept with the datasets in their GEOSXDATA directory.  Regardless, enough documentation should be provided to clearly identify the data source and reproduce any processing that was done to it.
  
