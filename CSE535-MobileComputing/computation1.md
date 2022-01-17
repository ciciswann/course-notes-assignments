# Computation Practice 

### Problem 1
We live in an age of semi-autonomous cars: The driver is in control most of the time, but during critical scenarios when the system understands that the driver is incapable of taking action, the car takes over the decision making.

 
Consider a brain mobile interface application that assists drivers on a freeway by monitoring their drowsiness. The driver wears a Neurosky headset that senses brain signals (EEG) at  **500 Hz**. Each brain data point is a **32-bit** floating point number. The brain signal is collected by a smartphone and sent to a server, where complex machine learning algorithms are used to determine the drowsiness level of the driver.

 
Additionally, the car is equipped with a 360° camera and sensors on the steering wheel, which are all interfaced with the driver’s smartphone. The data rate of the wheel sensors is  **2 kbps**, the data rate of the camera is  **200 kbps**.

 
Using data from all of these sources, the driver assist system attempts to predict impending accidents. If the system detects that the driver is drowsy and predicts an impending accident, the system should react with some actuation, either automatic braking or steering. After collecting **5 seconds** worth of data, the driver assist system has only **3 seconds** to decide.

 
There are two options for performing all of the related computation: (a) use a datacenter, or (b) use a fog server (such as a laptop with internet connectivity that is travelling with the driver). The datacenter upload speed is  1 Mbps, whereas the fog server upload speed is  **3 Mbps**. The datacenter computation speed is  **750 kbps** (i.e., the datacenter can finish the computation on **750 kb** of data in 1 second), while the fog server computational speed is  **400 kbps**.

 
Suppose the failure rate of the cloud server is **0.1**. This means that **10%** of the time the cloud will send a failure message back to the driver assist system. When this occurs, the system must transfer all of the information to the cloud again and redo the computation. The time taken to communicate that a failure has occurred is 210 milliseconds. What is the average  total time taken for both communication and computation to be performed in the cloud, in milliseconds?  (Write your answer as one number, rounded up to the nearest integer.)

### My Calculations

#### Communication Time Calculation:
Data collected is 500 * 32 = 16,000 bits \
in 5s - 80,000 bits or 80kb \
wheel - 2 * 5 = 10kb \
camera - 200 * 5 = 1000kb

**total data collected**: 1090 kb

Data Center - 1090/1000 = 1.09 seconds or 1090ms \
Fog - 1090/3000 = 363ms

#### Computation Time:
Data Center - 1090/750 = 1453ms \
Fog - 1090/400 = 2725 ms

### Average Total Time:
Data center - comm. + comp. \
1090 + 1453 = 2543ms \
.10(210+2543)+.90(2543) = **2564ms**

