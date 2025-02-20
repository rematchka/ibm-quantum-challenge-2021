
# Problem
- Factor number 35 using Shor's algorithm.
- In this exercise, we will factor 35 by doing phase estimation on a circuit that implements 13𝑦mod35. The exercise is to create a circuit that does this, and is also small enough to run on ibmq_santiago! This is not an easy task, so the first thing we’re going to do is cheat.

A detail of Shor’s algorithm is that our circuit only needs to work on states we can reach through applying 𝑈 to the starting state |1⟩. I.e. we can use any circuit that has the behavior:


![Alt text](images/Screenshot_30.png?raw=true "U")



So how can we make this easier for us? Since we only need to correctly transform 4 different states, we can encode these onto two qubits. For this exercise, we will choose to map the 2-qubit computational basis states to the numbers like so:

![Alt text](images/Screenshot_31.png?raw=true "U")

Why is this “cheating”? Well, to take advantage of this optimization, we need to know all the states 𝑈 is going to affect, which means we have to compute 𝑎𝑦mod𝑁 until we get back to 1 again, and that means we know the period of 𝑎𝑥mod𝑁 and can therefore get the factors of 𝑁. Any optimization like this, in which we use information that would tell us the value 𝑟, is obviously not going to scale to problems that classical computers can’t solve.

But the purpose of this exercise is just to verify that Shor’s algorithm does in fact work as intended, and we’re not going to worry about the fact that we cheated to get a circuit for 𝑈.


# Solutions 
## Circuit U has the following transformation
![Alt text](images/Screenshot_32.png?raw=true "U")


1. First you can notice that the first qubit is always flipped no matter what the second qubit is.
2.  Secondly: Second qubit is affected (controlled) by first qubit (CX gate)
3. Therfore our circuit Can be constructed by applying X gate on first qubit and CX gate (Control first qubit, target second qubit)

4. Circuit would be 
![Alt text](images/U.png?raw=true "U")

## Circuit U2 has the following transformation
![Alt text](images/Screenshot_33.png?raw=true "U")


1. which is applying U twice
2. Circuit would be 
![Alt text](images/U2.png?raw=true "U")

## Circuit U4 has the following transformation
![Alt text](images/Screenshot_34.png?raw=true "U")


1. if we look closer it doesnt change the system. acts as applying identity
2. Circuit would be 
![Alt text](images/U4.png?raw=true "U")


# Cost
- cost: 15



