# Week 7 Notes

### Software Quality Overview
* Software quality is "extent that specific software product attributes of interest to the user are satisfied"
* Quality management is the definition, monitoring, and assessment of development processes in order to achieve product quality as well as verification of conformance of the product to its requirements
* Functionality - what system does and how well it does it
* Customer reported unique defects (CRUD)
* Reliability - probability that service is continuously acceptable for a specified time
* Availability - Probability that service is acceptable when it is requested
* Usability
* Maintainability - post-delivery support refelcting the ability to understand and modify the product
* Portability
* Reusability
* Need to define quality attributes clearly - important to the user
* High Quality Software
  * high quality software is not produced by accident it must be planned from the start of the project
  * quality cannot be added at the end of a project
  * the quality of the product must be monitored throughout its development
  * development processes must be continuously assessed and improved to eliminate the source of quality problems
* Costs of failing to manage software quality
  * unnecessarily expensive projects
  * late projects
  * staff dissatisfaction
  * formation of low expectations for quality
* Benefits of Effective Quality Management
  * known and predictable product quality
  * minimal risk of legal/financial repercussions
  * enhanced reputation
  * less time spent on rework

#### Software Quality: The Elusive Target
* Views of software quality
  * transcendental - know it when you see it
  * user - different users may have different views of quality
  * manufacturing - emphasis on following good process - was the product constructed right the first time?
  * product - based on internal characteristics - product metrics
  * value - addresses tradeoffs of cost vs quality
* McCall Quality Model
* ISO 9126
* Correctness, Reliability, Efficiency, Integrity, Usability, Maintainability, Testability, Flexibility, Portability, Reusability, Interoperability
* Maintainability - the efforts need to make specified modifications on a set of attributes

#### Good Enough Quality: Beyond the Buzzword
* Paper introduce "market-driven" software - CMMI lvl 5 and Six Sigma are not always needed
* Good enough propositions
  * all propositions must be agreed on
  * sufficient benefits, no critical problems, benefits sufficiently outweight the problem, further improvement would be more harmful than helpful
* Good enough quality factors
  * factors to think about when weighing product factors
  * Assess benefits of the Product - identify, likelihood, impact, overall benefit
  * Assess the problems of the product
  * Assess product quality - overall quality
  * Assess the logistics of improving the product (or holding out for something better)
* Good enough Quality Perspectives
  * Stakeholders
  * Critical purpose
  * Time frame
  * Alternatives - competing products
  * Consequences of failure
  * Quality of assessment

### Software Quality Management
* the quality mgmt plan should include:
  * expression of quality objectives in **measureable** terms
  * definition of entry and exit criteria for each development phase
  * identification of quality functions to be performed
  * specification of schedules and responsibilities for performing the quality functions
* Nonfunctional reqs
 * Products can have the same functions but different attributes
 * performance, resource, security, safety
* functional reqs - API
* The House of Quality - correlation matrix, how, what, relationships, competitive assessments, how much
  * what addresses customer needs
  * how addresses design approaches to meet customer needs
  * relationships illustrate the relative relationship of the design approach addresses the customer need (e.g. strong, weak)
  * how much quantifies the impact of the design approach on the need
  * correlation matrix describes the interaction between the design approaches (i.e. complementary, contradictory)
  * competitive assessments provide a comparison of how other companies rank customer needs
* Deriving non-functional requirements
   * Begin by identifying stakeholder concerns and goals:
     * concerns and goals form the basis of functional reqs
   * concerns and goals provide constraints on the system
   * Examples of concerns and goals: system shall be easy to use, system shall enable visualization of traffic scenarios
   * concerns and goals are further decomposed into sub-goals and eventually non-functional quantitative reqs
* Quality Attributes
  * attributes such as maintainability are not operational
  * what does it mean to say the system shall be modifiable?
  * quality attribute scenarios provide an operational and measureable definition of the quality requirement
* Quality Attribute Scenarios - originates from use case modeling
  * a quality attribute specific res with six parts:
   * stimulus: a condition that needs to be addressed
   * its source: where it comes from
   * the environment: the conditions when the stimulus occurs
   * the artifact: what parts of the system are stimulated
   * the response: quantitative and measurable
   * the response measure: how we will measure
* General scenarios
  * patterns for creating quality attribute scenarios
  * general scenarios exist for: availability, modifiability, performance, security, usability
  * general scenarios can serve as a requirements checklist
  * applicability of general scenarios to the architecture tradeoff analysis methods
