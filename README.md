# FRT Ethics Prototype

The notebook implements a simplified decision pipeline designed to validate both functional and ethical goals of a facial recognition system.

The system models the following parameters:
- **T**: face-match threshold  
- **R**: number of candidates returned  
- **N**: watchlist size  
- **Csev**: crime severity level  

## Ethical Framework

The implementation is structured around three ethical cases:

1. **Deontological Constraint (Fairness)**
   - Configurations that introduce disproportionate demographic risk are blocked  
   - Implemented using Z3 constraint solving  

2. **Utilitarian Adjustment (Severity-Based)**
   - Threshold and return limits are adapted based on crime severity  

3. **Human-in-the-Loop Oversight**
   - System outputs are advisory and require human review  

## Z3 Usage

Z3 is used to formalise policy constraints.

- A **satisfiable (sat)** constraint set means the configuration is allowed  
- An **unsatisfiable (unsat)** result means the configuration is blocked  

This allows ethical constraints to be enforced as formal logical conditions.

## Scenarios

The notebook includes validation scenarios demonstrating:
- permissible configurations at lower severity levels  
- blocked configurations where fairness constraints are violated  
