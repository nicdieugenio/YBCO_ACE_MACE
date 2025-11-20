# YBCO_ACE_MACE
Machine-Learned Interatomic Potentials for YBCO, trained using ACE and MACE. All potentials have been trained on the same DFT data from CP2K. The DFT input file used to collect the training data is included as `CP2K_input`. All simulations were performed with CP2K version 2024.1.

In order to clone the repository, git lfs needs to be installed:

```
git lfs install

```
Then clone the repository with `git clone https://github.com/nicdieugenio/YBCO_ACE_MACE.git`. In order to utilise the potentials in LAMMPS, you must compile LAMMPS for use with ACE/MACE. 

Instructions on how to compile ACE with the **pacemaker** can be found for both CPU and GPU at: https://pacemaker.readthedocs.io/en/latest/pacemaker/quickstart/

Instructions on how to compile MACE with the **pair_symmetrix** package can be found for both CPU and GPU at: https://github.com/wcwitt/symmetrix/blob/main/pair_symmetrix/README.md

Overall, we recommend that smaller-scale studies focused on thermodynamic properties on non-stochiometric YBCO employ the `YBCO_MACE` potential, given its higher accuracy. For larger-scale simulations, `YBCO_ACE` gives adequate balance between accuracy and efficiency, given its greater speed.

