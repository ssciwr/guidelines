# Guidelines for Scientific software for processes/workflows
Our principal advice is to make your software runnable with a workflow configuration file, rather than manually entering inputs in a Interface(a GUI).

**Workflow configuration files, such as .yaml files,** can help users declaratively save their workflow configuration in your software for their research, which means the same workflow with the same data can produce the same results later
This saves time Garijo et al (2014) and helps users become comfortable and begin using your software via examples that help them engage with it (Procter, 2009)

## Keep cognitive load while creating workflows and templates low
- When unsure of layout or order, review existing popular scientific software and use similar approaches to help you decide.
- It can be tempting to say our software is completely novel/unique and invent quite widely; this can work but then try to keep the non-innovative parts/windows standardized.

### Such as in PanSeg, when creating workflow configurations for Batch Processing
In PanSeg, a workflow is created interactively by working through one example input. Each decision gets recorded, and after exporting the result of processing a single file, the user can export a workflow script. This workflow script can then be applied to a whole batch of inputs. This process gives the user confidence in their decisions by providing immediate interactive feedback. Also, the user is guided through the process by taking care which options are visible at what time to not overwhelm them.

You remove the manualy and finnicky limits of a UI by offering a workflow.

Users perceive shared workflow files as useful for learning, and critically, saving time - as reported by 19/21 participants in Garijo et al(2014).
This can be intimidating than exploring inputs and options and needing to provide values.

Users who see examples can **learn you programmes capabilities** from the content of workflow example file has as inputs and then what it produces. You can also reproducibility of workflow results and reuse of your software for new experiment directions.


# Workflow files 
- Save workflow files in readable formats like yaml which are human readable to scientists in many domains
- Use one single file for each workflow concept - To support re-use and user confidence, rerunning should generate the same result (outputs should be saved separately to workflow configuration), which is much easier without dependency on other files (Procter et al, 2009)
- Very simple usability can be sleekily achieved by published JSON schemas for workflow config files - e.g. in the KIMMDY project
This provides incredible usability as Users can see possible valid options and choose them with IDEs link VisualCode + JSON scehma validators
- Hide Advanced Options for workflows to encourage early use: For example, for PanSeg
Advanced options irrelevant to most users are hidden behind a toggle, communicating that they can be ignored if one does not understand them. To prevent the user getting stuck with the basic options, the documentation of the advanced options is always linked in each section of PanSeg.
- Provide multiple complete runnable example workflow files. These should express the different capabilities/options that are typical to jump start using your software and function as useful documentation/templates (Procter et al, 2009)

## Make your software reasonably installable and keep resources accessible
As covered in the general guidelines, share your research -
Installability: 49% of scientific software projects were not installable within 15 minutes(Mangul, 2019b)!
- **Test Installability itself separately to normal application-use [user tests]**(../user_testing/README.md) **on users or fresh devices**; modern installation techniques can save time. Software people cannot install will not be shared or help you goals, regardless of how much of a step change or benefit it is to the field.
- This is very important for workflow software.
- The world is missing out on your software if you create something specific and novel, but it simply only works on your machine and has no installation support or runs into installation errors on current set ups
- You do not need to pay for subscriptions to test your software - the easiest first method is to use CI with one main typical user operating system to automatically install/build your software upon version updates to ensure it can be installed (CI guidelines todo here link to general guidelines?)

99% of GitHub links remained acccessible in a review, while only 72% of non Github/SourceForge links were (2000-2017) a reducing problem but with over 200 papers a year being published with links that by time of the survey were inaccessible(Mangul et al, 2019b) - unless you have a reason not to, consider GitHub.
