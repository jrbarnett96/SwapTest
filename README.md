# SwapTest

## Overview

This repository contains an implementation of the quantum swap test, used to distinguish two quantum states. This test is then applied in two cases:

Given a randomly generated single qubit state with unknown parameters, the test is used to learn the parameters of a rotation that can replicate the state. 

Using only the distinguishing property of the swap test, we reconstruct a product state in which each qubit is in the state |0> or |1>.

I've included a Jupyter notebook for running this code and viewing benchmarks, as well as a conda environment file.

## Requirements

> Qiskit
> Scipy
> Numpy
> Matplotlib

I've provided a makefile and a conda environment file to use.

## Background

There'll be plenty of exposition in the notebook, but I figured I would use this space to go into more detail regarding the theory. What's the theory? *waves hands around* just about everything I feel is necessary to understand what's happening in the notebook, including details I ran into while reading into the problem. 

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

## Possible extensions

1. 
2. 
3.

## References



