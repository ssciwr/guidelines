## Usability and Design Guidebook for Scientific Software

An overview of common ways to improve your software usability and design covering different sub-types of scientific software, common findings from providing UI feedback to scientists at the UI. Good usability can **saves users time to conduct tasks** (24% on Desktop in Park et al (2019), and good design increases satisfaction, perception of use and contributes to usability.

My experience creating a consumer app with thousands of monthly users was that the rate who would **retrun to use again** and to **purchase subscriptions** could double after applying usability principles, improving design, and making flow changes based on [user testing](../user_testing/README.md))
User responses are not uniform - design is extremely important. For example in this question for a consumer app which I designed, a large difference. Implementing differently to user expectations could lead to higher cognitive load, and certainly appears in rentention/usage rates.

(maybe remove or only keep RSE point)
Software behaviour is a major component of scientific software and a RSE skill. Generally we are unforgiving to software: if it behaves inconsistently (makes an error or miscalculation) we are reticent to use it ever again, and if we are confused, we want to avoid it. The problem is, the way you use your own software may differ from other users: they may encounter problems you don't. Some of these can be avoided by following best practise principles described here and established interface design and usability research; others can only be unearthed by tests.

The most important [actionable design guidance for general usability](#good-design-requires-consistently---use-a-design-kit-for-that) in scientific software

General Usability actionable advice: [usability heruistics](#usability-heuristics-for-software) for our direct actionable guidance.

Workflow scientific software advice: [Workflow/Complex Scientific Software](../usability_scientific_workflows/README.md)

For existing projects you have became aware of needing to manage issues read about [maintaining usability ](#how-usability-issues-grow-over-time).


### What is usability for scientific software?
Usable software saves times for new users which can make research proceed faster. Usable software achieves the goal of the user with the execution and interaction of the software mapping and working with their modelling of their scientific domain and what they want to achieve.

More usable software increases productivity of using your software, **saves users time to conduct tasks** (24% on Desktop in Park et al (2019) for the "Basic Laboratory Information System" software).

Part of user testing is finding **what is confusing the user or frustrating them** - these seconds of being unsure or what is unsmooth make an incredible difference for how many people will share and enjoy your software (which helps them recommend it).

Different usability techniques apply to extensive/[highly configurable workflow software](../usability_scientific_workflows/README.md) (batch/experiment running/simulating), from other applications (e.g. data exploration/dashboards)

As the software creators (and as experts), we often overlook something instinctive to us which is confusing to newcomers. And we confuse that what is correct/functional is usable.

And especially **for research**, you have the opportunity for you and your users to **build (scientific) social capital*** and become important for moving your field forward faster than it otherwise would, technologically.

We want to bring the software closer to what the user expects and to be easier to understand and operate.

### Usability Heuristics for software
A close-to-timeless resoruce for user interfaces is [Nielsens 10 Usability Heuristics](https://pdfs.semanticscholar.org/5f03/b251093aee730ab9772db2e1a8a7eb8522cb.pdf) (Nielsen, 1998 & 2005), 5 of which are paraphrased below:
![Nielsen’s usability principles](../assets/images/nielsensPrinciples5.png)

### Specifically beneficial for scientific software
**Autocomplete** with valid options (e.g. genes analyzed in a dashboard graph tool, or [auto-suggesting valid options for a workflow configuration file](../usability_scientific_workflows/README.md#todo)) consistently improve scientific interfaces we work with.
![img.png](img.png) Above: Provide autocomplete available options


**Adjustable dials that react instantly - reactive outputs**
We common see scientists, even when prompting AI, create interfaces where one first sets many values, then clicks a button, and then sees the results.
While this flow is valid, seeing instant changes/results is an upgrade

![img_1.png](img_1.png)
Above: A timeline you can drag allows users to move along data points to see differences in their working memory rather than needing to choose each date.
<!---
better would be a GIF, perhaps of SMART RODENT where one can scroll through each day?
-->


### What is Design for scientific software?
Design is about prioritising information. WE all struggle with high cognitive load, but bad design or high amounts of visual information in your interface can increase cognitive load (Harper, 2009)

if your application has a view that is too complicated, it will become unusable for new users, which can reduce usage, and design can often benefit it strongly.

We can apply rules to our use of use colour, spacing and information correctness/appearnace on our software is correct and communicates in ways users understand to help make our software more approachable.
Aesthetic appealing software (using consistent colours)  is preferred by observers - important for when people are considering your software or if it should be supported

![Primary, Secondary and Success buttons before styling changes](../assets/images/buttons-before.png)

![Primary, Secondary and Success buttons after styling changes](../assets/images/buttons-after.png)

Using consistent font, borders and variations on colour transparency/brightness with fewer colour hues) makes the application **feel more usable**, even if the buttons actions, positions and text content does not change

Be consistent with other applications: Use save and folder icons rather than "File -> Save/Load" and place them at the top left on a thin bar. Sometimes without visual indicators that match the model the user has, users do not even know that action is possible, a common finding in usability testing.

Design is important for usability because it covers the perception and clarity side. What is unclear we interact with **slower, and with more mistakes**. Improving an application often therefore makes it more usable. Regarding perception, avoiding using old style libraries is also often overlooked by scientists in our experience (e.g. Bootstrap 2 --> Bootstrap 4)



### Good design requires consistently - use a Design kit for that:

Here are three recommended neutral defaults:

- For web applications: [tailwindcss](https://tailwindcss.com/)
- For R applications: [Shiny](https://shiny.posit.co/)/[bslib](https://rstudio.github.io/bslib/)
- For Python: [Streamlit](https://streamlit.io/)/[dash+mantine](https://www.dash-mantine-components.com/)

For further style there are fashions - for usability in science, it is useful not to be too experimental; look at other recent projects to decide.

Remember to use what libraries offer you to help manage cognitive load via design - e.g. R Shiny from Posit offers layout options.
![img_2.png](https://shiny.posit.co/r/articles/build/layout-guide/pages.png)
Above: Page Layouts from [https://shiny.posit.co/r/articles/build/layout-guide/](https://shiny.posit.co/r/articles/build/layout-guide/)

#### Be "consistent" with where users expect to find certain interface objects(e.g. button location)
`This is most common feedback I give to scientists: Review if the order you added interface objects in on the page matches what users expect!`
Often users will not be able to put into words that this is the issue - they can feel a block, be unabel to express, but it does not "feel right". Search out similar software.

On phones, we expect buttons towards the bottom or the right 

(Figure here: common vs uncommon buttons + familiar vs unfamiliar location for buttons)

### How does design have an impact on scientific software?

As well as saving time (Park, 2019) or increasing user productivity, after redesign, scientific software specifically can reduce user errors:
Karlovská et al. (2023), ""Redesigning Graphical User Interface of Open-Source Geospatial Software in a Community-Driven Way: A Case Study of GRASS GIS."”"

Lee and Koubek (2010) found that aesthetics affected **preference for simulated applications** before use; after use, both aesthetics and usability mattered. This supports focusing on **both design and usability**  when designing software.

`The perception of researchers, grant application reviewers can be affected by both usability and design`

### Helping your domain move forward with your software begets usability
**Do you see your software as capable of increasing the pace at which your niche or sub field moves forward?**
Then it is vital that you focus on real user experiences to make it usable to do that!

Add value to fresh beginners with Documentation/examples to make starting easier, Design to make understanding information in your software easier, and testing to make better decisions

### Your application should clarify what is important, the unambiguous, clear and correct system state, and what the user can do next
Design lets you highlight what is key with large size, bold. This is happening by design with almost every advert, every train announcement board, every website - focusing attention "feels" more pleasant than not knowing what to focus on, and influences the perceivers actions.

when you have less UI elements displayed, you can make space around them so the eye is more drawn to them.

If the user is not clear on what to do, it takes more cognitive load for them to user your software. Consumer commercial research shows this leads to more early user abandonment.

Really good software has people spreading positive reputation and awareness of you and your lab because of what it clearly does.

#### Domain-specific steps in your UI in a process --> Lower cognitive load for users

Many scientific workflows are processes; convert these into steps in your interface, and **only show the user relevant information for that step**

To help the user flow through your application, deliberately display only one clear prominent button only with no other buttons competing for it to proceed to the next step.
Provide a consistent "back" or "undo" option so the user does not get into a stuck state (("User Control and Information" - Nielsen (1998, updated 2005)).

### Managing usability and design
#### How usability issues grow over time
We don't have a complete picture effect of experience users have. It is easy to possess and expert blindspot and not realize that a few small changes to suit typical ordering
and to categorise and cordon off functionality so it is clear to use the application could make your tool understandable and usable for many people.

- AI in particular when given many additive features can produce them quickly, but lots of visual space clutters the UI and can make it less usable. For example, AI might use several different colours or types of button which contradicts the design guideline and Nielsens Heuristic to have appearance consistently.
- Users feel intimidated by seeing too much content at once, particularly if it is not clear what is important or "first". 

### Feature Growth - Feature Fatigue
**Based on actual user reviews, more capabilities does not equal more usability (Thomspon et al, 2005)**


### Timing of usability/design changes
Usability does not tend to be worst at the start as discussed above.

Yet, the mid/end part of your project is typically when it feels hard to justify or plan for work packages around usbility:

The problem is often that meeting A has an agenda of:
- Pipeline code decision that blocks everything else
- Data collection progress

Adding "Design feedback/user testing" - which at that point in time is conversely not a blocker to project progress - feels unjustiable

![Fitness changes after simplification (Lee et al., 2006, Figure 3)](../assets/images/lee2006-fitness-after-simplification.png)

Solution 1: **Schedule in advance to a specific date, separately, and with new/other users**

Solution 2: **Show variants early\** on to have fallbacks if changes in the project need different interface/data**

Solution 3: Seek feedback ahead\** of the actual implementation coding/data model decisions so you get feedback on look & feel and the task and can carry that information forward into the real implementation(not as effective typically as testing against the real application)


----

*Scientists contributing workflows were motivated by Social Capital in Procter (2009)
\** Note: Be wary not to overpromise progress - people often connect visuals/designs with "ready" - this is a different project timeline risk.
