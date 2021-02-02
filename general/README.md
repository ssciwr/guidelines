# General Guidelines

The general guidelines provide an overview of sustainable software development and good scientific practice in research software engineering. They provide a general framework which researchers should adhere to when writing scientific software. However, each programming language introduces its own flavor and so the tools that are recommended can be language-specific. Please check the guidelines for the language that you are using. Currently, [C++](../cpp/README.md) and [python](../python/README.md) are available. Please open an issue for requesting guides for further programming languages.

## Version control

Any software that is being actively developed should be under version control. Version control allows you to keep track of any changes to your software and review the history at any time. It also allows you to track issues and work collaboratively. A version-control system such as `git` for your software should be the default. Different providers are available such as GitHub, GitLab, and Bitbucket.

## Documentation

Good documentation is essential for ensuring users know what to do with the code, and are applying it to the correct use cases. It will save time in the long run, as code by itself is rarely obvious, and it will help outline dependencies. Depending on the programming language used, we recommend different tools like `doxygen`, `sphinx`, or using markdown/a wiki.

## Testing

(Automated) testing ensures that errors are detected early and that results are reproducible. Implementing the tests and keeping them updated requires effort, but will pay off in the long run. When planning your software, you can also make use of a test-driven development philosophy which makes structuring your code easier. Reproducibility is a requirement for good scientific practices. Testing also makes refactoring easier, and allows for continuous integration/continuous delivery (deployment) (CI/CD). Different CI/CD integration tools are available, such as GitHub actions, GitLab CI, Jenkins, and Travis CI, to name a few.

## Refactoring

Refactoring means that previously implemented functionality or legacy code is updated and improved as new parts are added to a software. This allows for a flexible adaptation of the software and ensures that the dependencies are up-to-date. "Always leave code better than you found it" ([source](https://biratkirat.medium.com/step-8-the-boy-scout-rule-robert-c-martin-uncle-bob-9ac839778385)). Make use of a good coding editor (such as `VS Code` or `atom`) and linting to keep your source code clean, and use profilers to check the computational bottlenecks.

## Code review

Code review - involving your collaborators in any changes you made to the code and vice versa - increases the chance of errors being detected early. Furthermore, it also aids knowledge transfer and keeps you up to date on what features are being implemented. Code review is easy to incorporate in your work flow through `github pull requests`.
