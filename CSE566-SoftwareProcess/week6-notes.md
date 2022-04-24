# Week 6 Notes

### Software Process Improvement
* Developing, testing, maintaining
* Process Improvement Phases:
* **Characterize the current process**
    * understanding the current process is important
    * excercise care in distinguishing among: 
      * the perceived process: what you think you do
      * official process: what you're supposed to do
      * actual process: what you do
    * software leader must ensure that the **actual process** being followed is understood prior to commencing any process improvement
* **Analyze current process**
  * identify value-added and non-value-added activities
  * identify the sources of variation in the process
  * software metrics play a key role in objective process analysis
  * the software leader must plan to collect the appropriate metrics as previously described
* **Characterize Target Process**
  * identify the ultimate goal of the process: for example - minimize cycle time, minimize late reqs
* **Process re-design**
  * improve the current process in the direction of the target process
  * explore ways for eliminating, simplifying, or combining activities
  * explore ways of elim. rework
  * explore ways of reducing the task variance
* **Implement Process Improvement**
  * set process improvement goals
  * implement process improvements: begin with candidates that are well defined, pilot candidates that are not proven
  * measure progress towards goals
* Process improvement tools: post mortem
  * a set of lessons learned is documented
  * post mortem analysis techniques include:
    * interviews with key personnel
    * statistical analysis of data
    * investigations of major problems
    * identification of what went well
* Process improvement: causal analysis
  * seeks to identify both the root cause of defects and also approaches to eliminate future occurrences
  * defect data is collected and analyzed:
    * currently done informally within projects
    * information can be used to support organization process improvement
* causal analysis steps: select a set of defects to analyze, identify the probable cause for each defect, identify common causes among defects, identify possible solutions to eliminate the common defect causes, tools are available to support causal analysis activities

### Root Cause Analysis Overview
* well-defined technique
* Flies analogy - screen tears
* is a group reasoning process applied to defect info to develop organizational understanding of the cause of a particular class of defects
* 1968
* defect: any flaw in product
* cuase: the underlying process flaws associated with the defect
* costs - time to utilize process; tools to facilitate process; training time
* benefits - fewer errors passed on to internal and external customers; less rework; more time to do new dev; improved productivity; less frustration involved with design maintenance activitiesl improved communication; improved teamwork; more satisfied internal and external customers
* IBM - 1% project budget 50% reduction in error rates
* applicability
   * root cause analysis can be performed for defects generate during any activity: development, testing, documentation, maintenance, planning
   * can be performed at various times: end of project, end of development, after certain number of defects (worst time is at the beginning)
*  root cause - process improvement; it can also come down to human error
*  high potential for ROI

### Root Cause Analysis Defect Categorization
* Process
   * Select defects to analyze
      * dependent upon the objectives of the activity
      * activities include: reducing defect repair costs, eliminating critical problems reported by customers, reducing an error type
      * pareto analysis is commonly used in selecting the types of defects to be targeted the the root causes analysis (steps: select a dimension to measure/compare defects, assemble data on the selected dimension, draw a vertical and horizontal axis, label the vertical with the chosen dimension, label columns on horizontal axis [largest category on the left], plot the data in column form and add descriptive details) 
 <img width="480" alt="Screen Shot 2022-04-24 at 11 41 56 🌅" src="https://user-images.githubusercontent.com/17733481/164991501-0bdf7737-7456-4698-b1ab-f02f1773d9e4.png">

   * analyze each defect to identify is probable root cause
      * must be analyzed by those most familiar with it: identify the probable root cause, identify the info necessary to formulate & evaluate possible ways to eliminate the root cause 
      * address questions such as: what is the defect cause category? what is the probable root cause of the defect? at what stage was the defect created? at what stage was the defect detected? how can this defect type be prevented in the future?
      * categories: enable teams to focus their search
         * comm. failure (missing or incorrect info; from whom to whom), oversight (result of failing to consider all cases and conditions), education (result of a lack of understanding of some aspect of the product or process), transcription (result of a simple mistake - human error, typo)
      * multiple defect causes
         * contibuting causes, chain of causes
      * root cause is the most important cause, and in a chain of causes corresponds to the original cause
      * not all root causes will have preventative actions
      * some root causes will be easier to eliminate than others  
   * team meets to: discuss and refine root causes (Ishikawa diagrams) and identify common root causes
   * team selects root causes to address
   * team implements solutions and evaluates effect
   * team develops and evaluates proposed solutions to eliminate defect root causes
 

### Root Cause Refinement and Solution
* **team meets to: discuss and refine root causes (Ishikawa diagrams) and identify common root causes**
   * determining probable root cause
      * five whys - why enough time to get to root cause, up to five repetitions may be needed, each path must be followed
   *  <img width="526" alt="Screen Shot 2022-04-24 at 12 00 27 🌃" src="https://user-images.githubusercontent.com/17733481/164992188-085c1a46-c30e-4cdd-b86a-747c2b59b01a.png">
   *  <img width="523" alt="Screen Shot 2022-04-24 at 12 01 26 🌃" src="https://user-images.githubusercontent.com/17733481/164992238-21f6143c-577c-4a15-930c-51648c6aea47.png">
   *  documentation
      * document the results of a root cause analysis performed on a defect in order to help teams develop defect prevention strategies
      * includes: nature of the defect, phase in which defect was found, phase in which the defect was introduced, proposed root cause of the defect, recommended solution, length of time required to correct the defect
   * analysis of defects:
      * refine root causes and look for common sources of defects 
      * ishikawa diagrams (fishbone) - constructed to represent the combined root causes - individuals present their findings, team comments and brainstorms to refine
   * ishikawa diagram steps: draw fishbone skeleton, identify relevant major categories and primary causes, combine root causes from individual defects under major categories, continue process until actionable root causes are identified
   * <img width="479" alt="Screen Shot 2022-04-24 at 12 09 25 🌃" src="https://user-images.githubusercontent.com/17733481/164992542-09da4b22-c5fd-44cb-abb9-a5943725288f.png">
   * <img width="516" alt="Screen Shot 2022-04-24 at 12 10 01 🌃" src="https://user-images.githubusercontent.com/17733481/164992565-259c82bd-5c88-4775-b6e7-ac28912128a9.png">
* **team selects root causes to address**
   * guidelines for selecting most likely root causes to resolve - easy does it (most feasible root cause to resolve), things--procedures--people (things and procedures are easier to change than ppl) 
* **team implements solutions and evaluates effect**
   * proposed solutions
      * oversights - use checklists; tools to automate checking; providing templates; perform reviews
      * education - provide JIT, appropriate tutorials
      * comm. failures - liaisons, tracking system, documentation, processes
      * transcription - automate checking, reviews 
* **team develops and evaluates proposed solutions to eliminate defect root causes**
* root cause analysis makes sense, is easy to apply, reduces defects, reduces rework, improves processes

#### Applying Software Engineering Standard in Very Small Entities
 
#### Hybrid Agile Software Development

#### Enough Software Processes, Let's Do Patterns

#### Using Analytics to Guide Improvement During an Agile DevOps Transformation

### Process Maturity

#### Improving Agility and Discipline of Software Development with the Scrum and CMMI

#### CMMI V2 Model At a Glance

