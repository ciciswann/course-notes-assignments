# Week 6 Notes

### Error Detection, Recovery, and Serviceability Testing
- **Objective**
    
    Helps ensure reliability, availability, and serviceability requirements are being met.
    
    Overall system reliability and availability is dependent upon the system's ability to detect and recover from a variety of failures
    
    - user
    - hardware
    - software
    - other systems
- **Error detection and recovery needs and approaches**
    - it's essential to have a list of errors to recover from specified in the requirements
    - usual testing approach consists of error injection
- **Serviceability Testing**
    - important for system availability
    - the objective is to verify serviceability requirements are being met
        - e.g. critical problems will receive fixes or workarounds within 4 hours
    - includes all aspects of problem reporting, isolation, correction, verification, and fix release
    - usual testing approach is to inject a failure and assess response
- **Summary**
    
    fault tolerance
    
    effective testing approaches
    
    we have to know what the targets and objectives are and what type of failures do we need to know what to recover from
### Usability Testing
Usability is important because close to one-half of code in many applications is in the user interface

- **Objective**
    
    Provide direct user feedback on a product that companies can use to improve their website for users.
    
    - Usability is the degree to which intended users are:
        - able to perform tasks the product is intended to support in the intended environment
        - satisfied by the procedures they must follow and the resultant output
        - protected from consequences of their actions
- **What are the requirements of usability?**
    - Learnability: the type and amount of training required to bring users to a desired level of performance
    - memorability: addresses the ability to retain skills in using a product once it is learned
    - errors: measures the number of incorrect actions a user makes in trying to accomplish a task
    - efficiency: measures the speed with which tasks can be performed
    - subjective satisfaction: the user's overall feeling about the product
- **What are some concerns of usability testing?**
    
    **Reliability:** would you get the same results if tests were repeated
    
    - best user in 10x faster than slower
    - best 25% are 2x faster than slowest
    
    **Validity:** does the usability test measure something of relevance
    
    - wrong user
    - wrong task
- **What are some of the goals of usability testing?**
    - **Formative Evaluation:**
        - learn which aspects of the interface are good and bad
        - how can design be improved
    - **Summative Evaluation:**
        - assess the overall quality of the interface
        - measurement test
- **When should it be performed?**
    
    Should begin early in the project. Formative evaluation on prototypes and even mockups.
    
- **What are test plan concerns?**
    
    Who are the users?
    
    What task will they perform?
    
    What user aids will be available?
    
    What data is to be collected?
    
    What criteria will be used to determine sucess?
    
- **Pilot Tests**
    - test procedures must be tried out in a pilot study
    - Evaluate
        - instructions
        - success criteria
        - time to perform tasks
        - evaluation criteria
- **Identifying Test Users**
    - Users must be representative
    - Evaluate with both novice and expert users
    - be prepared to train users to achieve expert level
- **Usability Comparison**
    
    When evaluating usability choices care must be taken when using the following testing strategies:
    
    - between subject testing
    - within subject testing
    
    Within subject testing is preferable
    
- **Ethical aspects with human subjects**
    - subjects may have concerns about performing inadequately
    - need to make subjects feel comfortable
    - emphasize system is being tested and not the user
    - maintain privacy issues
- **Test Tasks**
    - must be representative
    - begin with easy tasks to boost confidence
    - give one at a time
- **Stages of Test**
    1. Prep (ensure environment is set-up)
    2. Introduction (welcome, purpose)
    3. Running the test
    4. Debriefing
- **Thinking aloud**
    - test subject uses system while continuously thinking out loud
    - testers may need to periodically prompt test subject
