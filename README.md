# WAC2: Wheel Angle Calculator

## Overview

The **WAC2** repository is part of a broader Vehicle ECU and CAN Modeling project. WAC2 stands for "Wheel Angle Calculator" and is responsible for calculating the desired tire steering angles based on the vehicle's dynamic states. This repository is identical to WAC1, WAC3, and WAC4, serving as one of the core components that ensure accurate steering control in the simulated vehicle network.

## Code Content

WAC2 processes vehicle state data to determine the optimal steering angle for each wheel. This functionality is crucial for maintaining vehicle stability and responsiveness during dynamic maneuvers.

### Key Files:

- **`WAC2.c`**: Core logic for calculating the wheel angle based on the vehicle's states.
- **`WAC2_data.c`**: Data management and configuration specific to WAC2.
- **`ert_main.c`**: Main program file, including CAN communication routines.
- **`linuxinitialize.c`**: Linux-specific initialization routines.

## Compilation

To compile the WAC2 code, use the following GCC command:

```bash
gcc -o mycode /home/debian/WAC2_ert_rtw/WAC2.c /home/debian/WAC2_ert_rtw/WAC2_data.c /home/debian/WAC2_ert_rtw/ert_main.c /home/debian/WAC2_ert_rtw/linuxinitialize.c -I/home/debian/WAC2_ert_rtw -lm -lpthread
```
This command compiles the necessary source files into an executable named `mycode`.

## CAN Setup
Before running the compiled code, ensure that the CAN interface is correctly set up. The setup is done using the following bash script:

```bash
bash can_setup.sh can1 1000000
```
This command configures the CAN interface (`can1`) with a baud rate of 1 Mbps, identical to the setup used in WAC1, WAC3, and WAC4.

## Execution
Once the CAN interface is set up and the code is compiled, you can execute the program using:

```bash
./mycode
```
This will run the Wheel Angle Calculator code, enabling it to calculate and communicate the desired steering angles for all wheels within the simulated vehicle network.
