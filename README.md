# 🤖 Autobot Battle Game

A simple turn-based terminal game written in C++ featuring a combat simulation between **Optimus Prime** and **Megatron**.

---

## 🧠 Overview

This project simulates an automatic battle between two bots:

- **Optimus** and **Megatron** are subclasses of a common base class `AutoBot`.
- Each has a distinct set of moves with predefined `damage` and `accuracy`.
- The battle proceeds in alternating turns until one bot's health drops to zero.

---

## 🧱 Code Structure

### `AutoBot` (Base Class)
- Fields:
  - `int health`
  - `double accuracy`
  - `int damage`
  - `static bool megatron_move` – toggles turn
- Methods:
  - `virtual void attack()` – overridden by children
  - `void choose_attack_move()` – random move selection and application

---

### `Optimus` (Derived Class)
- Moves:
  - `ion_rifle` → 6 dmg, 1.0 acc
  - `Energon_swords` → 12 dmg, 0.8 acc
  - `shoulder_canon` → 45 dmg, 0.25 acc
- Implements `attack()` by selecting a random move via `choose_attack_move()`

---

### `Megatron` (Derived Class)
- Moves:
  - `Fusion_cannon` → 9 dmg, 0.9 acc
  - `Fusion_sword` → 18 dmg, 0.7 acc
  - `Tank_mode` → 60 dmg, 0.15 acc
- Also uses `choose_attack_move()` for randomized attack logic

---

### `main.cpp`
- Initializes both bots
- Alternates turns using `megatron_move` flag
- Deducts health based on `damage` from successful attacks
- Outputs game state each turn until one bot wins

---

## 🐳 Docker

Docker image available:  
**[youssef40/autobot-game](https://hub.docker.com/repository/docker/youssef40/autobot-game/general)**

---

## 📁 Files

```
autobot-game/
├── main.cpp         # Contains all class definitions and game loop
├── Dockerfile       # For containerized execution
└── README.md        # Project description and structure
```

---

## 🎮 Example Output

```
Turn 1
Megatron attacked with Fusion_cannon !
Health of Optimus     : 91
Health of Megatron    : 100
-------------------------------------
Turn 2
Optimus missed Energon_swords !
Health of Optimus     : 91
Health of Megatron    : 100
...
OPTIMUS WONNN!!
```

