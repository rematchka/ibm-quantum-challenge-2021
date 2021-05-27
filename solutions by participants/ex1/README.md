# problem 
Construct a Toffoli gate using the basis gates (CX, RZ, SX and X gates) of IBM Quantum systems.

# Solutions
- First i started by searching for how to consutruct toffli gates, then decompose each gate to CX, RZ, SX and X gates.
- I used this circuit 
![Alt text](images/Qcircuit_Toffolipng.png?raw=true "Toffoli gate")
- we could see that we could decomposed hadamard gate into three rotation RZ with PI/2 angle , SX, RZ  with PI/2 angle
- T and T dagger gates can be deomposed into RZ rotation with PI/4 and -PI/4 angles.
- Final circuit 
![Alt text](images/final_circuit.png?raw=true "Final Toffoli gate")
- Cost: 73

