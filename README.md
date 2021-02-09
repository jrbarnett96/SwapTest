# SwapTest

Outline 

- Overview
-- What it is 
-- What it does
-- What's in the repo
- Installation
-- Use conda to create environment
- Background
-- Distinguishing quantum states
-- Creating an arbitrary quantum state on a quantum computer
-- 
-- 
--


## Overview

This repo contains a Jupyter notebook which implements the swap test on a simulated quantum computer. After reviewing the basics of state generation on a quantum computer, we use the swap test to not only distinguish our input state with another quantum state, but estimate the inner product in order to transform our input state into the target state. We do this for the case of an arbitrary single-qubit state, and extend it to a multi-qubit case in which each state takes the form of a bitstring (i.e. |01001>, |000>, etc.). 

This notebook provides basic plots and animations to showcase this circuit in action as well as its convergence properties. I've provided a conda environment file to take care of the dependencies.

## Installation

You'll need conda to create the provided environment. Assuming you have that installed, use [insert code here] on environment.yaml to create the environment, then go into Jupyter to launch the notebook. I provide more details on the implementation there. 

## Background

There'll be plenty of exposition in the notebook, but I figured I would use this space to go into more detail regarding the theory. What's the relevant theory? *waves hands* just about everything I feel is necessary to understand what's happening in the notebook, including details I ran into while reading into the problem. 

### Creating an arbitrary quantum state

I'm not going to replicate a quantum information course in a readme, but I think it's important to review the basics of single-qubit representation first. There are a few. Once you've specified a basis, the qubit is described by two complex numbers that satisfy the normalization condition. 

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



