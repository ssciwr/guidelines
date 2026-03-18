# AI-assisted research software development

**Disclaimer: We try to keep this updated, but due to the pace of developments in the field, we cannot promise that the latest developments have been considered.**

For a list of AI-assisted code contribution policies, please take a look at [this repo](https://github.com/melissawm/open-source-ai-contribution-policies).

## In the planning and possible solution research phase

- Make sure to visit websites and review documentation of libraries of recommended tools, to check that what the AI promised is actually currently true.
- Do not reveal any personal or sensitive information, and possibly use a chat model provided by the URZ or the GWDG.
- To get better results from the interaction with the AI, be sure to: 
    1. Clearly formulate what problem is being solved; 
    2. review existing solutions if they may fit your needs; 
    3. consider the constraints that exist from your organization, research group, field of research, plus technical constraints such as memory, data sizes, compute efficiency, hardware. In software development, this usually goes under "Requirements Engineering". Only with a clear instruction, the AI will be able to provide reasonable suggestions. You may use the AI to refine your vision and achieve this clearer problem description in iterative cycles.

## In the prototyping phase: reach of the software = 1 person

The below are minimal best practices for any software that impacts at most one person. As soon as results from that software are published, the impact level is higher than one!

- Make sure to review and understand the code that the AI is suggesting. Use it as a tool to accelerate your contributions, but not as a complete replacement for any contributions from your side (verification and testing).
- Include docstrings and tests to further clarify specifications and required output.
- Indicate the tooling that was used for the creation of the code at least in your Pull Request (PR); some even recommend to include this information in any git commit message as "Generated-by: ".
- Protect sensitive data and do not expose such data to the AI tool.

## In the development phase: reach of the software > 1 person

Here the software achieves a higher reach and impact. As soon as the software and its produced output impact more than one person, the following applies in addition to the above:
- Do not overrely on the AI - critically inspect if the suggestions are correct. You can ask the AI to find flaws with the proposed approach or ask it to check for specific issues, for example, memory leaks, correct and sufficient type checking, etc.
- Make sure the suggested code follows project standards and conventions and is harmonized with the code base. This is crucially important for maintainability and low technical debt, working towards sustainability goals. See also the point about hallucination and redundancy in the next section.
- Include and frequently run at least unit tests, ideally also testing in continuous integration.
- Include static code analysis such as [SonarCube](https://docs.sonarsource.com/) and security scanning tools such as [snyk](https://github.com/snyk/actions).
- Disclose what the AI tools were used for (code suggestions, code review, code analysis, PR description and summary, etc).

Please make sure to also check the [ethical](#ethical-use) and [legal concerns](#legal-concerns) below, as they adress the important topics of AI slop and copyright.

## Additional best practices for research software development

- AI-assisted PRs tend to get too large and suffer from scope creep. Be sure to stay on task for the specific issue / feature you are working on. It helps to generate issues that clearly describe the problem and scope.
- AI models may reinvent code and utilities that exist elsewhere in the codebase. This is a different type of AI slop than the one mentioned below in the [ethical use](#ethical-use) section. Make sure that the code that is produced does not reinvent existing functionality, or mistake a certain functionality for something that does not exist (redundancy and hallucination issues). Make sure that the changes are really necessary and refactor as needed!
- Sometimes the AI suggests test code that does not actually test the functionality, but only appears so. It is therefore recommended to: 
    1. Not use random numbers in testing, since these make it harder to spot such cases and generally should only be used when behaviour is tested and not correctness; 
    2. inspect your tests carefully and make sure that when you change the function or the test, the outcome is what you expect. This can also be handled automatically by [mutation testing](https://github.com/theofidry/awesome-mutation-testing).
- Human-generated mistakes are often easier to spot than AI-generated mistakes. There are [entire libraries](https://www.promptfoo.dev/) dealing with typical AI mistakes for the different models. Be aware of this when using AI tools.

## Code review

You have the responsibility for the generated code and should review it carefully. You can also ask the AI to review code critically. You can also iterate roles with the AI, that it suggests code, you refactor the code, and then the AI reviews the code to scan for issues.

## Code documentation

It is perfectly applicable to use AI to help you generate a good documentation for your project. Make sure that the resulting documentation is factually correct, references are included and that it is not overly verbose or written in an "AI tone". This requires some effort from your side to refactor and review all the generated text. It is further a good practice to note if you used AI for support with this, see above.

## Legal concerns

The underlying models for the AI coding tools were trained on large amounts of open-source libraries. These libraries are published open-source under a certain license. Now the model can reproduce code that exactly matches code in these libraries. It is therefore advisable to verify that generated code does not violate copyright or licenses of code or subject matter that was part of the training data. In practice, this is quite difficult to ensure. GitHub Copilot does have a mode where it will refrain from including suggestions that match public code:

![alt text](image.png)

Additionally, there is an ongoing debate whether code produced by software achieves the originality standard to be protected under copyright. Copyright may be achievable if the prompting of the AI tool is sufficiently original. See for example [here](https://www.apache.org/legal/generative-tooling.html).


## Ethical use

AI assistance can lead to a large amount of content or code being produced in a very short time. This is currently referred to as "AI slop". The intentional creation of AI slop is widely considered unethical, due to several factors: 
1. The creator is responsible for the content and should aim at the best possible quality; 
2. mass low-quality content can spam and deter from original and high-quality content; 
3. it may create an additional burden on others, that are for some reason forced to consume the content, for example in open-source collaborative work. 

To reduce AI slop, review the created content critically and remove anything that is stating the obvious. Include your reasoning and not the AI summary. It is better to be clear and succinct than to achieve perfect grammar.

It is very easy to include unintentional AI slop: 
1. By adding in unrelated changes to the problem that you are currently trying to solve, thus creating an incomprehensive line of development; 
2. by over-reliance on the AI tool for example in the automatic generation of commit messages and Pull Request Summaries.

## Prompt suggestions and agent instructions

It is a good practice to use somewhat standardized instructions for projects. There are different ways that you can tell your AI tool or agent how it should behave:

1. Copilot prompt: Place them in the `.github` folder as `copilot-instructions.md` ([see here](https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions)). For an example, look at [Apache Airflow](https://github.com/astronomer/airflow/blob/main/.github/instructions/code-review.instructions.md).

2. Codex prompt: Place an `AGENT.md` file in the respective folder as described [here](https://developers.openai.com/codex/guides/agents-md).


3. Claude CLI prompt: Place a CLAUDE.md file in your repository root. An example can be found [here](https://github.com/pydata/xarray/blob/main/CLAUDE.md).


4. Antigravity prompt: Place the instructions in `.agents/rules` folder as described [here](https://antigravity.google/docs/rules-workflows).

In most tools, you can place a `AGENT.md` file in your repository root. It is also possible to define skills and provide further context like [here](https://platform.claude.com/docs/en/agents-and-tools/agent-skills/overview). Be aware that this poses further [security risks](https://doi.org/10.48550/arXiv.2601.10338).