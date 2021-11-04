# Optimal Power Flow (OPF)

An optimal power flow constitutes the core of power system operations. It is an optimization extension of the power flow analysis, where in addition to feasibility, an optimal dispatch is also desired. The objective of power system operation depends on the what kind of problem is being solved. Usually it is to serve the customers at the minimum cost, taking into consideration the physical constraints of the system. Optimal power flow can be expressed as an optimization problem and when security constraints are added it is referred to as security-constrained optimal power flow (SCOPF). In addition to power system operations, a solution to the optimal power flow is also essential for power system planning. 

In an OPF problem, the most important equations are about the representation of transmission branches. There are different approaches to model a transmission branch in a power system. The most commonly used representation of the transmission branch is called the π-model, which is what have adopted too.

<p align="center">
<img src="https://powersense.github.io//assets//opf//TransmissionModel.png" width="500" alt="Transmission Model">
</p>

The figure above shows a general representation of a π-model of a transmission branch, where y<sub>ij</sub> is the branch series admittance, y<sup>s</sup><sub>ij</sub> is the branch shunt admittance, yMij is the branch mutual admittance, and τ<sub>ij</sub> is the branch complex tap ratio. If a branch is only a transmission line then τ<sup>i</sup><sub>ij</sub>=1 and y<sup>M</sup><sub>ij</sub>=0. If a branch is only a transformer, then all the line parameters are zero. Thus, the figure represents a general model that can represent any type of transmission branch by simply adjusting the values of the parameters shown in the figure above.

## OPF Formulations

<p align="center">
<img src="https://latex.codecogs.com/svg.image?\bg_red&space;\begin{subequations}\begin{align*}&&space;min&&space;&&space;\sum_{\substack{g&space;\in&space;\mathcal{G}}}&space;c_{2g}&space;\cdot&space;(\Re[s_g])^2&space;&plus;&space;c_{1g}&space;\cdot&space;\Re[s_g]&space;&plus;&space;c_{0g}&space;\\&&space;\text{s.t.}&&space;&&space;s_{ij}=v_i&space;\cdot&space;(y^{net}_{ij}&space;\cdot&space;v_i&plus;Y_{ij}&space;\cdot&space;v_j)^*,&space;&\forall&space;\{i,j\}&space;\in&space;2\mathcal{K}.\\&&space;&&space;&&space;\sum_{\substack{g&space;\in&space;\mathcal{G}_n}}s_g&space;-&space;\sum_{\substack{d&space;\in&space;\mathcal{D}_n}}s_d=\sum_{\substack{k&space;\in&space;\mathcal{K}_n^f}}s_{nk}&plus;\sum_{\substack{k&space;\in&space;\mathcal{K}_n^t}}s_{kn}&space;&plus;Y^L_{n}\cdot&space;|v_n|^2,&space;&\forall&space;n&space;\in&space;\mathcal{N}.\\&&space;&&space;&&space;V_n^{Min}&space;\leq&space;|v_n|&space;\leq&space;V_n^{Max},&space;&\forall&space;n&space;\in&space;\mathcal{N}.&space;\\&&space;&&space;&&space;|s_{ij}|&space;\leq&space;I^{Max}_{ij}&space;\cdot&space;|v_n|,&space;&\forall&space;\{i,j\}&space;\in&space;2\mathcal{K}.&space;\\&&space;&&space;&&space;s_g^{Min}&space;\leq&space;s_g&space;\leq&space;s_g^{Max},&space;&\forall&space;g&space;\in&space;\mathcal{G}.\end{align*}\end{subequations}" title="ACOPF complex problem" />
</p>
