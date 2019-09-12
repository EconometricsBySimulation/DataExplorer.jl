# DataExplorer.jl
Julia package for intuitively navigating dataframes

Ideally something that working like the following.

```julia
dataexplorer> import mydf
Activating mydf 902 rows, 32 variables

dataexplorer> list names
:var1
:var2
:var3
...
:var31
:var32

dataexplorer> set var1 = var2 + var3
870 values changed
32 missing (20 from var2, 12 from var3)

dataexplorer> create var33 = var2 + var3
870 values set
32 missing (20 from var2, 12 from var3)

dataexplorer> set var33 = "" if var33 === missing
32 values changed

dataexplorer> show julia
Showing Julia command

dataexplorer> set var1 = var2 + var3
870 values changed
32 missing (20 from var2, 12 from var3)
julia> activedataframe[!,var1] = activedataframe[!,var2] + activedataframe[!,var2]

dataexplorer> create var33 = var2 + var3
Warning var33 already exists! Use [force] to override!

dataexplorer> create var33 = var2 + var3 [force]
870 values changed
32 missing (20 from var2, 12 from var3)
julia> activedataframe[!,var1] = activedataframe[!,var2] + activedataframe[!,var2]

dataexplorer> set var33 = "" if var33 === missing
32 values changed
julia> activedataframe[activedataframe[!,var33] === missing ,var33] = ""

dataexplorer> export as mydf2
Exporting mydf2 902 rows, 33 variables
julia> mydf2 = returnactivedataframe()
```
