## YBCO_MACE Potential

To use the `YBCO_ACE` potential, LAMMPS must be compiled with **pacemaker**: 

https://pacemaker.readthedocs.io/en/latest/

The results shown in the paper were obtained using the `output_potential.yace` model for LAMMPS, but we also include the `output_potential.yaml` for running ASE simulations.

To run a ACE simulation in LAMMPS, use the following input:

```
atom_style atomic

mass 1 137.327     # Ba
mass 2 63.546      # Cu
mass 3 15.999      # O
mass 4 88.90585    # Y

pair_style  pace
pair_coeff  * * output_potential.yace Ba Cu O Y

```

The training script for the `YBCO_ACE` model is provided (`ace_run.pbs`), and the training database is included as `ybco_ace.pkl.gz`. Energies are in eV, forces in eV/Å, and virial stress in eV.
