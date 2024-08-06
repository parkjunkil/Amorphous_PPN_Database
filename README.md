# Amorphous PPN Database Construction
[[`Paper`](To be uploaded)]
[[`Project Page`](https://parkjunkil.github.io/Amorphous_PPN_Database/)]

Database and machine learning scripts used for the following work:

"Large-Scale Construction and Analysis of Amorphous Porous Polymer Network Materials"  

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

  * We recommend to build a [`conda`](https://www.anaconda.com/products/distribution) environment. Please activate the environment while running the scripts.
    (You might need to specify a version of `torch` depending on your GPU driver.)
     ```
     conda create -n PPN python=3.9 -y && conda activate PPN
     pip install pandas matplotlib torch scikit-learn skorch numpy==1.23.0 schnetpack==1.0.0
     ```
  * Download machine learning inputs as follow:
    
     ```
     # Download chemical descriptors
     wget https://figshare.com/ndownloader/files/48176662 -O ML_Scripts/mordred_descriptors.csv
     
     # Download molecular fingerprints
     wget https://figshare.com/ndownloader/files/48176656 -O ML_Scripts/ECFP_fingerprint.csv

     # Download schnet inputs
     wget https://figshare.com/ndownloader/files/48176659 -O ML_Scripts/schnet_input_new.xyz
     

  * 'Random_Forest.ipynb' contains scripts for RF, using chemical descriptor as an input. Descriptor used in this work was obtained using [`mordred`](https://github.com/mordred-descriptor/mordred) python library.
    
  * 'DNN.ipynb' contains scripts for DNN model, using molecular fingerprint as an input. Among various fingerprints, ECFP was selected for this work.
    
  * 'Schnet.ipynb' contains scripts for SchNet model, which is one of the most well-known graph-based models.

  * Various methods have been utilized during data-processing and model training. More details can be found in each script and in the original paper. 
