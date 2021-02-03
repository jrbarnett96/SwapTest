# SwapTest

## Overview

An implementation of the swap test, used to reconstruct an arbitrary product state

This repository contains two main tracks: a script taking arguments that will then be taken as initial parameters of the circuit, and a Jupyter notebook that can be used to run this program step by step. Alongside the main script is a file containing all relevant functions, and a file containing tests which verify (to a point) that this circuit is doing what we want. 

## Requirements

> Qiskit
> Scipy
> 
>

I've provided a makefile and a conda environment file to use.

## Background

I should probably go into a little more detail.

The question: given an initially blank qubit, how do we tune its parameters to match that of an arbitrary reference state?

We approach the solution to this problem in steps.

### Creating an arbitrary quantum state

Let's start with the single-qubit case. Absent a global phase factor, the most general single-qubit statevector is represented by a pair of angles
(theta, phi), and in statevector form we have cos(theta/2)|0> + sin(theta/2)*e^(i*phi)|1>. Furthermore, we can rotate from |0> to this vector using
the following unitary gate:


which can be interpreted as a rotation about the y-axis, followed by a rotation about the z-axis.

This procedure can be extended to the multi-qubit case if we only consider product states. Product states can be cleanly represented as the tensor product of single-qubit states. This is distinct from entangled states, which cannot be represented in this form. We'll see later on that this allows us to approach the problem of reconstructing an arbitrary multi-qubit state in a qubit-by-qubit fashion.

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



