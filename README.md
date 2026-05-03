# 🚀 UVM-Based Verification of 4-bit Adder

## 📌 Project Overview

This project demonstrates a complete **UVM-based verification environment** for a simple **4-bit combinational adder**.

The goal is to showcase how industry-standard verification is performed using **SystemVerilog and UVM**, including:

- Stimulus generation  
- DUT interaction  
- Monitoring  
- Automated result checking  

Even though the design is simple, the verification approach follows a **scalable and reusable architecture**, similar to what is used in real **ASIC/SoC projects**.

---

## 🧮 Design Description

The Design Under Test (DUT) is a basic adder that:

- Accepts two 4-bit inputs  
- Produces a 5-bit output to handle overflow  

It is a **pure combinational design**, making it ideal for learning **UVM fundamentals without clock complexity**.

---

## 🔌 Interface Concept

An interface is used to group all DUT signals together into a single abstraction.

### ✨ Benefits

- Cleaner connectivity between DUT and testbench  
- Easier scalability for larger designs  
- Support for virtual interfaces in UVM components  

---

## 🏗️ UVM Architecture Overview

The testbench follows a layered UVM architecture:

- **Test** → Controls the overall simulation  
- **Environment (env)** → Top-level container for verification components  
- **Agent** → Encapsulates driver, monitor, and sequencer  
- **Driver** → Drives inputs to the DUT  
- **Monitor** → Observes DUT activity  
- **Scoreboard** → Verifies correctness  

### 📌 Advantages

- Reusability  
- Maintainability  
- Scalability  

---

## 🔄 Verification Flow

The verification process follows a clear data flow:

1. Random input stimulus is generated  
2. Inputs are driven to the DUT  
3. DUT processes the inputs and produces output  
4. Output is monitored and captured  
5. Expected and actual results are compared automatically  

✅ This makes the testbench **fully self-checking**, eliminating manual verification.

---

## 🧩 Component Responsibilities

### 🔹 Transaction
- Represents a single set of input and output values  
- Acts as the **data container** exchanged between components  

---

### 🔹 Generator (Sequence)
- Responsible for creating randomized test scenarios  
- Ensures different combinations of inputs are applied to the DUT  

---

### 🔹 Driver
- Applies the generated inputs to the DUT signals  
- Converts high-level transaction data into signal-level activity  

---

### 🔹 Monitor
- Passively observes DUT inputs and outputs  
- Collects data and forwards it for checking  

---

### 🔹 Scoreboard
- Performs functional verification by comparing:
  - Expected result (calculated internally)  
  - Actual DUT output  

- Determines whether the test:
  - ✅ Passes  
  - ❌ Fails  

---

### 🔹 Agent
- Groups related components (driver, monitor, sequencer)  
- Provides a reusable verification unit  

---

### 🔹 Environment
- Acts as the top-level container  
- Connects all verification components together  

---

### 🔹 Test
- Controls the simulation flow by:
  - Creating the environment  
  - Starting stimulus generation  
  - Managing simulation time using objections  

---

## 🔗 Data Flow Summary

### ▶️ Stimulus Path
**Generator → Driver → DUT**

### ▶️ Observation Path
**DUT → Monitor → Scoreboard**

### ▶️ Final Decision
**Scoreboard determines pass/fail**

---
