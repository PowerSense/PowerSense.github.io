An optimal power flow constitutes the core of power system operations. It is an optimization extension of the power flow analysis, where in addition to feasibility, an optimal dispatch is also desired. The objective of power system operation depends on the what kind of problem is being solved. Usually it is to serve the customers at the minimum cost, taking into consideration the physical constraints of the system. Optimal power flow can be expressed as an optimization problem and when security constraints are added it is referred to as security-constrained optimal power flow (SCOPF). In addition to power system operations, a solution to the optimal power flow is also essential for power system planning. 

In an OPF problem, the most important equations are about the representation of transmission branches. There are different approaches to model a transmission branch in a power system. The most commonly used representation of the transmission branch is called the π-model, which is what have adopted too.

<p align="center">
<img src="https://powersense.github.io//assets//opf//TransmissionModel.png" width="500" alt="Transmission Model">
</p>

The figure above shows a general representation of a π-model of a transmission branch, where y_{ij} is the branch series admittance, ysij is the branch shunt admittance, yMij is the branch mutual admittance, and τij is the branch complex tap ratio. If a branch is only a transmission line then τiij=1 and yMij=0. If a branch is only a transformer, then all the line parameters are zero. Thus, the figure represents a general model that can represent any type of transmission branch by simply adjusting the values of the parameters shown in the figure.
