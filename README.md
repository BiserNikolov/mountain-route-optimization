# 🏔️ Mountain Route Optimization: Graph Theory meets Elevation

> **Final Exam Project** | Mathematics & Python  
> **Deadline:** 17 March 2026

---

## 📌 Project Overview

Finding the optimal mountain route is not just about the shortest distance.
Elevation gain plays a crucial role in how difficult and time-consuming a trail truly is.

This project combines **Graph Theory** and **Naismith's Rule** to model, analyze,
and compare different definitions of "optimal" on two real Bulgarian mountain GPS tracks.

**Key Question:**
> *Is the shortest path always the best path in the mountains?*

---

## 🎯 Objectives

- Model real GPX mountain tracks as weighted graphs
- Implement **Dijkstra's Algorithm** from scratch
- Apply **Naismith's Rule** to estimate realistic hiking time
- Compare three versions of "optimal": shortest distance, least elevation, fastest time
- Visualize results on interactive maps and elevation profiles

---

## 🗻 Data

This project uses two real GPS tracks from Bulgarian mountains:

| Track | Location | Distance | Elevation Gain | Max Elevation | Naismith Time |
|-------|----------|----------|----------------|---------------|---------------|
| Rila Monastery → Seven Lakes | Rila Mountains | 37.47 km | 2947 m | 2735 m | ~12.4 hours |
| Vihren Peak | Pirin Mountains | 8.87 km | 1053 m | 2923 m | ~3.5 hours |

> GPX files are located in the `/data` folder.

---

## 📐 Mathematical Background

### Graph Theory
Each GPS point is a **node**. Connections between consecutive points are **edges**,
weighted by a cost function that accounts for both distance and elevation.

```
G = (V, E, w)
```
- `V` = set of GPS points (nodes)
- `E` = connections between consecutive points (edges)
- `w` = weight function (distance / elevation / Naismith time)

### Naismith's Rule
A classic formula for estimating hiking time, developed by Scottish mountaineer William Naismith (1892):

```
T = d/5 + h/600
```

Where:
- `T` = estimated time (hours)
- `d` = horizontal distance (km)
- `h` = total elevation gain (m)

Applied to our tracks:
- **Rila** (37.47 km, +2947 m): T = 37.47/5 + 2947/600 = **12.4 hours**
- **Vihren** (8.87 km, +1053 m): T = 8.87/5 + 1053/600 = **3.5 hours**

### Dijkstra's Algorithm
Used to find the minimum-cost path between two points in the graph,
depending on which cost function is chosen (distance / elevation / time).

---

## 🛠️ Tech Stack

| Tool | Purpose |
|------|---------|
| `Python 3.x` | Main language |
| `xml.etree` | Parsing GPX files (built-in) |
| `networkx` | Graph structure and comparison |
| `numpy` | Numerical computations |
| `matplotlib` | Elevation profiles and charts |
| `folium` | Interactive map visualization |

---

## 📁 Repository Structure

```
mountain-route-optimization/
│
├── data/
│   ├── rila-monastery-seven-lakes.gpx
│   └── vihren-pirin.gpx
│
├── notebooks/
│   └── mountain_route_optimization.ipynb
│
├── README.md
└── requirements.txt
```

---

## 📊 Results Preview

*(To be updated as the project progresses)*

- Which route is shortest by pure distance?
- Which route is fastest according to Naismith's Rule?
- Which route minimizes total elevation gain?
- How do the two Bulgarian mountain tracks compare?

---

## ⚠️ Limitations

- Naismith's Rule does not account for terrain type, fatigue, or weather
- GPS accuracy depends on the recording device
- The graph model simplifies continuous terrain into discrete points
- Descents are not penalized in the basic Naismith formula

---

## 📅 Project Timeline

| Date | Milestone |
|------|-----------|
| 01 Mar | Initial setup — repo + README |
| 03 Mar | Introduction & problem formulation |
| 05 Mar | Mathematical background (Graph Theory + Naismith) |
| 07 Mar | GPX data loading & graph construction |
| 09 Mar | Dijkstra's algorithm implementation |
| 11 Mar | Route comparison (distance vs elevation vs time) |
| 13 Mar | Visualizations (maps + elevation profiles) |
| 15 Mar | Conclusion & limitations |
| 16 Mar | Final review & polish |
| 17 Mar | Submission |

---

## 📚 References

- Naismith, W. (1892). *Excursions*. Scottish Mountaineering Club Journal.
- Dijkstra, E.W. (1959). *A note on two problems in connexion with graphs*. Numerische Mathematik.
- OpenStreetMap contributors — map data

