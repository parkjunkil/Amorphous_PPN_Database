# PPN_Database_Construction
Database and machine learning scripts used for the following work:

"Large-Scale Construction and Analysis of Amorphous Porous Polymer Network Materials" [Link to be updated]()  

![image](https://github.com/parkjunkil/PPN_Database/assets/88761984/0584bce0-6e0b-4eaa-a4c1-c30c896edf96)


<br/>

* **database**

  * This folder contains all generated PPN structures and their corresponding momnomers. 
  * 'monomers.tar.gz' contains all generated PPN momnomers in .xyz file format. 
  * 'structures.tar.gz' contains structures after self-assembly simulation in .cif file format.
  * 'property.csv' contains calculated pore volume and surface area of amorphous PPNs in the database.
  * More details about database construction could be found in the original paper.
    
* **scripts**

  * This folder contains scripts for machine learning prediction in juypter notebook file format. We used information of monomers as an input to predict surface area of amorphous PPNs. We tested three different input representations: descriptor, fingerprint, and graph
  * 'descriptor' folder contians scripts for RF, LGBM and MLP model using molecular descriptor as an input. Descriptor used in this work was obtained using mordred python library.
  * 'fingerprint' folder contians scripts for MLP model using fingerprint as an input. Among various fingerprints, ECFP was selected for this work.
  * 'graph' folder contians scripts for schnet model, which is one of the most well-known graph based models.
