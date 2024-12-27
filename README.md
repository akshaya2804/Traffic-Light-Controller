This repository showcases a Traffic Light Controller implemented in Verilog, designed for effective traffic management with additional features like emergency vehicle handling, pedestrian crossing, and manual override. A comprehensive testbench is also included to validate the functionality.

FEATURES
   -Dynamic Traffic Control: Seamless transitions between main and side street lights.
   -Pedestrian Crossing Support: Walk/Don't Walk signal for pedestrian safety.
   -Emergency Mode: Priority green light for emergency vehicles.
   -Manual Override: Maintains the main street green light on demand.
   -Reset Functionality: System resets to default state when triggered.

DESIGN OVERVIEW

Inputs
clk: Clock signal for synchronization.
reset: Resets the system to its default state.
pedestrian_request: Indicates a pedestrian crossing requirement.
emergency_vehicle: Activates emergency mode.
manual_override: Maintains main street light green.

Outputs
main_street_light: 3-bit signal (Red, Yellow, Green) for main street lights.
side_street_light: 3-bit signal (Red, Yellow, Green) for side street lights.
pedestrian_light: 1-bit signal for Walk/Don't Walk indication.
 
State Machine
The controller operates as a state machine with the following states:
Main Green: Main street has green light.
Main Yellow: Transitioning main street to red.
Side Green: Side street has green light.
Side Yellow: Transitioning side street to red.
Pedestrian Crossing: Activates Walk signal for pedestrians.
Emergency Mode: Both streets show green for emergency vehicles.

State Timings
State	Duration (Clock Cycles)
Main Green	100
Main Yellow	20
Side Green	80
Side Yellow	20
Pedestrian Crossing	50

TESTBENCH

The testbench simulates multiple scenarios to ensure system reliability:
Normal Operation: Validates standard state transitions.
Pedestrian Crossing: Simulates pedestrian crossing request.
Emergency Mode: Tests emergency vehicle detection and handling.
Manual Override: Ensures correct response to manual intervention.
Reset Operation: Verifies system behavior during and after a reset.

 SIMULATION OUTPUT
 
During simulation, you can monitor key signals:
Main Street Light: Green, Yellow, or Red state.
Side Street Light: Green, Yellow, or Red state.
Pedestrian Light: Walk or Don't Walk signal.

Sample Output:

Time=100, Main Street Light=001, Side Street Light=100, Pedestrian Light=0
Time=200, Main Street Light=010, Side Street Light=100, Pedestrian Light=0
Time=300, Main Street Light=100, Side Street Light=001, Pedestrian Light=0
