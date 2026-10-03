# Guidelines for Scientific software for processes/workflows
Does your interface have many inputs, help the user take their data through a process, simulation, or workflow? Certain practises ensure this kind of software will be usable.

# Prioritise effieciency and domain speicifc tooling over simplicity for experts
Unlike general applications where aesthetics, trying to minimalize the cognitive load of users, scientific applications often need many dozens of possibly inputs or states of different parts available to the user to conduct their research. Build menus mapped to your domain; display relevant inputs for a step without breaking them up simply because they take up more than one page.

## **Use Declarative/Workflow Configuration files**
Provide a way to declaratively run your scientific software workflow via key-value specification such as .yaml files, rather than specify details through an interface. This makes it easier for them to manage their cofniugration/set up and rely on it working for reproducible or batch use.


### Example: PanSeg
In PanSeg, a workflow is created interactively by working through one example input. Each decision gets recorded, and after exporting the result of processing a single file, the user can export a workflow script. This workflow script can then be applied to a whole batch of inputs. This process gives the user confidence in their decisions by providing immediate interactive feedback. Also, the user is guided through the process by taking care which options are visible at what time to not overwhelm them.
and supporting (re)running experiment variations confidently.

### Make your Workflow files:
- **Declarative** Save workflow files in human readable formats like `yaml`, with `key:value`s
- **Deterministic**: To support re-use and user confidence, rerunning should generate the same result (outputs should be saved separately to workflow configuration), which is much easier with a single file (Procter et al, 2009)
- **Autocompletable with valid parameter values** Very simple usability can be sleekly achieved by published JSON schemas for workflow config files - e.g. in the KIMMDY project. This provides incredible usability as Users can see possible valid options and choose them with IDEs like VisualCode + JSON schema validator

# Make sure your software gives users information on how to use it when they first download it (Learnability and Documentation)
Make sure your users can learn your software - if they do not understand what objects must be created or connected, they cannot use your software. Add a well-restricted-to-core-information tutorial or even better a sample worflow file they can run to see the results/process. This is far more important than for web applications! Many of your users will be confused - your software must guide them, by example they can modify, or by clear enough explanation that they can succeed.

Users perceive workflow file examples as useful for learning, and critically, saving time - as reported by 19/21 participants in Garijo et al(2014). Examples that naturally cover your softwares end-to-end workflow or process help users become comfortable and begin using your software via real examples of cofigurations, which helps them become exposed to your required paramters (Procter etl al, 2009)  and valid samples without needing to start from scratch - a real usabiltiy difference. Multiple different workflow configuration files can the different capabilities/options that are typical, which can function as useful documentation/templates (Procter et al, 2009)

__For multiple workflow files/complex workflows, read about [Cookiecutter](https://github.com/cookiecutter/cookiecutter) and read these [10 rules](https://journals.plos.org/ploscompbiol/article?id=10.1371/journal.pcbi.1010705) principally based on case study workflow software by Roach et al. (2022)__



# How to alter your workflow to be usable:
## Keep cognitive load low - try to avoid having too much on the screen for any one "task" within your application
- When unsure of layout or order, review existing popular scientific software and use similar approaches to help you decide.
- It can be tempting to view our software as completely new, and be inventive with the interface; this can work and innovate, but in that case keep the non-innovative parts/windows standardized.
 Hide Advanced Options for workflows is best practise to avoid overwhelming users (Queiroz et al, 2017) - if you show them too many options they cannot comprehend and effectively use them, and sometimes are totally unaware of the best options/feature for their task, see Karlovská (2023) and Procter et al. (2009).
- For example, for PanSeg:
Advanced options irrelevant to most users are hidden behind a toggle, communicating that they can be ignored if one does not understand them. To prevent the user getting stuck with the basic options, the documentation of the advanced options is always linked in each section of PanSeg.

# Support quick user actions
By adding keyboard shortcuts or default data for sensible domain defaults (e.g. resting mV potential of neurons)

# Make your software reasonably installable and keep resources accessible
## **Can users access your software?:**

As covered in the [general guidelines](../general/README.md), make your research reusable and accessible, use version control and provide user guidance.
- 99% of scientific codebases shared via GitHub links in papers were accessible in a review paper, while only 72% of non GitHub/SourceForge links were (2000-2017). This paper found this issue is reducing over time, but over 200 papers a year are published with links that by time the researchers checked, were inaccessible over a multi year period (Mangul et al, 2019b)
- --> unless you have a reason not to, consider [GitHub as the place where you save your code](../general/README.md#continuous-integration-ci--continuous-delivery-cd) for others to use 

## **Can users install your software?:**
- 49% of scientific software projects were not installable within 15 minutes(Mangul, 2019b)!
- --> **Test Installability itself separately to normal application-use [user tests]**(../user_testing/README.md) **on users or fresh devices**; modern installation techniques can save time. Software people cannot install will not be shared or help your goals, regardless of how much of a step change or benefit it is to the field. .
- --> Run CI tests with different operating systems on such as GitHub which install your package release (e.g. Our SSC C++ [Cookiecutter template has a GitHub action that tests across operating systems](https://github.com/ssciwr/cpp-project-template/actions/runs/28781039589/workflow))
  ![img.png](img.png) ![img_1.png](img_1.png)
