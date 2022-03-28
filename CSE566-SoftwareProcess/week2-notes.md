# Week 2 Notes

### Project Planning: Task Identification
* 9 management best practices from the SPMN: 
   * Formal Risk Management
   * Agreement on Interfaces - user interfaces myuust be defined before development
   * Formal Inspections - work products
   * Metric-Based Scheduling and Management - analytics
   * Binary Quality Gates at the Inch-Pebble level
   * Program-wide visibility of progress vs plan
   * Defect tracking against quality targets
   * Configuration management
   * People aware management accountability - 90 percentile software teams outperform 15 percentile teams by factors of 4 or 5 to 1, individual productivity ranges of 26:1, minimize burn-out, avoid excessive overtime, just-in-time training
* Software Planning Activities - identify external constraints (body count, project inputs and outputs), identify tasks to be performed, analyze dependencies among tasks, estimate the effort, expertise and other resources need to perform each task
* assess training and resources needs
* assign task responsibilities: resource level tasks
* map tasks to a timeline
* obtain commitment from participants
* Identify task to be performed - tasks to be performed must be identified based on the life cycle model, the selected development process, the contract, and the review of schedules from related programs
* task identification proceeds in a top down fashion until tasks are identified that: can be assigned to an individual or group, are small enough that they can be estimated accurately, are precise enough to identify interdependencies
* Work Breakdown Structure: Project into Reqs, Development and testing
* Agile task identification: product backlog, sprint backlog
* Which key aspects contribute to identifying the tasks to be performed? Life Cycle Model, selected development process, contract, review of schedules
* task identification is an essential first step in project planning and will vary based on the development process model

### Project Planning: Dependency Analysis
* after identifying tasks, peform a dependency analysis among the tasks: plan, discuss, and brainstorm seq of events; understand external dependencies
* Dependencies can be documented in a PERT (Program Evaluation and Review Technique) chart
* Critical Path Analysis - what is the minimum time it will take to complete the project? what activities are critical to complete the project in minimum time? what activities can be done in parallel? how long can each activity be delayed before it affects the finish date?
* The critical path(s) is the path through the PERT chart with no slack time
* critical paths can be identified by associating the earliest start and finish time with each node
* paths where the earliest start time is always equal to the earliest finish time of the preceding node correspond to critical paths  

