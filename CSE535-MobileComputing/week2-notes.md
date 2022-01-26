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
    * action
## BraiNet

## Mobility Models

## Machine Learning for Context Models
