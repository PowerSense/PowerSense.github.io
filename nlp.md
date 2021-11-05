# Nonlinear Solver

The nonlinear programming optimization component of [`Powersense.jl`](https://github.com/PowerSense/Powersense.jl) currently implements sequential linear programming method using line search algorithm for continuous nonlinear optimization. 

The package requires an external linear programming (LP) solver. Let's assume the following nonlinear non-convex example:

```julia
min   x^2 + x 
s.t.  x^2 - x = 2
```

This problem can be solved by the following code snippet:
```julia
# Load packages
using Powersense, JuMP
using GLPK # can be any LP solver

# Number of variables
n = 1

# Build nonlinear problem model via JuMP
model = Model(optimizer_with_attributes(Powersense.Optimizer, "external_optimizer" => GLPK.Optimizer))
@variable(model, x)
@objective(model, Min, x^2 + x)
@NLconstraint(model, x^2 - x == 2)

# Solve optimization problem with Nlopt
JuMP.optimize!(model)

# Retrieve solution
Xsol = JuMP.value.(X)
```
More details comming soon ...
