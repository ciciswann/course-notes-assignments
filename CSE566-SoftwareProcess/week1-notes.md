# Week 1 
14 readings this week 😧

* [Software Development History](#software-development-history)
* [Software Development SOA](#software-development-soa)
* [Successful Software Projects](#successful-software-projects)
* [Waterfall Model](#waterfall-model)
* [Incremental Model](#incremental-model)
* [Time Box Model](#time-box-model)
* [Readings](#readings)

#### Software Development History
* Complexity factors of software development: High cost, Difficult to manage, Poor reliability, Lack of user acceptance, Difficult to maintain

#### Software Development SOA
* Current state is still there with the same challenges as mentioned above
* **High cost** - software development is labor intensive, software productivity rates for engineering are around 1 loc (lines of code) per hour
* Off The Shelf Software and Hardware costs have both dropped dramatically overtime
* **Difficult to Manage** - software projects are difficult to estimate, plan, and track, many projects are late and over budget
* **Poor Reliability** - software defect rates are around 1 delivered defect per thousand lines of code, with applications spanning millions of line of code, customers experience many defects
* CRUD (Customer Reported Unique Defects)
* **Lack of User Acceptance** - In the "old days", customers tolerated a lot of cryptic interfaces (e.g. JCL), Today the success of a project is often a function of its GUI
* **Difficult to Maintain** - Despite advances in languages and methodologies, software is still difficult to maintain, maintenance requires both knowledge of the cose as well as the application domain
* **Time to Market** - software takes too long 

#### Successful Software Projects
* Perspectives on Successful Projects: (Two) what is a successful project from the perspective of the customer (on time, on budget, works-meets req, quality), what is a successful project from the perspective of the development org (profitable, didn't burn out team)
* Statistics - 26% of all software projects fail, 46% experience costand schedule overruns or significantly reduced functionality
* Symptoms of Failure - early: lack of project plan, lack of stakeholder communication, no external involvement of quality organization, project changes are managed poorly, deadlines are unrealistic, lack of understanding of user needs, project's scope is ill-defined, project lacks appropriate skills, best practices are ignored
* fatal symptoms: excessive hard work, high staff turnover, aggressive and defensive behavior, no fun
* critical success factors in software projects: start on the right foot (70% of dooming acts occur before a build ever starts, build the right team, give team what they need), maintain momentum (keep attrition low, monitor quality, manage the product not the ppl), track progress, make smart decisions, do lessons learned (post mortums, retrospectives)

#### Waterfall Model
* A software dev process model defines the steps that must be taken in developing the product
* each step must be **well-defined activity** with entry and exit criteria (when can i start, when can i end)
* intermediate work products are typically generated as a consequence of many steps
* metrics may also be gathered during each step (process or product)
* major life cycle models: waterfall, incremental
* "Documentation driven"
* Proceeds thru a sequence of phases: requirements, design, code, test
* a phase must be fully completed before the next phase may begin \
![image](https://user-images.githubusercontent.com/17733481/159184942-08377799-b536-4c1c-b466-6b9b69f682e9.png)
* Advantages: easy to plan, easy to track
* Disadvantages: hard to accomodate changes, cannot begin until all the of the reqs are defined (takes too long)

#### Incremental Model
* Constructs the software as a series of builds or increments: sequential, concurrent
* Sequential development occurs in separate increments or sequences, whereas concurrent development occurs with multiple increments being built at the same time
* each build contains a set of capabilities of the end product
* Sequential incremental - each increment is its own mini waterfall \
![image](https://user-images.githubusercontent.com/17733481/159185221-d2f0e531-0df2-45b9-ae9a-d3d75753f286.png)
* Regression testing is added in the next increments at the end
* Concurrent incremental - see significant speed ups \
![image](https://user-images.githubusercontent.com/17733481/159185304-d9242a52-176f-4e93-a8d4-0be601f03f62.png)
* Question: If all the requirements for a project are known in advance and some changes are made to those requirements later, which model is faster? (Answer: Incremental bc the testing phase in incremental development happens at the end of each increment so changes are flexible and are easier to make. For the waterfall model, changes could be costly and time-consuming.)
* Disadvantage: Potential rework, if the customer decides to change requirements that already exist or were built in, the potential rework could be costly - try to minimize with a flexible architecture
* Advantages: development can begin without knowing all the reqs in advance, easier to accomodate changes, customers may get earlier releases

#### Time Box Model
* Agile approach
* Team continuously identifies and prioritizes work to be done
* work is organized into a time box (usually 2-4 week interval): in each time box a few reqs or use cases are implemented, risk based strategies can be used to determine the order fo implementation
* produces a documented, tested executable at the conclusion of each time box
* Advantages: do not need to know all of the reqs in advance, easy to accomodate changes, speeds up the development process and shortens the delivery time
* Disadvantages: risk of rework
* Extreme Programming - pair programming, collective ownership, continuous testing, small releases, on-site customer, continuous integration, refactoring, metaphor approach to documentation

## READINGS 
#### Agile Software Development: An Overview
* Agile includes a group of software development methodologies: Scrum
* Agile manifesto - ppl interactions over processes and tools, working software instead of documentation, customer participations, embracing change
* Early and continuous delivery
* emphasis on teams \
![image](https://user-images.githubusercontent.com/17733481/159186112-8c6ab081-a0c3-4390-a318-c7483236080d.png)
* each iteration consists of: planning, reqs, analysis, design, implementation, testing, evaluation
* Potential limitations: limited support for distr. environment, limited support for subcontracting, limited support for building reusable artifacts, involving large teams

#### Scrum is Simple!
* Scrum is applied to many types of projects (1986)
* The product backlog created by owner: prioritized list of tasks driven by the customer, product backlog must be groomed
* Sprint or iteration backlog: list of tasks to be addressed in the next sprint, task duration is 4-16 hours of work
* Tasks are selected by team members - derived from decomposing tasks on the product backlog 
* Taskboard shows work in progress (updated by team members) - final column is what work has been verified by product owner
* Sprint burn down chart - displayed in plain view, shows work completed and work remaining in the sprint backlog, updated daily
* Scrum roles - product owner (voice of the customer, writes user stories, prioritizes user stories in backlog), Scrum Master (protects team from distractions, leads process), Team (self-organizing and self-managing)
* Scrum activities - daily scrum
* High level agile planning artifacts (sprint zero) - product vision, product roadmap, release plan
* Sprint planning at beginning of each sprint - first part done by product owner, team needs to be calculating their velocity
* Sprint review at end of sprint
* Sprint retrospective - making changes for the next sprint

#### The Scrum Guide
* Values - commitment, focus, openness, respect and courage
* primary focus to accomplish the sprint
* Product owner must articulate the product goal: future state of the product, long term objective for the scrum team
* Scrum roles
* events - sprint is a container for all events, sprint planning addresses three topics: why is the sprint valuable? what can be done? how will the chosen work be done?
* sprint review
* sprint retrospective
* Increments are concrete stepping stones toward the product goal: definition of done is a formal description of the state of the increment when it meets the quality measure required for the product

#### Daily Stand-Up Meetings
* Benefit - team cohesion and shared commitment
* How 15-minute meeting should be help - lots of variation
* 3 questions - what did i do yesterday (2/3 of meeting consisted of this question), what will i do today, do i see any impediments
* Proportion of topics - 34% of 3 questions and 31% problem issues and possible solutions
* Main criticism is that it was mostly reporting
* Recs - Stop asking what you did yesterday (minimize it), optimize communication patterns, meet at a least disruptive time

#### Why is Sprint Zero a Critical Activity?
* It creates an outline of critical reqs, estimates, activities, roles, and processes
* Key activities - definition of roles, list of priorized features along with estimates, release plan
* Crucial deliverable is the list of prioritized features along with estimates

#### Is Your Software Valueless?
* Software dev ignores human values - tradition, security, power, achievement, benevolence (social justice)
* Prioritize product backlog - possibly include human value
* Participatory design methods help with values
* consider values guardian to assist with identifying value stories

#### Hybrid Software Development Approaches in Practice
* Any combination of agile or traditional plan driven or rich approaches that organization unit adopts and customizes it to its own context
* Most use code reviews, code standards, continuous integration
* Methods - how software is developed over the whole lifecycle e.g. scrum, extreme programming 
* Practices - tasks or activities with a specific focus used within methods e.g. pair programming
* Each approach was categorized as a method or practice within tradition, agile or both
* According to the reading, refactoring is a practice only found in agile
* What are the major motivating drivers for involving hybrid approaches? 
   * Client constraints, company constraints, business constraints, operation and flexibility

#### Top 10 Adages in Continuous Deployment
* Continuous Deployment - automatically testing pincremental software changes, frequently deploying them to production
* **Dark Launching** - deploying code into production and testing the features in a live environment that is invisible to the users
* 1- Every feature is an experiment
* 2- The cost of change is dead - cost of changes decreases dramatically overtime
* 3- Be fast to deploy but slow to release
* 4- Invest for survival
* 5- Your are the support person
* 6- Configuration is code
* 7- Comfort the customer with discomfort
* 8- Looking back to move forward
* 9- Invite privacy and security in
* 10- Ready or not, here it comes

#### The DevOps Phenomenon
* Development Operations
* Shift to product-based management and delivering features continuously
* Continuous development on a product means that the software development process has no "end date", and the product is always updated with new features or software
* CALMS - Culture - cross-functional teams, Automation - deployment pipelines for continuous integration, Lean - shortening feedback loops, Measurement - monitoring metrics, Sharing - share knowledge

#### How to Make 100 Releases per Day with Only 6 Quality Engineers
* Wayfair releases software hundreds of times per day using best practices:
   * we analyze reqs - key stakeholders review for completeness
   * we use static code analysis, vulnerability scanners, and code reviews
   * we write unit tests
   * we automate only what matters
   * we provide training and coaching on what, why, and how to test or automate
   * most of our test run in isolated environments
   * visualize health of the product
   * enable continuous delivery through deployment pipelines
   * incremental rollout of big features
   * constantly monitor applications
   * if something goes wrong, rollback the changes
  * Code smells - not up to quality and need to be refactored

#### The Future of DevOps

#### Debunking Agile Myths

#### Lean Software Development Principles
