# Structural Modeling Benchmark

This repository provides a benchmark for structural modeling platforms using DockQ as ground truth. The workflow is managed via [OmniBenchmark](https://github.com/omnibenchmark/omnibenchmark).  
The pipeline was run with Miniforge3.

## Quickstart

Follow these steps to set up the environment and run the benchmark:

### 1. Download OmniBenchmark Environment File

```bash
curl -sSL https://raw.githubusercontent.com/omnibenchmark/omnibenchmark/main/omni-environment.yml -o omni-environment.yml
```

### 2. Create and Activate Conda Environment

```bash
conda create -n omnibenchmark python=3.12 -y
conda activate omnibenchmark
conda env update -f omni-environment.yml
```

### 3. Clone the Repository and Run the Benchmark

#### Clone the repository

```bash
git clone https://github.com/omnibenchmark/omnibenchmark_modeling.git
cd omnibenchmark_modeling
```

#### Dry Run (Preview Steps)

```bash
ob run benchmark -b modeling_conda.yml --dry-run --local-storage
```

#### Actual Run (Single Core)

```bash
ob run benchmark -b modeling_conda.yml --cores 1 --local-storage
```

## Files

- `modeling_conda.yml`: Benchmark specification file.
- `omni-environment.yml`: OmniBenchmark environment dependencies.

## Input

- `Generated Models:` Models can be provided in several ways:
  - From a GitHub repository (e.g., [short_peptide_modeling_benchmark](https://github.com/pszgaspar/short_peptide_modeling_benchmark)), typically within a `models` folder.
  - From a local directory, where each subdirectory corresponds to a different model name.
  - Update the `--input_path` argument in the YAML configuration file to specify the correct source.
- `native_metadata.csv`: A CSV file containing metadata for native structures, including model IDs, chain identifiers, and PDB IDs.
- `data/`: Example local input folder structure containing

## Notes

- It is recommended to have [Miniforge](https://github.com/conda-forge/miniforge) installed for managing environments.
- The benchmark runs locally and requires the specified Conda environments.
- For more details, see the [OmniBenchmark documentation](https://github.com/omnibenchmark/omnibenchmark)