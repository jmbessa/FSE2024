# Effect of Feature Subset Selection on Samplings (Artifact)

In this repository, we provide general instructions on how to reproduce the results of the paper "Effect of Feature Subset Selection on Samplings" and reuse our datasets of measurements.

## Overview

![Overview](link)

## Dataset Details

There are three main resources we will detail:

### 1) Feature Model (folder [model](model/))

There are four feature models available in the .xml format.
They are BerkeleyDB, Hipacc_red, VariabilityModel, and VariabilityModelSampling.

The XML Schema represents the metamodel of the feature modeling notation in a tree format structure.
An XML-based representation contains (1) binary options (represented as *\<binaryOptions\>*) and (2) numeric options (represented as *\<numericOptions\>*).

- The tag *\<parent\>* indicates which is the parent feature (aka. configuration option).

- Binary and numeric options contain information on whether this option is optional or mandatory by the tag *\<optional\>*. 
The optional tag is set to true when it is optional, and false otherwise.
  
- To represent alternative exclusive options, both binary and numeric options contain information about implied or (and) excluded configuration options. 
They use the tag *\<excludedOptions\>* that indicates all options that exclude a given option.
And, the tag *\<impliedOptions\>* for all options that imply the selection of a given option.

- Nodes that describe numeric options contain information about min and max values, as well as the step function for the value between min and max.

Beyond the tree format structure, there are the cross-tree constraints (represented as *\<booleanConstraints\>* and *<\nonBooleanConstraints\>*).
Both constraints can either be a logical expression or a mathematical expression, respectively.


### 2) Configuration samples (folder [sample](sample/))

The folder [sample](sample/) contains one folder for each system used in the study and these folders contains .csv files that represent represents a different sampling technique.

These files contain the results that have been measured on a system from a configuration of selected characteristics.

The first row of the file contains the feature names, and the following rows contain the value 1 in case the feature is selected, and the value 0 otherwise.
These sampling files are used to label the non-functional properties.

