![image](https://github.com/amo3315/ML/blob/master/Dataset/%E5%AE%9E%E9%AA%8C%E5%AE%A4logo.png?raw=true)
### 1.INTRODUCTION OF OUR DATASET
Vertical dual bearings rotating machinery, which is common in the industry, exists a bearing center inconsistent problem. This problem will lead to the worsening degree of wear and shortening service life of bearings. In some extreme cases, it could even lead to the tilt of the column, and the sudden fall of the column, finally resulting in injuries and deaths. To analyze this problem, a system-level destructive experiment was designed and carried out in Automatic Washing Equipment for CRH (AWE, a double-bearing rotary machine for cleaning the body of high-speed train). We describe the continuous changing process of bearings from normal (healthy) state to abnormal (fault) state in a discrete way by artificially changing the degree of concentricity deviation. Running data of every equipment state is collected using the Industrial Intelligent Gateway developed by us. Finally, the NGIRC-2022-AWE-Dual-Bearings-Industrial-Dataset is constructed. 

The main contributions of our work can be summarized as follows:

(1)The dataset contains five kinds of data, including vibration acceleration signal, electrical signal, temperature, swing and inclination, so that it could provide multi-dimensional sensor signals (multiple features) labeled dataset for researchers. 

(2)This destructive experiment mainly aims at the bearing center inconsistent problem of vertical dual bearings rotating machinery, and realizes the health perception task at the system level. 

### 2.INTRODUCTION OF INDUSTRIAL DATA ACQUISITION SYSTEM
We developed a industrial multi-sensor data collection system including 12 sensors in 6 kinds based on intelligent gateway which is shown in Figure 1.11. This system implements the elemental  functions of data acquisition, storage and transmission, so that it can provide reliable guarantee for the establishment of the dataset. 

In order to describe and record the running state(the health state) of the equipment, the system integrates six kinds of common sensors including accelerometer, hall ring, magnetic suction temperature sensor, proximity sensor and laser displacement sensor to respectively collect vibration data, current data, temperature data, swing data, inclination data, and rotation rate data. The deployment of sensors is shown in the Figure 1.

![image](https://github.com/amo3315/photo/blob/master/fig1.jpg?raw=true)

Hall ring is placed in the electric box to collect the three-phase current. Single-axis accelerometer is placed on the upper and lower bearings to collect vibration signals. Magnetic suction temperature sensor is placed in four positions including electric motor, reducer, upper bearing and lower bearing to collect temperature signals respectively. Laser displacement sensor is placed on the support frame to collect swing signal. Proximity sensor is placed on the rotating chassis to collect rotation rate signal. 

Industrial Intelligent Gateway collects sensor data through Ethernet, Modbus 485, RS232, USB2.0 and stores all of the data in local MongoDB database. 

### 3.DESTRUCTIVE EXPERIMENT SCHEME
For equipment with a long living cycle, there are two major challenges in capturing fault (especially multiple types and severity of faults) data from the whole lifecycle:

(1)	The run data of the whole lifecycle contains a lot of redundant data. Unfiltered storage and transmission will certainly cause great pressure on the data acquisition system. 

(2)	It is difficult to accurately classify data into corresponding health status from high frequency sampled signals, so the collected data can’t be correctly labeled. 

Therefore, in order to obtain fault data of various types and severity, a destructive experiment was designed and carried out to artificially simulate the different severity of concentricity deviation of vertical double bearings. The implementation is that adding different number of shims which is placed at the connection between the upper bearing and support arm, each shim is 3mm thick. Considering the actual safety factors, the number of shims is increased from 0 to 5, which will result in 6 level of deviation for the problem being explored. 

The collected data includes six kinds which are vibration acceleration data, current data, temperature data, gyroscope data, swing data, dip data and rotation rate data. Among them, vibration acceleration data has two channels, sampling frequency is 4 kHz; current data has three channels, sampling frequency is 20 Hz; temperature data has four channels, sampling frequency is 5 Hz; gyroscope data, swing data and inclination data only have one channel, sampling frequency is 20 Hz. 

In the actual process of overhaul, the single working time of the Automatic Car Washing Equipment is 10 minutes, and the task intervals depends on the arrival frequency of trains. Therefore, in order to fully simulate the facts, we set the acquisition length of single group to 10 minutes, the task intervals is selected randomly. Each level of deviation has 7 groups of data. 

### 4.INTRODUCTION OF DATA STRUCTURE
We classify the data according to the labels which are different concentricity deviation degree. Folder names are label names, such as Normal, One-chip, etc. Each type of the labels contains all the data files of this group, which are saved in JSON format. Each JSON file, called as one batch, contains all sensor data collected in 10 minutes. The specific organizational structure is shown in Figure 2.

![image](https://github.com/amo3315/photo/blob/master/fig2.jpg?raw=true)

### 5.HOW TO CITE
Dataset is currently available through this site and externally housed through University Digital Repositories. The usage rights are provided individually alongside the measurement data.

It is asked that if any data is used, then a citation to the corresponding published work should be made (if this exists). Acknowledgement is also asked to be given to this website with the following words. “Acknowledgement is made for the dataset used in this work provided through NGIT-2022-AWE-Industrial-Dataset”. 
