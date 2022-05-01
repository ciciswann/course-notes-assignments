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
* 

#### Using Guidelines to Improve Quality in Software Nonfunctional Attributes

#### Implementing Functional Safety

#### Safety, Security, Now Sustainability

#### Back to the Basics: Measurement and Metrics

#### A Large-Scale Empirical Study of Just In Time Quality Assurance

#### Effectivity and Economical Aspects for Agile Quality Assurance in Large Enterprises

#### The 3C Approach for Agile Quality Assurance

#### Legal Liability for Bad Software

#### Data Science: Technologies for Better Software

#### A Retrospective View of the Laws of Software Engineering
