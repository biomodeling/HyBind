# HyBind

HyBind calculates a residue-level score for the solvent-exposed surface of a protein from a PDB structure. The Jupyter notebook uses solvent-accessible surface area (SASA), residue hydrophobicity, and spatial distributions of surface residues to compare local hydrophobicity patterns against two reference distributions.

## Files

- `HyBind_calculator.ipynb` — notebook implementing the calculation.
- `1A0G_A.pdb` — example PDB structure.

## Requirements

- Python 3
- Jupyter Notebook or JupyterLab
- `biopython`, `numpy`, `pandas`, `tqdm`

Install the Python dependencies with:

```bash
pip install biopython numpy pandas tqdm jupyterlab
```

## Usage

1. Open `HyBind_calculator.ipynb` in Jupyter.
2. In the first cell, set `pdb_filepath` to the input PDB path (for example, `1A0G_A.pdb`).
3. Set `csv_filepath` to the desired output CSV path (for example, `HyBind_results.csv`).
4. Run the notebook cells in order.

The CSV contains the residue index, residue name, SASA, and calculated HyBind score. Residues with zero SASA retain a missing (`NaN`) HyBind value.

**Input note:** A single-chain PDB is recommended. If a multi-chain PDB is supplied, the notebook treats all chains as one protein for the calculation.
