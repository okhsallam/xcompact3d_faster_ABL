# Installation Steps for XCompact3d on TAMU Faster HPC

```bash
# 1. Login to Faster
ssh NetID@faster.hprc.tamu.edu

# 2. Create and enter directory
cd $HOME
mkdir xcompact3d && cd xcompact3d

# 3. Load required modules
module purge
module load GCCcore/11.3.0
module load CMake/3.29.3
module load gompi/2023a

# 4. Clone the repository
git clone https://github.com/xcompact3d/Incompact3d
cd Incompact3d

# 5. Set Fortran compiler
export FC=mpif90

# 6. Configure and build
cmake -S . -B build
cmake --build build -j 8

# The executable will be in build/bin/xcompact3d
```

Notes:
- Make sure to replace 'NetID' with your TAMU NetID
- The build process might take a few minutes
- Successful build will create executable at `build/bin/xcompact3d`
- For running tests, you'll need Python with NumPy installed


-------------

# XCompact3d Installation Guide for NREL Kestrel HPC

This guide provides step-by-step instructions for installing XCompact3d on the NREL Kestrel HPC system.

## Prerequisites
- Access to NREL Kestrel HPC system
- Basic knowledge of terminal commands
- Your Kestrel username and credentials

## Installation Steps

### 1. Login to Kestrel
```bash
ssh username@kestrel.hpc.nrel.gov
```
Replace `username` with your Kestrel username.

### 2. Create Installation Directory
```bash
cd $HOME
mkdir xcompact3d && cd xcompact3d
```

### 3. Load Required Modules
```bash
# Clear any previously loaded modules
module purge

# Load required modules in this specific order
module load intel-oneapi-compilers
module load intel-oneapi-mpi
module load intel-oneapi-mkl
module load cmake
```

### 4. Clone the Repository
```bash
git clone https://github.com/xcompact3d/Incompact3d
cd Incompact3d
```

### 5. Configure and Build
```bash
# Set the Fortran compiler
export FC=mpiifort

# Configure the build
cmake -S . -B build

# Build using 8 cores (adjust number as needed)
cmake --build build -j 8
```

### 6. Verify Installation
After successful compilation, the executable should be located at:
```bash
ls -l build/bin/xcompact3d
```


## Module Requirements
- intel-oneapi-compilers
- intel-oneapi-mpi
- intel-oneapi-mkl
- cmake



## Version Information
- Guide created for XCompact3d (latest version as of March 2024)
- Tested on NREL Kestrel HPC

