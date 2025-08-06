# FPGA Calculator Project

## Course: ECE128  
Contributors:  
- David Okeh  
- Elijah Blaylark  
- Taylor Grant  

---

## 🧮 Introduction

This project focuses on the design and implementation of a **4-bit calculator** using **Verilog** and deployed on an **FPGA board**. The calculator supports **eight operations**—four arithmetic and four logical—and displays results on a **seven-segment display**. Development included Verilog coding, simulation with a testbench, and hardware testing.

---

## 🎯 Objectives

- Develop and verify Verilog code and testbench for the calculator.  
- Simulate the design to ensure correct functionality.  
- Implement the calculator on an FPGA board with a seven-segment display.  
- Present findings through a project report, presentation, and live or recorded demonstration.

---

## 🧩 System Design Overview

### Pre-lab Diagram Overview

1. **Inputs and Outputs**:
   - Inputs: Two 4-bit operands (`A` and `B`) and a 3-bit operation selector (`op`)
   - Output: 8-bit result

2. **Supported Operations**:
   - Arithmetic: `A + B`, `A - B`, `A * B`, `A / B`
   - Logical: `A | B`, `A & B`, `A ^ B`, `~A`

3. **Modules**:
   - Calculator: Computes the selected operation based on `op`
   - `bin2BCD`: Converts binary result to BCD for display
   - 7-Segment Driver: Displays output on 7-segment display

4. **Control Signals**:
   - `clk`: Clock signal for synchronization
   - `reset`: Resets system state

---

## 🧑‍💻 Code & Methodology

### Files:
- `calculator.v` (main design file)
- `tb_calculator.v` (testbench for simulation)

### `calculator.v` Overview:
- **Inputs**:
  - `A`, `B`: 4-bit operands
  - `op`: 3-bit selector for operation
  - `clk`, `reset`: For control logic
- **Operations (`op` values)**:
  - `000`: Addition  
  - `001`: Subtraction  
  - `010`: Multiplication  
  - `011`: Division  
  - `100`: AND  
  - `101`: OR  
  - `110`: XOR  
  - `111`: NOT (`~A` only)
- **Outputs**:
  - `seg`: 7-bit output for 7-segment display
  - `digit_select`: 4-bit signal to multiplex between upper and lower 4-bit digits

### Logic Components:
- **Operation Logic**: Uses `op` to compute and store result in `result_bin`
- **Multiplexing**: Splits result into two 4-bit nibbles; alternates display using `digit_select`
- **7-Segment Decoder**: Converts binary digits to segment patterns (`seg` output)

---

## ✅ Results

### Sample Test Cases:
- `5 + 3 = 8`  
- `7 - 3 = 4`  

These results confirm the correct functionality of the calculator through both simulation and physical FPGA testing.

---

## 📦 How to Run

1. Clone the repository and open the project in your preferred Verilog IDE (e.g., ModelSim, Vivado).
2. Simulate using `tb_calculator.v` to test different operations.
3. Synthesize and implement `calculator.v` on a compatible FPGA board.
4. Connect inputs via switches or buttons, and observe outputs on the 7-segment display.

---

## 📽 Presentation

This project was presented through a written report, a PowerPoint presentation, and a live demonstration of the calculator operating on an FPGA board.

---

## 🛠 Tools & Technologies

- Verilog HDL
- FPGA development board
- 7-Segment Display
- Simulation tools (e.g., ModelSim, Vivado)

---

## 📃 License

This project is for academic purposes under the ECE128 course. For use outside of this scope, please contact the contributors.



