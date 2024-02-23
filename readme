# Drone Simulation System
# Authors: Seyed Alireza Mortazavi|Pezhman Rezaei Salkhori (AMPER group)

## Overview

This project simulates a drone operation environment, integrating multiple components for real-time control, monitoring, and management. It usees shared memory for efficient inter-process communication, allowing real-time updates and control flows betweens a simulated drone, control server, keyboard manager, graphical window interface and a watchdog for system stability. The logging mechanism ensures that operations are recorded for debugging or analysis. Signal handling provides graceful startup, shutdown, and error handling.

## Components

- **Drone Simulation:**
The Drone component simulates a drone's operational behaviors. It's essentially the heart of the system, where the simulated drone's movements, status updates, and reactions to commands are handled. This component utilizes shared memory to communicate with other components. The drone's motion is calculated numerically based on physical parameters, and its position is updated according to user input received from a shared memory board. The code also includes signal handling for interrupt signals (SIGINT) to gracefully terminate the program and log relevant information. Additionally, the program creates log files for process information and data, providing insights into the execution and behavior of the drone simulation.The code also includes signal handling for interrupt signals (SIGINT) to gracefully terminate the program and log relevant information. Additionally, the program creates log files for process information and data, providing insights into the execution and behavior of the drone simulation.

- **Master:**
This component acts as the central control unit, spawns child processes for different roles within the simulation and orchestrating the startup, operation, and shutdown of the simulation. It initializes logging of important information about these processes, like their unique IDs (PIDs) and the time when they started. It also set up to handle a specific signal (SIGINT), 
allowing for a controlled way to stop one of the processes. The main program waits for all the created processes to finish their tasks before it completes. This ensures a 
coordinated and gracefully shutdown of the entire system.

- **Server:**
This component creates shared memory for inter-process communication, initializes a server socket and waits for client connections. The program logs process information and data into files, 
handling errors and signals like SIGINT. Upon receiving a SIGINT signal, it cleans up resources, unlinks shared memory, closes sockets, and terminates the process.

- **Keyboard Manager:** 
This component applies physics-based calculations to simulate drone movement in response to user inputs, considering forces, velocity, and environmental constraints. It Interprets keyboard inputs to control the drone's motion, adjusting its velocity and direction based on predefined commands. Similar to the master component, it can safely terminate its operation in response to signals like SIGINT and it also records actions and states related to the keyboard management, facilitating troubleshooting and analysis.

- **Window:** 
The window component uses the NCurses library to create a simple interactive window for a drone simulation. It reads shared memory containing drone positions, updates the display accordingly and captures user input to control the drone. The code handles signals, logs process information, and efficiently manages the graphical interface. It demonstrates the integration of inter-process communication, graphical user interface development, and signal handling in a drone simulation environment.

- **Watchdog:** 
The watch_dog componet monitors the activity status of multiple processes by analyzing their last recorded activity times. It reads log files, extracts process IDs and timestamps, and checks for inactivity over a specified duration. If any process remains inactive for a set period, the program signals their termination. The code effectively serves as a watchdog mechanism for process activity, ensuring continuous operation.

### Prerequisites
- Linux-based operating system
- GCC compiler
- `ncurses` library installed (for window component visualization)

### Clone the repository:

    ```sh
    git clone https://github.com/AlirezaMortazavi/dronesimulation.git
    ```
