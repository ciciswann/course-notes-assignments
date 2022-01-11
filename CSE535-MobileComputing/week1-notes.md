# Week 1 Mobile Computing Notes

* [Mobile Computing Models](#mobile-computing-models)
  * [Smartphone](#smartphone)
  * [Smartphone + cloud](#smartphone-and-cloud)
  * [Fog Server](#fog-server)
  * [External Sensors](#external-sensors)
  * [Cloudlets](#cloudlets)
* [Adaptation and Smartness in Mobile Computing](#adaptation-and-smartness)

## Mobile Computing Models
### Smartphone
* Has a CPU (Quadcore), GPU, Batteries, Radio (WiFi, Bluetooth, etc.)
  * Battery is nearly 60-75% of the entire form factor of the device
* Sensors are for (among other things) context-aware computing
  * 2 cameras for stereo vision to measure depth
  * IMU sensors - accelerometer, gyroscope and orientation
    * Accelerometer - acceleration
    * Gyrometer - angular velocity
    * Orientation - angle of inclination
  * Physiological sensors
    * heart rate sensors
  * GPS
* The reason a smartphone has so many radios is because it's also intended to be an **edge device**
* What can you do?
  * Calls
  * File transfer
  * Games - single player
  * Track location - limited
#### Limitations of smartphone model
* Can't connect to the cloud - no cloud server backing
* Number of apps that can run is reduced

### Smartphone and Cloud
* Smartphone interfaced with a cloud server (hosted in a data center) - connected via  wifi/cellular
* This enables many different applications:
  * Email servers
  * Facebook, Youtube
* **Raises different concerns:**
  * Security - establishing a communication channel that can be vulnerable to loss of private data
  * Availability/Reliability - wireless comm. is unpredictable (may or may not have signal), load on the cloud (response time), TCP/IP best effort
  * Communication time - trade off exists between communication time and computation time
  * Offloading - do you want to execute an entire algorithm in the smartphone *or* do you want to transfer the computation to the server?

### Fog Server
* Fog is *closer* to you than a cloud
* It's smaller scale than cloud that's supplementary (i.e. your own laptop)
* Trade off between communication and computation when it comes to fog vs. cloud
* **Advantages**
  * Less communication time compared with cloud - faster access to computation bc it's near to you
  * Support multiple protocols (layers of communication) - may be more secure than cloud (or might not, depends)
* **Disadvantages**
  * Lower resources than cloud for storage and computation
* **Issues** (Resolved through proper mgmt)
 * Not as fast as cloud - can be resolved by optimizing code to run in a particular fog server
 * Machine Learning - have applications with trained machine learning models
  * Supervised classifier (sequence of attributes labelled with a proper class) - training test

### External Sensors
* They can connect with various types of communication mechanisms so heterogeneous communication capabilities are needed (Bluetooth, NFC, WiFi)
* Examples:
  * ECG - cardiac sensors
  * Brain sensors
  * Wristband - fitbit
  * fMRI - brain scans
  * CGM - blood glucose levels
* **Issue is that they can be very resource constrained**
  * Security - huge computational overhead for encryption, etc.
  * Low computation and storage capacities
* **Advantages**
  * Provides *context rich data* - context is the status of the environment (i.e. temperature, heart rate)
  * Data -> Knowledge -> "Smart" applications
* Sensors are an integral part of "smart" applications

### Cloudlets
* Not used widely and novel
* May or may not be far off, but they are much smaller computing devices that are around you, but also may or may not be closer to you or on the same network (i.e. other people's smartphones)
* Ad hoc Cloud - agreement to share a part of another computer's computational services. Setting up an adhoc network using a WiFi or Bluetooth communication mechanism, dividing the application into large number of threads, and sending these threads to each of the smartphones near you following some constraints.
 ![image](https://user-images.githubusercontent.com/17733481/149023056-237c63ec-945e-4454-b800-9f21c2df797b.png)
* **Volunteer computing** paradigm - receiving cloud services not from a data center but from other people's devices
  * Peer 2 Peer computation mechanisms - similar to torrents
* Smart Investigator -
  * Create a timeline for a missing person
  * Give police access to an application, pictures can be shared between all people related (in some way) to this missing person and it will match the image to all other images owned by the people related to the missing person. Collecting those images (face mapping) and creating a timeline from them and the person's location. (significant implications on privacy)
  * Would make use of volunteer computing


## Adaptation and Smartness

