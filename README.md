# Scientific Computing – Docker Environment (AlmaLinux 9)

This repository contains the solutions for the *Scientific Computing* tasks.
All codes have been tested inside a clean **AlmaLinux 9** Docker container to guarantee
full reproducibility across different systems.

The Docker image installs all required compilers, libraries, and Python packages
needed to compile and run the tasks.

---

## Requirements

- Docker (Docker Desktop on Windows/macOS, or Docker Engine on Linux)

No other dependencies are required on the host system.

---

## Docker Image Overview

The custom Docker image is built on top of:

- `almalinux:9`

and includes:

- GCC / G++
- OpenMP (via GCC)
- OpenMPI
- GSL
- FFTW
- HDF5
- Python 3
- NumPy, SciPy, Matplotlib

---

## Building the Docker Image

From the root directory of this repository (where the `Dockerfile` is located):

```bash
docker build -t scicomp-alma9 .
```

Then run an interactive container and mount the repository directory:
```
docker run -it \
  --name scicomp_container \
  -v $(pwd):/work \
  scicomp-alma9
```

If you are working on Windows, using Powershell:
```
docker run -it `
  --name scicomp_container `
  -v ${PWD}:/work `
  scicomp-alma9
```
