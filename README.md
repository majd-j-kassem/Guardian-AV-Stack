# Guardian-AV-Stack

An exploratory research architecture for studying safety-oriented autonomous driving systems from a cyber-physical systems (CPS) perspective.

This repository focuses on early-stage system design and architectural reasoning rather than full implementation. The goal is to investigate how autonomy stacks can be structured to explicitly consider safety, uncertainty, and runtime observability.

---

## 🧭 Research Motivation

Modern autonomous driving systems are typically developed as loosely coupled modules. This project explores an alternative perspective: treating autonomy as a unified, safety-aware system architecture.

Key questions include:
- How can safety be integrated as a structural design principle rather than an external constraint?
- How should perception, planning, and control interact under uncertainty?
- What role can runtime supervision play in system-level reliability?
- How can Digital Twin concepts support validation and monitoring?

---

## 🏗️ Architectural Overview

The system is decomposed into four conceptual layers:

- **Sensing Layer**: Representation of physical sensing inputs
- **Autonomy Core**: Perception, mapping, planning, and control logic (partially modeled)
- **Supervision Layer**: Runtime monitoring and system-level observability
- **Digital Twin Layer**: Conceptual parallel model for analysis and validation

---

## 🧠 Key Research Concepts

- Cyber-Physical System (CPS) architectural design
- Safety-aware system decomposition
- Runtime supervision and observability
- Modular autonomy stack reasoning
- Digital Twin as a conceptual validation tool

---

## ⚙️ Implementation Scope

## Current implementation is limited to early-stage prototypes and architectural experiments; most components are not fully integrated.

This repository includes:
- Partial prototype components (C++ / Python)
- System design diagrams and architectural notes
- Experimental supervision and control logic

It does not represent a complete or validated autonomous driving system.

---

## 📂 Repository Structure

```text
Guardian-AV-Stack/
├── architecture/     # System design diagrams and conceptual models
├── docs/             # Research notes and technical explanations
├── src/              # Prototype components (C++ / Python)
├── tests/            # Basic validation experiments
└── docker-compose.yml (experimental setup for modular execution)