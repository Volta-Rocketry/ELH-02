# Definition of System Requirements
## 1. Requirements

| **ID** | **Requirement Description** | **Type of Requirement** |
|--------|------------------------------| ------------------- |
| REQ-01 | The Instrumentation Subsystem shall comply with industry standards for its design process, manufacturing, and coding. | Operational |
| REQ-02 | The Instrumentation Subsystem shall have non-volatile storage capable of recording at least the entire duration of the flight plus 20% margin. | Functional |
| REQ-03 | The Instrumentation Subsystem shall measure structural loads at critical locations inside and outside the vehicle | Functional |
| REQ-04 | The Instrumentation Subsystem shall measure linear accelerations at least at three different axes | Functional |
| REQ-05 | The Instrumentation Subsystem shall measure internal temperature of the vehicle at different locations | Functional |
| REQ-06 | The Instrumentation Subsystem shall measure deformation of the bulkhead in at two ortogonal axis with high resolution | Functional |
| REQ-07 | The Instrumentation Subsystem shall measure ambient pressure | Functional |
| REQ-08 | The Instrumentation Subsystem shall operate in temperatures between -20° and 85°C according to the flight location conditions | Environmental |
| REQ-09 | The Instrumentation Subsystem shall operate in temperatures higher than 125°C at the moment of the ejection | Environmental |
| REQ-10 | The Instrumentation Subsystem shall withstand launch and flight vibration environments up to 16g. | Environmental |
| REQ-11 | The Instrumentation Subsystem shall operate correctly under pressures corresponding to altitudes up to 11000 ft. | Environmental |
| REQ-12 | The Instrumentation Subsystem shall withstand the recovery and ejection forces | Environmental |
| REQ-13 | The Instrumentation Subsystem shall be turned on while the vehicle is on the launch pad. | Operational |
| REQ-14 | The Instrumentation Subsystem shall operate from a power bus independent from the buses suplying the Main Flight Computer, the Ejection Computers and the Cameras. | Electrical |
| REQ-15 | The Instrumentation Subsystem shall operate when the input voltage at its power interface varies within ±10% of the nominal bus voltage. | Electrical |
| REQ-16 | The Instrumentation Subsystem Power Bus shall comply with the IREC DTEG for electronic devices. | Electrical |
| REQ-17 | The Instrumentation Subsystem shall include over-voltage and reverse-polarity protection. | Electrical |
| REQ-18 | The Instrumentation Subsystem shall be compatible with the avionics bay. | Functional |
| REQ-19 | The Instrumentation Subsystem shall provide a minimum autonomous operational time of 4 hours. | Electrical |



## 2. Key performace parameters

| **ID** | **Parameter** |
|--------|-----------------------------|
| PAR-01 | The Instrumentation Subsystem shall support a minimum sampling rate of 1 kHz for structural load and vibration measurements. |
| PAR-02 | The Instrumentation Subsystem shall support a minimum sampling rate of 500 Hz for inertial and low-frequency measurements. |
| PAR-03 | The Instrumentation Subsystem shall provide a minimum analog-to-digital conversion resolution of 16 bits. |
| PAR-04 | The Instrumentation Subsystem microcontroller shall support multiple procedures for calculations and data-storing with a minimum rate of 1kHz |
| PAR-05 | The Instrumentation Subsystem shall store all acquired data locally in non-volatile memory without data loss during flight. |
| PAR-06 | The Instrumentation Subsystem shall have at least one interface for data downloading . |
| PAR-07 | The Instrumentation Subsystem shall have at least one interface for programming and debugging. |
| PAR-08 | The Instrumentation Subsystem shall maintain data integrity during high-vibration and high-acceleration flight phases. |

## 3. Constraints
| **ID** | **Constraint Description** |
|--------|-----------------------------|
| CON-01 | The Instrumentation Subsystem PCBs shall be designed following the IPC rules for PCB design. |
| CON-02 | The Instrumentation Subsystem PCBs shall be designed for high temperature resistance in the bulkhead. |
| CON-03 | The total mass of all Instrumentation Subsystem hardware shall not exceed 250 g. |
| CON-04 | The Instrumentation Subsystem shall operate from a power bus independent of the main flight computer, the ejection computers and the cameras for a minimum duration of 4 hours. |
| CON-05 | The Instrumentation Subsystem shall be designed to be compatible with the available volume in the avionics bay, as defined in the Volta Tech Team avionics bay CAD model. |
| CON-06 | The Instrumentation Subsystem PCB assemblies shall be mechanically secured to withstand launch and recovery loads. |
| CON-07 | The Instrumentation Subsystem shall be design to allow access to all electronic modules and connectors for integration and removal purposes. |
| CON-08 | The Instrumentation Subsystem sensors shall operate at pass Mach conditions. |

