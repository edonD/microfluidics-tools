# Experiment Automation & Software Control

> Last updated: March 2026

## Overview

Modern microfluidic experiments increasingly require automated control — from simple flow rate changes to complex multi-step protocols with feedback loops. This guide covers software tools, APIs, and automation strategies.

## Vendor SDKs & Software

### Elveflow

| Software | Description | Languages |
|----------|-------------|-----------|
| **ESI (Elveflow Smart Interface)** | GUI for OB1 control. Sequencer for automated experiments. | — |
| **Elveflow SDK** | Programmatic control of OB1, AF1, flow sensors | Python, LabVIEW, MATLAB, C++ |

**Python example (Elveflow OB1):**
```python
# Elveflow Python SDK - basic flow control
from Elveflow64 import *

# Initialize OB1
Ession_ID = OB1_Initialization("COM3")

# Set pressure on channel 1 (in mbar)
OB1_Set_Press(Sess_ID, 1, 100.0)  # 100 mbar
time.sleep(5)

# Read pressure
pressure = OB1_Get_Press(Sess_ID, 1)
print(f"Pressure: {pressure} mbar")

# Set flow rate (requires flow sensor)
OB1_Set_Flow(Sess_ID, 1, 5.0)  # 5 µL/min

# Close
OB1_Destructor(Sess_ID)
```

### Fluigent

| Software | Description | Languages |
|----------|-------------|-----------|
| **OxyGEN** | GUI for instrument control and experiment design | — |
| **Fluigent SDK** | Comprehensive API for all Fluigent products | Python, C++, C#, LabVIEW, MATLAB |

**Python example (Fluigent MFCS):**
```python
# Fluigent Python SDK
import Fluigent.SDK as fgt

# Initialize
fgt.fgt_init()

# Get controller info
controller_count = fgt.fgt_get_controllersInfo()
print(f"Found {len(controller_count)} controllers")

# Set pressure (channel 0, 50 mbar)
fgt.fgt_set_pressure(0, 50)

# Read pressure
pressure = fgt.fgt_get_pressure(0)
print(f"Pressure: {pressure} mbar")

# Set flow rate (requires flow sensor)
fgt.fgt_set_sensorRegulation(0, 0, 10.0)  # 10 µL/min

# Close
fgt.fgt_close()
```

### Harvard Apparatus

| Software | Description | Connection |
|----------|-------------|------------|
| **Pump control software** | Basic GUI | USB serial |
| **RS-232/RS-485 protocol** | Command-line control | Serial |

**Python example (Harvard PHD ULTRA via serial):**
```python
import serial

pump = serial.Serial('COM4', 115200, timeout=1)

# Set syringe diameter (14.5 mm for 10 mL BD syringe)
pump.write(b'diameter 14.5\r')

# Set infusion rate
pump.write(b'irate 10 ul/min\r')

# Start infusion
pump.write(b'irun\r')

# Stop
pump.write(b'stop\r')

pump.close()
```

### Cetoni neMESYS

| Software | Description |
|----------|-------------|
| **QmixElements** | Full GUI with scripting, automation, and data logging |
| **QmixSDK** | Python, LabVIEW, C++ API |

---

## Open-Source Automation Tools

### Python Libraries

