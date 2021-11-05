---
layout: supplementary_page
title: FACTS Devices
description: PowerSense.io
---

<script id="MathJax-script" async src="https://powersense.github.io/mathjax/tex-chtml.js"></script>


# FACTS Devices

Flexible AC transmission system (FACTS) devices are power electronic network controllers with capabilities of adjusting a variety of power system parameters. They are, thus, deployed for a wide range of applications. FACTS technology is key to enhance the efficiency, controllability, and stability of the existing power grid. When the available transfer capability (ATC) of power system is limited and an upgrade is needed to relieve congestion, installation of FACTS devices provides a more efficient alternative to the lengthy and expensive process of new transmission line construction. Moreover, FACTS technology is an important approach to facilitating the power grid to accommodate the increasing renewable generation penetration. Currently, the United States has an ambitious goal of completely eliminating carbon emissions from its power grid by 2035. With power flow control and voltage control capabilities, FACTS devices, such as the thyristor controlled series compensator (TCSC) and the static VAR compensator (SVC), have been shown to be beneficial in enhancing the utilization of renewable generation.

## Shunt FACTS devices

Among the various types of FACTS devices, shunt devices, including SVCs and STATCOMs, are widely deployed for voltage support and reactive power compensation. They provide an important approach for enhancing voltage stability and improving power quality. Furthermore, shunt FACTS devices are applied to help power systems accommodate growing renewable energy penetration. SVC and STATCOM devices provide dynamic voltage control capabilities that can help alleviate the impact of large-scale wind farm integration on voltage stability.

<p align="center">
<img src="https://powersense.github.io//assets//opf//ShuntFACTS.png" width="300" alt="Shunt FACTS Model">
</p>

In the above figure (a) presents a typical configuration of the SVC, which consists of a fixed capacitor and a thyristor controlled reactor (TCR). Based on this structure, an SVC can be modeled as a variable shunt susceptance. This model is a commonly used representation of SVC devices in optimal power flow. The variable shunt susceptance model of the SVC is shown in (b).

The variable shunt susceptance at bus $$i$$, $$b_{i}^{\mathrm{SVC}}$$, is subject to the bounds defined in the following constraint: 
$$ b^{\mathrm{min}} \leq b_{i}^{\mathrm{SVC}} \leq b^{\mathrm{max}} $$

The reactive power compensation $$Q_{i}^{\mathrm{SVC}}$$ can be calculated based on the voltage model used in the ACOPF formulations and added as an injection source to the reactive power nodal balance equations. For polar voltages the $$Q_{i}^{\mathrm{SVC}}$$ can be calculated as:

$$ Q_{i}^{\mathrm{SVC}}=b_{i}^{\mathrm{SVC}} \cdot V_{i}^{2} $$

where $$V_{i}$$ is the nodal voltage of bus $$i$$. 

In the [`Powersense.jl`](https://github.com/PowerSense/Powersense.jl) package, shunt FACTS devices are operated by `FACTS_bShunt` flag. For instance, in optimal power flow it can be activated as shown in the following example.

```julia
# Load packages
using Powersense, Ipopt

# Build Powersense Data model. Path is the address to where PSSE or MATPOWER file types
Data = create_PowersenseData(path)

run_opf!(Data, 
         FACTS_bShunt = true,
         solver = Ipopt.Optimizer, 
         formulation = PNPAPVmodel
         );
```
The package assumes the shunt FACTS devices to be a continious variable.

More details comming soon ...

---

If you find this work useful, we kindly request that you cite the following paper:

```bibtex
@article{9562988,
    author={Sadat, Sayed Abdullah and Rui, Xinyang and Ardakani, Mostafa},
    booktitle={2021 IEEE North American Power Symposium (NAPS)}, 
    title={Computational Impacts of SVCs on Optimal Power Flow using Approximated Active-Set Interior Point Algorithm}, 
    year={2021},
    pages={1-6}
}
```

