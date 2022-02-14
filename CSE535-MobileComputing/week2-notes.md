# Week 2 - Context-Aware Computing

* [Context Models and Context-Aware Applications](#context-models-and-context-aware-apps)
    * [What is Context?](#what-is-context) 
    * [Context Definitions](#context-definitions) 
    * [Types of Context-Aware Applications](#types-of-context-aware-applications)
    * [Difficulties in Using Context](#difficulties-in-using-context)
    * [Context Sources and Models](#context-sources-and-models)
    * [ContextFSM](#contextfsm)
    * [Context Analysis](#context-analysis)
    * [Context Middleware](#context-middleware)
    * [CareDroid: Example of Middleware](#caredroid)
 * [BraiNet - A Framework for Cognitive Mobile Computing](#brainet)
 * [Mobility Models](#mobility-models)
 * [Machine Learning for Context Models](#machine-learning-for-context-models)

## Context Models and Context Aware Apps
### What is Context?
* Context means the state of the environment (not really a useful definition by itself, but will build upon this initial definition later)
* As humans we use context to adapt our behavior to the current situation/state
* We can use context in mobile computing to avoid interupting users in inappropriate situations or to create smart environments (discover and use nearby interaction devices, or turn devices on/off depending upon time, situation)
* Proactivity - set up env. according to preferences or usage history
* Context:
    * location, identities
    * time, temperature
    * emotional state, focus, tasks
    * env. that user and comp. know about
    * state of surroundings
 * Two main classes of context information are **human factors** and **physical environment**
 
### Context Definitions
* Information that can be used by a comp. to enhance interaction with it (example: train booking app - cust no. and booking details, location and time can be derived from context info)
* **Definition by Enumeration** - whatever information is available
* **Definition by Relevance** - enumerate only the relevant information 
* Times change (introduction of IoT) and lead to new definitions of context
* **Definition by Functionality and Relevance** - only refer to info as context that can actually be processed by an application (relevant) but that is not mandatory for its normal functionality (auxiliary information - what other info can be collected in order to enable an additional functionality)

### Types of Context Aware Applications
* Features include **presentation** of info and services, **automatic execution** of a service, **tagging of context** to info to support later retrieval, and **adaptation** of apps behavior and appearance
* **Presentation**:
    * present info relevant to current information
    * only refers to which info is presented (not how)
* **Execution**: 
     * if context changes according to if-then rules services are automatically executed
     * example: auto brightness control (if surroundings are dark, then increase brightness)
* **Tagging**:
     * associating contextual information to data in order to improve later retrieval
     * can be performed automatically or initiated by the user
     * example: geo tagging - crawl data and associate something to an address you just went to (e.g. user1 tags restaurant with good burgers, user 2 searches good burgers nearby and finds restaurant)
* **Adaptation**:
   * Adapt behavior and how info is presented to given context
   * example: battery mgmt - low batt. threshold of 15% - shuts down power hungry app if battery level goes below 15%

### Difficulties in Using Context
* context information differs from traditional sources bc it is gathered from heterogeneous sources (i.e. different types of sensors), is dynamic, and is error-prone
* context-aware apps have to consider two factors:
    * **Scalability**: should cope with many diff sensors and users
    * **Robustness**: stability and reliability of results, adapt to new situations, resistance to frequent changes in the environment, component failure, and disturbing factors
* How to build a context-aware application:
    * specification: what context-aware behavior should be implemented? which context is required for that purpose?
    * acquisition: which sensors can be used to retrieve this context?
    * delivery and reception: how is the context represented, managed and exchanged?
       * context models
       * access mechanisms
       * context storage and management
    * action- what functionality do you implement and how?

### Context Sources and Models
* sources - sensed context (sensors or software) and inferred or derived context (combining context data to gain new info ["higher level context"])
* context type - sensed context (physical sensors and virtual sensors), inferred context (logical sensors)
* Context models
    * goal is to take in raw data and convert it to knowledge bits
    * transform data in a way that becomes easier to store and query
    * must be represented in a machine readable form to enable an application to use it
    * define the exchange of context information
    * has to provide a useful set of attributes for each context data -- ideally, it addresses how to cope with the incompleteness and ambiguity of context information
* existing models can be classified by means of the data structure they use for exchanging context info:
    * key-value model - simplest, room = A12, ID = 44
    * markup scheme model - hierarchically structured, <location confidence = "94%">
    * object-oriented model - allows encapsulation and reuse of parts of the model
    * logic based model - everything is a function (locatedAt("44","A12",80%))
    * ontology based model - consists of concepts, properties, relations, and axioms. provides way to specify core concept. 
    * contextFSM (Finite-state machine)

### ContextFSM
* System model - system is described as a set of continuous and discrete variables 
* context is a specific set of valuations of the system variables - bipartite mapping (params set to the values set)
* Example: artificial pancreas - closed loop control system
    * system variables - continuous variables (Blood glucose levels), discrete variables (bolus request levels), system parameters (control algorithms, location of user)

### Context Analysis
* how does the system evolve as the context changes?
* as mappings change the dynamics also change
* Challenges:
   * environmental changes due to context have long term effects on system dynamics
   * often the effects of context change are not memory-less
   * hence we have to analyze each context change sequence individually
   * Reception quality (Packet Delivery Ratio (PDR))
      * Multi-path reflection - indoor (PDR is high), outdoor (PDR is low)
* Solutions: Randomized Analysis - contexts and their changes can be represented using a state based model (markov chain)
    * contextFSM is a tuple {X, T} where X is a set of states and T is a transition matrix
    * problem: infinitely many state transition sequences

### Context Middleware
* Accessing context - 2 ways - queries (request) and event subscription (notified when a specific event occurs)
   * Concerns related to privacy and security, for example by specifying domain dependent policy rules for access controls
* Context Storage and Management - specify a well-defined interface for accessing the context data, answer queries and notify the actual applications of context changes
* Context management models - widget, networked services, blackboard model
* middleware - facilitates the development of context-aware applications by separating the detection and usage of context data
* most middleware approaches use an architecture with the following layers: sensors (hardware specific) data is retrieved, preprocessed, storage/mgmt by middleware 

### CareDroid: Example of Middleware
* easier to develop and more efficient by:
    * decoupling functionality
    * mapping and monitoring
    * integrating context adaptation into the runtime
* Developers develop context-aware applications without having to directly deal with context monitoring and context adaptation in the application code
* devs can focus on application logic
* monitors context of the physical envrion based on the configuration file, context monitoring and method replacement (performed by the runtime system)

### Dealing with Uncertainty
* Has to be handled in 3 areas:
    * sensing context information
    * inferring context info
    * using context info
* How to determine uncertainty of sensed context: can be reported by sensor, specify a relevance function to take freshness of context data into account
* how to determine uncertainty of inferred context: most widely used reasonoing strategies are probabilistic and fuzzy logic and bayesian networks
* how to use uncertain context info: specify required confidence level, only regard the context value with maximum probability as valid
    
## BraiNet
   
### Network of Brains
* Utilize pervasive brain monitoring, recognize mental state on the go and providing online feedback to the user
* Challenge: large amt of high frequency data, accurate recognition of mental states, real-time feedback to the user, energy efficient processing on mobile (offload for edge computing and execute in real-time constraints for machine learning & prediction)
* Brain-Computer Interface Systems have 3 main phases:
    * data acquisition
    * signal processing
    * application
* 3 main components of big data: velocity, veracity and variety
* Frequency band state:
    * delta (.5-4Hz) sleep activity
    * theta (4-8Hz) attention level
    * alpha (8-13Hz) relaxation at decr. attention levels
    * beta (13-30Hz) active concentration and alertness
    * gamma (30-100Hz) perception

### Machine Learning Intro
* Supervised classification - training data set (distance metric, find closest data points, configure a machine), test data set, classes
![image](https://user-images.githubusercontent.com/17733481/153778303-ac9a956f-fa24-4a32-ae68-251667ee96cd.png)
* In terms of training dataset, supervised learning has training data with labels and unsupervised learning has training data without labels
* Machine Learning framework - apply a prediction function to a feature representation of the image to get the desired output
* Learned model is specific trained perameters of the model
* classifiers: nearest neighbor - all we need is a distance function for our inputs. It uses a distance metric to classify the data that is nearest to the test sample without any training
* linear classifier - SVM, decision trees - formulate a line to separate the classes
* **SVM** - Linear Support Vector Machine Classifier - they formulate a line to separate two classes using a non-linear sigmoid function to convert into 0s and 1s

### Generalization
* basic method by which any supervised classification technique works, any supervised classification technique
* generalization error has three types of components: bias, variance, and noise
   
### Infrastructure and Applications
* SafeDrive - driver assist - according to mental states of drivers (levels of attentiveness), appropriate warning message will be provided to avoid accidents
* nMovie - according mental state, the movie scene may change
* E-bias - each person has unique brain signal patterns, patterns can be considered as signatures for identification
* AyLA - students attention level, the lecture materials may change
* prosthetic control, telepathy, control of VR objects
   
## Mobility Models
### Mobility Models
* Mathematical forms that tell us where, when and by how much a person is likely to move
* environment changes with mobility and so do resources, computing strategies change with the environment
* Characteristic of human mobility: random, point of interest, long journeys are OK (heavy tailed/levy distribution), periodicity, varying speed, varying directions

### Randomized Models of Mobility
* Random Walk Model - node chooses a random direction from [0, 2pi]
* Random Waypoint Model - node is initialized at a random location, upon reaching the destination the node pauses for a uniformly distributed random time
* Gauss-Markov Model - the speed and direction of the nth step depends on the (n-1)st step
   
### Finite Markov Chains
![image](https://user-images.githubusercontent.com/17733481/153780436-a7b01b53-a380-4909-9fcc-53a6e4e6726a.png)

![image](https://user-images.githubusercontent.com/17733481/153780431-d4605832-5cac-449e-bffd-832bdb5c856d.png)



## Machine Learning for Context Models
