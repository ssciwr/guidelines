# General Guidelines

The general guidelines provide an overview of sustainable software development and good scientific practice in research software engineering. They provide a general framework which researchers should adhere to when writing scientific software. However, each programming language introduces its own flavor and so the tools that are recommended can be language-specific. Please check the guidelines for the language that you are using. Currently, [C++](../cpp/README.md), [Python](../python/README.md) and [Julia](../julia/README.md) are available. Please open an issue for requesting guides for further programming languages.

## Version control

Any software that is being actively developed should be under version control. Version control allows you to keep track of any changes to your software and review the history at any time. It also allows you to track issues and work collaboratively. A version-control system such as `git` for your software should be the default. Different providers are available such as GitHub, GitLab, and Bitbucket.

### Content of a repository

A repository is the central storage location for software source code, documentation and other related files. Through a repository and a version-control system, changes to the software are being tracked and managed.

A software repository should contain the following files:
- A `README.md` file with the following elements:
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
  - References:
      - Awesome README: https://github.com/matiassingers/awesome-readme?tab=readme-ov-file

- A `LICENSE` file for the project. There are a variety of licenses to choose from, the SSC generally recommends a license with all options but no restrictions like the MIT license. GitHub offers [license templates](https://github.com/licenses/license-templates) that you can use to create your license file. If you add a new file through the GitHub website to your repository, or if you create a new repository, you also have the option of generating the license from the templates automatically.

- A `CITATION.cff` file with information about [how to cite your software](https://citation-file-format.github.io/).

- Some sort of `requirements.txt`, `CMakeLists.txt`, `Makefile`, for example, or `Dockerfile`, that specifies the required packages and ideally, installation environment. Further installation instructions should be included in the README.md. Optional: A developer dependency file that contains additional dependencies needed for developing the software.

- A `.gitignore` file or similar that helps you [keep unnecessary files untracked by the version control system](https://github.com/github/gitignore). GitHub provides you with a template automatically when you add a new `.gitignore` file via the website, or create a new repository.

The following files are optional files:
- A `CONTRIBUTING.md` file with guidelines and information for contributors. This applies if you would like to actively solicit contributions to your repository.

## GitHub etiquette

If you use GitHub or GitLab, you should use the respective ettiquette as appropriate. A standard way of developing software under git version control is [git-flow](https://nvie.com/posts/a-successful-git-branching-model/); a lightweight version of this and recommended and predominantly used by the SSC is [github-flow](https://githubflow.github.io/).

Never push directly to the main branch! The git and GitHub workflow entail making changes in branches, running (and passing) automated checks (see below) like code linter, code formatter, code quality reviewer, unit tests, further tests, code test coverage, ... before merging with main. A merge with main is preceded by a Pull Request where teams and collaborators can review code, and that trigger the automated checks. These means are meant to keep the main branch deployable and functional at all times.

### Commiting Code: Commit messages
When committing code to the repository, use meaningful commit messages that explain others (and yourself) what you did and can be used to "tell a story". The commits should be grouped in Pull Requests (PR) that ideally serves only one purpose. The changes in the line of development in the PR should be summarized in the PR description. You may also [link issues during the PR](https://docs.github.com/en/issues/tracking-your-work-with-issues/using-issues/linking-a-pull-request-to-an-issue).

A way to structure your commit messages is using [conventional commits](https://www.conventionalcommits.org/en/v1.0.0/).
When you merge PRs that have multiple commits (as they have usually) with the main branch, it is recommended that you *squash and merge* to group the commits in this line of development together.

## Continuous integration (CI) / continuous delivery (CD)

It is recommended to use CI in Pull (Merge) requests, to run automated checks that ensure your code is adhering to certain standards and passing tests. Different CI/CD integration tools are available, such as GitHub actions, GitLab CI, Jenkins, and Travis CI, to name a few. 

Depending on the scope and computational demands of your software, checks that can be included entail [pre-commit](https://pre-commit.ci/), [Sonarcloud](https://www.sonarsource.com/products/sonarcloud/), [codecov](https://about.codecov.io/), and unit/regression/system/... tests (see the language-specific recommendations). You may also integrate [dependabot alerts](https://docs.github.com/en/code-security/dependabot) and [snyk](https://docs.snyk.io/) for automated PRs about new dependency releases and vulnerabilities. [GitGuardian](https://www.gitguardian.com/) is a tool that helps you keep your code and environment secrets safe.

To learn about CI and CD on GitHub, see [here](https://skills.github.com/#automate-workflows-with-github-actions). GitHub actions are free for public repositories, and underly a quota for private repositories. One of the big advantages of CI is that you can run checks in different environments (operating systems, dependency versions, etc).

## Documentation

Good documentation is essential for ensuring users know what to do with the code, and are applying it to the correct use cases. It will save time in the long run, as code by itself is rarely obvious, and it will help outline dependencies. Depending on the programming language used, we recommend different tools like `doxygen`, `sphinx`, or using markdown/a wiki.

The documentation can be hosted on ecosystem-wide platforms, for example, `readthedocs` for Python projects, or more generally using [GitHub pages](https://pages.github.com/) or Gitlab. To learn how to set up GitHub pages, see [here](https://github.com/skills/github-pages).

The documentation should be structured in Tutorials, How-to guides, API references, and Explanations (see [Diataxis documentation guide](https://diataxis.fr/)). 
The essential content of a documentation entails:
- Explanations  
  -[ ] Name of the software (optional: Badges)
  -[ ] Short description of the software
  -[ ] Authors
  -[ ] Date of initial development
  -[ ] Main features
  -[ ] Main requirements
  -[ ] Validity range of the parameters
  -[ ] License information
  -[ ] Bug tracker
  -[ ] References
  -[ ] Citation information
- Tutorials and How-To guides
  -[ ] Input examples and explanations, step-by-step instructions
  -[ ] More detailed description of scientific approach and input variables reference
- API and developer references  
  -[ ] Source code description - functions and classes, modules, variables

## Testing

(Automated) testing ensures that errors are detected early and that results are reproducible. Implementing the tests and keeping them updated requires effort, but will pay off in the long run. When planning your software, you can also make use of a test-driven development philosophy which makes structuring your code easier. Keep in mind that reproducibility is a requirement for good scientific practices. Automated testing allows for continuous integration/continuous delivery (deployment) (CI/CD). 

## Code review

Code review - involving your collaborators in any changes you made to the code and vice versa - increases the chance of errors being detected early. Furthermore, it also aids knowledge transfer and keeps you up to date on what features are being implemented. Code review is easy to incorporate in your work flow through `GitHub pull requests`.
