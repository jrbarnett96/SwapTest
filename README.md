# SwapTest
An implementation of the swap test, used to reconstruct an arbitrary product state

I should probably go into a bit more detail. 

The swap test is only one aspect of the problem. It's the means to an end.  

The end goal of this project is a variational quantum circuit. Given an arbitrary quantum state (the goal state), I want to reconstruct it. I'll be doing this iteratively; initialize a state, compute a cost function which quantifies the state's divergence from the goal state, modify the state appropriately, do so until the end state is approximated to my liking.

