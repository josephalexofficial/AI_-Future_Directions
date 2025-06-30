# ⚛️ Bonus Task – Quantum Computing Simulation

## Task Overview

In this task, a basic quantum circuit was designed using **IBM Quantum Experience** (Qiskit) to demonstrate how quantum computing can accelerate AI-related tasks. The use case focuses on **faster drug discovery**, a process that benefits greatly from quantum optimization and molecular simulation capabilities.

---

## Quantum Circuit Summary

```python
from qiskit import QuantumCircuit, Aer, transpile, assemble, execute
from qiskit.visualization import plot_histogram

# Create a simple 2-qubit entanglement circuit (Bell State)
qc = QuantumCircuit(2)
qc.h(0)        # Apply Hadamard gate to qubit 0
qc.cx(0, 1)    # Apply CNOT gate (entangle qubits)
qc.measure_all()

# Simulate
simulator = Aer.get_backend('qasm_simulator')
qobj = assemble(transpile(qc, simulator))
result = execute(qc, backend=simulator).result()

# Display result
counts = result.get_counts()
plot_histogram(counts)
