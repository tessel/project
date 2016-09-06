Notes: @johnmyman727
Moderator: @frijol and johnnyman727
Attending: @tcr, @hipsterbrown, @rwaldron

Day One:

@hipsterbrown and @frijol would love to bring the start experience into Gitbooks
@frijol points out that Tessel 1 start experience looks just like the T2 and it confuses people
Suggested new goals for 2016-2017:

@rwaldron "Reach is within Reach"
Update the tessel.io website, it's too "business-y", need to change expectations to an OS project. It's not just something for hardware, it's for everyone to get involved in (including designers, web devs who don't have specific interest in microcontrollers). Would be good to also make it easier to put out updates. Change the CTA from "Order" to "Contribute". Include compatibility to J5 and the J5IK. Reconsider the "Trusted By" section. Would be great to be able to have links to educational material (ie Sparkfun's endeavors)
Tessel 2.1, Minor hardware revision: more RAM and Flash: legitimize the platform and build out the capabilities so there is less user experience friction
Research group: What do people need to use T2 in production? Why aren't they using it?
Mesh Communication API: this would open up the use case scenarios and create a differentiating factor for T2 that other platforms just don't have
PouchDB Support: this would get our users the ability to use a legitimate database on T2
T3 where we completely update the chips, memory, etc. potentially shoot for ARM-based, cheaper
FPGA-based alternative
More modules?
Logic Analyzer (building an actual logic analyzer)
USB to module port (including kevinmehall/starfish)
Fractal
Rust API parity, documentation, and JS-Rust inter-exection
Documentation upgrade (fritzing examples, API prototypes, some calls are missing line pin interrupts/pulldowns etc.)
Making CLI extensible to other hardware platforms
Explore possibility of better working with web APIs (like canvas, etc.)
Guide to production-scale deployment

@frijol brings up that maybe we should assemble "Working Groups" for each goal. Encourage weekly meetings to keep folks engaged. Need a team lead for each working group to check in on people

What is the level of detail of the working group? Is the "Rust Working Group" too specific and should we phrase it as the "API Working Group?"
How do we align two first class languages?
Day Two:

Talking about what the high level goals are of the project. Is inaccessibility exclusive to production-ready?
@hipsterbrown points out that the fact that we integrate with existing tools like NPM makes it better at both of the above
"We bring great software platforms to hardware". "We are not trying to build our whole new ecosystems, we're trying to integrate with existing ecosystems"
@rwaldron points out that our choice to use Unix Domain Sockets for communication between Node and the MCU well encapsulates our dedication to using known, accessible tools instead of building tons of custom architecture
@johnnyman727 wants to keep accessibility as a guiding principle but wants to focus on getting people to production. Let's legitimize JS and Rust as production-ready hardware tools.
@frijol asks how much we want to build tools that may not be interesting for folks who are just getting started
@tcr notes that "accessibility" means being able to scope every level of the stack including at the hardware level which is why a logic analyzer tool, may not be interesting to new members at first but eventually could be a core learning tool
@rwaldron has already had a talk with an engineer in the process of building production ready hardware and discovered that we're not far off from being easy to deploy to. Need a good guide to make it clear
"We are trying to provide, OS community-driven ways forward for producing hardware at scale. Democritizing scalable hardware products with OS software" - @tcreate
"The best way to convince someone of a technology is to prove it out in production" - @rwaldron
It doesn't seem that the module system we have can scale very well. We should be making it clear that the modules are a good option for getting started and hackathons
It would be great to have more projects on reverse engineering real products like A/C units
Criteria for goal selection: focusing on projects to prove out scaling the platform. We want more people taking Tessel to production.

Tim proposes: a series of articles/posts/instructables whatever about replacing guts with Tessels. GUTS = Great Uses Tessel in Stuff
We agree that Reach is still a valid and reasonable goal based on the above criteria
@johnnyman727 proposes that we still plan on making the tessel.io redesign a goal based on that criteria. Evolve the website as we prove out the viability of the platform in production
