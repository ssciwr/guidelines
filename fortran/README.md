# Fortran Coding Guidelines
Our recommendations for creating and maintaining reliable scientific software in [Fortran](https://fortran-lang.org/).

## Fortran general remarks
Fortran is used for scientific high-performance computing focusing on numerical applications. It is especially strong for array-based operations, with its inherent support for parallelism and vectorization.

Fortran code is most often legacy code having been developed over generations of researchers, using different Fortran dialects (most commonly Fortran77 and Fortran90). It has therefore some very language-specific topics that are very briefly summarized here. For a more complete list, consult the [Fortran language community](https://fortran-lang.org/learn/best_practices/).

## Good default choices

Here are our suggested default choices for build systems and third party libraries:

- Version control: [GitHub](https://github.com/)
  - de facto standard for open source software
  - start from our [Fortran template repository](https://github.com/ssciwr/fortran-project-template) for a repository complete with documentation build, tests and GitHub actions
- Testing framework: 
  - [pFUnit](https://github.com/Goddard-Fortran-Ecosystem/pFUnit)
    - unit tests for Fortran
  - [pytest](https://docs.pytest.org/en/stable/)
    - use pytest to drive your Fortran code, harnessing the power of the testing framework and at the same time account for the intricacies of Fortran legacy codebases and workflows - see [an example](https://github.com/ssciwr/powr-refactor/blob/main/test/test_colitest.py)
- Continuous Integration: [GitHub Actions](https://github.com/features/actions)
  - well integrated with Github
- Documentation: [Doxygen](https://doxygen.nl/manual/index.html)
  - can harness your comments from the source code
- Documentation hosting: [readthedocs](https://docs.readthedocs.io/en/stable/) or [MkDocs](https://www.mkdocs.org/), or GitHub pages (see [general recommendations](../general/README.md))
- Fortran versions/dialects:
  - Use of Fortran versions from Fortran90 or later is recommended, due to the dynamic memory allocation and deprecation of GOTO constructs
 

Our [Fortran Project Template](https://github.com/ssciwr/fortran-project-template) is a simple way to
start a new Fortran project with all of the above already set up - just click on the green `Use this template` button. You can try it out and compare to learn how to adapt this for your legacy Fortran project.

## Fortran standards

Fortran has different standards according to its version. Some general remarks are summarized here, loosely based on [the Fortran90 documentation](https://www.fortran90.org/src/best-practices.html), [Fortran-lang](https://fortran-lang.org/learn/best_practices/) and own experience:
- Fortran implementations generally do not make heavy use of more complex objects and namespaces. Therefore, it is advised to use descriptive names, define them within their scope ideally in module files that are passed through `use` statements, keep names consistent in the scope and separate concerns. Historically, the use of memory was costly, so that legacy codebases often reuse variables and (parts of) matrices. Avoid this practice in newer code and refactor legacy code to be more explicit.
- Use English language for all variable names, comments etc.
- Use all lowercase letters for all Fortran constructs (`do`, `subroutine`, `integer`, `intent`, ...)
- Use four spaces for indent.
- Declare floats as `real(dp)` with `dp` defined in your parameters module.
- Refactor any `GOTO` constructs that you chance upon.
- Use `implicit none` to avoid setting of implicit variables including their types.
- Make use of modules and include your subroutines in modules.
- Keep the main program short, rather `use` modules and call subroutines.
- Make use of assumed-shape arrays `1D_array(:)` and `2D_array(:,:)` and initialize these to zero before you start using them. (Alternatively, your compiler can handle this, but users may work with modified compiler options.) Allocate them in a sensible place in the program, you may also use a module for the memory allocation. Deallocate after use with the same strategy.
- Keep in mind that Fortran stores arrays in column-major order. Always access slices as `2D_array(:, 1)` or `3D_array(:, :, 1)`, with the colons should be on the left for a contiguous stride in memory (same applies to loops):
```fortran
do i3 = 1, N3
    do i2 = 1, N2
        do i1 = 1, N1
            A(i1, i2, i3)
        end do
    end do
end do
```

This list is by no means complete, there are many constructs in Fortran legacy code that require specific techniques for adaption, but this is beyond the scope of this guideline.

## Tooling

Good tools make it easier to develop good code. Some tools have been named above, here are some more recommendations:

- IDE
  - [Visual Studio Code](https://code.visualstudio.com/): free, install Fortran language extension
  - [Sublime Text](https://www.sublimetext.com/): free but will ask you to purchase from time to time
- Linting
  - Keep your code clean using linters such as [fortitude](https://github.com/PlasmaFAIR/fortitude)
- Pre-commit hooks: 
  - Use [pre-commit](https://pre-commit.com/) to automatically lint your code upon commit.
- GitHub Actions
  - Use the GitHub [setup-fortran action](https://github.com/ssciwr/setup-fortran) for your CI pipeline to install compilers and math libraries
- Debugging
  - Use `gdb` or `valgrind` for debugging
- Profiling
  - Many different profiles exist, the very basic `gprof` already does a pretty decent job.

## Recommended libraries

The Fortran ecosystem does not benefit from a vast library usage as is the case in ie. Python. Make use of [BLAS/LAPACK](https://www.netlib.org/lapack/lug/node11.html) calls whenever possible, same applies to [FFTs](https://www.fftw.org/). For more specific operations such as solution of differential equations, different libraries exist.

## Other recommendations

- Use a `Makefile` at the very least.
- Compile and test your code without compiler optimization and debug flags, and with optimization, both for compilation and runtime errors.
- Use different compilers to test your code, ie. `ifx` and `gfortran`. While `ifx` leads to more performant code, `gfortran` is more strict on your implementation and may help you identify potential issues.