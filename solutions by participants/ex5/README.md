# Goal

Find the shortest ansatz circuits for representing accurately the ground state of given problems. Be creative!

# Plan

First you will learn how to compose a VQE simulation for the smallest molecule and then apply what you have learned to a case of a larger one.

1. Tutorial - VQE for H2: familiarize yourself with VQE and select the best combination of ansatz/classical optimizer by running statevector simulations.

2. Final Challenge - VQE for LiH: perform similar investigation as in the first part but restricting to statevector simulator only. Use the qubit number reduction schemes available in Qiskit and find the optimal circuit for this larger system. Optimize the circuit and use your imagination to find ways to select the best building blocks of parameterized circuits and compose them to construct the most compact ansatz circuit for the ground state, better than the ones already available in Qiskit.
# Theory
![Alt text](images/workflow.png?raw=true "Title")

# Solutions 

1. Trial 1:
  At first i experimented with different ansatz and optimizers, i tried different combination and number of iteration. I could get solution using ``SUCCD`` anstaz and ``SLSQP`` optimizers but the solution was to large (circuit id too large). 

2. Trial 2:
    fixing same anstaz and optimizers as before while adding Z2symmetry and twoqubit reduction, still i could get right answer but large circuit.

3. Trial 3: 
   Playing around with ``TwoLocal`` anstaz with defult params provided at begining of notebook, with  Z2symmetry and twoqubit reduction could yeild correct solution with 140 qubit



4. Trial 4:
    fixing ``TwoLocal`` anstaz with ``SLSQP`` optimizers.
    Playing around with freezeCore and orbital reduction, by experimenting different 1 combiation and 2 combination for orbital reduction, it was clear the removing 3-4 orbits are the best combination.

5. Trial 5:
    fixing everything while playing with number of repition params in ``TwoLocal`` anstaz. one could get 12 cnot while having 3 repitions only.

5. Trial 6/7/8:
    fixing everything while playing with number of repition params, rotation gates, and entaglemtn type in ``TwoLocal`` anstaz.
    at first i could decrease number of repitionts beyond 3 until i tried circular entaglment, which yeilded 4 cnots, linear entaglment yeilded 3 cnots.

# Cost
- Ansatz used:  TwoLocal
- Number of parameters:  16
- VQE Energy:  -1.0863472026328
- Error:  2.3588131019400826
- Pass/Fail:  True
- CNOT score:  3

