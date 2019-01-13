### Docking Ligands with proteins

Docking with Chimera and Autodock Vina is relatively simple. 

#### Protein Preparation

For Preparation of the protein. Download the protein or fetch by the PDB ID 2cab, link is provided in the README.md file. 

- Select the protein to prep with these parameters

![Select Protein](../../imgs/Autodock_Instructions/select_protein.png)

- Add Hydrogens for the Dock Prep

![Add Hydrogens](../../imgs/Autodock_Instructions/add_hydrogens.png)

- Assign charges for the protein

![Assign Charges](../../imgs/Autodock_Instructions/assign_charges.png)

- Specify the Net Charges

![Specify Net Charges](../../imgs/Autodock_Instructions/specify_net_charge.png)

- Save the File

![Save File](../../imgs/Autodock_Instructions/save_file.png)


#### Ligand Preparation

Since the files from ZINC are already minimized Mol2 Files the ligand is pre prepped for docking. We can use them out of the box from the download of the ZINC Database. 

#### Running Docking Simulation 

- Load both the dock prepped ligand and also the mol2 file. Select the Autodock Vina

![AutoDock Vina](../../imgs/Autodock_Instructions/select_autodock.png)

- Select both the protein and the ligand and the output file

- Add in the Docking Parameters as shown and move to the search parameters

![Docking parameters](../../imgs/Autodock_Instructions/dock_prep_params.png)

- Add in the Docking Search

![Docking Search](../../imgs/Autodock_Instructions/dock_prep_search.png)

- Click Okay and run the simulation. 
