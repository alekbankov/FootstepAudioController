# 👣 Terrain-Aware Footstep Audio System for Unity

A modular and extensible **footstep audio system** for Unity that:

- 🎯 Detects terrain texture under the player  
- 🔄 Swaps footstep audio sets dynamically  
- 🎲 Plays randomized, non-repeating footstep clips  
- 📦 Uses ScriptableObjects for clean expansion  
- 🦘 Includes jump and landing sounds  
- ⏱ Supports custom step-cycle timing  

---

## ✨ Features

### ✔ Terrain Recognition  
Uses `TerrainChecker` to read Terrain **alphamap texture data** and determine the dominant terrain layer under the player.

### ✔ Automatic Footstep Swapping  
`FootstepSwapper` automatically replaces the active footstep set when the terrain layer changes — allowing seamless transitions between surfaces.

### ✔ ScriptableObject Audio Sets  
`FootstepCollection` assets allow designers to build new surface types (Grass, Sand, Snow, Wood, etc.) **without modifying code**.

### ✔ Randomized Natural Footsteps  
Avoids repetition by using a non-repeating random selection algorithm:
1. Pick a random index  
2. Play the selected clip  
3. Swap the selected clip with index 0  
4. Ensures the next step won’t repeat the last  

### ✔ Adjustable Step Cycle  
Footsteps are triggered based on **player velocity**, not fixed timers — creating smoother, more natural walking sounds.

---

## 📁 Script Overview

| Script | Role |
|--------|------|
| **FootstepCollection.cs** | ScriptableObject storing surface-specific audio lists |
| **TerrainChecker.cs** | Reads alphamap and returns the dominant terrain type |
| **FootstepSwapper.cs** | Picks and assigns the correct FootstepCollection |
| **PlayerFootsteps.cs** | Handles step timing, randomization, jump & landing sounds |

---

## 🛠 Requirements

- Unity **2021+**  
- A **CharacterController**-based player controller  
- A **Unity Terrain** with painted layers  

---

## 📦 How to Use

1. **Create FootstepCollection assets**  
   - One per terrain layer (Grass, Dirt, Sand, etc.)

2. **Assign audio clips**  
   - Multiple footstep sounds per surface  
   - Optional jump and landing sounds  

3. **Attach components to your player**  
   - `PlayerFootsteps`  
   - `FootstepSwapper`

4. **Populate the terrain footstep array**  
   - Assign each FootstepCollection to its matching terrain layer

You're now ready to walk around your scene with fully terrain-reactive, natural-sounding footsteps.

---
