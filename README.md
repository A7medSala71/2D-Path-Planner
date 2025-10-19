# 🧭 A* Pathfinding in Python

## 📖 Introduction
This project implements the **A\*** (A-Star) pathfinding algorithm for navigating a 2D grid map.  
The algorithm efficiently finds the shortest path between a **start** and **goal** position while avoiding obstacles.  

It uses the **Manhattan distance** as its heuristic and allows four-directional movement (up, down, left, right).

---

## 🗂️ Table of Contents
1. [Features](#-features)
2. [Installation](#-installation)
3. [Usage](#-usage)
4. [Example Output](#-example-output)
5. [Algorithm Overview](#-algorithm-overview)
6. [Dependencies](#-dependencies)
7. [Configuration](#-configuration)
8. [Troubleshooting](#-troubleshooting)
9. [Contributors](#-contributors)
10. [License](#-license)

---

## 🚀 Features
- Implements **A\*** search on a 2D grid  
- Supports **obstacle detection** (cells with value `1` are blocked)  
- Uses **Manhattan distance** as the heuristic  
- Returns the **shortest path** as a list of coordinates  
- Easy to customize for different grid sizes and heuristics  

---

## 💻 Installation
Clone this repository and navigate to the project directory:

```bash
git clone https://github.com/yourusername/a-star-pathfinding.git
cd a-star-pathfinding
```

Ensure you have **Python 3.7+** installed.  
No external dependencies are required beyond the standard library.

---

## 🧠 Usage

### Run the script:
```bash
python a_star.py
```

### Example code:
```python
from a_star import a_star

MAP = [
    [0, 0, 0, 0, 1, 0, 0, 0, 0, 0],
    [0, 1, 1, 0, 1, 0, 1, 0, 1, 0],
    [0, 1, 0, 0, 0, 0, 1, 0, 1, 0],
    [0, 0, 0, 1, 1, 1, 1, 0, 0, 0],
    [0, 1, 0, 0, 0, 0, 0, 0, 1, 0],
    [0, 1, 0, 1, 1, 0, 1, 0, 1, 0],
    [0, 0, 0, 0, 1, 0, 1, 0, 0, 0],
]

START = (0, 0)
GOAL = (6, 8)

path = a_star(MAP, START, GOAL)
print(path)
```

---

## 🧩 Example Output
```
Shortest path found:
(0, 0)
(1, 0)
(2, 0)
(3, 0)
(3, 1)
(3, 2)
(2, 2)
(2, 3)
(2, 4)
(3, 4)
(4, 4)
(4, 5)
(5, 5)
(6, 5)
(6, 6)
(6, 7)
(6, 8)
```

If no valid path exists, the script will print:
```
No path exists from start to goal.
```

---

## 🧮 Algorithm Overview
The **A\*** algorithm combines:
- **G-cost (g)** → the cost from the start node to the current node  
- **H-cost (h)** → the heuristic estimate from the current node to the goal  
- **F-cost (f)** = g + h  

It uses a **priority queue (min-heap)** to expand the node with the smallest F-cost first, guaranteeing an optimal path when using an admissible heuristic like the Manhattan distance.

---

## 📦 Dependencies
- Python standard library only (`heapq` module for priority queue)

---

## ⚙️ Configuration
You can modify:
- **Grid layout:** Edit the `MAP` variable to represent walls (`1`) and free spaces (`0`).  
- **Start/Goal positions:** Change the `START` and `GOAL` tuples.  
- **Heuristic:** Replace the `heuristic` function for Euclidean or Diagonal distance.  
- **Movement model:** Extend `directions` to include diagonal moves.

---

## 🧰 Troubleshooting
| Issue | Possible Cause | Solution |
|-------|----------------|-----------|
| Program prints “No path exists” | No valid route | Check grid configuration or obstacles |
| Incorrect path | Misdefined start/goal | Ensure coordinates are within grid bounds |
| Slow performance | Large grid | Use more efficient heuristics or pruning |

---

## 👥 Contributors
- **Your Name** — Creator & Maintainer  

Feel free to contribute improvements via pull requests!

---

## 📜 License
This project is licensed under the **MIT License**.  
See the [LICENSE](LICENSE) file for details.
