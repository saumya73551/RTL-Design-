
# Sky130 RTL Design and Synthesis Workshop

## 1. Introduction

This repository documents my hands-on learning and practical implementation of RTL Design and Synthesis using open-source VLSI tools and the SkyWater SKY130 Process Design Kit (PDK).

The workshop focuses on understanding the digital design flow, starting from Verilog RTL coding to simulation, synthesis and analysis.

**Original Workshop Repository:**  
https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop

**Development Environment:** Ubuntu 24.04 LTS running inside Oracle VirtualBox.

---

## 2. Development Environment

| Component | Details |
|---|---|
| Operating System | Ubuntu 24.04 LTS |
| Virtualization | Oracle VirtualBox |
| Hardware Description Language | Verilog HDL |
| Version Control | Git |
| Synthesis Tool | Yosys 0.33 |
| Simulation Tool | Icarus Verilog 12.0 |
| Waveform Viewer | GTKWave 3.3.116 |
| Technology | SkyWater SKY130 |

---

## 3. Repository Setup

### Step 1: Clone the Workshop Repository

The workshop repository was downloaded from GitHub using Git.

```bash
git clone https://github.com/kunalg123/sky130RTLDesignAndSynthesisWorkshop.git
```

### Step 2: Navigate to the Repository

```bash
cd sky130RTLDesignAndSynthesisWorkshop
```

### Step 3: Verify Repository Contents

```bash
ls -la
```

### Repository Setup Screenshot

![Workshop Repository Contents](tool%20instal/workshop%20contents.png)

*Figure 1: Successfully cloned Sky130 RTL Design and Synthesis Workshop repository in Ubuntu.*

---

## 4. EDA Tools Installation and Configuration

The following open-source tools were installed and verified in the Ubuntu environment.

### 4.1 Yosys – RTL Synthesis Tool

**Introduction:**

Yosys is an open-source framework used for RTL synthesis. It converts a digital design written in Verilog HDL into a gate-level representation.

**Main Functions:**

- Reads Verilog RTL source files.
- Performs RTL elaboration and logic optimization.
- Converts behavioral descriptions into logic gates.
- Performs technology-independent synthesis.
- Supports technology mapping to standard-cell libraries.
- Provides synthesis statistics such as cell count and design structure.

**Role in RTL Design Flow:**

Yosys is used after RTL coding and functional verification to synthesize the design into a hardware-oriented netlist.

**Installation Command:**

```bash
sudo apt-get install yosys
```

**Version Verification:**

```bash
yosys -V
```

**Installed Version:**

```text
Yosys 0.33
```

---

### 4.2 Icarus Verilog – RTL Simulation Tool

**Introduction:**

Icarus Verilog is an open-source Verilog compiler and simulation tool. It is used to compile and simulate digital designs written in Verilog HDL.

**Main Functions:**

- Compiles Verilog source files.
- Supports Verilog testbench execution.
- Checks functional behavior of RTL designs.
- Helps identify logical and functional errors.
- Generates simulation output and waveform files.

**Important Commands:**

Compile a Verilog design:

```bash
iverilog -o simulation.out design.v testbench.v
```

Run the simulation:

```bash
vvp simulation.out
```

Generate waveform files using `$dumpfile` and `$dumpvars` in the testbench.

**Role in RTL Design Flow:**

Icarus Verilog is used to verify the functional correctness of the RTL design before synthesis.

**Installation Command:**

```bash
sudo apt-get install iverilog
```

**Version Verification:**

```bash
iverilog -V
```

**Installed Version:**

```text
Icarus Verilog 12.0
```

---

### 4.3 GTKWave – Waveform Viewer

**Introduction:**

GTKWave is an open-source waveform viewer used to visualize and analyze digital simulation signals.

It helps designers understand how signals change over time during RTL simulation.

**Main Functions:**

- Displays digital signals in waveform format.
- Visualizes input and output transitions.
- Helps analyze clock and reset signals.
- Supports VCD (Value Change Dump) waveform files.
- Helps debug timing and functional behavior.

