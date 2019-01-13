# DeepCure

** Problem Set for Interview **

![Build status](https://ci.appveyor.com/api/projects/status/jcp91fvbgmqws30p/branch/master?svg=true)
![Python 3.6](https://img.shields.io/badge/python-3.6-blue.svg)

<hr>

## Links
- Progress Tracker: [./docs/sources/CHANGELOG.md](./docs/sources/CHANGELOG.md)
- Error Log: [./docs/sources/ERRORLOG.md](./docs/sources/ERRORLOG.md)

## Section 1: Virtual Docking

**Background**: To improve the accuracy and consistency of current virtual docking algorithms,
we are developing DeepDockR, a machine learning powered docking platform. Achieving that
requires us to dock thousands of molecules into a target of interest and store all associated
scores and metadata in our database. While we have automated much of the docking pipeline,
a very important step is the choice and preparation of the structures to use for docking.

**Goal**: Evaluate the performance of a docking software in estimating the binding affinity of
compounds to Carbonic Anhydrase I, by comparing the virtual docking results to available
bioactivity data. The evaluation should comprise of regression and as well as ranking metrics.

### Protein Evaluation 

To tackle this goal we need to evaluate the protein in question. Protein's can exist in several different states but for evaluation of a docking software the user should pick a protein that is already in a docked state. Here we can determine what what exactly the pocket size looks like and how it interacts with a possible therapuetic inside of the protein. 
    
The problem asks for evaluation of docking for CA1, to initialize we are going to big an undocked ligand into the protein which stems from the x-ray structure 2CAB.  [2cab.pdb](http://www.rcsb.org/structure/2CAB) which has the zinc ion in the pocket of the protein in the protein docked state which can be the most unbiased x-ray structure and prove as the docked protein template.

![2cab Protein](./imgs/2cab_undocked_protein_2.png)

### Ligand Selection 

For our ligand selection we need enough chemical space to explore known inhitors, negative inhibitors, and possible positive inhibitors that match functional groups revelant to the known inhibitors. The ligands that I have chosen for this project are listed below. 

Known Inhibitors            |  Common Name
:-------------------------:|:-------------------------:
<img src="./imgs/2d_ligands/Methazolamide.png" width="300" height="250"/> |  Methazolamide
<img src="./imgs/2d_ligands/Polmacoxib.png" width="300" height="250"/>  |  Polmacoxib
<img src="./imgs/2d_ligands/(R)-Methocarbamol.png" width="300" height="250"/> |  (R)-Methocarbamol
<img src="./imgs/2d_ligands/(S)-Methocarbamol.png" width="300" height="250"/> |  (S)-Methocarbamol
<img src="./imgs/2d_ligands/Acetazolamide.png" width="300" height="250"/> |  Acetazolamide

Negative Inhibitors            |  Common Name
:-------------------------:|:-------------------------:
<img src="./imgs/2d_ligands/Terphenyl.png" width="300" height="250"/> |  Terphenyl
<img src="./imgs/2d_ligands/Triphenylbenzene.png" width="300" height="250"/>  |  Triphenylbenzene

Positive Inhibitors            |  Common Name
:-------------------------:|:-------------------------:
<img src="./imgs/2d_ligands/Adrafinil.png" width="300" height="250"/> |  Adrafinil
<img src="./imgs/2d_ligands/Bucetin.png" width="300" height="250"/>  |  Bucetin
<img src="./imgs/2d_ligands/Indol.png" width="300" height="250"/> |  Indol

