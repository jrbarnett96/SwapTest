# SwapTest

## Overview

This repo contains a Jupyter notebook which implements the swap test on a simulated quantum computer using Qiskit. After reviewing the basics of state generation on a quantum computer, we use the swap test to not only distinguish our input state with another quantum state, but estimate the inner product in order to transform our input state into the target state. We do this for the case of an arbitrary single-qubit state, and extend it to a multi-qubit case in which each state takes the form of a bitstring (i.e. |01001>, |000>, etc.). 

This notebook provides basic plots and animations to showcase this circuit in action as well as its convergence properties. I've provided a conda environment file to take care of the dependencies.

## Installation

You'll need conda to create the provided environment. Assuming you have that installed, use `conda create env -f environment.yaml` to create the conda environment, `activate swap` to activate the environment, then go into Jupyter to launch the notebook. I provide more details on the implementation there. 

## Background

I run the risk of getting too deep into the weeds here, but I'll attempt to go through all the background necessary to understand what's going on in the swap test circuit, and my code. I'm assuming a baseline knowledge of quantum computing (i.e. what a qubit is, what a quantum circuit is, measurement, etc.) as well as some linear algebra. I'll include references at the end for further reading.

### Creating an arbitrary quantum state

We start with the ways in which you can represent a qubit. There are a few. 

Enter a qubit's Hilbert space, specify a basis, call it the computational basis to satisfy the jury. Suppose you have a qubit in this space. It can be a superposition of the basis states: a|0> + b|1>. The weights of this superposition are complex numbers which satisfy the normalization condition |a|<sup>2</sup> + |b|<sup>2</sup> = 1. The modulus squared |x|<sup>2</sup> of these weights represent the probability of observing the corresponding states in a measurement. Standard fare so far. 

With some algebra, however, this superposition can be restated as cos(θ/2)|0> + e<sup>(iφ)</sup>sin(θ/2)|1>, where 0 <= θ <= π and 0 <= φ <= 2π if you want to restrict yourself to unique states (φ = 0 and φ = 2π result in the same state, but let's, uh, let's ignore that). These angles are known as Bloch angles. Any state can be multiplied by a global phase factor e<sup>iγ</sup> without affecting measurement probabilities, so for our purposes we can ignore this phase. 

If you can parameterize the qubit with two angles, it isn't a big leap to visualize the state vector as lying on a sphere, the Bloch sphere. The states we truck with are restricted to the surface of this sphere (mixed states, those in a statistical ensemble, lie within the sphere, but we don't worry about those). 

(INSERT BLOCH SPHERE IMAGE)

The usage of Bloch angles to describe our states becomes useful when when considering unitary transformations of these states. Unitary transformations can be seen as rotating states around the Bloch sphere with respect to some axis. An arbitrary unitary can be decomposed in any number of ways, but the one that will be most useful is this one:

<img src="assets/images/u_gate.png" alt="alt" title="title" width="300" />

If we have a qubit in the state |0>, applying this transformation to the qubit will transform it into cos(θ/2)|0> + e<sup>(iφ)</sup>sin(θ/2)|1>, so this unitary is capable of getting us anywhere on the Bloch sphere. So for our purposes, we have a way of initializing our quantum state to any state we choose; all we have to do is specify 0 and φ

One final note before we continue. The above gate is not necessarily the one implemented on whatever physical quantum computer you use. Quantum computers have fundamental gate sets, a set of primitives that every gate in your program is transpiled to. While Qiskit presents this gate in code, they have their own technique for initializing quantum states, given in [reference] (in their own words, they start with the target state and work backwards to |0>, inverting the transformation).

### Distinguishing quantum states

The swap test was originally concieved by Watrous et al. in a paper exploring how to effectively distinguish quantum states. In their paper they were concerned with two parties with secret keys in the form of quantum states. They need to determine if their keys are the same, so they send copies of them to an arbiter. This arbiter then performs the swap test, then informing the two parties of the result. 

Our ancilla is |0>, our states are |> and |>. Conveniently enough, this works even if |> and |> consist of more than one qubit each. We apply the following circuit:

<img src="assets/images/swap_circuit.png" width="300" />

In words, we apply the Hadamard gate to our ancilla, controlled-swap our initial qubit and target qubit, apply the Hadamard to the ancilla again, and finish by measuring the ancilla. 

If you work through the algebra, you'll find that the state before measurement comes out to be (INSERT STATE HERE). We can then compute the probability of 


### Approximating a single-qubit state

Now we're posed a problem. Say we're given a state, any state. It's only one qubit, but it's in some random superposition. Also, assume we have a lot of copies of this state. We want to replicate this state in a qubit of our own. To do so we 

<img src="assets/images/swap_circuit_multi.png", width="300" />

### More qubits, but simpler: approximating a product



## Further improvements

If you look at the notebook, you'll see that I accomplished the basic goals of this task.

1. Alternative methods of searching parameter space for the optimum
2. Applying this technique to a real quantum computer, with considerations for error
3. Implementing this circuit with PennyLane

## References

[1] 
[2] 
[3]
