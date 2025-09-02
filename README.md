# Finite Element Analysis of synchronous motor

This repository contains coursework materials for the ELEC2213 module on Electrical Machines.

## Assignment
To investigate the performance of a permanent magnet synchronous motor using COMSOL simulations. 
- Key topics explored include startup methods, inverter control, equivalent circuit analysis, and electromagnetic power flow.

## ⚠️ Academic Integrity
This repository contains **no solutions or code**. It exists to showcase my technical communication, software exposure, and engineering documentation skills.

## Tools Used
- COMSOL Multiphysics
- MATLAB (optional for phasor analysis)
- GitHub for version control and documentation

## Section Overviews – Synchronous Motor FEA

#### 1. Winding Diagram
  - Constructed a winding diagram for **Phase A** of the stator windings based on a 30-slot, double-layer configuration.
  - The layout followed key principles such as minimizing wire length and aligning coil spans with the machine's pole-pitch.
  - Provided accurate representation of the winding structure within the simulation model.

#### 2. Comparison of Direct Online Start Motor Simulations

Rotor Types: Rotors can be designed with different materials (conductive or insulating) to optimize performance.

##### **Simulation of Synchorous Speed Vs Time of an Conductive rotor body**
<img width="661" height="468" alt="image" src="https://github.com/user-attachments/assets/cf62c088-0723-46e0-9ab8-6b8712d2a152" />

- DC excitation induces currents interacting with the stator field, producing torque.
- Rotor accelerates to synchronous speed and locks in with the stator field.
- Initial slip causes oscillatory behavior before synchronization.

#### **Simulation of Synchronous Speed Vs Time of an Insulating rotor body**
<img width="675" height="455" alt="image" src="https://github.com/user-attachments/assets/2b782d10-1070-455c-8df2-fe0ad81c6ecf" />

- Cannot reach synchronous speed, so no net torque is produced.
- Oscillates due to alternating magnetic forces from the stator.
- Permanent magnets respond but cannot lock in, causing overshoot and direction reversa


#### 3. Issues with a Direct Online Start Approach

### **Insulating Rotor Body**
Characteristics:
- Low permeability prevents significant induction of magnetic fields.
- Flux distribution in stator and rotor is minimal, with only the permanent magnets generating notable flux.

**Susceptibility to Damage:**
- High inrush currents can create electrostatic and mechanical stress.
- Low flux levels produce minimal stress, but high inrush currents lead to deformation of stator windings and rotor permanent magnets.

**Distribution of magnetic flux in insulating rotor**

<img width="175" height="441" alt="image" src="https://github.com/user-attachments/assets/879bac3e-30ea-438d-bf4d-299418eae5d5" />

### **Conducting Rotor Body** 

- Inrush Current present in Conductive Rotors
- DOL starting causes inrush current far above rated values.
- Generates a large rotating field and high flux around stator windings.
- Back EMF, load angle, and torque increase with inrush current.
- High inrush leads to power loss, heating, and partial irreversible demagnetization of rotor magnets.

**Distribution of magnetic flux in conducting rotor**

<img width="193" height="458" alt="image" src="https://github.com/user-attachments/assets/bab903fa-9dac-4162-8fe8-ef634a2d1b39" />


#### 4. Benefits of the Inverter Fed Motor Approach
  - I analyzed an **inverter-fed start method**, where voltage magnitude and phase were dynamically adjusted based on rotor position.
  - This method enabled smooth synchronization and significantly improved torque control. I discussed how additional rotor angle data was used, and how it could be obtained using encoders in practice.

##### **Simulation of Synchronous Speed Vs Time of an Inverter Fed Motor**

<img width="714" height="484" alt="image" src="https://github.com/user-attachments/assets/7dccc42b-9ab5-47ff-a7f6-08ef0444aaf7" />

**How it Works:**
- Converts DC supply to AC with controlled magnitude and frequency for the synchronous motor.
- Voltage increases smoothly, allowing the rotor to accelerate to synchronous speed with less mechanical stress and higher efficiency.
- Speed rises gradually and smoothly until synchronous speed, as shown in Figure 6.

**PWM Inverter Implementation:**
- Requires a switching frequency much higher than the fundamental 50 Hz.
- Frequency modulation ratio determines harmonic frequencies (higher ratio → higher harmonics).
- Amplitude modulation compensates for unregulated DC voltage and allows control of motor speed.
- Leads to improved efficiency, reduced mechanical stress, and minimized unwanted oscillations.

#### 5. Determining R and Motor Efficiency
  - Using provided RMS voltage and current phasors, I calculated the resistance \( R \) in the motor's equivalent circuit and evaluated the system's efficiency.
  - I discussed the nature of losses represented by \( R \), primarily resistive (Joule) heating in the stator windings.
  - These calculations reinforced understanding of how power dissipation occurs in synchronous machines.

<img width="433" height="241" alt="image" src="https://github.com/user-attachments/assets/efb76a19-ccdf-4c1c-ac81-e1ad5aa29d4a" />

#### 6. Explanation of the “net_power” Probe

- Tracks power losses compared to the system’s input power.

**Composed of multiple terms:**
- Three-phase power inputs: Power received from each coil in the three-phase system.
- Mechanical power (mf.Tax_0 * ω_r): Represents useful mechanical work and allows motor efficiency analysis.
- Joule losses: Surface integral of electromagnetic loss density, representing heat dissipated due to copper losses in windings.
- Magnetic energy transfer: Surface integral of the derivative of magnetic energy density reflects energy storage and transfer (e.g., negative power during regenerative braking).
- Helps assess how power is distributed, stored, and converted, making it important for studying motor operation and efficiency.

# What I learnt 
Working on this coursework gave me a deeper understanding of synchronous motor behavior and finite element analysis (FEA) in practical engineering contexts. Key takeaways include:

**Motor Startup Dynamics:**
- Observed the stark difference between direct online (DOL) start and inverter-fed start.
- Learned that conductive rotors experience high inrush currents leading to mechanical stress and demagnetization risks, while insulating rotors fail to lock in with the stator field.
- Recognized the importance of controlled voltage and phase ramping to reduce mechanical and electrical stress.

**Electromagnetic Field Visualization:**
- Gained hands-on experience with COMSOL Multiphysics for modeling flux distributions.
- Visualizing flux in both stator and rotor deepened my understanding of magnetic coupling, back EMF, and torque generation.
- Flux patterns highlighted how rotor material properties significantly affect motor performance.

**Inverter Control and Power Electronics:**
- Learned how PWM inverters allow smooth acceleration and torque control.
- Saw the practical effect of frequency and amplitude modulation on motor efficiency and harmonic generation.
- Understood the benefits of integrating rotor position feedback via encoders for optimized control.

**Equivalent Circuit Analysis and Efficiency:**
- Calculated resistance from voltage and current phasors, linking theory with measurable losses.
- Explored the relationship between Joule heating, magnetic losses, and mechanical output, reinforcing the concept of efficiency in real machines.

**The “net_power” probe in COMSOL helped me quantify power flow, storage, and loss, bridging simulation data with physical understanding.**

**Simulation as a Learning Tool**
- Recognized the value of FEA in predicting motor performance without physically building a prototype.
- Learned to interpret simulation results critically—identifying unrealistic artifacts vs. physically meaningful trends.
- Developed technical documentation skills, including presenting results visually and explaining their engineering significance.

I gained a holistic understanding of synchronous motors from electromagnetic principles to practical startup methods and efficiency analysis, while improving my simulation, analysis, and technical communication skills.
