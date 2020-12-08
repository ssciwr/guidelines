# C++ Coding Guidelines
Our recommendations for creating and maintaining reliable C++ scientific software.

## Good default choices

Here are our suggested default choices for build systems and third party libraries, which are all widely used and well supported:

- Version control: [GitHub](https://github.com/)
  - defacto standard for open source software
  - start from our [c++ template repository](https://github.com/ssciwr/cpp-project-template)
  - private repos also available
- Build system: [CMake](https://cmake.org/)
  - defacto standard for C++
  - widely used and supported
  - cross-platform
- Testing framework: [Catch2](https://github.com/catchorg/Catch2)
  - simple to setup and to use
- Continuous Integration: [GitHub Actions](https://github.com/features/actions)
  - well integrated with Github

For each choice there are of course many alternatives, each with their pros and cons, but these represent a
sensible default choice for the vast majority of C++ projects.

Our [C++ Project Template](https://github.com/ssciwr/cpp-project-template) is a simple way to
start a new C++ project with all of the above already set up - just click on the green `Use this template` button.

If you are looking for more features such as python bindings, or alternative CI or git hosting providers,
see our [C++ Project Cookiecutter](https://github.com/ssciwr/cookiecutter-cpp-project).

## Recommended third party libraries

It is nearly always better, where possible, to use a well tested and maintained third party library instead of rolling
your own solution to a problem. Typical benefits include: less bugs, better performance, less maintenance.

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
