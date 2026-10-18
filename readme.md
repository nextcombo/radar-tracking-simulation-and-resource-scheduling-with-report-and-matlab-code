# Radar Tracking Simulation and Resource Scheduling [with Report and MATLAB Code]

Figure 1: Simulation flowchart of target motion model point traces
II. Data Processing Radar data processing and radar signal processing are both important components of modern radar systems. Signal processing is used to detect targets, utilizing certain methods to obtain various useful information about the target. Data processing can further process the target's trajectory and track, predicting the target's position at future moments, forming a reliable target trajectory, thereby achieving real-time tracking of the target. This article utilizes simulated trace data, sending target information to the trajectory processing module in accordance with a predetermined format for various trajectory processing tasks such as target trajectory-related filtering and tracking. Finally, the processed trajectories are sent to the overall control console in a network format for display. The radar data processing flow is shown in Figure 2.
Figure 2: Radar Data Processing Flowchart
2.1 Preprocessing
The input data for radar data processing often contains some interference. Data preprocessing is the process of filtering out data before the data processing stage, eliminating those that fall outside the thresholds, leaving only the data that passes all decision thresholds. The advantage of data preprocessing is that it significantly reduces the scale of the data during subsequent data processing, significantly decreases computational load, and to some extent, alleviates the burden on computers, enhancing the speed and accuracy of data processing, as well as reducing the likelihood of false tracks forming. The flowchart of data preprocessing is shown in Figure 3. In this paper, the distance threshold for preprocessing is set at 300m~3600000m, and both the azimuth angle and elevation angle thresholds are set to .
Figure 3: Data Preprocessing Process Diagram
2.2 Portman
The Boom is a region generally divided into initial and related booms. The initial boom is used during the initialization phase of a trajectory, centered around an arbitrary point, defining a spatial range within which the target's observation values may occur. Due to the long distance between the target at the start of a trajectory, it is beneficial to establish a large boom for better capture of the target. The related boom is a spatial area centered on the predicted value of the tracked target, specifying the range within which the observed values of the tracked target may occur. The determination criteria for the shape and size of the related boom are to ensure that the probability of real observations falling within the boom is high, while also preventing the related boom from containing too many irrelevant observation points. Generally, the size of the related boom should match the type of target being tracked, as this paper focuses on correlation in polar coordinates, hence using a sector-shaped correlation boom in polar coordinates, as shown in Figure 4.
Figure 4: Polar coordinates of a sector-related wave gate.
2.3 Track Start
The starting point of the track is from when the target falls within the radar detection range to the first point where the track is established for that target. The purpose of track initiation is to quickly establish a track for targets entering the radar's effective range, and to minimize the creation of false tracks. The algorithm used in this paper for track initiation is the logic method, also known as the sliding window method, as shown in Figure 5.
Figure 5: Schematic diagram of the sliding window method.
2.4 Data Integration
The text discusses the technical requirements for a product, specifically the manufacture of radar-detected vehicles. It outlines the process of data association between radar observations and other time frames or existing tracks, using the Kalman filter algorithm. The article explains how to establish relevant wavefronts based on reliable track predictions for each target, which is crucial for accurately associating point traces with tracks.

2.5 Tracking Filtering
Tracking filtering involves processing data that have been associated with reliable tracks to estimate the state of the target, thereby achieving continuous tracking. The Kalman filter algorithm is applied in this study, focusing on the x-axis direction for simplicity.

Firstly, the motion of the target along the axis can be described by the following state equation:

In matrix form, it reads:

Here,

and

represent zero mean noise sequences with known variance.

Considering the radar observations, the observation equation is:

where

is a zero-mean noise sequence with known variance.

Based on the correlation theory, the following iteration formula can be derived:

where

reflects the estimation of the current state from previous observations.

The predicted error covariance can be expressed as:

For optimal filtering, the iteration expression is:

where K(k) is the Kalman gain.

The filtering error covariance is:

When applying these formulas for Kalman filtering, initial values need to be specified. Since it's common in practice to not have access to the initial state of the target, we can use previous observations to establish an initial estimate for the state, for example, using the first two observations:

This results in an estimated error of
1. Error Covariance Matrix:
2.6 Simulation Results
Utilizing Matlab to simulate the radar data processing workflow, we can obtain the starting points of tracks as shown in Figure 7, the original track as depicted in Figure 8, and the direction of tracks displayed as shown in Figure 9.
Figure 7 Track Starting
Figure 8 Radar Original Track Map
Figure 9 Radar Track Simulation
3. The beam steering capability of resource-scheduling array antennas is a significant characteristic distinguishing phased array radars from other types of radars. An advanced resource-scheduling method is key to leveraging this advantage. The simulation and implementation of the scheduling module are central to the realization of phased array radars. To perform multiple tasks, phased array radars require the scheduling module to allocate radar time and energy resources among various tasks, thereby achieving optimization of the overall radar performance. This paper employs an adaptive resource-scheduling strategy, with the algorithm flowchart shown in Figure 10.
Figure 10 Adaptive Scheduling Algorithm Flowchart
During the Matlab simulation experiment, the specific process is shown in Figure 11. The experimental results are depicted in Figure 12.
Figure 11 Adaptive Scheduling Algorithm Process
(a) Event Request
(b) Adaptive Scheduling Algorithm Scheduling Sequence
Figure 12 Adaptive Scheduling Algorithm Experimental Results
4. Issues:
1. The track simulation is set for predefined tracks, which currently has limited capabilities and does not implement target tracking route simulation integrated with the entire phased array radar.
2. The resource scheduling only implements a part of the algorithm flow, and the parts that have not been implemented are due to poor display effects, leading to simplification of the algorithm flow.

## Images

![Radar trace simulation, resource scheduling [with report and MATLAB code]](01.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](02.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](03.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](04.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](05.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](06.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](07.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](08.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](09.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](10.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](11.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](12.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](13.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](14.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](15.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](16.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](17.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](18.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](19.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](20.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](21.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](22.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](23.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](24.jpg)
![Radar trace simulation, resource scheduling [with report and MATLAB code]](25.jpg)

<!-- PAYMENT_BLOCK -->

## Get this dataset

- Payment link (Stripe): [Buy now](https://buy.stripe.com/3cs8yP7sY87d0vu9AB)
- Payment QR code: ![Payment QR code](pay.png)

<!-- /PAYMENT_BLOCK -->
