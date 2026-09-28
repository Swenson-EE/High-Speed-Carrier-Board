# LattePanda-Mu High-Speed Carrier Board

A custom carrier board designed for the **LattePanda Mu** compute module, with a focus on high-speed digital design, signal integrity, power distribution, and practical PCB design.

This project was developed to apply high-speed PCB design concepts to a real embedded computing platform. The design process incorporated concepts studied through online courses, technical forums, datasheets, and reference designs.

> **Project Status:** Fabrication
> **PCB Design Tool:** KiCad
> **Primary Focus:** High-speed digital design, power distribution, signal integrity, and embedded hardware

---

## Overview

The goal of this project is to design a custom carrier board around the LattePanda Mu rather than relying on an off-the-shelf carrier board to explore high-speed digital design concepts.

The carrier board is intended to provide practical interfaces for development and experimentation while giving me experience designing a PCB containing multiple high-speed interfaces.

### Design Goals

- Develop a custom carrier board for the LattePanda Mu
- Apply high-speed PCB layout techniques
- Develop controlled-impedance routing practices
- Maintain appropriate differential-pair geometry
- Minimize high-speed signal discontinuities
- Develop a robust power distribution network
- Practice schematic-to-PCB design workflows
- Use datasheets and reference documentation to make design decisions
- Validate the design using available electrical and PCB design tools
- Produce a board suitable for fabrication and bring-up

---

## Hardware

### Compute Module

**LattePanda Mu**

The LattePanda Mu provides the primary compute platform for the carrier board.

The carrier board interfaces with the module through its high-density connectors and routes the available interfaces to the desired peripherals and connectors.

---

## PCB Designs

<table style="background: white;">
  <tr>
    <td align="center"><b>Top Silk Screen</b><br><img src="./graphics/LattePandaMu-Carrier-F_Silkscreen.svg" width="400"/></td>
  </tr>
  <tr>
    <td align="center"><b>Front Cu (L1)</b><br><img src="./graphics/LattePandaMu-Carrier-F_Cu.svg" width="400"/></td>
  </tr>
  <tr>
    <td align="center"><b>GND (L2)</b><br><img src="./graphics/LattePandaMu-Carrier-In1_GND.svg" width="400"/></td>
  </tr>
  <tr>
    <td align="center"><b>PWR (L3)</b><br><img src="./graphics/LattePandaMu-Carrier-In2_PWR.svg" width="400"/></td>
  </tr>
  <tr>
    <td align="center"><b>Bottom Cu (L4)</b><br><img src="./graphics/LattePandaMu-Carrier-B_Cu.svg" width="400"/></td>
  </tr>
</table>

## Interfaces

The carrier board is designed around several interfaces provided by the LattePanda Mu.

| Interface      | Purpose                     | Design Considerations                       |
| -------------- | --------------------------- | ------------------------------------------- |
| USB            | Peripheral connectivity     | High-speed differential routing             |
| HDMI / Display | Display output              | Differential high-speed routing             |
| Ethernet       | Network connectivity        | Differential pairs and magnetics            |
| PCIe           | Expansion                   | Controlled impedance / differential routing |
| M.2            | Expansion/storage           | High-speed differential routing             |
| GPIO           | General-purpose I/O         | Digital signal integrity                    |
| Power          | Module and peripheral power | Power integrity / decoupling                |

---

# High-Speed PCB Design

A major purpose of this project is to practice PCB design techniques applicable to high-speed digital hardware.

Rather than treating PCB traces simply as electrical connections, the design considers them as transmission lines at sufficiently high signal frequencies.

Areas being considered include:

### Controlled Impedance

High-speed interfaces are routed using appropriate controlled-impedance structures based on the PCB stackup and manufacturer's capabilities.

Examples include:

- Differential impedance
- Single-ended impedance
- Trace width
- Trace spacing
- Reference planes
- Dielectric thickness
- Copper thickness

The final trace geometries are based on the selected PCB stackup rather than relying solely on generic routing rules.

### Differential Pairs

High-speed differential interfaces are routed as matched differential pairs where required.

Design considerations include:

- Differential impedance
- Pair spacing
- Intra-pair length matching
- Continuous reference planes
- Avoiding unnecessary vias
- Minimizing discontinuities
- Maintaining consistent routing geometry

### Return Paths

High-speed signal routing considers the return current path rather than treating the signal trace independently.

Particular attention is given to:

- Continuous reference planes
- Plane transitions
- Ground vias
- Layer transitions
- Signal crossings
- Connector transitions

### Via Design

Vias can introduce discontinuities into high-speed signals.

Where applicable, the design considers:

- Via stubs
- Via placement
- Differential via geometry
- Ground-via placement
- Layer transitions
- Back-drilling requirements

---

# Power Distribution

The carrier board includes power regulation and distribution for the compute module and attached peripherals.

Power design considerations include:

- Input power requirements
- Voltage regulation
- Current requirements
- Decoupling
- Ground-plane design

Decoupling capacitors are placed with consideration for the physical connection between the capacitor, power pin, and return path rather than simply placing them near the associated component.

---

# PCB Stackup

The PCB stackup is an important part of the high-speed design.

The stackup is selected based on the requirements of the interfaces being routed and the capabilities of the intended PCB manufacturer.

Example stackup:

| Layer | Function |
| ----- | -------- |
| L1    | Signal   |
| L2    | Ground   |
| L3    | Power    |
| L4    | Signal   |

The stackup is used to determine the appropriate controlled-impedance trace geometries.

---

# Research & Learning

This project is also a practical study of high-speed PCB design.

The design process has been informed by:

- LattePanda Mu documentation
- Component datasheets
- Manufacturer application notes
- PCB fabrication guidelines
- High-speed PCB design coursework
- Engineering forums
- Technical discussions
- Reference designs
- Signal-integrity design practices

The purpose of using these resources is to understand **why** particular PCB design decisions are made rather than simply reproducing an existing board.

Where external designs or reference material influence the project, the relevant source will be documented in the project documentation.

---

# Verification

Before fabrication, the design will be reviewed using:

- Electrical rule checking
- PCB design rule checking
- Connectivity verification
- Differential-pair constraints
- Length matching constraints
- Controlled-impedance calculations
- Power-tree review
- Datasheet requirement verification
- Manufacturer design-rule review

Where practical, calculations and design assumptions will be documented in the `/docs` directory.

---

# Disclaimer

This is an independent educational hardware project.

The project is intended to demonstrate my understanding and application of PCB design principles. It is not an official LattePanda design.

The design should be independently reviewed and validated before being used in a production or safety-critical application.

---

# References

- LattePanda Mu documentation
- LattePanda Mu hardware/reference documentation
- Relevant component datasheets
- PCB manufacturer fabrication specifications
- High-speed PCB design course material
- Relevant application notes and technical references

---

## Author

**Tyler Swenson**

This project was created as a hands-on embedded hardware and high-speed PCB design project, with an emphasis on understanding the engineering decisions behind the design rather than simply producing a functioning PCB.
