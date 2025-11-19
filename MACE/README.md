## YBCO_MACE Potential

To use the `YBCO_MACE` potential, LAMMPS must be compiled with the **symmetrix** package: 

https://github.com/wcwitt/symmetrix

The results shown in the paper were obtained using the `ybco_mace-8-29-39-56.json` model, but we also include the stage-two model (`ybco_mace_stagetwo-8-29-39-56.json`) for completeness.

To run a MACE simulation in LAMMPS, use the following input:

```
atom_style atomic
atom_modify map yes
newton on

mass 1 137.327     # Ba
mass 2 63.546      # Cu
mass 3 15.999      # O
mass 4 88.90585    # Y

pair_style symmetrix/mace
pair_coeff * * ybco_mace-8-29-39-56.json Ba Cu O Y

```

The training script for the `YBCO_MACE` model is provided (`mace_run.pbs`), and the training database is included as `ybco_mace.xyz`. Energies are in eV, forces in eV/Å, and virial stress in eV. If you were to add any configurations, remember to add a key in the header section to energies, forces and stress (here, `REF_`), as MACE does not recognize them otherwise.


