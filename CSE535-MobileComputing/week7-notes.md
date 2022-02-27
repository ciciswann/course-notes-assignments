# Week 7 Notes

## Cyber Physical Systems (CPS) - Properties, Issues and Challenges
### IoT: 50 Billion Devices Jam
* 1% of physical world is connected to the internet
* Huge potential - innovative business process, operational efficiency, new customer services, smart cities and infrastructure
* IoT coined in 1999 by Kevin Ashton
* 1982 - Coke machine at CMU was connected to the internet to report its inventory and temp
* **IoT is a network of physical objects connected to the internet**
   * embedded systems with electronics, software, and sensors
   * enables objects to exchange data with a manufacturer
   * allows remote control
### IoT Enabled CPS
* Cyber-physical systems - main goal is to interact with the physical world (power plants, home, human body) - a system having sensors, its controllers and an actuation into a physical system enabled by IoT.
* Can create a closed loop control system - sensors interact with physical world, software module (controller) analyzes the sensor data and comes up with **actuation decisions** (external input that you give to physical system that drives its operation)
   * actuation example - setting the thermostat
* AI enabled CPS - smart grid, autonomous cars, robotic surgery, intelligent satellite imagery, artificial pancreas, performance feedback
### IoT Challenges
* Technology and inherent problems in the application
* Enabling technology pros/cons- 
    * Cloud computing - lack of context rich data, abundance of training examples, significant computatioon, significant storage
    * cloudlet/fog - limited context rich data, downloadable training examples, moderate computation, moderate storage
    * edge devices and sensors - context rich data, no training examples, limited computation, limited storage
 * Moving from sensors to the cloud - network delay increases, while uncertainty decreases
![image](https://user-images.githubusercontent.com/17733481/155862639-3ab15b90-d0a2-41c5-8e7c-299145d57a80.png)
* Computational needs - data and computation are not at the same place ("bringing computation to the edge") - classic offloading problem
* Properties, Issues, Challenges - dynamic distributed large-scale systems to control physical process, human-in-the-loop, cyber and physical components are integrated, operations in computing
* Heterogeneous entities with order of magnitude and difference in capabilities e.g. sensors, medical devices, servers (need a single middleware)
### IoT Examples
* Novel applications - investigator assist app (volunteer computing), patient data management
* crowdsensing/crowdsourcing - diet monitoring application
### IoT Problems
* Uncertainty of device availability and relevant data
* No single entity managing IoT devices - availability is uncertain
* moving devices - change context very quickly
* Security problems - prone to attacks
* contextual data provides deeper insights about the infrastructure
* uncertainty may cause task disruption
* device availability - proactive user recruitment
* resource prediction
   * State transition matrix using Markov Chain is a model that can be used to predict battery state and location in a smartphone
### Human Augmentation
* Semi-autonomous cars - interaction btwn human and machine
* Aircrafts - trending towards more automation (autopilot when cruising at high altitude)
* Virtual Reality - not safety critical like cars or aircrafts
* Artificial Intelligence - large number of AI enabled CPS
   * "No Oracle" Problem + Validation
   * Risk of Tampered Data - sensor errors + no oracle problems can lead to disaster (MCAS in aircrafts)
* human interaction in a semi-autonomous system is giving control to the human whenever a machine is uncertain.
## IoT Applications
### IoT Applications
* media, environmental monitoring, infrastructure, manufacturing, energy mgmt, medical, building
* Media IoT + big data - target advertisement to customized content
* Infrastructure - monitoring structural condition
* Large scale - smart city (buildings, water, mobility, energy, integration, public services)
* Traditional - transmission side and distribution side - privacy risk is why they don't share data
* Privacy is a key factor that prevents the infrastructure to sense and share data from being implemented in every home
* Smart home (different from connected home)
* Impact - civic engagement, privacy, autonomy, control, technology = active agent, IoT = human augmentation, data-driven decision making, security (spy on ppl in their own homes), increase in electronics waste 10x
### IoT Architecture Platform and Middleware
* Giving IP address to every entity (assumes TCP/IP 4G/Wifi)
* Challenges for software development in IoT
   * Heterogeneous sensors are available in an IoT environment - location of mobile device
   * 4 different classes of devices: sensors, smartphone/edge device, fog server, cloud
   * Networking - packet drops, entity doesn't respond
   * Resource management - fault tolerance, power mgmt
* Middleware - chooses expert solutions and comes up with code for IoT applications based on specifications
* Middleware has to be in every possible layer of IoT architecture - Software with a distributed set of codes that integrates to every layer of IoT architecture
* it can be a new programming language, set of APIs, set of system calls, OS, new distributed computing method
### IoT Middleware: TinyLink MobiCom 2017
![image](https://user-images.githubusercontent.com/17733481/155863747-c0c7fc48-f3cb-4b7c-abdb-50e6bbd6c8aa.png)
* two streams - hardware generation and software generation \
![image](https://user-images.githubusercontent.com/17733481/155863805-c07711d1-c0c2-4147-93f2-55772f97878c.png)
* solver - multiobjective optimization problem
* Arduino, LinkIt ONE, RasPi 2, Beaglebone black


