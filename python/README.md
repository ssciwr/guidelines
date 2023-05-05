# Python Coding Guidelines
Our recommendations for creating and maintaining reliable scientific software in Python.

## Good default choices

Here are our suggested default choices for build systems and third party libraries, which are all widely used and well supported:

- Version control: [GitHub](https://github.com/)
  - de facto standard for open source software
  - start from our [Python template repository](https://github.com/ssciwr/python-project-template)
  - private repos also available
- Testing framework: 
  - [unittest](https://docs.python.org/3/library/unittest.html)
    - already part of the Python standard library
  - [pytest](https://docs.pytest.org/en/stable/)
    - offers all of the functionality of unittest and additional tools for more advanced testing requirements
- Continuous Integration: [GitHub Actions](https://github.com/features/actions)
  - well integrated with Github
- Documentation: [Sphinx](https://www.sphinx-doc.org/)
  - the default for Python documenation
- Python versions:
  - official list of [supported versions](https://devguide.python.org/versions/#supported-versions)
 
For each choice there are of course many alternatives, each with their pros and cons, but these represent a
sensible default choice for the vast majority of Python projects.

Our [Python Project Template](https://github.com/ssciwr/python-project-template) is a simple way to
start a new Python project with all of the above already set up - just click on the green `Use this template` button.

For more advanced features such as automated pypi deployment and package versioning integrated with git
see our [Python Package Cookiecutter](https://github.com/ssciwr/cookiecutter-python-package)

## Tooling

Good tools make it easier to develop good code. Unlike the previous section, where a single choice must be made
for the project, each person contributing to a project can use whichever tools they prefer. Some recommendations:

- IDE
  - [Visual Studio Code](https://code.visualstudio.com/): free
  - [Atom](https://atom.io/): free
  - [Sublime Text](https://www.sublimetext.com/): free but will ask you to purchase from time to time
- Code formatting
  - Don't do this manually, and especially don't spend time debating how code should be formatted!
  - Just pick a tool that does it automatically (e.g. your IDE, or [autopep8](https://pypi.org/project/autopep8/), or use [Black](https://github.com/psf/black))
- Linting
  - Keep your code clean using linters such as [flake8](https://pypi.org/project/flake8/)

## Recommended libraries

There is a vast abundance of available modules in Python. For common problems in scientific computing, use

- [NumPy](https://numpy.org/)
  - use case: array and matrix operations, mathematical functions
- [SciPy](https://www.scipy.org/)
  - use case: enhanced linear algebra, additional mathematical functions compared to numpy
- [SymPy](https://www.sympy.org/)
  - use case: symbolic math (e.g. differentiation)
- [pandas](https://pandas.pydata.org/)
  - use case: statistical data analysis and data transformation
- [seaborn](https://seaborn.pydata.org/)
  - use case: statistical data visualization
- [Keras](https://keras.io/)/[TensorFlow](https://www.tensorflow.org/)
  - use case: machine learning objectives, build and run your own ML models
- This list is by no means complete. Check e.g. [PyPi](https://pypi.org/) and [SciKits](https://www.scipy.org/scikits.html) for more options.
