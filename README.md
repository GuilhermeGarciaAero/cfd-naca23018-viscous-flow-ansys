# ✈️ CFD Analysis — NACA 23018 Airfoil (Viscous Flow)

Computational aerodynamic analysis of the NACA 23018 airfoil under
viscous incompressible flow using ANSYS Fluent 2022 R1, with results
validated against Xfoil (thin airfoil theory) and experimental data.

> 📚 Aerodynamics — University of Brasília (UnB), 2022

---

## 📌 Overview

This study performs a full CFD analysis of the NACA 23018 airfoil,
computing lift, drag, and moment coefficients across multiple angles
of attack — from zero-lift to stall — using the k-ε turbulence model.
Results are compared with theoretical (Xfoil) and panel method (Work 2)
references.

---

## 📐 Geometry & Domain

| Parameter         | Value        |
|-------------------|--------------|
| Airfoil           | NACA 23018   |
| Chord Length (c)  | 0.6096 m     |
| Flow Velocity     | 46.8 m/s     |
| Flow Type         | Viscous / Incompressible |
| Domain Type       | C-type domain |

**Angles of attack simulated:**

| Symbol            | Value  | Description              |
|-------------------|--------|--------------------------|
| α (zero-lift)     | -1.2°  | Zero lift angle          |
| α₀                | 0°     | Zero incidence           |
| α_stall/3         | 6°     | Pre-stall regime         |
| α_2stall/3        | 9.75°  | Near-stall regime        |
| α_stall           | 16°    | Stall angle              |

---

## 🧮 Mathematical Formulation

Thin airfoil theory (Kutta-Joukowski & Kelvin theorems):

$$C_l = 2\pi\left(\alpha + \frac{1}{\pi}\int_0^{\pi}
\frac{dz}{dx}(\cos\theta - 1)d\theta\right)$$

$$\frac{dC_l}{d\alpha} = 2\pi$$

**Turbulence model: k-ε (Launder & Spalding, 1974)**

$$\mu_t = \rho C_\mu \frac{k^2}{\varepsilon}, \quad C_\mu = 0.09$$

---

## 🖥️ Mesh

| Property         | Value          |
|------------------|----------------|
| Solver           | ANSYS Fluent   |
| Element Type     | Linear         |
| Element Size     | 2.1553 m (domain) |
| Total Nodes      | 343,035        |
| Total Elements   | 342,000        |

- Structured C-type mesh with refinement near the airfoil surface
- Inflation layers applied for accurate boundary layer resolution
- y⁺ monitored for all angles of attack

---

## 📊 Results

### Lift Coefficient (Cl)

| α      | Xfoil (Ref) | Numerical (CFD) |
|--------|-------------|-----------------|
| -1.2°  | 0           | -0.0151         |
| 0°     | 0.1         | 0.0506          |
| 6°     | 0.72        | 0.4847          |
| 9.75°  | 1.15        | 1.0370          |
| 16°    | 1.6         | 1.5146          |

### Drag Coefficient (Cd)

| α      | Xfoil (Ref) | Numerical (CFD) |
|--------|-------------|-----------------|
| -1.2°  | 0.007       | 0.0125          |
| 0°     | 0.0072      | 0.0122          |
| 6°     | 0.0079      | 0.0320          |
| 9.75°  | 0.0102      | 0.1306          |
| 16°    | 0.02        | 0.7149          |

### Moment Coefficient (Cm)

| α      | Xfoil (Ref) | Numerical (CFD) |
|--------|-------------|-----------------|
| -1.2°  | -0.002      | 0.0028          |
| 0°     | -0.0025     | 0.001           |
| 6°     | 0           | -0.0221         |
| 9.75°  | 0.002       | -0.0042         |
| 16°    | 0.005       | 0.0037          |

### Center of Pressure (Xcp/c)

| α      | Xfoil (Ref) | Numerical (CFD) |
|--------|-------------|-----------------|
| -1.2°  | 0.25        | 0.2684          |
| 0°     | 0.275       | 0.2290          |
| 6°     | 0.25        | 0.2545          |
| 9.75°  | 0.2482      | 0.2540          |
| 16°    | 0.2468      | 0.2475          |

---

## 🔑 Key Observations

- **Cl** results show good agreement at high angles of attack (α ≥ 9.75°),
  with larger deviations at low angles due to mesh resolution limitations
  in the student version
- **Cd** diverges significantly near stall (α = 16°), consistent with
  the high turbulence and flow separation expected in viscous simulations
- **Cm** and **Xcp** values remain close to the theoretical quarter-chord
  location (~0.25c), confirming aerodynamic center behavior
- Discrepancies are attributed to mesh refinement limitations of the
  ANSYS Student license and computational hardware constraints
- Simulations required between 3,000 and 7,000 iterations per case,
  with run times between 2 and 5 hours each

---
---

## 🛠️ Tools Used

![ANSYS](https://img.shields.io/badge/ANSYS-Fluent_2022_R1-yellow?style=flat)
![CFD](https://img.shields.io/badge/CFD-Viscous_Flow-blue?style=flat)
![Turbulence](https://img.shields.io/badge/Turbulence-k--epsilon-orange?style=flat)
![Validation](https://img.shields.io/badge/Validation-Xfoil-green?style=flat)

---

## 📚 References

- Anderson, J. *Fundamentals of Aerodynamics*, McGraw-Hill, 5th ed., 2010
- Abbott, I.; Von Doenhoff, A. *Summary of Airfoil Data*, NACA Report 824, 1945
- Launder, B.E.; Spalding, D.B. *The numerical computation of turbulent flows*, 1974

---

## 👨‍💻 Author

**Guilherme Garcia Guedes**
Aerospace Engineer — UnB (2024)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Guilherme_Garcia-blue?style=flat&logo=linkedin)](https://www.linkedin.com/in/guilherme-garcia-guedes-aeroespacial/)
