# Guardian-AV-Stack

An exploratory architecture for studying safety-oriented autonomous driving systems from a cyber-physical systems (CPS) perspective.

This repository focuses on system-level design rather than full implementation, with emphasis on modular decomposition, runtime supervision, and the potential role of Digital Twin systems in validation and safety reasoning.

---

## 🧭 Research Focus

The project investigates how autonomous driving systems can be structured as integrated architectures rather than isolated modules, with particular attention to:

- Safety-aware system design (not as an add-on, but as a core principle)
- Hierarchical decomposition of perception, mapping, planning, and control
- Runtime supervision and system monitoring
- Integration of Digital Twin concepts for validation and anomaly detection

---

## 🏗️ System Overview

The architecture is organized into four main layers:

- **Sensing Layer**: Physical sensors and vehicle interface
- **Autonomous Core**: Perception, mapping, planning, control, and supervision
- **Telemetry Layer**: External monitoring and data interface
- **Digital Twin Layer**: Parallel system for state mirroring and analysis

---

## 🧠 Key Concepts

- Cyber-Physical System (CPS) design principles
- Safety-critical supervision and override mechanisms
- Modular autonomy stack decomposition
- Closed-loop control architecture
- Digital Twin as a runtime validation tool

---

## 📌 Status

This is a conceptual research-oriented architecture.  
No full production implementation is assumed; the focus is on structural design and system reasoning.

---

## 📄 Notes

Diagrams and subsystem definitions are used to formalize architectural thinking for future research directions in autonomous systems and safety-critical robotics.

---

## 👤 Author

Majd Kassem
Systems Engineer | Robotics & Control Systems

```
       [ External Client / Web Dashboard ]
                       │
                       ▼ (Asynchronous Telemetry & Data Logging)
            ┌─────────────────────┐
            │   FastAPI Gateway   │  <--- (Web Monitoring Interface)
            └──────────┬──────────┘
                       │
  ─────────────────────┼─────────────────────────────────────────
                       │  [ Isolated Docker Network Bridge ]
                       ▼
           ┌───────────────────────┐
           │   System Supervisor   │ <─── Subsystem Monitoring Stub
           └───────────┬───────────┘
                       │
       ┌───────────────┼───────────────┐
       ▼               ▼               ▼
┌────────────┐   ┌────────────┐   ┌────────────────────────┐
│ Perception │──>│  Mapping   │──>│    Motion Planning     │
│   (Stub)   │   │   (Stub)   │   │         (Stub)         │
└────────────┘   └────────────┘   └───────────┬────────────┘
                                              │
                                              ▼ (Kinematic Trajectory Data)
                                  ┌────────────────────────┐
                                  │  Vehicle Control (C++) │ <─── Eigen Library
                                  └────────────────────────┘
```

## 🛠️ Subsystem Modularity Reference

The framework aligns its component boundaries with standard autonomous vehicle processing pipelines to analyze integration interfaces:

1. **Environment Perception (Stub):** Simulates sensory processing inputs for dynamic object identification and localization.
2. **Environment Mapping (Stub):** Represents localized map layouts, handling occupancy grid placeholders and coordinate references.
3. **Motion Planning (Stub):** Mimics the routing pipeline required to compute localized target path arrays.
4. **Vehicle Control:** A native **C++** implementation utilizing the **Eigen** library to execute foundational kinematic calculations and local trajectory tracking.
5. **System Supervisor:** An independent software monitoring block designed to study subsystem frequency consistency and log module-level output states.

## 🚀 Testing & Integration Workflow

To maintain code structure and compilation validity during architectural iterations, the repository integrates:
* **Environment Isolation:** Container orchestration via `docker-compose` to enforce component-level dependency separation.
* **Continuous Integration:** A basic automated pipeline managed through **GitHub Actions** to check compilation on updates.
* **Unit Verification:** Functional mathematical validation blocks implemented via the **GTest (Google Test)** framework within the C++ control module.

## 📂 Repository Structure

```text
Guardian-AV-Stack/
├── .github/workflows/    # Automated GitHub Actions compilation workflows
├── architecture/         # System design layouts and sequence diagrams
├── docs/                 # Research notes, kinematic equations, and log files
├── src/
│   ├── vehicle_control/  # Trajectory tracking logic using C++ and Eigen
│   ├── system_supervisor/# Module state auditing and monitoring node
│   └── web_gateway/      # Telemetry bridge built with Python and FastAPI
├── test/                 # Component-level verification suites (GTest)
└── docker-compose.yml    # Container networking and isolation configuration
```

## 📋 License

This project is for academic research and prototyping purposes.
