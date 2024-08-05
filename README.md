# Amorphous PPN Database Construction
Database and machine learning scripts used for the following work:

"Large-Scale Construction and Analysis of Amorphous Porous Polymer Network Materials" [Link to be updated]()  

![image](https://github.com/parkjunkil/PPN_Database/assets/88761984/0584bce0-6e0b-4eaa-a4c1-c30c896edf96)


<br/>

# Database
  * The Database can be downloaded in a following manner.
    
  ```
  mkdir Database  # skip if there already exists

  # Download Amorphous PPN structures
  wget https://figshare.com/ndownloader/files/48171718 -O Database/structures.tar.gz
  
  # Download PPN monomers (Optional)
  wget https://figshare.com/ndownloader/files/48171715 -O Database/monomers.tar.gz
  ```

  * 'structures.tar.gz' contains structures after self-assembly simulation in .cif file format.
  * 'monomers.tar.gz' contains all generated PPN momnomers in .xyz file format.

  * We provide extracted chemical descriptors, molecular fingerprints and SchNet input in the ML_Scripts folder. Therefore, if you only want to run the ML training scripts, you don't need to download the database.

  * More details about database construction could be found in the original paper.
 
    
    
# ML_Scripts

  * This folder contains scripts for machine learning training in juypter notebook format. We used information of monomers as an input to predict surface area of amorphous PPNs. We tested three different input representations: descriptor, fingerprint, and graph
  * We recommend to build a [`conda`](https://www.anaconda.com/products/distribution) environment. You might need to specify a version of `torch` depending on your GPU driver.
  ```
  conda create -n PPN python=3.9 -y && conda activate PPN
  pip install pandas matplotlib torch scikit-learn skorch numpy==1.23.0 schnetpack==1.0.0
  ```

  * 'descriptor' folder contians scripts for RF, LGBM and MLP model using molecular descriptor as an input. Descriptor used in this work was obtained using mordred python library.
  * 'fingerprint' folder contians scripts for MLP model using fingerprint as an input. Among various fingerprints, ECFP was selected for this work.
  * 'graph' folder contians scripts for schnet model, which is one of the most well-known graph based models.
