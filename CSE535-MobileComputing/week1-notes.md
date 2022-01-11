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
* **Disadvantages**
  * Lower resources than cloud for storage and computation

### External Sensors

### Cloudlets

## Adaptation and Smartness