| Library | Purpose | Link |
|---------|---------|------|
| **AMFTools** | Python interface for AMF microfluidic devices (USB, RS232, RS485) | [amf.ch](https://amf.ch/introducing-amftools-enhanced-control-for-advanced-microfluidics-amf-devices/) |
| **MagScope** | Open-source multiprocessing app — GUI, hardware control, real-time analysis | [biorxiv preprint](https://www.biorxiv.org) |
| **pyserial** | Serial communication with pumps/controllers | [pypi.org/project/pyserial](https://pypi.org/project/pyserial/) |
| **pyvisa** | VISA instrument control (GPIB, USB, serial) | [pypi.org/project/pyvisa](https://pypi.org/project/pyvisa/) |
| **nidaqmx** | National Instruments DAQ control | [pypi.org/project/nidaqmx](https://pypi.org/project/nidaqmx/) |

### LabVIEW

LabVIEW is still commonly used in microfluidics labs, especially for:
- National Instruments DAQ integration
- Real-time control with FPGA
- Vendor-supplied VIs (Elveflow, Fluigent, Harvard)

**Performance note:** LabVIEW outperforms Python in data acquisition speed (365s vs 1505s in one benchmark), but Python is better for interfacing, lower RAM usage, and easier development.

### Arduino-Based Automation

For DIY and budget setups:
```
Arduino → stepper motor driver → syringe pump
Arduino → solenoid valves → pneumatic valve control
Arduino → pressure sensor → feedback loop
Arduino → temperature sensor → hot plate control
```

**Common Arduino shields for microfluidics:**
- CNC Shield V3 (for stepper motor pumps)
- Motor Shield (for DC motor pumps)
- Relay Shield (for solenoid valve switching)

---

## Automation Strategies

### Level 1: Manual with Software Control

**Setup:** PC running vendor software → USB → pressure controller/pump
**Use case:** Simple experiments, parameter optimization
**Tools:** Elveflow ESI, Fluigent OxyGEN, pump vendor software

### Level 2: Scripted Experiment Sequences

**Setup:** Python/LabVIEW script → vendor SDK → instruments
**Use case:** Multi-step protocols, reproducible experiments
**Example workflow:**
```python
# Automated droplet generation optimization
for pressure in range(50, 200, 10):  # Sweep continuous phase pressure
    set_pressure(channel_oil, pressure)
    time.sleep(30)  # Wait for stabilization
    capture_image()
    droplet_size = analyze_droplets(image)
    log_data(pressure, droplet_size)
```

### Level 3: Closed-Loop Feedback Control

**Setup:** Camera/sensor → analysis → controller adjustment → instrument
**Use case:** Maintaining target droplet size, flow rate control
**Architecture:**
```
Sensor (camera/flow/pressure)
    ↓
Real-time analysis (Python/OpenCV)
    ↓
PID controller
    ↓
Actuator (pressure controller/pump)
```

**PID flow control example:**
```python
import simple_pid

# PID controller for flow rate
pid = simple_pid.PID(Kp=2.0, Ki=0.5, Kd=0.1, setpoint=10.0)  # Target: 10 µL/min

while running:
    flow_rate = read_flow_sensor()
    correction = pid(flow_rate)
    new_pressure = current_pressure + correction
    set_pressure(new_pressure)
    time.sleep(0.1)  # 10 Hz control loop
```

### Level 4: Machine Learning-Assisted Control

**Setup:** Camera → ML model → optimal parameters → instrument
**Use case:** Droplet generation optimization, sorting decisions
**Emerging tools:**
- Neural networks trained on droplet images for real-time size prediction
- Reinforcement learning for optimal flow parameter discovery
- Computer vision (OpenCV/YOLO) for droplet counting and sizing

---

## Image Analysis for Microfluidics

### Software Tools

| Tool | Type | Best For | Cost |
|------|------|----------|------|
| **ImageJ/Fiji** | Open source | General measurement, particle counting | Free |
| **MATLAB Image Processing** | Commercial | Custom analysis, batch processing | $2,150 + $1,000 toolbox |
| **Python + OpenCV** | Open source | Real-time analysis, automation | Free |
| **Python + scikit-image** | Open source | Batch image analysis | Free |
| **CellProfiler** | Open source | Cell-related measurements | Free |
| **µManager** | Open source | Microscope control + acquisition | Free |
| **NIS-Elements** | Commercial | Nikon microscope software | Bundled / $5k+ |
| **Zen** | Commercial | Zeiss microscope software | Bundled / $5k+ |

### Common Image Analysis Tasks

| Task | Tool | Method |
|------|------|--------|
| Droplet size measurement | ImageJ, Python+OpenCV | Hough circle transform, contour detection |
| Flow velocity (µPIV) | PIVlab (MATLAB), OpenPIV (Python) | Cross-correlation of image pairs |
| Mixing efficiency | ImageJ, Python | Fluorescence intensity profile across channel |
| Cell counting | CellProfiler, ImageJ | Threshold + watershed segmentation |
| Channel width measurement | ImageJ | Line profile + edge detection |

### Python Droplet Analysis Example

```python
import cv2
import numpy as np

# Load microscope image
img = cv2.imread('droplets.tif', cv2.IMREAD_GRAYSCALE)

# Detect circles (droplets)
circles = cv2.HoughCircles(
    img, cv2.HOUGH_GRADIENT,
    dp=1, minDist=30,
    param1=50, param2=30,
    minRadius=10, maxRadius=50
)

# Calculate statistics
if circles is not None:
    radii = circles[0, :, 2]
    diameters = 2 * radii * pixel_size_um  # Convert to µm
    print(f"Mean diameter: {np.mean(diameters):.1f} µm")
    print(f"CV: {np.std(diameters)/np.mean(diameters)*100:.1f}%")
    print(f"Count: {len(diameters)}")
```

---

## Data Logging & Analysis

### Recommended Data Stack

```
Instrument control: Python (vendor SDK)
Data acquisition:   Python (pandas, numpy)
Real-time plotting: Python (matplotlib, plotly)
Data storage:       CSV, HDF5, or SQLite
Post-analysis:      Python (scipy, pandas) or MATLAB
Visualization:      Python (matplotlib, seaborn) or Origin
```

### Best Practices

1. **Log everything** — pressure, flow rate, temperature, timestamps
2. **Use consistent file naming** — `YYYY-MM-DD_experiment-name_run-N.csv`
3. **Include metadata** — chip ID, reagent batch, operator, parameters
4. **Automate data collection** — don't rely on manual recording
5. **Version control** analysis scripts (git)
6. **Use reproducible analysis** — Jupyter notebooks document analysis steps
