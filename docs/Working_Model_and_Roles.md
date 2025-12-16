# Working Model and Roles

## 1. Document Objective

Define a **collaborative and structured working model**, aligned with industry practices, for the design of a rocket instrumentation PCB by **two engineers**, where responsibilities are clearly separated but **both roles are essential and complementary**.

This document establishes:

* Role definitions
* High-level task distribution
* Interaction and authorization rules
* Workflow and change management

---

## 2. Working Principles

* Each technical domain has a **clearly identified owner**.
* Decisions are based on **defined inputs and agreed interfaces**.
* Technical information is frozen at specific milestones (*design freezes*).
* Work progresses through **coordination and review**, not unilateral changes.

---

## 3. Role Definition

### 3.1 Role A – System Definition & Design Constraints

**Scope:** provide the technical framework within which the hardware is designed.

#### Responsibilities

* Define and freeze system requirements
* Define system architecture
* Define and approve interface contracts
* Select MCU, sensors, and digital interfaces
* Define PCB stackup
* Define PCB design rules
* Perform technical reviews of schematics and layout
* Prepare and release fabrication files
* Coordinate with manufacturers

This role focuses on **system-level coherence and constraints**.

---

### 3.2 Role B – Power & PCB Design

**Scope:** implement the complete hardware design within the defined framework.

#### Responsibilities

* Design the complete power architecture
* Select power-related components
* Design **all schematics** (power, digital, sensors)
* Design the **complete PCB**:

  * Component placement
  * Routing
  * Power planes and returns
* Apply the defined PCB stackup and design rules
* Implement all interface contracts as defined
* Support technical reviews and resolve findings

This role focuses on **detailed electrical and physical implementation**.

---

## 4. High-Level Task Distribution

### Role A

* Requirements definition
* Architecture definition
* Interface contract definition
* Component selection (MCU, sensors, interfaces)
* Definition of PCB constraints (stackup, rules)
* Design reviews
* Fabrication and release activities

---

### Role B

* Power system design
* Power component selection
* Schematic capture (entire system)
* PCB placement and routing
* Electrical and physical optimization

---

## 5. Interface Contracts

Interface contracts define the **technical agreements** that allow both roles to work in parallel without ambiguity.

They cover, at minimum:

* Power rails, limits, and sequencing
* Digital interfaces and voltage levels
* Control and enable signals
* Physical and PCB-related constraints

Once approved, interface contracts are considered **frozen inputs**.

---

## 6. Workflow and Milestones

### 6.1 Design Phases

1. Requirements defined
2. Architecture defined
3. Interface contracts agreed
4. PCB constraints defined
5. Schematics completed
6. Layout completed
7. Release to fabrication

---

### 6.2 Parallel Work Model

* Role A focuses on system definition and constraints
* Role B focuses on detailed design and implementation
* Synchronization occurs at defined review points
* The same design files are not modified concurrently

---

## 7. Change Management

Any modification after a defined milestone requires:

* A documented change request
* Assessment of technical impact
* Agreement between both roles

This ensures changes are deliberate and traceable.

---

## 8. Success Criteria

This working model is considered effective when:

* Responsibilities are clearly understood
* Parallel work proceeds without rework
* Design milestones are met
* The PCB integrates cleanly and is ready for fabrication

---

