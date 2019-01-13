# DeepCure

** Problem Set for Interview **

![Build status](https://ci.appveyor.com/api/projects/status/jcp91fvbgmqws30p/branch/master?svg=true)
![Python 3.6](https://img.shields.io/badge/python-3.6-blue.svg)

<hr>

## Links
- Progress Tracker: [./docs/sources/CHANGELOG.md](./docs/sources/CHANGELOG.md)

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

Alternatively for evaluation of a docking software we can also remove a docked ligand from a protein and dock it again to the same protein. The drawbacks would be several 
- Ligands could induce a minor flexibility in the protein in the docked state and would be biased towards the ligand if reused 
- Time consumption would be drastic in terms of short-term docking where we would need to evaluate each ligand per protein in their docked states. Since the problem is asking for a minimum of 10 ligands it would scale linearly (also since it is not automated we run into the burnout of the user). 
    
This served as my impetus for selecting [2cab.pdb](http://www.rcsb.org/structure/2CAB) which has the zinc ion in the pocket of the protein in the protein docked state which can be the most unbiased x-ray structure and prove as the docked protein template.

![2cab Protein](./imgs/2cab_undocked_protein_2.png)

### Ligand Selection 


