# Energy-efficient Image Processing on FPGA

## Abstract
Convolution is widely used in image and video processing. Despite being simple to describe mathematically, it is a very intensive operation in terms of computation and memory usage. The ever-increasing popularity of photos and videos, especially on mobile devices like smartphones, has made it inevitable that we look for ways to perform convolution on handheld devices faster while maintaining power constraints. GPUs have been considered for accelerating performance, but they may not be the most ideal in low-power situations. We implemented a baseline solution and analyzed its performance in terms of latency and energy costs. After determining the energy hotspots and performance bottlenecks, we developed two different variations. One was designed to be more performant by exploiting the inherent parallelism in convolution across pixels. We achieved up to a 3.2x speedup compared to our original solution, but at a cost of 1.8x power increase. The other variation was able to achieve the same performance as the original but with a 3.3x power reduction. This was done using efficient use of buffers and selective memory management.

## Milestones 
1. Implement baseline 2D convolution on FPGA
2. Perform analysis on energy usage and latency
3. Identify hotspots and other areas for improvement
4. Implement proposed optimizations

## Schedule
* September 29 – October 19: **Implement baseline 2D convolution on FPGA**
* October 20 – October 26: **Complete midpoint presentation and report**
* October 27 – November 7: **Identify energy hot spots; Evaluate tradeoffs between energy and latency**
* November 8 – November 18: **Identify and implement optimizations**
* November 19 – November 26: **Evaluate performance and efficiency of optimized algorithm**
* November 27 – December 6: **Wrap up and complete final presentation**
* December 7 – December 14: **Complete final report**

## Overview
### 2D Convolution
Convolution is a mathematical operation on two functions that produces a third function.
For image convolution, the inputs to the convolution are the original image and kernel (which determines the type of processing to perform), and the output of the convolution is the altered image.
![alt text](https://github.com/sandybisaria/743castle/blob/master/system/convolutionfn.jpg)
![alt text](https://github.com/sandybisaria/743castle/blob/master/system/convolutionsobel.png)
![alt text](https://github.com/sandybisaria/743castle/blob/master/system/convolutionsobelexample.png)

### Flow of Baseline Algorithm
![alt text](https://github.com/sandybisaria/743castle/blob/master/system/convolutionflow1.jpg)
![alt text](https://github.com/sandybisaria/743castle/blob/master/system/convolutionflow2.jpg)

### Hardware Testbench
The do_conv module in this diagram would be swapped between different implementations.
![alt text](https://github.com/sandybisaria/743castle/blob/master/system/blockdiagram.PNG)

## (Milestone 2) Baseline Convolution Algorithm Characteristics
|Estimated Min Period (ns)|Uncertainty (ns)|Latency (cycles)|Latency (ms)|
|---|---|---|---|
|6.002|2.50|7603204|45.6|

![alt text](https://github.com/sandybisaria/743castle/blob/master/baseline/onchippowerbyfunction.PNG)
![alt text](https://github.com/sandybisaria/743castle/blob/master/baseline/onchippowertypical.PNG)

## (Milestone 4)
### Pipelined Convolution Algorithm Characteristics
|Estimated Min Period (ns)|Uncertainty (ns)|Latency (cycles)|Latency (ms)|
|---|---|---|---|
|10.498|2.50|2360327|24.8|

![alt text](https://github.com/sandybisaria/743castle/blob/master/pipelined/onchippowerbyfunction.PNG)
![alt text](https://github.com/sandybisaria/743castle/blob/master/pipelined/onchippowertypical.PNG)

### Energy-Efficient Convolution Algorithm Characteristics
|Estimated Min Period (ns)|Uncertainty (ns)|Latency (cycles)|Latency (ms)|
|---|---|---|---|
|6.002|2.50|7603204|45.6|

The timing results are in fact the same as the baseline convolution implementation.

![alt text](https://github.com/sandybisaria/743castle/blob/master/energyefficient/onchippowerbyfunction.PNG)
![alt text](https://github.com/sandybisaria/743castle/blob/master/energyefficient/onchippowertypical.PNG)

### Comparisons
![alt text](https://github.com/sandybisaria/743castle/blob/master/comparison/powernormalized.PNG)
![alt text](https://github.com/sandybisaria/743castle/blob/master/comparison/resourceutil1.PNG)
![alt text](https://github.com/sandybisaria/743castle/blob/master/comparison/resourceutil2.PNG)
