# London Underground Network Visualization

A Python-based data visualization and network graph analysis tool representing key London Underground tube lines, station connections, and route distances. Built using NetworkX for graph structure modelling and Matplotlib for custom rendering.

---

## Project Overview

This project models selected London Underground routes as a weighted, undirected graph. Each station is represented as a network node containing metadata regarding its corresponding line, while edges model physical track connections labeled with distance intervals in miles.

### Key Features
* Graph Modeling: Custom node-edge network representation built with NetworkX.
* Line-Specific Styling: Visual distinction of tube lines using official color schemes (Piccadilly, Central, Northern, and Jubilee lines).
* Distance Metadata: Edge labels providing distance metrics between adjacent stations.
* Custom Layout: Coordinate positioning designed to mirror real-world spatial layouts while optimizing readability.

---

## Key Improvements & Refactoring

* Accuracy: Fixed station typos (e.g., Northan -> Northern, Kenningtion -> Kennington, Westminister -> Westminster) and standardized duplicate station nodes.
* Visual Clarity: Eliminated label collisions and text overlap by introducing subtle background patches (bbox) and structured vertical offsets.
* Layout Optimization: Repositioned the legend to the top-left corner and expanded axis limits to ensure all nodes and labels remain fully visible.

---

## Tech Stack

* Language: Python 3.x
* Graph Network Library: NetworkX
* Data Visualization: Matplotlib

---

## Getting Started

### Prerequisites

Ensure you have Python installed, then install the required dependencies:

```bash
pip install networkx matplotlib
