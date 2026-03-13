## Installation differences compared to acados
For using acados with linked MuJoCo dynamics, first clone this repo and the submodules of acados:
```bash
git clone https://github.com/AIMotionLab-SZTAKI/acados-mujoco-zoro.git
cd acados-mujoco-zoro
git submodule update --recursive --init
```

Install acados:
```bash
mkdir -p build
cd build
cmake -DCMAKE_POLICY_VERSION_MINIMUM=3.5 ..
make install -j4
```

Then, and most importantly, put the MuJoCo binaries into the include directory of acados, with
```bash
wget https://github.com/google-deepmind/mujoco/releases/download/3.2.4/mujoco-3.2.4-linux-x86_64.tar.gz
tar -xf mujoco-3.2.4-linux-x86_64.tar.gz -C /path/to/acados-mujoco-zoro/include
```
Finally, if you use the python interface, export the MuJoCo path as well:
```bash
export LD_LIBRARY_PATH=$LD_LIBRARY_PATH:"<acados_root>/lib:<acados_root>/include/mujoco-3.2.4"
export ACADOS_SOURCE_DIR="<acados_root>"
```

<!-- # acados -->

![](docs/_static/acados_logo.png)
<!-- [![Travis Status](https://secure.travis-ci.org/acados/acados.png?branch=master)](http://travis-ci.org/acados/acados) -->
[![Appveyor status](https://ci.appveyor.com/api/projects/status/q0b2nohk476u5clg?svg=true)](https://ci.appveyor.com/project/roversch/acados)
![Github actions full build workflow](https://github.com/acados/acados/actions/workflows/full_build.yml/badge.svg)
<!-- [![codecov](https://codecov.io/gh/acados/acados/branch/master/graph/badge.svg)](https://codecov.io/gh/acados/acados) -->

`acados` provides fast and embedded solvers for nonlinear optimal control.
It is written in `C` and offers interfaces to the programming languages `Python`, `MATLAB` and `Octave`.

## General
- `acados` implements
  1. fast SQP-type solvers for Nonlinear Programming (NLP) formulations with an Optimal Control Problem (OCP) structure
  2. efficient integration methods, also called *integrators*, to solve initial value problems with dynamic systems given as an ODE or index-1 DAE.
  These integrators can efficiently compute first and second-order sensitivities of the results.

## Documentation
- Documentation can be found on [docs.acados.org](https://docs.acados.org/)
- An overview of the interfaces can be found at [docs.acados.org/interfaces](https://docs.acados.org/interfaces)

## Forum
- If you have any `acados`-related questions, feel free to post on our forum at [discourse.acados.org](https://discourse.acados.org/)

## Citing
- References can be found at [docs.acados.org/citing](https://docs.acados.org/citing)

## Installation
- Instructions can be found at
[docs.acados.org/installation](https://docs.acados.org/installation)
