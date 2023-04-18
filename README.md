# PPN_Database_Constructione
Database and machine learning scripts used for the following work:

"Large-Scale Construction and Analysis of Amorphous Porous Polymer Network Materials" [Link to be updated]()  

<br/>

* **database**

  * database folder contains all generated PPN structures and their momnomers 
  * 'monomers.tar.gz' contains all generated PPN momnomers in xyz file format 
  * 'structures.tar.gz' contains structures after self-assembly simulation in cif file format
  * 'property.csv' contains calculated pore volume and surface area of amorphous PPNs in database
  * More details about database construction could be found in original paper
    
* **scripts**

  * scripts folder contains MOF-NET library, machine learning model used in the work, and a script for data processing and machine learning prediction (ML_prediction.ipynb).
  * MOF-NET is machine learning library desinged for predicting the adsorption capacity of MOFs. [ACS Appl. Mater. Interfaces 2021, 13, 20, 23647–23654](https://doi.org/10.1021/acsami.1c02471)
  * The first part of 'ML_prediction.ipynb'contains the contents of extracting working capacity from the data ('cycle_tot.txt'), and the later part contains the contents of predicting the hydrogen working capacity using machine learning model. 
