# 🔢 4-Bit ALU Design using Logisim

This project implements a **4-bit Arithmetic Logic Unit (ALU)** using Logisim.  
The ALU is capable of performing both **arithmetic** and **logical operations** on 4-bit binary inputs.

---

## 📌 Features

The ALU supports the following operations:

### 🔹 Logical Operations
- ✅ AND
- ✅ OR
- ✅ NOT
- ✅ XOR

### 🔹 Arithmetic Operations
- ✅ 4-bit Addition (Parallel Adder)
- ✅ Full Adder chain (bit-by-bit)
- ✅ Addition/Subtraction (using control logic)

---

## 🧠 Circuit Overview

The design is divided into two main parts:

### 🔸 1. Arithmetic Unit
- Built using **4 Full Adders**
- Performs:
  - Addition
  - Subtraction (by inverting B and using carry-in logic)
- Uses **multiplexers (MUX)** to control operations

---

### 🔸 2. Logical Unit
- Implements basic logic gates:
  - AND
  - OR
  - NOT
  - XOR
- Each bit (A0–A3, B0–B3) is processed individually
- Outputs are selected using multiplexers

---

### 🔸 3. Output Selection
- A **final multiplexer (MUX)** selects between:
  - Arithmetic Output
  - Logical Output
- Controlled by selection lines `S1` and `S0`

---

## 🎛️ Inputs and Outputs

### Inputs
- `A[3:0]` → 4-bit input
- `B[3:0]` → 4-bit input
- `S1 S0` → Control signals
- `Cin` → Carry input (for arithmetic operations)

### Outputs
- `D[3:0]` → Result (output)
- `Cout` → Carry out (from arithmetic unit)

---

## ⚙️ Operation Control Table

| S1 | S0 | Operation        |
|----|----|------------------|
| 0  | 0  | AND              |
| 0  | 1  | OR               |
| 1  | 0  | XOR              |
| 1  | 1  | ADD / SUBTRACT   |

> ⚠️ Note: Subtraction is performed using 2’s complement (invert B + carry-in = 1)

🔹 ✅ ARITHMETIC OPERATION TABLE (ALU)

S1 S0 | Cin | Operation        | Description
------|-----|------------------|----------------------------
 1   1 |  0  | A + B           | Normal Addition
 1   1 |  1  | A + B + 1       | Addition with Carry
 1   0 |  1  | A - B           | Subtraction (2's complement)
 1   0 |  0  | A - B - 1       | Subtraction with Borrow

🔹 ✅ FULL ADDER (Core Arithmetic Unit)
A B Cin | Sum Cout
--------|---------
0 0  0  |  0   0
0 0  1  |  1   0
0 1  0  |  1   0
0 1  1  |  0   1
1 0  0  |  1   0
1 0  1  |  0   1
1 1  0  |  0   1
1 1  1  |  1   1

🔹 ✅ 4-BIT ADDITION (Parallel Adder Example)
   A = 1010
 + B = 0101
-----------
Result = 1111
Cout   = 0

🔹 ✅ 4-BIT SUBTRACTION (Using 2’s Complement)
   A = 1001
 - B = 0011
-----------
Result = 0110

---

## 🧪 Example Operations

### ✅ AND Operation
 A = 1100 B = 1010 Output = 1000

 
### ✅ Addition
A = 0101 B = 0011 Output = 1000

### ✅ Subtraction
A = 0110 B = 0011 Output = 0011


---

## 🛠️ Tools Used
- Logisim (Version 2.7.1)
- Digital Logic Design Concepts

---

## 🚧 Limitations
The following features are NOT implemented:
- ❌ Shift operations (Left/Right Shift)
- ❌ Rotate operations
- ❌ Multiplication

---

## 🚀 Future Improvements
- Add Barrel Shifter (Shift & Rotate)
- Implement Multiplier Unit
- Expand to 8-bit ALU

---

## 👤 Author
- Name: Shawon Gazi

---

## ⭐ Conclusion
This project demonstrates a basic but functional implementation of a **4-bit ALU**, combining arithmetic and logic operations using fundamental digital components like gates, adders, and multiplexers.

---
