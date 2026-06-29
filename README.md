# 32-Bit Arithmetic Logic Unit (ALU) using Verilog HDL

A 32-bit Arithmetic Logic Unit (ALU) designed in **Verilog HDL** and simulated using **Xilinx Vivado**.

This project demonstrates the implementation of common arithmetic and logical operations in digital design and serves as a beginner-friendly VLSI/Verilog project.

---

## 📌 Features

The ALU performs the following operations:

| Operation | Description |
|-----------|-------------|
| Addition | A + B |
| Subtraction | A - B |
| Multiplication | A × B |
| Division | A ÷ B (Division-by-zero handled) |
| Bitwise AND | A & B |
| Bitwise OR | A \| B |
| Bitwise XOR | A ^ B |
| Bitwise NOT | ~A |

---

## 📂 Project Structure

```
ALU32/
│── 32_ALU Design code.txt         # Verilog Design
│── 32_ALU testbench code.txt      # Testbench
│── 32_Bit_ALU_schematic diagram.png
│── 32_Bit_ALU_schematic diagram
│── README.md
```

---

## 🛠️ Tools Used

- Verilog HDL
- Xilinx Vivado
- Vivado Simulator

---

## 📥 Inputs

| Signal | Width | Description |
|--------|-------|-------------|
| a | 32-bit | First Operand |
| b | 32-bit | Second Operand |

---

## 📤 Outputs

| Signal | Width | Description |
|--------|-------|-------------|
| add | 33-bit | Addition Result |
| sub | 33-bit | Subtraction Result |
| mul | 64-bit | Multiplication Result |
| div | 32-bit | Division Result |
| and_out | 32-bit | AND Result |
| or_out | 32-bit | OR Result |
| xor_out | 32-bit | XOR Result |
| not_out | 32-bit | NOT Result |

---

## 🔒 Division by Zero

To avoid invalid division, the ALU checks whether the divisor is zero.

```verilog
assign div = (b != 0) ? a / b : 32'b0;
```

If **b = 0**, the output of the division operation is **0**.

---

## 🧪 Test Cases

The following test cases are included in the testbench:

| Test | A | B |
|------|----|----|
| 1 | 20 | 10 |
| 2 | 100 | 25 |
| 3 | 255 | 15 |
| 4 | 500 | 200 |
| 5 | 50 | 0 (Division by Zero) |

The simulation automatically displays all operation results using `$monitor`. :contentReference[oaicite:2]{index=2}

---

## RTL Schematic

The synthesized RTL consists of:

- Adder
- Subtractor
- Multiplier
- Divider
- Multiplexer (Division Protection)
- AND Gate
- OR Gate
- XOR Gate
- NOT Gate

Refer to **RTL_Schematic.pdf** for the complete architecture. :contentReference[oaicite:3]{index=3}

---

## Simulation Result

The waveform verifies that all arithmetic and logical operations produce the expected outputs.

Example:

| A | B | ADD | SUB | MUL | DIV |
|---|---|-----|-----|-----|-----|
| 20 | 10 | 30 | 10 | 200 | 2 |
| 100 | 25 | 125 | 75 | 2500 | 4 |
| 255 | 15 | 270 | 240 | 3825 | 17 |
| 500 | 200 | 700 | 300 | 100000 | 2 |
| 50 | 0 | 50 | 50 | 0 | 0 |

<img width="1624" height="893" alt="simulation of 32_ALU" src="https://github.com/user-attachments/assets/b865fc1c-5ceb-4304-93d3-f54cfca37eb8" />


---

## Future Improvements

- Carry Flag
- Zero Flag
- Overflow Flag
- Sign Flag
- Shift Operations
- Rotate Operations
- Comparison Operations
- ALU Control Signal
- Parameterized Data Width (16/32/64-bit)

---

## Learning Outcomes

- Verilog HDL Coding
- Continuous Assignments
- Arithmetic Operations
- Bitwise Logic Operations
- RTL Design
- Testbench Development
- Functional Simulation in Vivado

---

## Author

**Kandregula Hari Sai Mallikarjun**

B.Tech Electronics and Communication Engineering

Interested in:
- VLSI Design
- Digital Design
- RTL Design
- Verilog HDL
- ASIC Design

---

⭐ If you found this project useful, consider giving it a **Star** on GitHub!
