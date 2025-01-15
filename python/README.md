# Python Coding Guidelines
Our recommendations for creating and maintaining reliable scientific software in Python.

## Good default choices

Here are our suggested default choices for build systems and third party libraries, which are all widely used and well supported:

- Version control: [GitHub](https://github.com/)
  - de facto standard for open source software
  - start from our [Python template repository](https://github.com/ssciwr/python-project-template) for more basic Python code or our [Python cookiecutter](https://github.com/ssciwr/cookiecutter-python-package) for developing Python packages
  - private repos also available
- Testing framework: 
  - [unittest](https://docs.python.org/3/library/unittest.html)
    - already part of the Python standard library
  - [pytest](https://docs.pytest.org/en/stable/)
    - offers all of the functionality of unittest and additional tools for more advanced testing requirements
- Continuous Integration: [GitHub Actions](https://github.com/features/actions)
  - well integrated with Github
- Documentation: [Sphinx](https://www.sphinx-doc.org/)
  - the default for Python documentation
- Documentation hosting: [readthedocs](https://docs.readthedocs.io/en/stable/) or [MkDocs](https://www.mkdocs.org/), or GitHub pages (see [general recommendations](../general/README.md))
  - Recommendations:
    - Recommendation 1
    - Recommendation 2
  - References: 
    - [Sphinx setup tutorial Scientific Software Center](https://ssciwr.github.io/sustainable_development_course/unit4/STEPS.html)
- Python versions:
  - official list of [supported versions](https://devguide.python.org/versions/#supported-versions)
 
For each choice there are of course many alternatives, each with their pros and cons, but these represent a sensible default choice for the vast majority of Python projects.

Our [Python Project Template](https://github.com/ssciwr/python-project-template) is a simple way to
start a new Python project with all of the above already set up - just click on the green `Use this template` button.

For more advanced features such as automated pypi deployment and package versioning integrated with git
see our [Python Package Cookiecutter](https://github.com/ssciwr/cookiecutter-python-package)

## Python standards and package names

Adhere to Python styling recommendations ([PEP8](https://peps.python.org/pep-0008/)). A standard style of Python code helps you parse the code more quickly and also helps others understand your code without mental effort involved in [figuring out how the information is presented](https://github.com/zakirullin/cognitive-load).

Once you decide on a valid Python package name, check the general web and the Python ecosystem if this name is already taken ([google.com](www.google.com),-[pypi.org](https://pypi.org/), [pystats](https://pypistats.org/)).

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
- Pre-commit hooks: 
  - Use [pre-commit](https://pre-commit.com/) to automatically format (black) and lint (flake8) your code upon commit. You should also include [nbstripout](https://github.com/kynan/nbstripout) when working with Jupyter notebooks, to ensure only the input is retained in the commit history and not the output (this can overexaggerate your changes and make finding the real changes difficult)
- Notebooks:
  - Use a [spell checker for Jupyter Notebooks](https://github.com/ipython-contrib/jupyter_contrib_nbextensions)
  - Make notebooks available for easy use through [google colab](https://colab.research.google.com/) or [binder](https://notebooks.gesis.org/binder/)
- Command Line Scripts:
  - For interactive scripts, use [argparse](https://docs.python.org/3/library/argparse.html) or [click](https://click.palletsprojects.com/en/stable/)

## Recommended libraries

There is a vast abundance of available libraries in Python. When you incorporate such a library in your Python project, you are introducing a dependency. For dependencies you should check that  
- the dependency is actively maintained
- the dependency does not have many issues that have been open for a long time
- the dependency has been tested and more widely used (otherwise, be vigilant)
- the dependency itself has not too many sub-dependencies
- there are no conflicting sub-dependencies between the dependencies themselves that you use in the project

When you use a dependency, you should reference it in your `requirements.txt`or `pyproject.toml` file. As long as you only use it and not distribute the dependency with your code, you are free to choose the license of your code independently. However, note that if you distribute third-party code together with your software, the [licenses need to be compatible](https://www.gnu.org/licenses/license-list.html) and you need to pay proper attribution.