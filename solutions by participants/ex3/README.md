# Problem
Problem: Implement a small quantum error correction code.
# Goal
Create circuits which can detect x and z errors on two qubits.

# Informal definnition about the problem
when you transpile your circuit, the transpiler assigns your circuit’s qubits to each of physical qubit numbers specified in initial_layout list.
So, for example, the initial_layout list provided in the notebook is currently [0,2,6,10,12,1,5,7,11]. This means that:
q0 in your circuit is assigned to physical qubit 0,
q1 in your circuit is assigned to physical qubit 2,
q2 in your circuit is assigned to physical qubit 6,
etc.

Now, if you happen to have a CNOT gate between quibts that are not physically connected in the quantum processor, the transpiler will try to reassign and/or introduce some extra gates to allow that CNOT operation.
The core of this problem is to avoid that from happening. You have to design your circuit and then select the right initial_layout so that the transpiler doesn’t introduce any additional gates.

# Solution
 

1. we need to fully understanding why the given circuit could not be uniquely (or ideally) represented on the specific backend looking at its graph properties --> draw it out and see why there are many ways to implement and none that fit 
![Alt text](images/layout.png?raw=true "layout")
![Alt text](images/image.png?raw=true "layout 2")
2. Taking a deeper look into the circuit 
c0....s0....c1
:      :     :        
:      :     :
s1....c2....s2
:      :     :
:      :     :
c3....s3....c4

c0----------c1
| \   s0   / |
|   \    /   |
| s1  c2  s2 |
|   /    \   |
| /   s3   \ |
c3----------c4

we could find that in the Right ZZZ code 1 and sync 2 are not physically connected (2,7 in the initial layout). Therefore solution is to swap it and perform correct cx operation with the swapped qubits. 