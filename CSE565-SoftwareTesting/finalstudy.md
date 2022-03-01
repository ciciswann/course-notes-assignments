# Final Study Guide Questions

- What are the criteria for conducting performance testing?
    - Quantitative and measurable requirements
    - reasonably stable system
    - test environment representative of customer site
    - tools - load generator, resources monitor

- What is the objective of performance testing?
    
    Verify the system meets its performance requirements for specified load conditions including stress and volume scenarios
    
- What is the objective of stress testing?
    
    It helps to evaluate how a system responds when resources are saturated over a short period of time/pushed past their limits
    
- What are the four steps of stress testing?
    1. Identify stress points
    2. Develop a strategy to stress the system at points identified in step 1
    3. Verify that intended stress is actually generated
    4. Observe behavior
- When should stress testing begin?
    
    Stress testing should begin earlier in a project
    
- What is volume testing? What is its objective?
    
    It helps evaluate how a system responds to different loads over an extended period of time.
    
- What are some errors targeted by volume testing?
    - Memory leaks
    - Counter overflow
    - Resource depletion
- What is the objective of configuration testing?
    
    Verify that the functional and performance requirements of the system are met for the different configurations that the system must run on
    
- What are the three steps of configuration testing?
    1. Identify parameters that define each configuration that have an impact on the system's ability to meet its functional and performance requirements
        1. CPU
        2. Operating system
        3. memory
        4. database
    2. Partition (Group similar parameters to reduce possible numbers of configurations)
    3. Identify configuration combination to test
        1. boundaries (min and max)
        2. risk-based
        3. Design of Experiments (Pairwise combinations)
- What is the objective of regression testing?
    
    To evaluate and ensure the workability of previous software in the presence of software additions. Modifying software is high-risk.
    
- What are some reasons software modifications have to occur?
    - to fix errors
    - the incorporation of new functions and features
- In what ways do modifications introduce new errors?
    - code ripple effects
    - unintended feature interactions
    - changes in performance synchronization, resource sharing, etc.
- In what way must regression testing be approached?
    
    It must be approached in a multilevel point of view
    
    - unit level
    - integration level
    - system level
- What are two strategies for regression testing?
    - Full - rerun all existing tests in response to code modifications, which is normally impractical
    - selective - rerun a selected subset of tests based on modification, execute a standard confidence test regardless of the modification
- What is needed to test code deltas?
    - requires coverage tool for mapping test cases to code at the desired granularity level
        - code block
        - component
    - requires configuration management tool to identify code change deltas
- What is ripple effect analysis?
    
    Requires devs to identify impact of changes on other requirements or features.
    
    best addressed via checklist items in a modification inspection.
    
    Potentially impacted requirements and features are communicated to system test
    
- What is the process of selective regression testing using a confidence test suite?
    - select a subset of tests to execute to verify previous functionality
    - include tests addressing:
        - high-frequency use cases
        - critical functionality
        - functional breadth
- Do regression tests need to be revalidated?
    
    yes, they must be revalidated to ensure they are consistent with software modifications
    
- What is the objective of error detection, recovery, and serviceability testing?
    
    Helps ensure reliability, availability and serviceability requirements are being met. Its dependent upon the systems ability to detect and recover from a variety of failures:
    
    - user
    - hardware
    - software
    - other systems
- What is needed for error detection and recovery?
    
    Need a list of errors to recover from specified in the requirements. the approach usually consists of error injection.
    
- What is the objective of serviceability testing?
    
    to verify serviceability requirements are being met
    
    - critical problems will receive fixes or workarounds within x hours
    
    includes all aspects of problem reporting, isolation, correction, verification, and fix release
    
    usual approach is to inject a failure and assess response
    
- What is the objective of usability testing?
    
    Provide direct user feedback on a product that companies can use to improve their website for users.
    
    Usability is the degree to which intended users are:
    
    - able to perform tasks the product is intended to support in the intended environment
    - satisfied by the procedures they must follow and the resultant output
    - protect users from consequences of their actions
- What are the requirements of usability?
    - Learnability - the type and amount of training required to bring users to a desired level of performance
    - Memorability - addresses the ability to retain skills in using a product once its learned
    - Errors - measures the numbers of incorrect actions a user makes in trying to accomplish a task
    - Efficiency - measures the speed with which tasks can be performed
    - Subjective satisfaction - the user's overall feeling about the product
- What are some concerns of usability testing?
    
    Reliability - would you get the same results if tests were repeated?
    
    Validity - does the usability test measure something of relevance
    
- What are some of the goals of usability testing?
    
    Formative evaluation - learn which aspects of the interface are good and bad, how can design be improved
    
    Summative evaluation - assess the overall quality of the interface, measurement test
    
- When should usability testing be performed?
    
    Should begin early in the project. Formative evaluation on prototypes and even mockups.
    
- What are test plan concerns?
    - Who are the users?
    - What tasks will they perform?
    - What user aids will be available?
    - What data is to be collected?
    - What criteria will be used to determine success?
- What are pilot tests?
    
    Test procedures tried out in a pilot study to evaluate:
    
    - instructions
    - success criteria
    - time to perform tasks
    - evaluation criteria
