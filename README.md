# Minesweeper Competition Robot — PCB Design 🤖💣

Custom KiCad-designed PCBs for a minesweeper competition robot, consisting of a **Control PCB** housing the main microcontroller and sensing/driving circuitry, and a **Power PCB** acting as a smart relay system for safely switching robot subsystems on and off.

<div align="center">
  <img src="images/thumbnail.png" alt="Minesweeper Robot PCBs" width="800"/>
</div>

<br>
<div align="center">
  <a href="https://codeload.github.com/TendoPain18/minesweeper-competition-robot-pcb/legacy.zip/main">
    <img src="https://img.shields.io/badge/Download-Files-brightgreen?style=for-the-badge&logo=download&logoColor=white" alt="Download Files" style="height: 50px;"/>
  </a>
</div>

## 📋 About

Both PCBs were fully designed from schematic to layout in **KiCad** and manufactured as real printed circuit boards. The two boards work together: the Control PCB handles all logic, motor driving, sensing, and protection, while the Power PCB receives switching commands from the Control PCB and safely controls power delivery to the robot's subsystems.

## 🛠️ Tools Used

- **KiCad** — Schematic capture and PCB layout
- **Arduino IDE** — Firmware for the Arduino Mega

---

## 🟦 Control PCB

The brain of the robot. Hosts the microcontroller and all peripheral circuitry needed to drive motors, read sensors, and manage safe shutdown.

<div align="center">
  <img src="images/control_kicad.jpeg" alt="Control PCB KiCad Layout" width="700"/>
</div>

<div align="center">
  <img src="images/control_circuit_diagram.jpeg" alt="Control Circuit Diagram" width="700"/>
</div>

### Key Components

- **Arduino Mega** — Main microcontroller
- **Two HW-315 Motor Driver Modules** — Drive the main locomotion motors
- **H-Bridge** — Additional motor driving stage
- **Two MPU-6050 IMUs** — Inertial measurement units for orientation sensing
- **Auto Safe-Shutdown Circuit** — Capacitor-backed circuit using ICs, capacitors, and resistors that detects power loss and safely closes the system before supply rails collapse

### Connector Pins / Interfaces

| Interface | Description |
|-----------|-------------|
| Motor Control ×2 | PWM/direction signals for drive motors |
| Motor Driver ×2 | Power outputs to HW-315 modules |
| Encoder ×2 | Quadrature encoder inputs for wheel odometry |
| Arm Motor | Control signal for the mine-detection arm |
| 9V Battery | Main power input |
| Power PCB Link | Control signals sent to the Power PCB |

### PCB Photos

<div align="center">
  <img src="images/control.jpeg" alt="Control PCB" width="700"/>
</div>

<div align="center">
  <img src="images/control_1.jpeg" alt="Control PCB View 1" width="32%"/>
  <img src="images/control_2.jpeg" alt="Control PCB View 2" width="32%"/>
  <img src="images/control_3.jpeg" alt="Control PCB View 3" width="32%"/>
</div>

### Safe Shutdown Circuit

A key protection feature of the Control PCB is the automatic safe-shutdown circuit. When the power supply is cut or drops below a safe threshold, the capacitor bank holds enough energy to allow the ICs to complete a controlled shutdown sequence, preventing state corruption and protecting the motor drivers from abrupt power loss.

---

## 🟥 Power PCB

Acts as a smart relay board, receiving switching signals from the Control PCB and toggling power to the robot's subsystems in a safe, controlled manner.

<div align="center">
  <img src="images/power_kicad.jpeg" alt="Power PCB KiCad Layout" width="700"/>
</div>

<div align="center">
  <img src="images/power_circuit_diagram.jpeg" alt="Power Circuit Diagram" width="700"/>
</div>

### Key Features

- Receives control signals from the Control PCB
- Safely switches power to robot subsystems on and off
- Protects against back-EMF and switching transients
- Designed for low-resistance power paths to minimise losses

### PCB Photos

<div align="center">
  <img src="images/power.jpeg" alt="Power PCB" width="700"/>
</div>

<div align="center">
  <img src="images/power_1.jpeg" alt="Power PCB View 1" width="32%"/>
  <img src="images/power_2.jpeg" alt="Power PCB View 2" width="32%"/>
  <img src="images/power_3.jpeg" alt="Power PCB View 3" width="32%"/>
</div>

---

## 🖨️ Manufactured Boards

<div align="center">
  <img src="images/real_printed_circuit_with_components.jpeg" alt="Real Printed Circuit with Components" width="700"/>
</div>

*Fully assembled and populated PCBs ready for robot integration*

---

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## 🙏 Acknowledgments

- KiCad open-source EDA tool
- Competition organizers for the design challenge

## <!-- CONTACT -->
<div id="toc" align="center">
  <ul style="list-style: none">
    <summary>
      <h2 align="center">
        🚀
        CONTACT ME
        🚀
      </h2>
    </summary>
  </ul>
</div>
<table align="center" style="width: 100%; max-width: 600px;">
<tr>
  <td style="width: 20%; text-align: center;">
    <a href="https://www.linkedin.com/in/amr-ashraf-86457134a/" target="_blank">
      <img src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white" style="height: 33px; width: 120px;"/>
    </a>
  </td>
  <td style="width: 20%; text-align: center;">
    <a href="https://github.com/TendoPain18" target="_blank">
      <img src="https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white" style="height: 33px; width: 120px;"/>
    </a>
  </td>
  <td style="width: 20%; text-align: center;">
    <a href="mailto:amrgadalla01@gmail.com">
      <img src="https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white" style="height: 33px; width: 120px;"/>
    </a>
  </td>
  <td style="width: 20%; text-align: center;">
    <a href="https://www.facebook.com/amr.ashraf.7311/" target="_blank">
      <img src="https://img.shields.io/badge/Facebook-1877F2?style=for-the-badge&logo=facebook&logoColor=white" style="height: 33px; width: 120px;"/>
    </a>
  </td>
  <td style="width: 20%; text-align: center;">
    <a href="https://wa.me/201019702121" target="_blank">
      <img src="https://img.shields.io/badge/WhatsApp-25D366?style=for-the-badge&logo=whatsapp&logoColor=white" style="height: 33px; width: 120px;"/>
    </a>
  </td>
</tr>
</table>
<!-- END CONTACT -->
