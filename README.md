# Finite Element Analysis of synchronous motor

This repository contains coursework materials for the ELEC2213 module on Electrical Machines.

## 📄 Assignment
To nvestigate the performance of a permanent magnet synchronous motor using COMSOL simulations. 
- Key topics explored include startup methods, inverter control, equivalent circuit analysis, and electromagnetic power flow.

## ⚠️ Academic Integrity
This repository contains **no solutions or code**. It exists to showcase my technical communication, software exposure, and engineering documentation skills.

## 🧰 Tools Used
- COMSOL Multiphysics
- MATLAB (optional for phasor analysis)
- GitHub for version control and documentation

## 🔍 Section Overviews – Synchronous Motor FEA

#### 1. Winding Diagram
  - Constructed a winding diagram for **Phase A** of the stator windings based on a 30-slot, double-layer configuration.
  - The layout followed key principles such as minimizing wire length and aligning coil spans with the machine's pole-pitch.
  - Provided accurate representation of the winding structure within the simulation model.

#### 2. Comparison of Direct Online Start Motor Simulations
  - Compared two simulation cases: one with a **conductive rotor body**, and one with an **insulating rotor body**.
  - The conductive rotor induced eddy currents, producing torque that allowed the motor to reach synchronous speed.
  - The insulating rotor lacked this mec

#### 3. Issues with a Direct Online Start Approach
  - I examined why directly connecting the motor to the supply is not viable.
  -  Used the conductive rotor model, I observed high initial currents, mechanical instability, and long start-up times.
  -   The analysis demonstrated that such a method can strain the power system and motor components, making it impractical for real-world applications.

#### 4. Benefits of the Inverter Fed Motor Approach
  - I analyzed an **inverter-fed start method**, where voltage magnitude and phase were dynamically adjusted based on rotor position.
  - This method enabled smooth synchronization and significantly improved torque control. I discussed how additional rotor angle data was used, and how it could be obtained using encoders in practice.

#### 5. Determining R and Motor Efficiency
  - Using provided RMS voltage and current phasors, I calculated the resistance \( R \) in the motor's equivalent circuit and evaluated the system's efficiency.
  - I discussed the nature of losses represented by \( R \), primarily resistive (Joule) heating in the stator windings.
  - These calculations reinforced understanding of how power dissipation occurs in synchronous machines.

#### 6. Explanation of the “net_power” Probe
  - I interpreted the probe variable `net_power` used in the COMSOL model.
  - It represents the net electromagnetic power transferred to the rotor, based on torque and angular velocity.
  - I explained the relevance of each term and how this probe enables insight into dynamic power flow and system performance during transient startup.
