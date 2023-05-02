# Perceptron

Chris Stange
18-224/624 Spring 2023 Final Tapeout Project

## Overview

(high-level overview of what your project does, in a few lines)

## How it Works

(deeper description of your project's internal operations, along with any diagrams. large parts of this can likely be copied from your project design plan and/or RTL checkpoint submission)

![Computation](/docs/computation.png)

![Datapath](/docs/Perceptron_datapath.pdf)

![FSM](/docs/Perceptron_fsm.pdf)

## Inputs/Outputs

### Input signals:
* go
* update
* correct
* sel_out 
* in_val 

### Output signal:
* done
* classification
* sync
* out_val

## Design Testing / Bringup

⋅⋅* Simulation: In order to run the testbench ensure that the oss-cad-suite is enabled and that you are running on an x86 machine.  Use the command "make -f perceptron.mk" in the terminal.  The expected output can be seen below in the media section.  The testbench initializes the weights of the perceptron, runs inference, runs training, and then re-runs inference.  This is done for the logical functions OR, AND, and XOR.  This demonstrates the perceptrons ability to learn linearly separable functions (OR and AND) but also demonstrates its limitations in learning non-linearly separable functions (XOR).

⋅⋅* Testing after fabrication: 

(explain how to test your design; if relevant, give examples of inputs and expected outputs)

## Media
Testbench output:
![Testbench output](/docs/test.png)

## Further development

If there is anything else you would like to document about your project such as background information, design space exploration, future ideas, verification details, references, etc etc. please add it here. This template is meant to be a guideline, not an exact format that you're required to follow.