Datasets
========

Goal of this page
-----------------

An overview of the datasets and links to further information about their naming and contents.

.. toctree::
   :maxdepth: 2
   :caption: Contents:


Collision data
--------------

The	collision data passing the CMS trigger selections (L1 & HLT) is organized in Primary Datasets (PD). All open data primary datasets can be found in http://opendata.cern.ch/search?page=1&size=20&type=Dataset&subtype=Collision&experiment=CMS

The PD definition is centered around physics objects (SingleMu, Jet, etc), and triggers	with similar physics use are mostly in the same PD. Besides requirements on the physics content, the organisation of the primary dataset has to satisfy constraints related to the data processing and handling, such as the average event rate approximately uniform across the different PDs, and the event rate more than 10 Hz and less than 200 Hz. Each CMS collision dataset comes with a brief description of the contents, and the full listing of all possible HLT trigger streams included in the dataset.

There an average overlap between the PDs of around 25% during Run1 and it must be taken into account when combining events from different datasets in an analysis.



Simulated data
--------------

Refs
G. Franzoni: Dataset definition for CMS operations and physics analyses
https://cds.cern.ch/record/1976679/files/CR2014_311.pdf
