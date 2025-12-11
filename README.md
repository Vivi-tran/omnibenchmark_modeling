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

## Notes

- Make sure you have [Conda](https://docs.conda.io/en/latest/) installed.
- The benchmark runs locally and requires the specified Conda environments.
- For more details, see the [OmniBenchmark documentation](https://github.com/omnibenchmark/omnibenchmark)