![image](https://user-images.githubusercontent.com/17733481/160301048-9d8dfe6a-e479-4c07-879c-41cdd6101f4a.png)

### Project Planning: Scheduling
* assign task responsibilities (agile vs plan driven) - assign similar tasks to the same person, minimize necessary communication, match knowledge and skills to the task, assign tasks to people so that they learn and grow, attempt to accomodate preferences
* The scheodule myust be well thought out and taake into account: constraints (milestones, note that some constraints may be negotiable), taks dependencies, availability of personnel, risk
* developing a schedule is an iterative process - adjust tasks, durations, resources and sequencing
* participants must commit to the schedule
* agile considerations - overall release plan is based on predicted project velocity; tasks identified in sprint planning method should specify a person responsible as well as start and end dates
* Ganntt chart - the schedule can be documented in a Gantt chart; gantt charts identify duration of tasks along with their starting and ending dates (taks duration = work/resources), use historical data from similar projects, document assumptions; gantt charts identify parallel tasks; multiple gantt charts can be developed to show various levels of details (hierarchy of gantt, open and close increment Gantt chart for different levels of tasks)\
![image](https://user-images.githubusercontent.com/17733481/160302244-81f2009a-5277-47ae-9815-aebe0a690602.png)
* Why are schedule buffers so important? Schedule buffers are needed to allocate time for possible future risks. - risk mgmt must be used to guide the team in the amount of contigency time (buffer), which must be allocated to the schedule
* schedule confidence is tied to the buffer
* Possible ways to shorten critical paths - negotiate constraints, long activites can be sometimes be split into shorter and overlapping activities, assign more experienced personnel to critical path activities, if possible reduce dependencies
* Software project dev plan: introduction/scope, controlling documents, project description (SOW), overall dev plan, support reqs, project organization, development standards

### Tracking Project Process
* monitoring progress: software dev teams must track progress against plan (if software subcontracting is used, supplier activities must also be tracked against the subcontract mgmt plan, tracking is necessary to detect problems early); without tracking there is no control; items to track include: schedule, budget, quality, risk
* project review reports: the software task lead has the responsibility of communicating project status to senior mgmt, typical info in this report includes: presentation of software metrics (perf to plan, risk indicators), analysis of metrics, risks to the project, planned corrective actions
* review reporting guidelines: provide info consistently, suggest candidate solutions when raising problems (control solution space), communicate major accomplishments, filter status information (do not present too detailed info that senior mgmt cannot have an impact on)
* monitory status: in order to monitor the status the software task lead must obtain info from many sources; subjective data: mgmt by walking around, personal inquiry of status, individual team member status reports, project meetings, hard data: quantitative project metrics
* individual status reports: info - issues requiring immed. attention, agile considerations
* project meetings: meetings should be help periodically and at a fixed time, they should contribute to the atmosphere of order and control, key items from the meeting should be recorded (project progress and future plans), action items, agile stand-up meetings
* possible agenda - general info, individual reports, agile (yesterday, today, issues)
* monitoring schedule progress: comparing tasks completed against the plan; visibility into schedule progress is obtained via analysis of: milestone completion, taks completion (partial task completion is OK as long as it can be objectively measured)
* milestones: binary (done or not done); examples: contract, deliverables, subcontract milestones, commitments, end review, demo
* milestone completion is a scheduled item
* schedule progress must also be monitored at the task completion level
* visibility into the project is dependent upon the granularity of the tasks
* Track dev progress utilizing binary quality gates at the inch-pebble level
* ideally planning is based upon an inch-pebble detailed network
* binary quality gates - procide objective task completion criteria (measured objectively)
* Gantt, critical path, kanban board
* In terms of binary quality gates, how is each task measured for duration and effort, and performance? No more than 5% of duration and effort, and at least 95% performance

### Earned Values
* Heavily utilized in government contracting
* EV is a standard method and set of metrics to describe: schedule performance, cost performance, future performance needed to hit the target
* basic tenets: plan the entire effort, determine accomplishment at the level where work is done, measure accomplishment objectively, summarize for higher levels, analyze variances and forecast impact
* EAC (Estimate at Completion)
* 3 pieces of info: schedule (BCWS - budgeted cost of work scheduled), performance (BCWP - budgeted cost of work performed), and actual costs (ACWP - actual cost of work performed)

![image](https://user-images.githubusercontent.com/17733481/160305336-7ee3ebba-37fb-4b30-9b4b-3b64880d1ea9.png)

* Variance analysis: schedule, budget, quality; variances always exist but are not always a cause for concern; significant variances are those that cross predetermined thresholds and require corrective action (org thresholds, customer thresholds)
* Significant variances might indicate: the original plan was incorrect, the performance data is incorrect, the project is not performing according to plan
* variance analysis is used to identify and isolate problems, calculate trends (schedule variance, cost variance, estimate at completion, software performance index, cost performance index, to complete performance index)
* schedule variance - critical path, gantt chart, earned values
* SV = BCWP - BCWS - schedule variance (positive is ahead of schedule, negative is behind)
* SPI = BCWP/BCWS - provides efficiency rating; SPI <.95 indicates condirtions that warrant risk mgmt

### Tracking Budget Progress
* monitoring budget progress - tracked by comparing the effort and cost consumed against the plan; visibility into budget progress is obtained via analysis of: effort consumed and cost 
* tracking effort consumed - the effort spent on tasks must be recorded, earned values ACWP and BCWP are used to track effort as previously shown
* CV = BCWP - ACWP - cost variance; positive lower cost than planned and negative is higher cost than planned
* CPI = BCWP/ACWP - <.95 indicates conditions that warrant risk mgmt
* EAC = ACWP + (BAC - BCWP)/CPI - estimate at completion; BAC (budget at completion); watch for exceptions
* TCPI = (BAC-BCWP)/(BAC-ACWP) - to complete performance index; should be compared against the cumulative to date CPI
* all project costs must be tracked and compared against the plan
* possible cost items: subcontractor costs, licensing, equipment, travel

#### The Two Most Useful Earned Value Metrics: The CPI and the TCPI
* CPI tells the user what has been accomplished for what has already been spent
* tends to stabilize on projects from about the 20% complete point
* total costs predicted EAC=BAC/CPI
* greater than 1 - good 
* TCPI identifies the performance level needed to complete remaining work - TCPI = (BAC-BCWP)/(BAC-ACWP)
* What is the difference between CPI and TCPI? CPI shows accomplishment for what has been spent, whereas TCPI shows the performance level needed to stay in budget with the remaining work left

#### Earned Value Management (EVM) for Agile Software Projects
* agile evm enables: 
   * comparing effort of value planned, earned, and consumed
   * calculating cost and schedule efficiency
   * forecasting end of project time and cost
* Which metric is an actual performance metric in scrum projects? Sprint burdown chart

### Tracking Software Quality
* monitoring quality progress: the quality of the product must be tracked against the plan; quality objectives are derived from the customer as well as the org
* traditional quality indicators: robustness, integrity, efficiency, usability, reliability, maintainability, flexibility, portability
* monitory quality progress via inspection results: work product inspections provide critical visibility into the quality of the product
* the qty of defects as well as their type and severity must be compared against expectations - defects/DSI
* other relevant quality indicators must be assessed via inspection checklist items
* testing activities must be monitored in order to predict over time: CRUD, Reliability, Availability
* Types of measurements include: number of failures per day, execution time accumulated each day, restoration times for each failure, anticipated preventative maintenance time
* effectiveness can be defined as : number of defects detected/number of defects detectable
* calculated after identifying defects in later phases
* quality variance - comparing quality measures against the goals (estimated CRUD)
* Which kinds of measurement can help monitor progress via test results? # of failures, execution time accumulation, restoration times for failure, preventative maintenance time
* orthogonal defect classification - can be used to monitor the effectiveness of the development process via examination of defects detected
   * information collected for each defect: activity being performed when defect surfaced, defect type
   * a comparison can be done against the org's performance
* possible corrective actions: use float (mgmt reserve), rearrange tasks, acquire needed skills, reprioritize requirements, reallocate requirements to increments, acquire tools, improve dev process


#### 16 Critical Software Practices for Performance-Based Management
* Which practice is a critical software practice for performance-based management? Design Twice, Code Once
* Project integrity - risk mgmt, schedule, track EV
* Construction integrity - life cycle config mgmt, "design twice, code once"
* Product stability and integrity - inspect reqs

#### Are Management Basics Affected When Using Agile Methods?
* Scope, staffing and skills; life cycle and schedule; reviews, methodologies, tools, etc.; budget
* Scope - tradition detailed WBS, agile less detail provided early on
* Staffing - traditional mgmt focus, agile more crossfunctional teams
* Life cycle and schedule - detailed for traditional, agile just-in-time planning rolling wave approach to scheduling
