Forked from https://github.com/Edric-Matwiejew/weighted_maxcut

# Qiskit-Aer ROCm Build (Setonix)

Scripts to build a ROCm-enabled Qiskit-Aer wheel and install it in a Python 3.11 virtual environment on the Pawsey Setonix GPU cluster.

> **Note:** For runtime guidance on GPU acceleration see [GPU Simulation](https://qiskit.github.io/qiskit-aer/tutorials/1_aersimulator.html#GPU-Simulation). The steps there mention CUDA/NVIDIA, but they apply equally to this ROCm/AMD build.

## Quick Start

1. Python virtual environments contain a lot of files and will quickly reach the user limit for `$HOME` and `$MYSOFTWARE`. So, first:

```bash
cd $MYSCRATCH
```

1. Clone:

```bash
git clone https://github.com/JolyonJoyce/qiskit_aer_rocm.git
cd  qiskit_aer_rocm
```
2. Submit the build job:

```bash
salloc -N 1 --gpus=1 -p gpu-dev --account=${PAWSEY_PROJECT}-gpu \
bash use-qiskit-aer-rocm-setonix.sh
```

What the job does:

1. Loads the required Setonix modules.
2. If no virtual environment is already active, it creates (or re-uses) the target venv.
3. Clones Qiskit-Aer, builds a ROCm wheel, and installs it into that venv.
