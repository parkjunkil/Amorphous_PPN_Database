# Amorphous PPN Database Construction
Database and machine learning scripts used for the following work:

"Large-Scale Construction and Analysis of Amorphous Porous Polymer Network Materials" [Link to be updated]()  

![image](https://github.com/parkjunkil/PPN_Database/assets/88761984/0584bce0-6e0b-4eaa-a4c1-c30c896edf96)


<br/>

* **Database**

  * This folder contains all generated PPN structures and their corresponding momnomers.
  ```
  mkdir Database  # skip if there already exists

  ## Download Amorphous PPN structures
  wget https://figshare.com/ndownloader/files/48171718 -O Database/structures.tar.gz
  
  ## Download PPN monomers (Optional)
  wget https://figshare.com/ndownloader/files/48171715 -O Database/monomers.tar.gz
  ```

  * 'structures.tar.gz' contains structures after self-assembly simulation in .cif file format.
  * 'monomers.tar.gz' contains all generated PPN momnomers in .xyz file format. 
  * More details about database construction could be found in the original paper.
    
* **ML_Scripts**

  * This folder contains scripts for machine learning prediction in juypter notebook file format. We used information of monomers as an input to predict surface area of amorphous PPNs. We tested three different input representations: descriptor, fingerprint, and graph
  * 'descriptor' folder contians scripts for RF, LGBM and MLP model using molecular descriptor as an input. Descriptor used in this work was obtained using mordred python library.
  * 'fingerprint' folder contians scripts for MLP model using fingerprint as an input. Among various fingerprints, ECFP was selected for this work.
  * 'graph' folder contians scripts for schnet model, which is one of the most well-known graph based models.
