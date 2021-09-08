# **CarND-PID-Control-Project-8** 
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

Overview
---

This project implements a PID controller for autonomous driving on a structured path. The PID algorithm runs based on the **cross-track error (CTE)**. In this project, CTE is provided by udacity's simulator via websocket - CTE is computed using the ego vehicle's distance from the center of the lane. The controller returns steering & throttle values (commands) to drive the car around the (simulator's) track.


Directory Structure
---

```
root
|   CMakeLists.txt
|   cmakepatch.txt
|  
|___src
    |   main.cpp
    |   PID.h
    |   json.hpp
    |   PID.cpp
```

PID Controller (Parameters)
---

The diagram below provides a visual summary of the anatomy of the PID controller.

- **P**: *Proportional* accounts for the present values of the error. 
- **I**: *Integral* accounts for all past values of the error.
- **D**: *Differential/Derivative* accounts for plausible future trends of the error based on current rate of change. 

![img1](https://user-images.githubusercontent.com/76077647/132515503-1e15b098-4ce2-42fa-b2f7-01e09c5f3b3c.JPG)

**Fig 1** credit to [microcontrollers lab](https://microcontrollerslab.com/pid-controller-implementation-using-arduino/)

Determining PID Hyperparameters
---

Finding the optimal set of parameters for the *PID* controller requires experimentation. This can be accomplished either manually, which may be a tedious task unless we have prior knowledge of the PID-parameter-configuration. In the absence of that knowledge, we can naively discover these parameters using trial-and-error or could use a more algorithmic approach such as *coordinate ascent* aka *Twiddle*. This implementation uses the naive approach granted we had knowledge of the optimal configuration and the simulated environment isn't as complex. 


Code Style
---

Please (do your best to) stick to [Google's C++ style guide](https://google.github.io/styleguide/cppguide.html).

Dependencies
---

- cmake >= 3.5

    - All OSes: [click here for installation instructions](https://cmake.org/install/)

- make >= 4.1

    - Linux: make is installed by default on most Linux distros
    - Mac: [install Xcode command line tools to get make](https://developer.apple.com/xcode/features/)
    - Windows: [Click here for installation instructions](http://gnuwin32.sourceforge.net/packages/make.htm)
    
- gcc/g++ >= 5.4

    - Linux: gcc / g++ is installed by default on most Linux distros
    - Mac: same deal as make - [install Xcode command line tools](https://developer.apple.com/xcode/features/)
    - Windows: recommend using [MinGW](http://www.mingw.org/)

- [uWebSockets](https://github.com/uWebSockets/uWebSockets)

    - Run either install-mac.sh or install-ubuntu.sh.
    - If you install from source, checkout to commit e94b6e1, i.e. 
   
    ```
    git clone https://github.com/uWebSockets/uWebSockets 
    cd uWebSockets
    git checkout e94b6e1
    ```
    

Basic Build Instructions
---

1. Clone this repo.
2. Make a build directory: mkdir build && cd build
3. Compile: cmake .. && make
4. Run it: ./pid

Future Improvements
---

To improve current implementation, we will consider employing *coordinate ascent* for hyperparameter tuning.

References & Credits
---

* udacity (self driving car nanodegree - CarND-PID-Control-Project)
* course peers
