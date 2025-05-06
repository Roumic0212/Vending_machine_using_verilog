# Vending Machine – Verilog HDL

This project involves the design and implementation of a **vending machine** using **Verilog HDL**. The vending machine can dispense four different products with varying prices and has the capability to return change when a higher denomination coin is inserted. It accepts only two denominations: **Nickel (5)** and **Dime (10)**.

---

## 🧠 Project Overview

- Developed using a **Finite State Machine (FSM)** model.
- Accepts coin input, dispenses products, and returns change accordingly.
- Fully simulated using a testbench to verify functionality across multiple scenarios.
- Focused on digital design principles and FSM logic using Verilog.

---

## ⚙️ Specifications

### 📥 Inputs:
- `item_number[3:0]`: 4-bit input to select one of the four products.
- `nickel_in`: Indicates insertion of a nickel.
- `dime_in`: Indicates insertion of a dime.
- `clock`: Clock signal for FSM synchronization.
- `reset`: Resets the vending machine to the initial state.

### 📤 Outputs:
- `nickel_out`: Outputs a nickel as change if required.
- `dispense`: Indicates the selected item is ready to be dispensed.

### 🧮 Internal Variables:
- `current_state`: Holds the current state of the FSM.
- `next_state`: Determines the next state based on input.

---

## 🧩 Modules

- `Item_One(...)`: Handles transactions for item 1.
- `Item_Two(...)`: Handles transactions for item 2.
- `Item_Three(...)`: Handles transactions for item 3.
- `Item_Four(...)`: Handles transactions for item 4.
- `VendingMachine(...)`: Top-level module that routes control to the appropriate item module based on user input.

---

## 🚀 How It Works

1. **Select** the desired item using `item_number`.
2. The machine initializes (`S0`) and waits for coin input.
3. Coins are inserted one per clock cycle.
4. Once enough value is inserted:
   - The item is **dispensed**.
   - **Change** is returned if needed.
5. The system **resets** and waits for the next transaction.

### 💡 Example Scenario:
- Select `item_number = 3` (Cost = 25).
- Insert coins in the following order:
  - Nickel → State: `S5`
  - Dime → State: `S15`
  - Nickel → State: `S20`
  - Dime → State: `S30` → Dispense Item + Return Nickel
- Machine resets to `S0`.

---

## 🧪 Testbench

A dedicated testbench simulates various scenarios, including:
- Different coin insertion sequences.
- Selection of all four products.
- Change return scenarios.

---



## 🛠️ Technologies Used

- **Verilog HDL**
- **Finite State Machines (FSM)**
- **ModelSim / GTKWave** (for simulation)
- **Digital Design Principles**

---

## 🔮 Future Scope

- Add a **termination button** to allow users to cancel a transaction and return all inserted coins sequentially.
- Extend support to more coin denominations.
- Implement real-world FPGA-based deployment using Xilinx or Altera boards.

---

## 📦 Run Locally

Follow these steps to simulate the Verilog code on Linux/Mac:

1. Install [Icarus Verilog](http://iverilog.icarus.com/) and [GTKWave](http://gtkwave.sourceforge.net/).

