# 💻 Netrunner: Breach Protocol - Grid Navigation Sim

A strategic puzzle game where you play as a hacker infiltrating a high-security memory grid. You must navigate your avatar (P) to the system core (C) while avoiding static firewalls (#). Every move consumes a CPU cycle; if your cycles hit zero before you reach the core, the connection is severed and the breach fails.

This project focuses on teaching:
* **2D Coordinate Validation:** Using boundary checks to keep players within a defined $(5 \times 5)$ matrix.
* **Collision Detection:** Comparing player coordinates against a list of blocked "Wall" coordinates.
* **Resource Depletion Logic:** Tracking a "Cost-per-Action" mechanic to create gameplay tension.
* **Nested Loop Rendering:** Drawing a visual representation of a data grid in a 1D terminal environment.

---

## ✨ Features

* **Procedural Hazards:** Every game generates 6 random wall locations, ensuring no two "Breach" attempts are identical.
* **WASD Controls:** Traditional movement mapping converted into $(x, y)$ coordinate shifts.
* **Visual Feedback:** A real-time updating map that displays the player, the goal, and the obstacles.
* **Victory/Loss States:** Unique triggers for reaching the goal or running out of "CPU" resources.

---

## 🚀 How to Run the Game

### 1. Prerequisites
You need **Python 3** installed on your system.

### 2. Setup and Execution
1.  **Save the Code:** Save the script as `breach_protocol.py`.
2.  **Open Terminal:** Navigate to the folder containing the script.
3.  **Run the Script:**
    ```bash
    python breach_protocol.py
    ```

### 3. Gameplay Instructions
1.  **Analyze the Grid:** Identify the path of least resistance to the **[C]** Core.
2.  **Navigate:** Use `W` (up), `A` (left), `S` (down), or `D` (right) to move.
3.  **Watch the Walls:** You cannot pass through **[#]** blocks; you must go around them.
4.  **Manage CPU:** Each move costs **1 Cycle**. Plan your route to avoid being stranded!



---

## 🧠 Code Structure Highlights

### Collision and Boundary Logic
This is the most critical part of the engine. Before the player actually moves, the code checks if the new destination is (A) inside the 0-4 range and (B) not currently occupied by a wall.

```python
# Check if new_pos is inside the 5x5 grid
if 0 <= new_pos[0] <= 4 and 0 <= new_pos[1] <= 4:
    if new_pos in walls:
        # Block movement
    else:
        # Finalize movement and spend CPU

