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
* Quality Attribute Scenarios
 * a quality attribute specific res with six parts:
  * stimulus: a condition that needs to be addressed
  * its source: where it comes from
  * the environment: the conditions when the stimulus occurs
  * the artifact: what parts of the system are stimulated
  * the response: quantitative and measurable
  * the response measure: how we will measure  


### Software Quality Assurance

#### Evaluating Essential and Accidental Code Complexity Triggers by Practitioners' Perceptions

#### Managing Technical Debt

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