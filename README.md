# mobile_robot_sim_setup
Setup for simulating mobile robot in Coppleiasim(V-REP)

## Setup:
OS: Ubuntu 20.04
Python: 3.6.x
Coppeliasim: V4.3.0

## Usage:

  1. Ensure Coppeliasim is installed on your system 
  2. Launch Coppeliasim, open the provided [scenario](https://github.com/BijoSebastian/mobile_robot_sim_setup/blob/main/mobile%20robot.ttt)
  3. Start the simulation 
  4. Launch main.py(Ensure the code has executable permissions)
     
## Working 

The main file sets up the simulation by establishing connection, obtaining handles, using the handles to obtain the position of the walls within the simulated scenario, read the position and orientation of the robot as well as goal point, turn the robot and move the robot forward.
Note that this is just a demonstration of some of the basic capabilities available.

All of the interactions with Coppleiasim is contained within the [sim_interface file](https://github.com/BijoSebastian/mobile_robot_sim_setup/blob/main/sim_interface.py)
For the sim_interface to work it needs the files sim.py and simConst.py. The code relies entirely on the [Legacy remote API functions (Python)](https://www.coppeliarobotics.com/helpFiles/en/remoteApiFunctionsPython.htm). The [sim_interface file](https://github.com/BijoSebastian/mobile_robot_sim_setup/blob/main/sim_interface.py) contains wrappers on top of the API functions to simplify mobile robot simulation within Coppeliasim. 

### sim_init()
Closes all existing connections to Coppleiasim and creates a new connection to the default socket opened by Coppleiasim at the start of the simulation

### get_handles()
To interact with any object in Coppleiasim we need to first obtain the objects handle. This handle needs to be provided in subsequent function calls for setting the objects position, reading the objects position, setting velocity for motor etc.

### start_simulation()
Wrapper for the simxStartSimulation function to check if the simulation started without errors.
Ideally using this right after the sim_init, should remove the need for step 3 in Usage section.



