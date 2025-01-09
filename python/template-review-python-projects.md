# Template for Python Project Consultations

*Goal:* Provide a user with recommendations to improve a Python project. This template will serve as a basis to analyze an Open Source Python project. The person(s) involved in the review could add more fields if needed.

**Project's name:**

**User(s):**

**Consultor(s):** 



## Project’s name
**Purpose:** to investigate if the project’s name is already taken for another software project.

Resources:
- [google.com](www.google.com)
- [pypi.org](https://pypi.org/)
- [pystats](https://pypistats.org/)
  
Comments: <put the result of your findings>

Recommendations: 
- Recommendation 1
- Recommendation 2

## Documentation

### Repository
- Does it include a `README.md` file with the following elements?
  - [ ] Name
  - [ ] Description of the project
  - [ ] Badges (optional)
  - [ ] Overview diagrams (visuals) to understand the project
  - [ ] Installation guide
  - [ ] Usage examples
  - [ ] Support
  - [ ] Roadmap
  - [ ] Contributing
  - [ ] Authors and acknowledgment
  - [ ] License
  - [ ] Project status 
  
  - Recommendations: 
      - Recommendation 1
      - Recommendation 2
  - References:
      - Awesome README: https://github.com/matiassingers/awesome-readme?tab=readme-ov-file

- Does it include a `CONTRIBUTING.md` file?
  - Recommendations:
    - Recommendation 1
    - Recommendation 2

- Does it include a `LICENSE` file for the project?
  - Recommendations:
    - Recommendation 1
    - Recommendation 2

### Webpage for the project

- *Are you using [sphinx](https://www.sphinx-doc.org/en/master/), [readthedocs](https://docs.readthedocs.io/en/stable/), [MkDocs](https://www.mkdocs.org/) for building your documentation?*
  - Recommendations:
    - Recommendation 1
    - Recommendation 2
  - References: 
    - [Sphinx setup tutorial Scientific Software Center](https://ssciwr.github.io/sustainable_development_course/unit4/STEPS.html)

- *Are you hosting your webpage?*
    - Where?: 
    - Recommendations: 
        - Use [GitHub pages](https://pages.github.com/)

- *Is the documentation divided in Tutorials, How-to guides, API references, Explanations?*
    - Recommendations: 
        - Recommendation 1
        - Recommendation 2
    - References:
        - [Diataxis documentation guide](https://diataxis.fr/)


### Notebooks (optional)
- *Are you using a spell checker for Jupyter Notebooks?*
    - Recommendations: 
        - Recommendation 1
        - Recommendation 2

- *Are you posting Jupyter notebooks in Google Colab for easy access of users?*
    - Recommendations: 
        - Recommendation 1
        - Recommendation 2

### Command Line Scripts
- *Do your scripts are interactive with an user?*
    - Recommendations: 
        - Use argparse (built-in Python library)


## Project Structure
- Does it have a `pyproject.toml` file?
    - Recommendation: 
        - Recommendation 1
        - Recommendation 2

- Does it have a developer dependency file?
    - Recommendation: 
        - Recommendation 1
        - Recommendation 2

## Workflow
### Writing code
- *Is this project following PEP8 guidelines?*
  - Recommendations: 
    - Recommendation 1 (for instance, choose a docstring style)
    - Recommendation 2 (for instance, add doctstrings to methods)
    - Recommendation 3 (for instance, use snake-case for naming functions)

- *Is this project applying good commit messages, i.e. conventional commits?*
  - Recommendation: 
    - Recommendation 1
    - Recommendation 2

### Testing code
- *Are you using a testing framework, i.e. `pytest`?*
    - Recommendation: 
        - Recommendation 1
        - Recommendation 2

- *Is this project using `pre-commit hooks`?*
    - Formatter: 
    - Import ordering: 
    - Code linter: 
    - Typing annotations linter:
    - Strip output for Jupyter Notebooks:
    
    - Recommendations: 
        Recommendation 1
        Recommendation 2
    - References:
        - Block course: Scientific Software Development
        - The required commands in live session
        - Welcome to precommend

- *Does it have a developer dependency file?*
    - Recommendation: 
        - Recommendation 1
        - Recommendation 2
  
### Commiting Code
- *Do you have Multiple commits that can be combined?*
  - Recommendation
    - Squash and merge using Git

### Pushing code to remote repository
- Branches
  - Recommendation:
    - Use Pull Requests, never push directly to main, and protect your main branch.

### CI/CD
- *Is this project using Continuos Integration workflows?*
  - Recommendation:
    - Use GitHub Actions
- *Is this project using Sonarcloud and codecov integration?*
- *Is it project using precommit in the remote repository?*
- *Is this project using dependabot?*
  

## Publishing Packages
- *Check if the package is already published in PyPi or Conda*
    - Recommendation: 
        - Recommendation 1
        - Recommendation 2

