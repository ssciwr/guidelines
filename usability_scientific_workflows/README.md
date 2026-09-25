# Guidelines for Scientific software for processes/workflows
Our principal advice is to make your software runnable with a workflow configuration file, rather than manually entering inputs in a Interface(a GUI).

**Workflow configuration files, such as .yaml files,** can help users declaratively save their workflow configuration in your software for their research, which means the same workflow with the same data can produce the same results later
This saves time Garijo et al (2014) and helps users become comfortable and begin using your software via examples that help them engage with it (Procter, 2009)

### Enable batch processing for faster processing - such as in PanSeg
In PanSeg, a workflow is created interactively by working through one example input. Each decision gets recorded, and after exporting the result of processing a single file, the user can export a workflow script. This workflow script can then be applied to a whole batch of inputs. This process gives the user confidence in their decisions by providing immediate interactive feedback. Also, the user is guided through the process by taking care which options are visible at what time to not overwhelm them.

You remove the manualy and finnicky limits of a UI by offering a workflow.

Users perceive shared workflow files as useful for learning, and critically, saving time - as reported by 19/21 participants in Garijo et al(2014).
This can be intimidating than exploring inputs and options and needing to provide values.

Users who see examples can **learn you programmes capabilities** from the content of workflow example file has as inputs and then what it produces. You can also reproducibility of workflow results and reuse of your software for new experiment directions.


# Guidelines
- Save workflow files in readable formats like yaml which are human readable to scientists in many domains
- Use one single file for each workflow concept - To support re-use and user confidence, rerunning should generate the same result (outputs should be saved separately to workflow configuration), which is much easier without dependency on other files (Procter et al, 2009)
- Very simple usability can be sleekily achieved by published JSON schemas for workflow config files - e.g. in the KIMMDY project
This provides incredible usability as Users can see possible valid options and choose them with IDEs link VisualCode + JSON scehma validators
- Hide Advanced Options for workflows to encourage early use: For example, for PanSeg
Advanced options irrelevant to most users are hidden behind a toggle, communicating that they can be ignored if one does not understand them. To prevent the user getting stuck with the basic options, the documentation of the advanced options is always linked in each section of PanSeg.
- Provide multiple complete runnable example workflow files. These should express the different capabilities/options that are typical to jump start using your software and function as useful documentation/templates (Procter et al, 2009)
- When unsure of layout or order, review existing popular scientific software and use similar approaches to help you decide
- As in the [general guidelines](../general/README.md) cover make your software installable, enable issue(bug/idea) tracking and make them run the same on different machines. Versioning can be more important for workflow software/files.
