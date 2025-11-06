# Qiskit Grover Search Algorithm

This notebook (`Qiskit_grover_search.ipynb`) demonstrates **Grover’s Search Algorithm** using **Qiskit 2.x**.

---

## Explanation of the Code

### 1. Oracle Construction
The **oracle** marks the target state by flipping its phase.  
In the code, it applies **X gates** to match the marked state, applies a **multi-controlled X gate (`mcx`)**, and then reverses the X gates.

### 2. Diffuser
The **diffuser** amplifies the amplitude of the marked state by performing an **inversion about the mean**.  
It uses Hadamard (H) and X gates with another `mcx()` operation.

### 3. Grover’s Search Function
- Creates a quantum circuit with `n` qubits.  
- Applies Hadamard gates to create a superposition.  
- Runs the oracle and diffuser once.  
- Adds measurement at the end to read out the result.

### 4. Execution and Visualization
The function `run_grover()` simulates the circuit using **Qiskit AerSimulator** and visualizes the output as a histogram.  
The marked state (e.g., `101`) appears as the most probable result.

---

## Student Practice Tasks

1. **Change the marked state**  
   Try different marked states such as `001`, `111`, or `010` and observe the output histogram.

2. **Modify the number of qubits**  
   Extend the algorithm to 4 qubits and update the oracle and diffuser accordingly.

3. **Add multiple iterations**  
   Run the oracle and diffuser steps multiple times to increase the probability of finding the marked state.

4. **Circuit Visualization**  
   Use `qc.draw('mpl')` to visualize the circuit structure in the notebook.

5. **Experiment with Noise**  
   Add a noise model using Qiskit Aer’s `NoiseModel` and compare results with the ideal simulator.

6. **Real Hardware Execution (Optional)**  
   If you have IBM Quantum credentials, try running the same circuit on a real IBMQ backend and compare the histogram results.

---

## Requirements

Install the dependencies before running the notebook:

```bash
pip install qiskit qiskit-aer matplotlib
