# Design Overview

## Problem

Tactile feedback refers to localized touch sensations generated through small-scale actuators or sensors, enabling users to perceive contact forces, pressure, and interaction with objects. This capability is fundamental to how humans manipulate the physical world and is especially critical in emerging human–robot interaction systems.

*   **In Teleoperation (e.g., Surgery, Industrial Manipulation):** Operators remotely control robotic systems but typically lack **localized fingertip-level tactile feedback**. This prevents them from sensing fine grip forces, contact onset, or surface interactions, which reduces precision, increases error rates, and contributes to operator fatigue.
*   **In Virtual Reality (VR) and Training Simulators:** Haptic feedback is often limited to generic vibration (“rumble”), failing to replicate realistic interactions such as grasping an object or feeling surface texture, thus limiting immersion and training effectiveness.
*   **In Robot Learning and Training Pipelines:** Teleoperation demonstrations are used to generate datasets for imitation learning. Current systems primarily capture **visual motion and position data**, without fingertip tactile cues, constraining the quality of learned manipulation behaviors.

**Consequently, existing haptic gloves and teleoperation interfaces provide only general or vibration-based feedback, lacking the localized fingertip force cues required for precise grip control, realistic interaction, and high-fidelity human-to-robot skill transfer.**

## Proposed Solution
A compact, rolled **Dielectric Elastomer Actuator (DEA) module** integrated into a wearable glove to provide localized, normal force feedback, bridging the sensory gap between human operators and advanced robotic systems.

## System Architecture
This is a multi-domain system validated through rigorous modeling and custom hardware design:
*   **Actuator:** Rolled multilayer DEA films with compliant Carbon Nanotube (CNT) electrodes.
*   **Power Electronics:** Custom high-voltage drive circuit leveraging **SiC MOSFETs** for rapid and precise voltage modulation.
*   **Embedded Control:** **ESP32-based microcontroller** running **Embedded C/C++** for real-time, closed-loop control of the actuation signal.
*   **Sensing:** Thin-film force sensors integrated for force feedback and performance validation.
*   **Verification:** Design verified using **COMSOL** (electro-mechanical) and **LTspice** (circuit simulation).

## Key Design Constraints
The system was engineered to meet a specific set of demanding, quantitative goals:

* **Compact Form Factor:** Final module volume constrained to $\le 2 \text{ cm}^3$ for seamless fingertip integration and lightweight construction.
* **Performance (Force):** Targeted output of $\ge 0.2 \text{ N}$ blocked force.
* **Performance (Displacement):** Targeted output of $\ge 0.5 \text{ mm}$ of free (no-load) displacement.
* **Electrical Safety & Insulation:** Proof-of-concept operating voltage constrained to **< 300 V**, ensuring electrical safety and insulation within a wearable environment.
* **Durability:** Designed and verified for $\ge 500{,}000$ actuation cycles to meet product lifespan requirements.



