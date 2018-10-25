# Energy Efficient Image Processing on FPGA

### Abstract
Convolution is widely used in image and video processing. Despite being simple to describe mathematically, it is a very intensive operation in terms of computation and memory usage. The ever-increasing popularity of photos and videos, especially on mobile devices like smartphones, has made it inevitable that we look for ways to perform convolution on handheld devices faster while maintaining power constraints. GPUs have been considered for accelerating performance, but they may not be the most ideal in low-power situations. In our project, we will implement a baseline solution and analyze its performance in terms of latency and energy costs. We plan to accelerate the algorithm by exploiting the inherent parallelism in convolution along with the parallelism and other hardware features offered by FPGAs. FPGAs can also make efficient use of memory using buffers and selective memory management. We intend to compare the tradeoffs between energy and latency, and we will identify energy hot spots in our baseline solution that were optimized out in our final.

### Milestones 
1. Implement baseline 2D convolution on FPGA
2. Perform analysis on energy usage and latency
3. Identify hotspots and other areas for improvement
4. Implement proposed optimizations

### Schedule
September 29 – October 19: **Implement baseline 2D convolution on FPGA**\
October 20 – October 26: **Complete midpoint presentation and report**\
October 27 – November 7: **Identify energy hot spots; Evaluate tradeoffs between energy and latency**\
November 8 – November 18: **Identify and implement optimizations**\
November 19 – November 26: **Evaluate performance and efficiency of optimized algorithm**\
November 27 – December 6: **Wrap up and complete final presentation**\
December 7 – December 14: **Complete final report**

### (Milestone 2) Baseline Convolution Algorithm Characteristics
![alt text](https://github.com/sandybisaria/743castle/blob/master/checkpoint/on-chip_power_by_function.PNG)
![alt text](https://github.com/sandybisaria/743castle/blob/master/checkpoint/on-chip_power_vs_temperature.PNG)
+ Timing (ns):\
   |Clock       |Target   |Estimated|Uncertainity|
   |------------|---------|---------|------------|
   |ap_clk      |20.00    |10.498   |2.50        |

+ Latency (clock cycles): 
    * Summary: 
    +---------+---------+---------+---------+---------+
    |      Latency      |      Interval     | Pipeline|
    |   min   |   max   |   min   |   max   |   Type  |
    +---------+---------+---------+---------+---------+
    |  2360327|  2360327|  2360327|  2360327|   none  |
    +---------+---------+---------+---------+---------+
