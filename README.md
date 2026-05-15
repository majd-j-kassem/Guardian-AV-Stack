# Guardian-AV-Stack: A Modular Prototyping Architecture for Autonomous Vehicle Subsystems

Guardian-AV-Stack is an exploratory software framework designed to study the architectural separation between core autonomous driving modules and external monitoring interfaces using a containerized, Docker-based environment.

The framework serves as a prototyping sandbox to evaluate data-flow consistency, subsystem modularity across standard autonomous vehicle pipelines, and basic automated testing workflows.

## 🏗️ Architectural Layout

The layout isolates essential autonomous functions from external web connectivity by decoupling the system into distinct, independent services.

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

This project is developed for academic research and prototyping purposes.
