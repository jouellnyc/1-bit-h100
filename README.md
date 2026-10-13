# 1-bit-h100

> *Enterprise-grade 0.000000000001 AI accelerator. Zero wattage, two transistors, pure unadulterated silicon flexing.*

---

## Part I: The Genesis Core (Discrete 1-Bit Latch)

Welcome to **1-bit-h100**, the world's most aggressively over-engineered, severely under-budgeted compute unit. While Silicon Valley burns billions on multi-node Blackwell clusters and H100 arrays, true innovation happens on a modest breadboard in Brooklyn with two humble BJTs and a handful of resistors.

This repository documents the absolute ground floor of our architecture: a classic cross-coupled bistable multivibrator (flip-flop). It is a 1-bit memory cell that holds its state using pure positive feedback.

---

### How It Works & What We Can Simulate

* **The Architecture:** Two cross-coupled transistors ($Q1$ and $Q2$) act as opposing switches. When one transistor turns completely **ON**, it pulls its collector low, starving the opposing transistor's base of current and forcing it **OFF**.
* **The State Retention:** This cross-coupling creates a permanent latch loop. It remembers its state indefinitely as long as power is applied—no clock signal required.
* **Simulation / Manual Execution:**
* **The "Sliders" (Manual Triggers):** Instead of software sliders or register writes, input state changes are handled via physical touch or a jumper wire. Tapping the base of $Q2$ to ground forces a state flip, lighting the LED indicator. Tapping $Q1$'s base clears it back to zero.



---

### Technical Schematic (For Engineers)

```text
       +VCC (Red Rail, +)
         |
        [R1] (1k)  [R2] (1k)
         |          |
         +----------+--------+ (Collector Q1 / Q2)
         |          |        |
         |         [R3]     [R4] (10k feedback)
         |          |        |
        [Q1]        +--------+ (Base Q2)
        Collector/Base/Emitter
         |
        GND (Blue Rail, - via Emitters)

```

* **Components:**
* $Q1, Q2$: NPN Transistors (e.g., 2N3904)
* $R1, R2$: $1\text{ k}\Omega$ collector load resistors
* $R3, R4$: $10\text{ k}\Omega$ cross-coupling feedback resistors
* Power Supply: Standard 5V DC breadboard rail



---

### Non-Engineer Quick-Start Guide (Try It at Home!)

Ever wondered how computers actually "remember" things like a 1 or a 0? You don't need a degree in electrical engineering to build one. Here is how to think about it in plain English:

1. **The Teeter-Totter Analogy:** Imagine two light switches wired together so that whenever one switch is flipped **ON**, it forces the other one **OFF**. They fight each other, but once one wins, it locks in that position.
2. **The Push-Button / Jumper "Slider":**
* Take a loose wire and gently touch it from the ground rail to the control pin (base) of one transistor.
* Boom—the circuit snaps into a new state, turning an LED on and *keeping* it on even after you let go of the wire.
* Touch the other side, and it clears out.


3. **Why It Matters:** You just built a literal "memory bit"—the exact same fundamental building block that stores data inside modern computer RAM and CPU caches, stripped down to its bare, beautiful, physical essence.

---

### Up Next: Part II

*Stay tuned for the upcoming hardware expansion...*