- How do you identify test users for usability testing?
    - users must be representative
    - evaluate with both novice and expert users
    - be prepared to train users to achieve expert level
- What is the preferable usability testing strategy?
    
    Within-subject (skill, knowledge level) testing is preferable. Care must be taken when using the strategies of between subject testig and within subject testing
    
- What are some ethical aspects to consider with human subjects?
    - concerns about performing adequately
    - need to make subject feel comfortable
    - maintain privacy issues
    - emphasize system is being tested and not the user
- What is important to remember in regards to usability test tasks?
    
    they must be representative
    
    begin with easy tasks to boost confidence
    
    give one at a time
    
- What are the stages of a usability test?
    1. Prep (ensure environment is set up)
    2. Introduction (welcome)
    3. Running the test
    4. Debriefing
- What are the objectives of reliability testing?
    
    Provide an estimation of how long a system can run without a failure for a specified time. It also covers the availability of a system, which looks at whether a system is performing correctly at a given time. 
    
- What is availability and how is it calculated?
    
    The probability at any given time that a system or capability of a system functions satisfactorily in a specified environment
    
    (MTTF/(MTTF + MTTR))X 100%
    
    Mean time to failure
    
    mean time to repair
    
- What is the 5NINES availability requirement?
    
    The system shall be available 99.999% of the time. Only 5 minutes of unavailability
    
- How do you achieve high reliability and availability?
    
    Requires the prudent application of SRE techniques.
    
    Appropriate development techniques must be applied for:
    
    - fault prevention
    - fault tolerance
    
    Appropriate testing techniques must be applied along with models for assessing whether reliability and availability objective are met
    
- What is N-version programming?
    
    different teams create different versions of software, creating alternatives
    
    - added redundancy
- What is Operational profile testing?
    
    Operation profile describes how users utilize a product.
    
    Consists of a set of major functions performed by the system and their occurrence probabilities.
    
    **An operation profile is essential for reliability prediction.**
    
- How is a basic operation profile constructed? (3 steps)
    1. Identify the major functions performed by the system
        1. identify different types of users/external entities
        2. use-cases are good candidates for basing the operational profile
    2. Identify the occurrence rates
        1. historical data
        2. marketing
    3. Calculate the occurrence probability
- How are reliability tests developed?
    
    They are developed based on the Operational profile. Test generation is modified to incorporate critical functions with low occurrence probabilities.
    
    - number of tests to execute is based on the reliability objectives
- What are two ways of interpreting failure data?
    - Development testing - goal is to remove faults that have caused failures
    - Certification Testing - goal is to determine whether a software component or system should be accepted or rejected
- What are some other uses of operational profiles?
    - guide development priorities
    - assist in performance analysis
- What are reliability models?
    
    trying to show how reliability changes over time
    
    support answering "when to stop testing?" question
    
    numerous models exist
    
    effectiveness of any reliability measurement is directly related to the effectiveness of collecting the right data during testing such as: failure intensity (the number of failures per natural or time unit)
    
    All models possess assumptions such as:
    
    - no new errors are introduced by fixes
    - reliability will improve over time as defects are found and removed
- What are some reliability testing problems?
    - Operational profile uncertainty
        - is the OP an accurate reflection fo the real use of the system
    - High costs of test data generation
        - very expensive to generate and check the large number of test cases that are required
    - Statistical uncertainty for high-reliability systems
        - it may be impossible to generate enough failures to draw statistically valid conclusions
- What is the goal of security testing?
    
    To ensure that private data is protected from unauthorized users
    
- What are security testing strategies?
    - deny application access to libraries it needs
    - try to overflow input buffers by inputting long strings
    - try special characters as inputs
    - try default or common user names and passwords
    - attempt to fake the source of the data
    - force system to use default values
    - test all routes to perform a task
    - produce each error message and ensure it doesn't compromise security
- What are some components that might exploit software?
    
    OS, File System, GUI, Other systems (databases, libraries, etc.)
    
- What must a system test plan do?
    
    It must reflect an in-depth understanding of the objective of the system test as well as project constraints
    
    Must begin early 
    
- What must the system test plan address?
    - system test objectives
    - dependencies and assumptions
        - resource availability
        - software completed on time
    - adopted test strategy - how objectives will be met within project constraints (risk-based)
        - techniques to be used for test data generation
        - test environment
        - entry and exit criteria
        - schedule
    - specification of the test environment
        - include - platforms to test on, simulators, testing tools
        - performance testing may require load generation tools
    - specification of system test entry and exit criteria
        - established based on test strategy to maximize test effectiveness
        - problems with beginning test too early include - inability to run all test, excessive communication with devs on problem fixes, high degree of retest
        - possible entry criteria include - code under configuration management, completion of integration test, no outstanding high priority problems, successful completion of system test readiness assessment
    - schedule
        - identify all of the testing tasks to be performed
        - identify dependencies among the testing tasks
    - risk management
        - correspond to scenarios that could impact testing schedule or effectiveness
- How is the critical path identified?
    
    The path through the PERT chart with no slack time
    
    Can be identified by associating with each node, its earliest start and finish time
    
    those paths where the earliest start time is always equal to the predecessor's nodes earliest finish time correspond to critical paths
    
- What are the steps of a generic estimation process?
