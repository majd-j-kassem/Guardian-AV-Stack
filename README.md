# Guardian-AV-Stack

An exploratory research architecture for studying safety-oriented autonomous driving systems from a cyber-physical systems (CPS) perspective.

This repository focuses on early-stage system-level design rather than full implementation, with emphasis on modular decomposition, runtime supervision, and the role of Digital Twin concepts in system validation and safety analysis.

---

## 🧭 Research Focus

The project investigates autonomous driving systems as integrated architectures rather than isolated modules, with emphasis on:

- Safety-aware system design as a core architectural principle rather than an external constraint
- Hierarchical decomposition of perception, mapping, planning, and control functions
- Runtime supervision and system-level monitoring for observability and reliability
- Integration of Digital Twin concepts for system validation and anomaly detection
---

## 🏗️ System Overview

The architecture is structured into four conceptual layers:

- **Sensing Layer**: Physical sensing components and vehicle interface abstraction
- **Autonomy Core**: Perception, mapping, planning, control, and supervisory functions
- **Telemetry Layer**: External communication, monitoring, and data exchange interfaces
- **Digital Twin Layer**: Parallel system representation for state estimation, analysis, and validation

---

## 🧠 Key Concepts

- Cyber-Physical System (CPS) design principles
- Safety-critical supervision and override mechanisms
- Modular autonomy stack decomposition
- Closed-loop control architecture
- Multi-objective decision-making under uncertainty
- Digital Twin as a runtime validation tool

---

## 📌 Status

This is a conceptual, research-oriented architecture.  
No full system implementation is assumed; the focus is on system-level design, structural reasoning, and exploratory modeling of autonomous driving architectures.

---

## 📄 Notes

System diagrams and subsystem definitions are used to formalize architectural reasoning and support future research directions in autonomous systems and safety-critical robotics.
---

## 👤 Author

Majd Kassem
Systems Engineer | Robotics & Control Systems
       [ External Interface / Monitoring Concept ]
                       │
                       ▼
            ┌─────────────────────┐
            │  Communication Layer │
            │  (Conceptual Gateway)│
            └──────────┬──────────┘
                       │
                       ▼
           ┌───────────────────────┐
           │   System Supervisor   │
           │ (Observability Model) │
           └──────────┬──────────┘
                       │
       ┌───────────────┼───────────────┐
       ▼               ▼               ▼
┌────────────┐   ┌────────────┐   ┌────────────────────┐
│ Perception │   │  Mapping   │   │   Planning / Control│
│  (Model)   │   │  (Model)   │   │      (Model)       │
└────────────┘   └────────────┘   └───────────┬────────┘
                                              │
                                              ▼
                                  ┌────────────────────┐
                                  │ Control Interface   │
                                  │ (Conceptual C++)    │
                                  └────────────────────┘

## 🛠️ Subsystem Modularity Reference

The framework defines subsystem boundaries aligned with standard autonomous vehicle processing pipelines to study integration interfaces and system-level interactions:

1. **Environment Perception (Model):** Abstract representation of sensory processing for object identification and localization under uncertainty.
2. **Environment Mapping (Model):** Conceptual representation of spatial mapping structures and coordinate space abstraction.
3. **Motion Planning (Model):** High-level representation of trajectory generation and decision logic.
4. **Vehicle Control:** Conceptual control module representing kinematic execution and control law behavior.
5. **System Supervisor:** Independent monitoring component for studying timing consistency, observability, and subsystem-level state reporting.

## 🚀 Testing & Integration Workflow

To support structural consistency and experimental reproducibility during architectural iterations, the repository includes lightweight validation and development tooling:

- **Environment Isolation:** Container-based setup for separating experimental components and dependencies.
- **Continuous Integration (Experimental):** Basic automated checks using GitHub Actions to validate repository integrity.
- **Unit-Level Validation:** Minimal verification routines inspired by testing principles (e.g., GTest structure in C++ components) for conceptual consistency.

## 📂 Repository Structure

Guardian-AV-Stack/
├── .github/workflows/    # Experimental CI configuration
├── architecture/         # System design diagrams and conceptual models
├── docs/                 # Research notes and system-level reasoning
├── src/
│   ├── vehicle_control/  # Conceptual control module (C++)
│   ├── system_supervisor/# Observability and monitoring model
│   └── web_gateway/      # Optional interface layer (experimental)
├── test/                 # Lightweight validation experiments
└── docker-compose.yml    # Experimental environment configuration

## 📋 License

This project is for academic research and prototyping purposes.
