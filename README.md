# FPGA-Based Traffic Light Controller with Emergency Priority

## Project Overview
This project implements a Traffic Light Controller using Verilog HDL with an Emergency Priority Override system.

The design is based on a Finite State Machine (FSM) and was implemented and simulated using Xilinx Vivado on an FPGA platform.


## Features
- Main Road and Side Road traffic control
- Red, Yellow, Green light sequencing
- Timer-based state transitions
- Emergency override input
- Asynchronous reset



## Tools Used
- Verilog HDL
- Xilinx Vivado
- Spartan FPGA Board


### FSM States
The controller operates in five states:

- MAIN_GREEN
- MAIN_YELLOW
- SIDE_GREEN
- SIDE_YELLOW
- EMERGENCY

State transitions are controlled using:
- Clock signal
- 32-bit timer counter
- Emergency input signal


## 🚑 Emergency Priority Logic
When the emergency signal is HIGH:
- The system immediately switches to EMERGENCY state
- Main road is forced to GREEN
- Side road is forced to RED

When emergency signal becomes LOW:
- System returns to normal traffic sequence

## Timing Control
A 32-bit timer counter is used for delay generation:
- MAIN_GREEN duration controlled by timer threshold
- YELLOW states use shorter delay
- State transitions occur based on timer comparison

## Module Interface
Inputs:
- clk
- reset
- emergency

Outputs:
- main_road [2:0]
- side_road [2:0]

Light Encoding:
- GREEN  = 3'b001
- YELLOW = 3'b010
- RED    = 3'b100

## Simulation
Functional simulation performed in Vivado Simulator:
- Verified state transitions
- Verified emergency override
- Verified timer-based delays



## Implementation
1. Open Vivado
2. Create new RTL project
3. Add traffic_light_controller.v
4. Add testbench( Added in the project)
5. Run behavioral simulation


##  Learning Outcomes
- FSM-based hardware design
- Timer implementation using counters
- Priority-based digital system design
- FPGA synthesis and simulation


## Author
Rithesh Sherugar  
Student
Electronics & Communication Engineering
