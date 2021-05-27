# Problem
Using Qiskit Pulse, study the behavior of transmon qubits in IBM Quantum systems.
Find |1⟩→|2⟩ transition frequency 𝑓12 using the calibrated X-180 pulse and spectroscopy (sweeping frequency).
# Solutions
- you just need two x_pulses. One from |0> to |1>, next one from |1> to |2>. You need to set two different frequencies for them. 
- for |0⟩→|1⟩ already calculated from tutorial
- for |1⟩→|2⟩ transition pulse i used freq+anharm_guess_GHz)*GHz 