# Julia coding guidelines 
Our recommendations for creating and maintaining reliable scientific software in [Julia](https://julialang.org/).

## Good default choices 

- Version control: [GitHub](https://github.com/)
    - de facto standard for open source software 
    - provides all necessary tools for developing software in a team
    - includes Continuous Integration pipelines for continuous testing 
    <!-- - start from our [template repository](todo) -->

- Continuous integration: [GitHub actions](https://github.com/features/actions)
    - comes integrated into GitHub already
    - large template library from which your workflow can be put together

- Testing framework: [Test.jl](https://docs.julialang.org/en/v1/stdlib/Test/)
    - standard library option for unit tests, rough analogon to Python's UnitTest library

- Documentation: [Documenter.jl](https://github.com/JuliaDocs/Documenter.jl)
    - Markdown based 
    - includes doctests for code examples 
    - can be seen as an analogon to [Sphinx](https://github.com/sphinx-doc/sphinx)

- Profiling: 
    - [Profile.jl](https://docs.julialang.org/en/v1/manual/profile/): 
        - Part of the Julia standard library.
        - Can be used to profile allocations and CPU - time
        - various visualizations available via separate packages ([ProfileView.jl](https://github.com/timholy/ProfileView.jl), [FlameGraphs.jl](https://github.com/timholy/FlameGraphs.jl), [ProfileVega.jl](https://github.com/davidanthoff/ProfileVega.jl))

    - [BenchmarkTools.jl](https://github.com/JuliaCI/BenchmarkTools.jl): Provides more high-level performance information including statistical information about execution times.

## Tooling 
Julia is a relatively young language with a smaller community than, say, Python, C++ or Matlab. As such, the selection of tools is a bit more limited. Some suggestions: 

- IDE/Code Editor: 
    - [Visual Studio Code](https://code.visualstudio.com/): Free. The de-facto standard in the community. Provides support for linting, test discovery, formatting and more. Recommended way to go.
    - [Juno](https://junolab.org/): Free. Build on top of [Atom](https://atom-editor.cc/). Atom is no longer supported by Microsoft/GitHub, and Juno is only maintained and wont receive new features. Only consider this if you already have an Atom-based workflow and are unwilling to switch. 
    - [Sublime Text](https://www.sublimetext.com/): Free, but will ocassionally ask you to buy it. Syntax highlighing for Julia is available, but support for other functions is less developed than in the other two.

- Code Formatting: 
    - automatical formatting is available via VSCode's Julia plugin or through Juno.

- Linting: 
    - linting is available via VSCode's Julia plugin or through Juno.

## Recommended libraries
 
- Arrays and vectors (numpy analogon): 
    - standard library core contains classes for dense, n-dimensional arrays analogous to numpy-arrays. 
    - [SparseArrays.jl](https://docs.julialang.org/en/v1/stdlib/SparseArrays/): Sparse vectors and - matrices are supported through
    - [Tensors.jl](https://github.com/Ferrite-FEM/Tensors.jl) and [TensorOperations.jl](https://github.com/Jutho/TensorOperations.jl): For higher-order Tensor operations 

- Linear Algebra: 
    - [LinearAlgebra.jl](https://docs.julialang.org/en/v1/stdlib/LinearAlgebra/): Standard library module for linear algebra operations like matric traces, in verse, multiplication and so on. 

- Data analysis and data transformation: 
    - [DataFrames.jl](https://github.com/JuliaData/DataFrames.jl) and [DataFramesMeta.jl](https://github.com/JuliaData/DataFramesMeta.jl)

- Data input/output and storage: 
    - [HDF5.jl](https://github.com/JuliaIO/HDF5.jl): For arbitrary data that should have a hierarchical organization in a single file. 
    - [Arrow.jl](https://arrow.apache.org/julia/stable/): For arbitrary data that's organized in a tabular fashion.
    - [CSV.jl](https://github.com/JuliaData/CSV.jl): For tabular, human readable data output. 

- Visualization: 
    - [Plots.jl](https://github.com/JuliaPlots/Plots.jl): Julia Frontend with a homogeneous interface for various well known plotting packages like [matplotlib](https://matplotlib.org/), [plotly](https://plotly.com/) or [GR](https://gr-framework.org/#). 
    - [Makie.jl](https://github.com/MakieOrg/Makie.jl): Feature-complete plotting package in pure Julia. 
    - [AlgebraOfGraphics.jl](https://github.com/MakieOrg/AlgebraOfGraphics.jl) provides support for the grammar-of-graphics paradigm on the basis of Makie.jl .
    - [VegaLite.jl](https://github.com/queryverse/VegaLite.jl): Provides Julia support for [VegaLite](https://vega.github.io/vega-lite/) which is particularly useful for making interactive graphics. 

- Machine Learning/Deep Learning: 
    - [SciKitLearn.jl](https://github.com/cstjean/ScikitLearn.jl) for having access to the python based [scikit-learn](https://scikit-learn.org/) library in Julia 
    - [Flux.jl](https://github.com/FluxML/Flux.jl) for deep learning applications. 

Have a look at [JuliaHub](https://juliahub.com/ui/Packages) to find other packages for your use case. 


## Style guides and best-practices:

Much has already been written about how to write good Julia code which needs not be repeated here. Here are some starging points: 
- [Official style guide](https://docs.julialang.org/en/v1/manual/style-guide/)
- [Official performance tips](https://docs.julialang.org/en/v1/manual/performance-tips/)

