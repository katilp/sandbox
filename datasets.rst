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

The collision data passing the CMS trigger selections (L1 & HLT) is organized in primary datasets (PD). All open data primary datasets can be found in 
http://opendata.cern.ch/search?page=1&size=20&type=Dataset&subtype=Collision&experiment=CMS

The primary dataset definition is centered around physics objects (SingleMu, Jet, etc), and events triggered by HLT triggers with a similar physics use are mostly directed in the same PD. http://opendata.cern.ch/docs/cms-guide-trigger-system gives an overview of the CMS trigger system. Besides requirements on the physics content, the organisation of the primary datasets has to satisfy constraints related to the data processing and handling, such as the average event rate approximately uniform across the different PDs, and the event rate more than 10 Hz and less than 200 Hz. (relevant?)

One year of data taking is divided in several "eras" indicated as RunA, RunB, etc. According to the CMS data policy, 50% of data is published after the embargo period, completed with the full release within 10 years.

Each CMS collision dataset comes with a brief description of the contents, and the full listing of all possible HLT trigger streams included in the dataset. The instructions how to find the exact definitions and parameters of the HLT trigger definitions can be found in http://opendata.cern.ch/docs/cms-guide-trigger-system under "HLT Trigger Path definitions". 

Since a given event can pass more than one HLT path, it can be included in more than one primary dataset. There's an overall overlap between the PDs of around 25-35% during Run1 and it must be taken into account when combining events from different datasets in an analysis.

Integrated luminosity here or in a separate chapter?

Refs
G. Franzoni: Dataset definition for CMS operations and physics analyses
https://cds.cern.ch/record/1976679/files/CR2014_311.pdf


Simulated data
--------------


