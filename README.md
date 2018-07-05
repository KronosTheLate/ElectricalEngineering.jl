# EE.jl

This is a Julia package on electrical engineering based on [Unitful](https://github.com/ajkeller34/Unitful.jl).
The processing and calculation of real and complex quantities is supported. Julia 0.6.2 is supported.

The non-official package EE.jl can be installed by (has to be done only once):

```julia
Pkg.clone("git://github.com/christiankral/EE.jl.git")
```

In order to update to the actual version of GitHub use:

```julia
Pkg.update("EE")
```

The module EE.jl has to be loaded by `using EE`. In order to use all the features of EE.jl, modules Unitful and PyPlot have to be loaded as well. It is thus recommended to appy:

```julia
using Unitful,Unitful.DefaultSymbols,PyPlot,EE
```

After updating to a newer version of EE.jl, the module can be reloaded without exiting the session by applying `reload("EE")`.

# Features

## Phasors

- Function `phasor`
    - Plot publication ready phasor diagrams
    - LaTeX labeling with absolute or relative rotation of text

![Phasor diagram](https://raw.githubusercontent.com/christiankral/EE.jl/master/resources/phasordiagram.png?raw=true)

- Function `polar` to generate a complex quantitiy based on the length and the angle
- Constant `j` represeting the imaginary unit equvalent to `1im`

## Circuits and Physics

- Function `∥`
    - Calculate parallel connections of impedances
    - Calculate parallel impedance with or without units
  
## Inputs and Outputs

- Function `printuln`
    - Print complex variables (including) units in rectangular and polar form
    - Limit output to six significant digits
    - Convert printed quantitiy optionally into a target unit
    - Works with scalars and vectors of real or complex quantities
- Function `save3fig`
    - Save one figure in the three file formats `png`, `eps` and `pdf`
    - Optionally crop figures
    
    ## Plotting
    
- Assign color schemes based on https://matplotlib.org/users/plotting/colormaps/grayscale_01_04.pdf
- Assign line and marker types
- Assign color schemes to quanities, using either `using EE.Gray` of gray scale graphics or `using EE.Tab20bc` to apply colors based on https://matplotlib.org/users/plotting/colormaps/grayscale_01_04.pdf