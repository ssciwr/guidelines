# Usability and Design Guidebook for Scientific Software

Start by checking whether users can complete a real scientific task without your explanation. Arrange the interface around that task, make the current state and next action clear, and provide a way to recover when something goes wrong.

You already know which inputs to choose and which buttons to click. Other users may follow a different route, use unfamiliar data, or misunderstand terminology that seems obvious to you. Use the advice below to review your interface, then conduct [user testing](../user_testing/README.md) to find the problems specific to your software.

Improving design and usability can **save users time** . In the Basic Laboratory Information System, redesign reduced desktop interaction time by approximately 24% ([Park et al., 2019](https://www.itu.int/dms_pub/itu-t/opb/proc/T-PROC-KALEI-2019-PDF-E.pdf#page=97)). The GRASS GIS redesign also shortened successful data-import tasks ([Karlovská et al., 2023](https://doi.org/10.3390/ijgi12090376)). You can bring direct benefits if you plan in your lab to use this software repetitively, and are also able to get more users.

## Help users complete their scientific task

### Follow universal design principles

Use [Nielsen's ten usability heuristics](https://www.nngroup.com/articles/ten-usability-heuristics/) to review your interface's consistency, familiar terminology, error prevention, and user control. They also cover system status and errors explained in language users understand. Apply them to your users' scientific tasks.

![Nielsen's usability principles](../assets/images/nielsensPrinciples5.png)

Above: A selection from Nielsen's ten usability heuristics, originally published in 1994 and subsequently updated.

### Arrange controls in the order users expect

Arrange inputs, actions, and results around the user's scientific workflow: loading data, choosing parameters, running an analysis, and inspecting results. Make main buttons visually prominent to guide users through the process.

Review whether the layout reflects the user's task or the order in which you added features. Place familiar actions where users of similar software expect to find them.

### Align the technical approach with scientists' domain models

Make your softwares classes/data model match the real domain scientists' models of their work. This can bring major usability benefits, making scientific software and workflows more familiar and fluid to use. In OMERO, scientists preferred adding labels as they viewed images to creating a category hierarchy in advance. Supporting tagging aligned the software with how they understood and organised their data, enabling more fluent use of their scientific workflow ([Macaulay et al., 2009](https://doi.org/10.1109/MS.2009.27)). This also fosters strong collaboration and goodwill from the users to use your software.

### Give users a working example to start from

Provide sample data or workflow configurations files, and a short example taking users from input to a recognisable result in documentation. Show the expected result and which settings they can change next.

### Offer valid and suggested input options

Provide autocomplete or selection controls for known valid options. For example, suggesting genes present in the selected dataset when the user types their first letter in the text input.

For workflow configuration files, provide a schema that supports suggestions for valid parameters and values. See the [scientific workflow guidelines](../usability_scientific_workflows/README.md) for more advice on configuration files.

![Autocomplete offering available options](img.png)

### Make the current state and next action clear

Show the selected data and settings, whether an analysis is running, and which inputs produced the displayed results. Make the next action easy to identify.

If a process has distinct stages, group the relevant information and controls by stage. Keep information needed to compare inputs or results visible together.

### Update results reactively when computation is quick

When computation is quick and cheap, update results immediately as inputs change. For example, let users drag along a timeline to compare measurements across days. This makes exploration more fluid and keeps results aligned with the selected inputs.

For an expensive analysis, provide an explicit action to start it and show its progress. If inputs change after a run, make it clear that the existing results came from the previous settings.

![Timeline control for exploring data across dates](img_1.png)

### Let users undo and go back

Provide a consistent back or undo action so users can revise choices and continue their task. Preserve inputs that remain valid. This follows Nielsen's [user control and freedom](https://www.nngroup.com/articles/ten-usability-heuristics/#3-user-control-and-freedom) heuristic.

When an input is invalid, explain what needs correcting and provide a route back to it.

A back or undo action can turn "I quit" into "That wasn't what I expected, but I could still complete it".

## Make the interface clear and consistent

### Show the information needed for the task

Group related inputs and separate groups with space and clear labels. Use size, position, and emphasis to highlight the main action and the information needed to proceed.

Put advanced options behind a clearly labelled button so users can open them when needed.

[Harper et al. (2009)](https://doi.org/10.1145/1498700.1498704) linked perceived visual complexity with cognitive effort. Clear grouping helps users focus on their task; keep scientific inputs visible together when the task requires it.

### Reuse consistent design components

Use consistent fonts, spacing, borders, and button styles. Reuse your project's established components and layout patterns, including those provided by its design library.

Review the whole interface after adding features, including those generated with AI assistance, so each section follows the same design.

[Lee and Koubek (2010)](https://doi.org/10.1016/j.intcom.2010.05.002) found that aesthetics affected preference for simulated applications before use; after use, both aesthetics and usability mattered. Give attention to both appearance and ease of use.

Before applying consistent button styles:

![Primary, Secondary and Success buttons before styling changes](../assets/images/buttons-before.png)

After applying consistent button styles:

![Primary, Secondary and Success buttons after styling changes](../assets/images/buttons-after.png)

### Make different actions easy to distinguish

Give primary, secondary, and destructive actions distinct, consistent appearances. Group related actions to make their purpose clear.

Use familiar icons for actions such as opening or saving a file. Keep clear text labels for scientific actions whose meaning an icon may not convey, and combine colour with labels or symbols to communicate state.

## Review usability as features are added

### Revisit the layout after functionality changes

We are naturally drawn to add features: each new feature is useful to somebody. But **more capabilities does not equal more usability**. [Thompson et al. (2005)](https://doi.org/10.1509/jmkr.2005.42.4.431) found that consumers gave more weight to capabilities before using a product, and more to usability afterwards.

As features accumulate, extra controls and choices can increase complexity and cognitive load. Users have more to understand and hold in working memory just to complete their task. Keep inputs needed for the scientific task together, while moving less-used options out of the main path.

**Without noticing it, by adding, we can reduce overall usability** - since we use our software with the same habits, we may miss these difficulties. [Lee et al. (2006)](https://doi.org/10.1177/154193120605002410) discuss this growth in complexity. Their conceptual illustration below shows how overall "fitness" can decline, requiring time and effort to simplify the design.

**Plan user testing and usability improvements during development, not only at the end**. After functionality changes, review whether the order and layout of controls still match what users expect. Reorganise the interface, or simplify or remove features whose complexity outweighs their usefulness. The OMERO team used a weekly develop-and-evaluate cycle to adjust the software from user feedback ([Macaulay et al., 2009](https://doi.org/10.1109/MS.2009.27)).

![Conceptual illustration of fitness changes after simplification (Lee et al., 2006, Figure 3)](../assets/images/lee2006-fitness-after-simplification.png)

Research references are in the [bibliography](citations.bib), with the OMERO reference in the [user testing bibliography](../user_testing/citations.bib). See the [scientific workflow guidelines](../usability_scientific_workflows/README.md) for highly configurable workflow software.
