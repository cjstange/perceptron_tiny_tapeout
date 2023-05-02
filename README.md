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

All signals are 1-bit unless otherwise stated.

### Input signals:
* go - Used to control the loading of input values. Set to 1 to load in_val and move to next state.
* update - Set to 0 if running inference. Set to 1 if running training.
* correct - The correct classification of the inputs.  Used for training.
* sel_out - 2-bit input select line for out_val.  Used to read outweights combinationally. 0 -> output of the adder, 1 -> W2, 2 -> W1, 3 -> W0.
* in_val - Where all 6-bit inputs are loaded.  Used to loads weights, learning rate, and input values.

### Output signal:
* done - Notifies when the computation is finished.  Classification will be valid on next clock edge if running inference, weights already available if running training.
* classification - The perceptrons classification of the inputs.
* sync - Set high after successfully loading an input. Allows synchronization of hardware thread with external drivers.
* out_val - Where weights can be read out of the perceptron. Output selected by sel_out.

## Design Testing / Bringup

* Simulation: In order to run the testbench ensure that the oss-cad-suite is enabled and that you are running on an x86 machine.  Use the command "make -f perceptron.mk" in the terminal.  The expected output can be seen below in the media section.  The testbench initializes the weights of the perceptron, runs inference, runs training, and then re-runs inference.  This is done for the logical functions OR, AND, and XOR.  This demonstrates the perceptrons ability to learn linearly separable functions (OR and AND) but also demonstrates its limitations in learning non-linearly separable functions (XOR).

* Testing after fabrication: TODO

## Media
### Testbench output:
![Testbench output](/docs/test.png)

## Further development

If there is anything else you would like to document about your project such as background information, design space exploration, future ideas, verification details, references, etc etc. please add it here. This template is meant to be a guideline, not an exact format that you're required to follow.