# Neon Rain City — 3D Cyberpunk Diorama

[![Three.js](https://img.shields.io/badge/Three.js-r160-000000?style=flat-square&logo=three.js)](https://threejs.org/)
[![WebGL](https://img.shields.io/badge/WebGL-2.0-990000?style=flat-square&logo=webgl)](https://www.khronos.org/webgl/)
[![Performance](https://img.shields.io/badge/FPS-60_Stable-00f3ff?style=flat-square)](https://github.com/agouti-ar/neon-rain-city)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg?style=flat-square)](https://opensource.org/licenses/MIT)

A lightweight, real-time 3D isometric diorama built with **pure Three.js** in a single standalone file (`index.html`). Designed with a low-poly / voxel cyberpunk aesthetic inspired by Night City, running at a rock-solid 60 FPS with zero external bundlers or build steps.

[**View Live Demo →**](https://agouti-ar.github.io/neon-rain-city/)

---

<p align="center">
  <img src="preview.gif" alt="Neon Rain City 3D Diorama Demo" width="850"/>
</p>

---

## Overview & Architecture

The goal of this project was to achieve a dense, atmospheric cyberpunk environment while maintaining extreme rendering efficiency on mobile and integrated GPUs without relying on expensive post-processing passes.

### Key Highlights
- **Single-File Zero-Dependency Setup:** Runs directly in any modern browser via ES Modules CDN. No `npm`, `vite`, or compilation required.
- **Optimized PBR Materials:** Tuned `MeshStandardMaterial` (`roughness: 0.12`, `metalness: 0.28`) simulating wet asphalt and reflective lacquer without the 2x render overhead of real-time planar reflectors (`Reflector.js`).
- **Balanced Lighting Scheme:** Dual-tone `HemisphereLight` coupled with carefully positioned local `PointLight` sources to highlight polygonal facets and create specular reflections.
- **Volumetric Illusion without Post-Processing:** Depth is achieved through `THREE.FogExp2` and additive blended cone volumes (`AdditiveBlending`) on drone spotlights instead of full-screen bloom shaders.
- **Procedural Particle Effects:** Rain streaks and animated ripples on wet pavement driven by optimized geometry loops.
- **Procedural Cable Geometry:** Suspended industrial conduits modeled dynamically via `THREE.CatmullRomCurve3`.
- **Cinematic Orbit Camera:** Smooth continuous turntable inspection with damping via `OrbitControls`.

---

## Tech Stack

- **Core Engine:** Three.js (r160)
- **Renderer:** WebGL 2.0
- **Camera Controls:** OrbitControls (ESM)
- **Math & Curves:** CatmullRomCurve3, Vector3 kinematics

---

## Running Locally

Clone the repository and serve it using any lightweight static server:

```bash
git clone https://github.com/agouti-ar/neon-rain-city.git
cd neon-rain-city

# Python 3:
python -m http.server 5173

# Or Node.js:
npx serve .
```
