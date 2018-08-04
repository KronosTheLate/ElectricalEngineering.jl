# Unitful

The Julia package [Unitful](https://github.com/ajkeller34/Unitful.jl) provides units so that calculations can be performed with physical quantities instead of numbers only. The package can be installed with `Pkg.add("Unitful")`. The [Unitiful homepage](https://ajkeller34.github.io/Unitful.jl/stable/) presents a documentation of the relevant functions in order to work with units.

## Working with untis

In electrical engineering I recommend to load the `Unitful` package as well as the default units `Unitful.DefaultSymbols`, in addition to `EE`:
```julia
using Unitful,Unitful.DefaultSymbols,EE
```
Between number and quantity, no blank is allowed.
```julia
julia> V1=3V
3 V
julia> I1=1mA
1 mA
julia> R1=V1/I1
3.0 V mA^-1
```

In oder to get a formatted output with six significant digits and a selected unit, function `printuln` (provied by `EE.jl`) can be used:

```julia
julia> printuln("R1",R1,Ω)
              R1 = 3000 Ω
```

## Brief summary of `Unitful` function

### `unit`

Determine the used unit
```julia
julia> unit(V1)
V
julia> unit(I1)
mA
```

### `upreferred`

Determine a quantify in coherent (preferred) units, i.e., the SI unit without prefix.
```julia
julia> upreferred(V1)
3//1 kg m^2 A^-1 s^-3
julia> upreferred(I1)
1//1000 A
```
Additionally, this function can be used to determine coherent unit of a non-coherent unit.  
```julia
julia> upreferred(mA)
A
```
