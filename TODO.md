# AgriDrone — TODO

## Key Constraints — Always Keep in Mind

1. **Simple Interface:** Non-programmers must be able to configure and run scenarios without writing code.
2. **Low Latency:** Prioritize fast sensing, communication, decision-making, and UAV response.
3. **Real-World Fidelity:** Simulate realistic sensor limitations, communication failures, drone dynamics, terrain, and animal behavior.
4. **Lightweight & Modular:** Avoid unnecessary computational overhead; components should be independently replaceable or upgradeable.
5. **Scalability:** Support large agricultural areas, distributed sensors, and multiple UAVs.
6. **Safety:** Respect geofencing, wildlife welfare, fail-safe behavior, and human intervention requirements.

## 1. Architecture Planning
- [ ] Plan the overall system architecture and data flow.
- [ ] Define interactions between sensors, communication networks, decision-making systems, UAVs, and the simulation environment.
- [ ] Identify components that can be simulated initially versus those requiring realistic hardware/software integration.
- [ ] Finalize the technology stack and component interfaces.

## 2. Base Prototype

### Simulation Environment
- [ ] Evaluate **Gazebo / MuJoCo / AirSim** and select a suitable simulator.
  - Lightweight and performant.
  - Supports single and multi-UAV scenarios.
  - Supports or allows simulation of **drone-to-base and drone-to-drone communication**.
  - Exposes simulation state, sensor outputs, and control APIs directly or through Python.
  - Supports configurable terrain, obstacles, sensors, and wildlife movement.
- [ ] Implement a basic farm environment with configurable boundaries.
- [ ] Introduce simulated wildlife intrusion events.
- [ ] Integrate a basic UAV with takeoff, navigation, and return-to-base functionality.

### IoT & Communication
- [ ] Simulate distributed sensors (motion, RGB cameras, thermal).
- [ ] Implement configurable sensor placement, range, noise, and detection behavior.
- [ ] Model communication between sensors, base stations, and UAVs.
- [ ] Account for communication latency, packet loss, and connectivity failures.

### Decision & Control
- [ ] Implement an event-driven pipeline: **Detection → Assessment → Dispatch → Response → Return**.
- [ ] Support configurable detection thresholds and response policies.
- [ ] Include basic mission safety constraints and manual override.

### Operator Interface
- [ ] Build a simple interface for users with little or no programming experience.
- [ ] Allow drag-and-drop placement of sensors, UAV stations, and intrusion events.
- [ ] Provide simulation controls (start, pause, reset, replay).
- [ ] Display UAV paths, sensor coverage, detection events, and response outcomes.

## 3. Evaluation & Progressive Realism
- [ ] Define metrics: detection accuracy, end-to-end response latency, coverage, battery consumption, and intervention success.
- [ ] Test multiple scenarios, sensor configurations, and UAV deployment strategies.
- [ ] Introduce realistic flight dynamics, communication protocols, and hardware-in-the-loop capabilities progressively.
- [ ] Validate simulated behavior against real-world measurements when available.

---

**Initial milestone:** Demonstrate one animal approaching a farm, triggering a simulated sensor, dispatching a UAV, and recording the resulting response and system latency.