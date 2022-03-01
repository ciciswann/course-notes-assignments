# Week 5 Notes

* [Performance Testing](#performance-testing)
* [Stress Testing](#stress-testing)
* [Volume Testing](#volume-testing)
* [Configuration Testing](#configuration-testing)
* [Regression Testing](#regression-testing)

### Performance Testing
- **Objective** - Verify the system meets its performance requirements for specified load conditions including stress and volume scenarios
- Criteria for Performance Testing
    - Quantitative and measurable requirements
    - reasonably stable system
    - test env. representative of customer site
    - tools - load generator, resource monitor
- Test Data Management
    - full data sets replicate real data from operational systems
- Example:
    - performance requirement - excellent response time
        - needs to be quantitative and verifiable
        - response time of less than 1 second
            - to make a reservation defined as a point from where a screen of info has been filled in
            - Under what conditions? - under normal conditions (needs to be defined)
- Load Specification
    - for relevant use-cases, it is important to specify performance requirements in terms of load
    - Resource usage can also be tracked as the load is varied to identify potential bottlenecks
- Summary - we have to define criteria, ensure a stable system
### Stress Testing
- What is the objective of stress testing?
    
    It helps evaluate how a system responds when resources are saturated over a short period of time/past their limits.
    
    Verify the behavior of the system meets its requirements when the resources are saturated and pushed beyond their limits
    
- What are the 4 steps for stress testing?
    1. Identify stress points
        1. work with developers and architects
        2. Identify potential bottlenecks
    2. Develop a strategy to stress the system at points identified in step 1
        1. often requires load generation tools
    3. Verify that intended stress is actually generated
        1. system performance may be better than expected
        2. stress test may inefficient
    4. Observe behavior
        1. verify stress-related requirements are met
        2. ensure functional correctness
- When should stress testing begin?
    
    Stress testing should begin earlier in a project.
### Volume Testing
- What is volume testing? What is its objective?
    
    It helps to evaluate how a system responds to different loads over an extended period of time
    
- What are some errors targeted by volume testing?
    - Memory leaks
    - Counter overflow
    - resource depletion
### Configuration Testing
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
        2. Risk-based
        3. Design of Experiments (Pairwise combinations)
### Regression Testing
- What is the objective of regression testing?
    
    To evaluate and ensure workability of previous software in the presence of software additions
    
- modifying software is high-risk
- What are some reasons modifications have to occur?
    - To fix errors
    - the incorporation of new functions
- In what ways do modifications introduce new errors?
    - code ripple effects
    - unintended feature interactions
    - changes in performance synchronization, resource sharing, etc.
- Regression testing must be approached from a multi-level point of view
    - unit-level regression tests
    - integration level regression tests
    - system-level regression tests
- Name 2 strategies for regression testing
    - Full -
        - rerun all existing tests in response to code modifications
        - normally impractical
    - Selective
        - rerun a selected subset of tests based on modification
        - execute a standard confidence test regardless of the modification
- Testing of code deltas
    - requires coverage tool for mapping test cases to code at the desired granularity level
        - code block
        - component
    - requires configuration management tool to identify code change deltas
- What is ripple effect analysis?
    - Requires developers to identify impact of changes on other requirements or features
    - Best addressed via checklist items in a modification inspection
    - potentially impacted requirements and features are communicated to system test
- Selective regression testing using a confidence test suite
    - select a subset of tests to execute to verify previous functionality
    - include tests addressing:
        - high-frequency use cases
        - critical functionality
        - functional breadth
- Revalidation issue
    - regression tests must be revalidated to ensure they are consistent with software modifications
