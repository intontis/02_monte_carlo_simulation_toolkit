# ⚛️ Rutherford Particle Scattering Simulation

Monte Carlo simulation of the famous 1909 Rutherford gold foil experiment,
extended with an inverse scattering problem to identify unknown materials.

## 🔬 Background

In 1909, Geiger and Marsden fired alpha particles at a thin gold foil and 
observed that while most passed straight through, a small fraction bounced 
back at large angles. This was Rutherford's proof that atoms have a dense 
central nucleus — one of the most important discoveries in physics.

This simulation reproduces that experiment computationally using the 
Rutherford scattering formula:

**θ = 2 · arctan(a / b)**

Where:
- θ = scattering angle
- b = impact parameter (how close the particle aims at the nucleus)
- a = Coulomb parameter (depends on charges of both particles)

## 📊 Results

### Forward Problem — Gold Nucleus (Z=79)

![Particle Scattering](results/02_particle_scattering.png)

- 10,000 alpha particles simulated
- ~97% scattered at angles < 10° → most particles miss the nucleus
- < 1% scattered at angles > 90° → rare direct hits

### Inverse Problem — Unknown Material

![Inverse Scattering](results/02_inverse_scattering.png)

Given only the scattering angle distribution of an unknown material,
the simulation back-calculates its atomic number Z using:

**Z_estimated = median(b · tan(θ/2))**

| Material | True Z | Estimated Z | Error |
|---|---|---|---|
| Silver | 47 | 47 | 0 |

## 🧠 Physics Concepts Demonstrated

- **Coulomb scattering** — electromagnetic repulsion between charged particles
- **Impact parameter** — geometric relationship between trajectory and nucleus`
- **Forward problem** — known material → predict scattering distribution
- **Inverse problem** — observed scattering → identify unknown material

## 🌍 Real World Applications

The inverse scattering principle used here is the same mathematical 
foundation behind:
- CT scanning and medical imaging
- X-ray crystallography
- Seismology (determining Earth's interior structure)
- Nuclear material identification

## 🛠️ Tech Stack

- Python 3.11.9
- NumPy
- Matplotlib

## ▶️ How to Run

```bash
pip install numpy matplotlib
```
Open `02_particle_scattering.ipynb` and run all cells in order.

## 👤 Author

Ioannis Ntontis | Physics Graduate | [LinkedIn](https://www.linkedin.com/in/intontis/) | [GitHub](https://github.com/intontis)
