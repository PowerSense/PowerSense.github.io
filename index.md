---
layout: default
---

# PowerSense

PowerSense is a virtual lab for the development of [`Powersense.jl`](https://github.com/PowerSense/Powersense.jl), which is an open-source Julia package of tools at the cross-section of Power System Operations, Applied Mathematics, High-Performance Computations, and Machine-Learning.  

## Installation
```julia
import Pkg
Pkg.add("Powersense")
```

## Bug reports

Please report any issues via the Github [issue tracker]. All types of issues
are welcome and encouraged; this includes bug reports, documentation typos,
feature requests, etc.

[issue tracker]: https://github.com/PowerSense/Powersense.jl/issues

Here are the descriptions of the different features of the package.

# Nonlinear Programming (NLP)
The package implements active set methods for continuous nonlinear optimization. The package currently implements sequential linear programming methods.

<!-- # Power Flow Analysis
The package implements power flow analysis for a transmission system. The tool also implements an interference for OpenDSS. -->

# Optimal Power Flow
The package implements specialized algorithms for solving alternating current optimal power flow (ACOPF). The package has the following seven formulations implemented. 
1. Power Branch-Flow Rectangular Admittance Polar Voltage (PBRAPV):
2. Power Branch-Flow Rectangular Admittance Rectangular Voltage (PBRARV):
3. Current Branch-Flow Rectangular Admittance Rectangular Voltage (CBRARV):
4. Current Branch-Flow Rectangular Admittance W-matrix Voltage (CBRAWV):
5. Power Nodal-Injection Polar Admittance Polar Voltage (PNPAPV):
6. Power Nodal-Injection Rectangular Admittance Polar Voltage (PNRAPV):
7. Power Nodal-Injection Rectangular Admittance Rectangular Voltage (PNRARV):