* Utility Trees
  * used to identify, prioritize, and refine the most important quality attribute goals
  * the most important quality goals are identified at the highest level
  * the quality scenarios are the leaves of the utility tree
  * each quality scenario is prioritized - high/medium/low importance for the success of the system; high/medium/low difficulty to achieve (architect's assessment)    
<img width="479" alt="Screen Shot 2022-04-25 at 1 02 45 🌃" src="https://user-images.githubusercontent.com/17733481/165165825-afaa240d-1e85-4e12-a02d-da58ddb5ac37.png">
* Quality functions
  * measurement
    * appropriate measures must be defined for each of the attributes important to the project to facilitate the monitoring and controlling of project quality progress
    * a plan for capturing the data in a timely manner must be developed  
  * defect prevention
    * standardization
    * checklists and job aids
    * causal analysis 
    * lessons learned
  * defect detection and removal 
    * software inspections 
    * various levels of testing

### Software Quality Assurance
* SQA the practice of monitoring development processes and product development to ensure quality objectives are achieved (tracking)
* numerous guidelines and standards exist
* IEEE Standard 730: Software Quality Assurance Processes - 5.3 **SQA Process Implementation**: 
   * 5.3.1 Establish the SQA Processes
   * 5.3.2 Coordinate with related software processes
   * 5.3.3 Document SQA Planning
   * 5.3.4 Execute the SQA Planning
   * 5.3.5 manage the SQA Records
   * 5.3.6 Evaluate organizational independence and objectivity
*  5.4 **Product assurance activities**
   * Evaluate Plans for conformance to contracts, standards, and regulations
   * evaluate product for conformance to estab. reqs.
   * evaluate product for acceptability
   * evaluate product life cycle support for conformance
   * measure products  
*  5.5 **Process assurance activities**
   * Evaluate life cycle processes and plans for conformance
   * Eval environments for conformance
   * evaluate subcontractor processes
   * measure processes
   * assess staff skill and knowledge
* Measurement - the process by which numbers or symbols are assigned to attributes of entities in the real world in such a way as to descrine them accoridng to clearly defined rules
* Product Metrics - measure of the software product at any stage of dev (complexity of code, number of pages of documentation)
* Process metrics - measure of the software dev process (software coding productivity)
* nominal scale - give names to object - e.g. one can measure the type of program being produced by placing it into a category of some kind such as database program, OS, etc.
* ordinal scale - assign numbers or symbols to object in a particular order but any numbers that maintain that order are equally good (e.g. programmer experience level may be measured as low, medium, high)
* interval scale - assign numbers to objects in such a way that the interval btwn two measured values is meaningful thru the range of values (e.g. mccabe complexity measure)
* Ratio scale - assign values in such a way that the ratio of two measures is meaningful - program of 2000 loc is twice as large as one with 1000loc
* SQA requires careful planning and execution of the plan

#### Evaluating Essential and Accidental Code Complexity Triggers by Practitioners' Perceptions
* code complexity determines the difficulty of understanding code
* code complexity is an emergent property of code that expands due to increasing code elements and interconnections
* code elements: logical (variables, operators, control statements), representational (how code is represented - variable names), evolutional (how many times has code changed or how many ppl are changing code)
* Types of complexity:
  * essential complexity is inherent to the program task and is irreducible
  * accidental complexity arises from non-optimal design and can be eliminated (for ex. variable names)
* influence of complexity trigger (aspects of the code that contribute to increased complexity)
* most triggers are accidental and can be removed
* Figure 1 results - most triggers are accidental and can neutralized - essential triggers are at the top, high levels of influence onn complexity from survey are red/orange area, misleading comments are the highest
* accidental - too-short names, incorrect indentations
* the next three influential triggers are incorrect indentations, logically unrelated tasks, and too short names
* deep nesting and deep inheritance are the next two triggers that have substantial influence on increased complexity
* top 7 triggers are essential but have little influence on complexity -- they reflect current measures
* developers should strive to avoid influential complexity triggers
* essential elements have little influence on complexity

#### Managing Technical Debt
* technical debt - maintenance obligations software teams accumulate as a result of their actions
* software dev teams willing to accum. tech debt can speed up development of functionality by three times
* orgs need to make tradeoffs: accumulating debt vs speed of delivery
* 3 dimensions of techn debt: customer satisfaction needs (demands placed on the team), extent of software reliability demanded by the business, probability of tech disruption (acquiring new software/tech)
* eight scenarios - observe low/low high/high

#### Using Guidelines to Improve Quality in Software Nonfunctional Attributes
* NFAs - different software systems have different NFA priorities - bank has security first, followed by availability and performance
* There are many guidelines that can be utilized to achieve NFAs: architectural styles, design patterns, best practices
* guidelines can have a negative, positive, or neutral effect on NFAs
* guidelines can be:
  * complementary - guidelines positively affect each other
  * overlapping - both produce the same effect
  * conflicting - one guideline negatively impacts the other
  * independent - one guideline has no effect on another
* SWE must select the best combination of guidelines to achieve desired NFA

#### Implementing Functional Safety
* functional safety is a property of the system rather than the component
* safety standards: standards require top-down refinements of safety reqs based on hazard analysis
* failure mode and effects analysis (FMEA) and fault tree analysis are techniques used for traceability analysis
* avoid failures and make unavoidable failures safe
* safety requires addressing three needs in parallel - 
  * system-oriented development
  * safety as an integral part of engineering methods: use coding standards and rules, integrate safety methods and techniques (defect prediction, detection, correction, prevention)
  * strong process maturity: need for certification, documentation trails, reviews

#### Safety, Security, Now Sustainability
* environmental sustainability should be considered as a NF req in the software engineering process
* three orders of magnitude:
  * first-order impact - direct effects of a system on environment - energy usage
  * second-order - indirect effects of software - more efficient energy mgmt such as thermostat
  * third-order - rebound effects - increased efficiency encourages more use of systems that consume more energy
* Life Cycle Assessment
  * lots of analogies presented
  * need to do LCA for sustainability in two scopes:
    * software itself wo consideration for the process it supports
    * applied to the system in which the software is embedded

#### Back to the Basics: Measurement and Metrics
* You cannot control what you cannot measure
* too much measurement will inundate someone
* metrics are measurements of different aspects of an endeavor that will help us determine whether we are progressing toward a desired goal
* metrics need to be a part of a metrics program used as a decision support tool
* planning should be based on GQM (Goal Question Metric) paradigm
* Planning steps include:
  * defining goals
  * deriving questions
  * developing metrics
  * define collection process:
    * what data is to be collected?
    * what will be the source of data?
    * how will it be measured?
    * who will perform the measurements?
    * how frequently should the data be collected?
    * who will the derived metrics be delivered to?
* implementing the metrics program - keep the number of measurements between 5 and 10; evaluating the metrics program (program should be periodically evaluated to see if it is meeting the needs of the metrics users, a metrics repository should be established)
* collect data, validate data, derive metrics, make decisions

#### A Large-Scale Empirical Study of Just In Time Quality Assurance
* most software quality assurance work is based on predicting defect-prone modules and components
* problems with approach:
  * coarse grained (don't show risky areas)
  * relevant experts needs for review and testing are not identified
  * predictions might be made too late (after all modifications have been incorporated)
* Just in Time QA ius an approach to identify risy mods that should be analyzed further
* factors to consider in defect-inducing changes: goals is to produce a way to predict defect prone changes
* Which change measure is *excluded* from considering defect inducing changes? Feature points come under Size Measure in estimation of cost
* diffusion, history, size, purpose, experience
* Size has a higher chance of introducing more defects in one large change, whereas diffusion requires keeping track of all locations that must be changed.
* Cased study on 11 object, results analyzed for:
  * confusion matrix
  * accuracy - number of correctly classified changes over the total number of changes
  * recall - ratio of correctly predicted defect-inducing changes to the actual number of defect inducing changes
  * precision - fraction of correctly predicted defect-inducing changes to all changes (there is a tradeoff btwn prediction and recall)

#### Effectivity and Economical Aspects for Agile Quality Assurance in Large Enterprises
* People Business Change
* introduces the SPI manifesto (3)
* focus on people
* SPI is what you do to make the business successful
* SPI is inherently linked to change
* Scrum master leads QA aspects of project
* QA activities are part of the product backlog - performance testing, test automation
* Quality cycle
* ![image](https://user-images.githubusercontent.com/17733481/166165820-d2c0e38b-36c3-463b-b612-79212ab9e8ba.png)


#### The 3C Approach for Agile Quality Assurance
* Continuous Integration: new code is automatically detected from CMS, compiled, integrated into app, and tested
* Continuous Measurement: after integration and passing of tests, metrics are captured and violations of thresholds detected
* Continuous Improvement: quality manager views results and identifies areas for improvement (GQM)

#### Legal Liability for Bad Software
* noteworthy software disasters - raptor flight control system
* mentality in some orgs: "ship now, patch later"
* lawsuits are common:
  * breach of warranty - software defects lead to economic losses - When software vendors include their license agreements and express warranties about their products performance
  * fraud - vendors willful misrepresentation of software
  * tort product liability
  * negligence
  * malpractice
* Negligence is when the developer fails to provide due care whereas malpractice is when the developer is licensed and fails to provide due care to the software

#### Data Science: Technologies for Better Software
* Lots of data available on software projects due to short iterations
* data science aids software engineers via:
  * data driven quality mgmt (Q-rapids tool)
  * automatic post-processing of code analysis - code analysis reduces failures by 50% and cuts development costs by 20-30%
    * key is not to overwhelm the developer with defects
    * need to prioritize what to bring to dev's attention
    * need to train defect classifiers 
* For which part of the Q-Rapids framework architecture is an analyst decision maker needed? At the end, we need decision makers to have the visualization, recommendation, and prioritization of the key things that need to be known from the data.
* Steps: Business, data, data preparation, modeling, evaluation, deployment

#### A Retrospective View of the Laws of Software Engineering
* software engineering is still based on custom designs and manual coding - same level of sophistication as manufacturing guns in 1784; no standard reusable parts
* selected laws:
  * Conway's law - if three orgs build, likely three subsystems - any piece of software reflects the org structure that produced it
  * Gresham's law - bad mgmt drives out good software engineers
  * Humphrey's law - users do not know what they want a software system to do until they see it working. Really supports agile and rapid prototyping
* did not originate from software, but taken from physics, math
