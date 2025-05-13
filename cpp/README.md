# C++ Coding Guidelines
Our recommendations for creating and maintaining reliable C++ scientific software. 

## Good default choices

Here are our suggested default choices for build systems and third party libraries, which are all widely used and well supported:

- Version control: [GitHub](https://github.com/)
  - de facto standard for open source software
  - start from our [C++ template repository](https://github.com/ssciwr/cpp-project-template)
  - private repos also available
- Build system: [CMake](https://cmake.org/)
  - de facto standard for C++
  - widely used and supported
  - cross-platform
  - Have a look at [our dedicated CMake recommendations](cmake.md)
- Testing framework: [Catch2](https://github.com/catchorg/Catch2)
  - simple to setup and to use
- Continuous Integration: [GitHub Actions](https://github.com/features/actions)
  - well integrated with Github
- Documentation: [Doxygen](https://www.doxygen.nl/index.html)
  - de facto standard for C++ documentation generation
- C++ Standard: 11 (or higher)
  - many third party libraries now require this as a minimum

For each choice there are of course many alternatives, each with their pros and cons, but these represent a
sensible default choice for the vast majority of C++ projects.

Our [C++ Project Template](https://github.com/ssciwr/cpp-project-template) is a simple way to
start a new C++ project with all of the above already set up - just click on the green `Use this template` button.

If you are looking for more features such as python bindings, or alternative CI or git hosting providers,
see our [C++ Project Cookiecutter](https://github.com/ssciwr/cookiecutter-cpp-project).

## Tooling

Good tools make it easier to develop good code. Unlike the previous section, where a single choice must be made
for the project, each person contributing to a project can use whichever tools they prefer. Some recommendations:

- IDE
  - [Visual Studio Code](https://code.visualstudio.com/): free
  - [CLion](https://www.jetbrains.com/clion/): paid (but offer free academic licenses)
  - [CodeBlocks](http://www.codeblocks.org/): free
- Code formatting
  - Don't do this manually, and especially don't spend time debating how code should be formatted!
  - Just pick a tool that does it automatically (e.g. your IDE, or [clang-format](https://clang.llvm.org/docs/ClangFormat.html))
  - [pre-commit](https://pre-commit.com/) and [pre-commit.ci](https://pre-commit.ci/) is a great way to do this
- Sanitizers 
  Sanitizers are compiler tools that enable runtime checks for specific aspects of a program, e.g., thread-safety, memory management, undefined behavior and others. These sanitizers can be enabled at compile time, and will run alongside the compiled program and detect and report suspicious behavior. This comes with a performance penalty that depends on the sanitizer used, hence they should not be enabled in production builds. To get the best reports, make sure you compile a symbolized binary. Available sanitizers differ from compiler to compiler: 
    - [Visual Studio](https://learn.microsoft.com/en-us/cpp/build/reference/fsanitize?view=msvc-170)
    - [Clang](https://clang.llvm.org/docs/UsersManual.html#controlling-code-generation)
    - [GCC](https://gcc.gnu.org/onlinedocs/gcc/Instrumentation-Options.html)
- Package managers
  - Package managers can help reduce overhead from dependency management.
  - [Conan](https://conan.io/)
  - [vcpkg](https://vcpkg.io/en/)
- Debugging, Profiling and Benchmarking
  There is a plethora of solutions for different platforms and use cases
  - [Google Performance Tools](https://github.com/gperftools/gperftools) CPU and Memory profiling
  - [Nvidia Nsight](https://developer.nvidia.com/nsight-compute-2019_5) for CUDA code
  - [Valgrind](https://valgrind.org/) Instrumentation suite that includes heap- and cache-profilers as well as memory debugging tools
  
## Recommended third party libraries

It is nearly always better, where possible, to use a well tested and maintained third party library instead of rolling
your own solution to a problem. Typical benefits include: less bugs, better performance, less maintenance. Wherever possible, one should use the C++ standard template library (STL) and only use third-party dependencies when the STL does not suffice. 

Here are our recommendations for third party libraries to solve some common problems in scientific computing:

- Vector/Matrix algebra: [Eigen](http://eigen.tuxfamily.org/)
  - use case: multiply matrices, invert matrices
  - allows you to write simple, expressive code
  - high performance results
- Logging: [spdlog](https://github.com/gabime/spdlog)
  - use case: log messages / debugging information to the terminal / to a file
  - simple to setup and to use
- String formatting: [fmt](https://fmt.dev/)
  - use case: formatting strings, e.g. replacing `printf` calls
  - simple python-like interface, fast performance
- General purpose libraries that augment the STL with a wide array of functionality:
  - [Boost](https://www.boost.org/)
  - [Abseil](https://github.com/abseil/abseil-cpp)
- Cross-language hierarchical data storage:
  - [HDF5](https://www.hdfgroup.org/solutions/hdf5/) 
- Fast, cross-language tabular data storage: 
  - [Apache Arrow](https://arrow.apache.org/)
- Multithreading and Parallelization:
  - [OpenMP](https://www.openmp.org/)
  - [Intel oneTBB](https://github.com/uxlfoundation/oneTBB)
