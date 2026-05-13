# 🔧 RTOS from Scratch — ARM Cortex-M4

> Build your own Real-Time Operating System on bare-metal ARM hardware, step by step.

---

## 🧰 Target Hardware

| Component | Details |
|-----------|---------|
| **MCU** | STM32F401CCU6 (ARM Cortex-M4) |
| **Dev Board** | BlackPill — WeAct Studio Mini STM32F4x1 |
| **Architecture** | ARMv7-M |

---

## 📚 Required Documentation

Before writing a single line of code, gather the following reference documents:

### 1. ARM Cortex-M4 Generic User Guide
**File:** `DUI0553A_cortex_m4_dgug.pdf`

The architecture-level reference for any Cortex-M4 device. Used to understand core peripherals that are common across all vendors.

- ✅ SysTick timer registers and configuration
- ✅ NVIC (Nested Vectored Interrupt Controller)
- ✅ Exception model and vector table layout

---

### 2. STM32F401CCU6 Reference Manual
**File:** `RM0368.pdf` *(starts with `RM`)*

The definitive guide to every peripheral inside this specific STM32 chip.

- ✅ How to enable peripheral clocks via RCC registers
- ✅ Bit-level configuration for each module (GPIO, TIM, ADC, UART, etc.)
- ✅ Bus architecture and peripheral base addresses

---

### 3. STM32F401CCU6 Datasheet
**File:** `DS9716.pdf` *(starts with `DS`)*

The electrical and physical reference for the chip.

- ✅ Block diagram of the entire microcontroller
- ✅ Which bus each peripheral is connected to (AHB1, APB1, APB2…)
- ✅ Electrical characteristics and timing constraints
- ✅ Memory map and Flash/SRAM demarcations
- ✅ Pin definitions and alternate function table

> **Example workflow:** To enable the ADC — check the *datasheet* to find which bus the ADC is on (e.g. APB2), then jump to the *reference manual* to find the exact RCC register bit that enables it.

---

### 4. BlackPill Board Schematic
**Source:** [WeAct Studio GitHub](https://github.com/WeActStudio/WeActStudio.MiniSTM32F4x1/tree/master)

Schematic and layout files for the BlackPill development board.

- ✅ Onboard components (crystal, USB, button, LED)
- ✅ Pin connections between STM32 and board peripherals
- ✅ Power supply circuitry

---

## 🗺️ Build Roadmap

```
Step 1 — SysTick Timer
  └─ Use DUI0553A to locate SysTick registers
  └─ Configure SysTick for periodic interrupts (e.g. 1 ms tick)

Step 2 — Peripheral Setup
  └─ Use Datasheet  → identify bus for target peripheral
  └─ Use Ref Manual → enable clock & configure registers

... (more steps coming)
```

---

## 📁 Project Structure

```
RTOS_from_Scratch/
├── docs/               # Reference PDFs go here
├── src/
│   ├── startup/        # Vector table, reset handler
│   ├── kernel/         # Scheduler, context switch
│   └── drivers/        # Peripheral drivers
├── include/
└── README.md
```

---

## 🔗 References

- [ARM Cortex-M4 Technical Reference Manual](https://developer.arm.com/documentation/dui0553/latest)
- [STM32F401 Product Page — ST Microelectronics](https://www.st.com/en/microcontrollers-microprocessors/stm32f401cc.html)
- [WeAct Studio BlackPill Repository](https://github.com/WeActStudio/WeActStudio.MiniSTM32F4x1)

---

<p align="center">Built from scratch — no HAL, no shortcuts.</p>
