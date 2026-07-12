# Three-Phase Grid-Connected Solar PV System

A MATLAB/Simulink implementation of a three-phase grid-connected photovoltaic (PV) system featuring Maximum Power Point Tracking (MPPT), a DC-DC boost converter, synchronous reference frame (dq) current control, PLL-based grid synchronization, and PWM-controlled three-phase inverter operation.

> **Note:** This project began as a study of an existing Simulink implementation. The objective is to understand, document, and eventually modify the controller architecture while gaining a deeper understanding of grid-connected converter systems.

---

## Features

- ☀️ PV Array (~100 kW)
- ⚡ DC-DC Boost Converter
- 📈 Perturb & Observe (P&O) MPPT
- 🔋 DC-Link Voltage Regulation (700 V)
- 🔄 Three-Phase Voltage Source Inverter (VSI)
- 🎯 dq-Axis Current Control
- 🧭 Phase Locked Loop (PLL) Grid Synchronization
- ⚙️ Sinusoidal PWM Generation
- 🔌 Three-Phase Grid Integration at 400 V, 50 Hz
- ✅ Unity Power Factor Operation

---

## System Architecture

```
         Solar Irradiance
                │
                ▼
          PV Array (~100 kW)
                │
                ▼
      DC-DC Boost Converter
         + P&O MPPT Control
                │
                ▼
        700 V DC-Link Capacitor
                │
                ▼
     Three-Phase VSI Inverter
                │
                ▼
           RL Filter
                │
                ▼
     400 V, 50 Hz Utility Grid
```

---

## Control Architecture

The inverter employs a cascaded control structure:

```
          Grid Voltage
                │
                ▼
              PLL
                │
                ▼
      abc → αβ → dq Transformation
                │
                ▼
      Outer DC-Link Voltage Loop
                │
                ▼
      Inner dq Current Controllers
                │
                ▼
        dq → abc Transformation
                │
                ▼
        PWM Generation Block
                │
                ▼
        Three-Phase Inverter
```

---

## Repository Structure

```
.
├── model/
│   └── Three_Phase_Grid_Connected_Solar_PV_System.slx
│
├── docs/
│   └── (architecture screenshots and documentation)
│
└── README.md
```

---

## Software Requirements

- MATLAB
- Simulink
- Simscape Electrical (Specialized Power Systems)

---

## Current Progress

- [x] Simulate complete grid-connected PV system
- [x] Study boost converter with MPPT
- [x] Analyze PLL implementation
- [x] Understand dq reference frame transformations
- [x] Study cascaded voltage/current control loops
- [ ] Document PWM generation subsystem
- [ ] Tune controller gains
- [ ] Investigate alternative MPPT algorithms
- [ ] Extend controller for battery or DC microgrid applications

---

## Future Improvements

- Replace P&O MPPT with Incremental Conductance MPPT
- Compare different PLL algorithms
- Improve controller tuning and transient response
- Integrate battery energy storage
- Extend the model for DC microgrid applications
- Perform harmonic and THD analysis
- Validate controller performance under irradiance changes

---

## References

This project is based on a MATLAB/Simulink implementation of a three-phase grid-connected PV system and is being used as a learning platform to understand:

- Grid-connected inverter control
- Synchronous Reference Frame (SRF) PLL
- dq-axis current control
- MPPT algorithms
- PWM generation
- Grid synchronization techniques
