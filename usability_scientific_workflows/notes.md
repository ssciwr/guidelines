### These are notes. In_complete is the draft file.


Help users interpet options and outputs as they edit them
Users who cannot confidently say what a feature or option does ignore it; even features you may prioritise as top or unique features migth go unused.
Help users understand what a feature does if it is key in your conception of the UI.
Undertake user interviews and try to find frustration points:

### Growing your user base
- Note for increasing user base to wider audiences, you need to be mindful to take the perspective of real users to understand how they see your software - we have expert blindspots ourselves which make our software very easy and very reliable for us - because we walk the same trodden path with the same situations and data.
- When appropriate telemetrics can help you find bottlenecks/crash points.



### Decide on features this way:
- Can this be a separate interoperable project? - Coupling
- Can this be a small feature on one part of a process or must it be constantly accessible? The former, polish like adding an export option to export as a "Croissant file", has far lower potential complexity and negative ramifications than a new tab with new functionality visible from all pages in the application
- Does a third party tool already implement this feature with the output my project provides?

### If you feel stuck on usability:
Common usability rules are not as applicable - rules writetn for mobile apps are not directed at scientific apps where many configuration options, small options and many steps are necessary for usefulness.

Instead measure from users:
Is it now your usability, the efficiency of the programme, or the scientific capability which limits users? and work on what is weakest.






---
### Previous guidelines bit:



guidelines:

try to avoid describing what soemthing does or how to start to soembody testing

overemphasize listening and holding back,  try not to interrupt

make sure you're happy with how it can feel, but asking for what is worse - and what is best - tends to get great specific ways you can improve the interface. People agree about whats currently bad more than about what an application should be

collate issues and avoid making committment (stakjeholder dependent) right upon receiving ideas. Avoid making it an everything software

remember iti s easier to vary something like colur simplicity, then to ask someone if something "would be better" if you changed it

where possible test demos (especially with AI now), do not send screenshots. How an applications loads, what shows first, what you can interact with are too important to describe as "And this is the main view after you show the data"

More regular user feedabck sessions with completely novel users result in more actionable and high end results than gaps and longer sessions with users who have already been using your designs - try to involve othe rresearchers, researchers from other insitutions in your testing


---

Workflow files:

Workflow execution makes your sfotware be perceived as more reliable, regular and gives a way to save experiemnts in a way users can be confident in declaratively.

Hve the configruation file be terse, readable and it's own file apart from the application code (e.g. YAML or JSON)
Try to avoid splitting configuration across files

For examples and documentation, share multiple  different workflow/config files, with one as simple as possible. [add source]

Be clear what parts of your application or pipeline workflows or configurations do

Provide obsevability to completion percentage or run time for long running tasks or batch jobs (i nthe UI as well)

A nice way to prompt configuration is to offer users the ability to "save the experiment" when exiting. THis fits normal UI patterns.


---

UI basics:

colour complexity language spacing 00> order of interactive elements
get feedback (link other guidelines)
one next thing/keep screen simple if it can for a given purpose

for sceintific UIs, keep it and settings visible as well as the stage

---
# Feature Fatigue
Sounds good, but not really so much research behind it (Except that cognitive load can be increased, or that some users are unaware of advanced features Karlovská (2023) and Procter et al. (2009))
I think it can be conflated with users being disgruntled by design chagnes "Learnability" for highly-used software.
I don't think it is an important point to make as other points already make you think about maanging features and usability of those features and their cognitive load.


---
### More workflow notes:
Workflow support
Enabling users to configure and save a workflow means they can batch, rerun or vary their experiments with high trust. The way workflows operate declaratively feels intuitive to some researchers (particualrly working with simulations or processing).

A way to enable workflows is supporting yaml or other configuration files where users specify exactly what parameters to use and sometimes input/output data sources

The other benefit to your software is propagation to grow the user base:

A workflow lets users explain the various processes, input/flows without an overhwelmingly GUI.

Generally users come in two ways: Somebody is told to use the tool (this is the case for most of the first users, as tools are custom built) - for these we need an efficient way to start.

And two - somebody finds your tool clear enough to get started with that they use it.

A workflow file thye can use as a springboard operates like an example. It menas one researcher can send another their file and the other person only needs to run that workflow, not understand this GUI


For us as software developers - for you as a domain researcher - labelling tabs "PReprcoessing, processing, postprocessing", makes perfect sense. It describes exactly what is going on and the actions in each steps are logical. But to a new user, they may use other software using the same terms. What differs between those steps is not always clear. Sidestepping the menu/need for a GUI with a workflow file - letting them read from the **example** in the workflow itself having preprocess: collect bboxs, process: run model etc - lets them "grep" the way the osftware works from the safe point/feeling of a running example

This helps you bridge the gap between what you find hard to explain (to someone who to the software or field


---
# Why is user testing/usability not always carried out for scientific software?

1) Publishing a paper is in some senses a one moment in time event
    - Sometimes requirements are to have resources available (reviewers may not need to check they are actually installable --> Software ends up accessible but not installable)
    - Sometimes links decay and stop working; but unless a software is very popular, the authors may not be made aware
2) By contract commercial software ties usability and feedback form users into the "Product development" process/loops
    - Revenue being directly linked to user retention etc and larger scales of users (for succesful companies) means A/B testing etc has value to them and they invest resources. There is no equivalent easy (and necessary) to quantify value for scientific software.
    - Whereas for science, it needs to be (A) argued for typically upfront in the grant funding model, (B) conducted despite many other pressing priorities for the given researcher
    - It is hard to show empirically that the same benefits of usability/AB testing apply for scientific software (Though there are studies cited in these guidelines about perception, saving time and surveys showing that popularity is associated with usability in some sub fields)
That is how we can know that usability of most software being improved can have benefits for users, but some scientific user does not focus on that



# And relatedly: How can we convince scientists or present to them benefits from usability?
1) If their software pushes their sub domain forward (e.g. for a certain kind of experiment or to measure a certain concept or simulate a certain class of problems), being the one to steer it brings scientific social capital and impact(evidence?)
2) If their software is not usable, others cannot replicate their results or build off them, as easily - less people may engage with them
3) Usable software helps with a major science specific problem: relatively high turnover of people in lab/groups due to how academia tends to function: "onboarding" or bringing people on to projects is hard. Usable software with examples can be more learnable(evidence?), and definitely operated faster (24% dekstop speed up) - and this affects their group/labs ability to conduct research faster. This I want to collect more opinions on.

---
# The objectives of the Usability Scientific Workflow Guidelines:
1) Convince researchers to establish workflow configuration files for suitable software
2) By clarifying in their terms what is useful (Easier for non-programmers to use, saves time, better scientific FAIR principles/reuse) - citing relevant studies
3) Suggest several specific qualities of those files and how those can be implemented with some examples

-- Problems for now: I mention the example role/learning part of workflow files (Procter 2009) several times in different places including
the guidelines below and teh advantages/why part: it should be in one, or the other.