# SwapTest

## Overview

This repo contains a Jupyter notebook which implements the swap test on a simulated quantum computer using Qiskit. After reviewing the basics of state generation on a quantum computer, we use the swap test to not only distinguish our input state with another quantum state, but estimate the inner product in order to transform our input state into the target state. We do this for the case of an arbitrary single-qubit state, and extend it to a multi-qubit case in which each state takes the form of a bitstring (i.e. |01001>, |000>, etc.). 

This notebook provides basic plots and animations to showcase this circuit in action as well as its convergence properties. I've provided a conda environment file to take care of the dependencies.

## Installation

You'll need conda to create the provided environment. Assuming you have that installed, use `conda create env -f environment.yaml` to create the conda environment, `activate swap` to activate the environment, then go into Jupyter to launch the notebook. I provide more details on the implementation there. 

## Background

I'm not going to replicate a quantum information course in a readme, but I figured I would use this space to go into more detail regarding the theory surrounding the swap test and my implementation. What's the relevant theory? *waves hands* just about everything I feel is necessary to understand what's happening in the notebook, including details I ran into while reading into the problem. 

### Creating an arbitrary quantum state

We start with the ways in which you can write a qubit. There are a few. 

Suppose you have a single qubit, described by a superposition of the basis states |0> and |1>:

![superposition](/assets/images/statevector_amp.png)

The weights of this superposition are complex numbers which satisfy the normalization condition |a|^2 + |b|^2 = 1. 

On the other hand, these numbers can be reframed as (cos(theta/2), e^(iphi)sin(theta/2)), where (thetaRange) and (phiRange) if you want unique states (permuting by 2pi just gives the same state anyway)

(How is this derived?)

Once you've opened your mind to specifiying the quantum state to two angles, you can start to visualize the states as lying on a sphere, the Bloch sphere. We'll be using this sphere to represent our quantum states and visualize their differences.

Finally, you can transform these angles into spherical coordinates (x, y, z) on this sphere. This isn't going to be very useful in this project.

---





### Distinguishing quantum states

Without the ability to compute the inner product directly, we have to ask ourselves how we can decide whether two states are the same. As it turns out, there's a roundabout way of getting this answer with a quantum circuit. That circuit is the Swap Test [1], shown in the following figure. 

A single run of the circuit takes in three qubits: an ancilla qubit |0>, and the two quantum states we want to distinguish. 

### Approximating a 

### More but simpler: approximating product states

## Further improvements

1. 
2. 
3.

## References