**Important Command:**

```bash
gtkwave waveform.vcd
```

**Role in RTL Design Flow:**

GTKWave is used after simulation to inspect signal transitions and verify the expected behavior of the digital design.

**Installation Command:**

```bash
sudo apt-get install gtkwave
```

**Version Verification:**

```bash
gtkwave --version
```

**Installed Version:**

```text
GTKWave Analyzer v3.3.116
```

---

### 4.4 Git – Version Control System

**Introduction:**

Git is a distributed version control system used to track changes in source code and manage project development.

**Main Functions:**

- Tracks modifications in RTL source files.
- Maintains project history.
- Supports branching and merging.
- Allows synchronization with GitHub repositories.
- Helps manage collaborative development.

**Important Commands:**

Check Git version:

```bash
git --version
```

Check repository status:

```bash
git status
```

Add files:

```bash
git add .
```

Commit changes:

```bash
git commit -m "Update RTL design files"
```

Push changes:

```bash
git push
```

---

### 4.5 SkyWater SKY130 PDK

**Introduction:**

The SkyWater SKY130 PDK is an open-source process design kit for the 130 nm semiconductor technology.

It provides technology-specific information and resources required for designing and implementing integrated circuits.

**Main Components:**

- Standard-cell libraries.
- Transistor models.
- Technology and process information.
- Timing and physical design libraries.
- Design rules and technology files.

**Role in VLSI Design:**

The SKY130 PDK provides the technology-specific library information required for mapping synthesized RTL designs into standard cells.

It is useful for exploring the connection between RTL design, standard-cell implementation and physical design.

---

## 5. RTL-to-Synthesis Design Flow

The general digital design flow followed in this workshop is:

```text
       Verilog RTL Design
               |
               v
       RTL Compilation
        (Icarus Verilog)
               |
               v
       Functional Simulation
               |
               v
       Waveform Analysis
          (GTKWave)
               |
               v
        RTL Synthesis
           (Yosys)
               |
               v
       Logic Optimization
               |
               v
       Netlist Generation
               |
               v
     Standard Cell Mapping
        (SKY130 PDK)
```

---

## 6. Installation Verification Summary

| Tool | Version | Status |
|---|---|---|
| Yosys | 0.33 | Installed and Verified |
| Icarus Verilog | 12.0 | Installed and Verified |
| GTKWave | 3.3.116 | Installed and Verified |
| Git | 2.43.0 | Installed and Verified |
| SKY130 PDK | SKY130 | Workshop Technology |

---

## 7. Learning Objectives

- Understand digital design fundamentals.
- Develop RTL designs using Verilog HDL.
- Learn combinational and sequential logic.
- Perform RTL compilation and functional simulation.
- Analyze digital waveforms using GTKWave.
- Understand RTL synthesis using Yosys.
- Explore standard-cell libraries and technology mapping.
- Understand the RTL-to-synthesis design flow.
- Gain practical exposure to open-source VLSI tools.

---

## 8. Project Progress

- [x] Ubuntu 24.04 environment setup.
- [x] Git installation and verification.
- [x] Sky130 RTL Design and Synthesis Workshop repository cloned.
- [x] Yosys installation and version verification.
- [x] Icarus Verilog installation and version verification.
- [x] GTKWave installation and version verification.
- [ ] Verilog RTL coding exercises.
- [ ] Testbench development and simulation.
- [ ] Waveform analysis.
- [ ] RTL synthesis using Yosys.
- [ ] Standard-cell technology mapping.
- [ ] Further synthesis and design analysis.

---

## 9. Conclusion

The initial development environment has been configured successfully, and the required open-source EDA tools have been installed and verified.

This repository will serve as a record of my practical learning, RTL design exercises, simulation results and synthesis experiments throughout the Sky130 RTL Design and Synthesis Workshop.

---

**Author:** Saumya Agrahari  
**Domain:** VLSI Design | RTL Design | Digital Design and Synthesis
