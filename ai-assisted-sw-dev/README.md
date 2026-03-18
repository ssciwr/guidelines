# AI-assisted research software development

**Disclaimer: We try to keep this updated, but due to the pace of developments in the field, we cannot promise that the latest developments have been considered.**

## In the planning and possible solution research phase

- Make sure to visit websites and review documentation of libraries of recommended tools, to check that what the AI promised is actually currently true
- Do not reveal any personal or sensitive information, and possibly use a chat model provided by the URZ or the GWDG

## In the prototyping phase: reach of the software = 1 person

The below are minimal best practices for any software that impacts at most one person. As soon as results from that software are published, the impact level is higher than one!

- Make sure to review and understand the code that the AI is suggesting. Use it as a tool to accelerate your contributions, but not as a complete replacement for any contributions from your side.
- Include docstrings and tests to further clarify specifications and required output
- Indicate the tooling that was used for the creation of the code at least in your Pull Request; some even recommend to include this information in any git commit message as "Generated-by: ".

## In the development phase: reach of the software > 1 person

Here the software achieves a higher reach and impact. As soon as the software and its produced output impact more than one person, the following applies in addition to the above:
- Do not overrely on the AI - critically inspect if the suggestions are correct. You can ask the AI to find flaws with the proposed approach or ask it to check for specific issues, for example, memory leaks, correct and sufficient type checking, etc.
- Make sure the suggested code follows project standards and conventions and is harmonized with the code base. This is crucially important for maintainability and low technical debt, working towards sustainability goals. 
- Include and frequently run at least unit tests, ideally also testing in continuous integration.
- Include static code analysis such as [SonarCube](https://docs.sonarsource.com/).

## Additional best practices for research software development

- Sometimes the AI suggests test code that does not actually test the functionality, but only appears so. It is therefore recommended to: (1) Not use random numbers in testing, since these make it harder to spot such cases and generally should only be used when behaviour is tested and not correctness; (2) inspect your tests carefully and make sure that when you change the function or the test, the outcome is what you expect. This can also be handled automatically by mutation testing.

## Code review

You have the responsibility for the generated code and should review it carefully. You can also ask the AI to review code critically. You can also iterate roles with the AI, that it suggests code, you refactor the code, and then the AI reviews the code to scan for issues.


## Legal concerns

The underlying models for the AI coding tools were trained on large amounts of open-source libraries. These libraries are published open-source under a certain license. Now the model can reproduce code that exactly matches code in these libraries. It is therefore advisable to verify that generated code does not violate copyright or licenses of code or subject matter that was part of the training data. In practice, this is quite difficult to ensure. GitHub Copilot does have a mode where it will refrain from including suggestions that match public code:

![alt text](image.png)

Additionally, there is an ongoing debate whether code produced by software achieves the originality standard to be protected under copyright. Copyright may be achievable if the prompting of the AI tool is sufficiently original to be copyrightable. See for example [here](https://www.apache.org/legal/generative-tooling.html).


## Ethical use

AI assistance can lead to a large amount of code being produced in a very short time. This is currently referred to as "AI slop". The intentional creation of AI slop is widely considered unethical, due to several factors: (i) The creator is responsible for the content and should aim at the best possible quality; (ii) mass low-quality content can spam and deter from original and high-quality content; (iii) it may create an additional burden on others, that are for some reason forced to consume the content, for example in open-source collaborative work.

It is very easy to include unintentional AI slop: (i) By adding in unrelated changes to the problem that you are currently trying to solve, thus creating an incomprehensive line of development; (ii) by over-reliance on the AI tool for example in the automatic generation of commit messages and Pull Request Summaries.

## Prompt suggestions and agent instructions

It is a good practice to use somewhat standardized instructions for projects. There are different ways that you can tell your AI tool or agent how it should behave:

1. Copilot prompt: Place them in the `.github` folder as `copilot-instructions.md` ([see here](https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions)). For an example, look at [Apache Airflow](https://github.com/astronomer/airflow/blob/main/.github/instructions/code-review.instructions.md).
