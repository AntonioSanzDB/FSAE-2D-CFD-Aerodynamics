2D CFD Aerodynamic Analysis: Selig S1223 FSAE Rear Wing

Author: [Antonio Sanz]  
Date: March 2026  
Software: ANSYS Fluent, ANSYS DesignModeler, ANSYS Meshing  

## Project Objective
The objective of this project is to validate the aerodynamic force generation of a highly-cambered Selig S1223 airfoil, a common profile used in Formula SAE for maximum downforce. The simulation was conducted at a typical FSAE cornering speed of 15 m/s to analyze pressure distribution, flow separation, and the resulting Lift-to-Drag (L/D) ratio.

## Methodology & Setup
The computational domain was constructed to mimic a virtual wind tunnel, ensuring boundary walls were sufficiently far from the airfoil to prevent artificial flow constriction.

* **Airfoil Profile:** Selig S1223
* **Angle of Attack (AoA):** 15° (Inverted to generate downforce)
* **Solver:** Steady-State, Pressure-Based
* **Turbulence Model:** $k-\omega \text{ SST}$ (Selected for accurate boundary layer and flow separation prediction)
* **Inlet Velocity:** 15 m/s (~54 km/h)
* **Fluid:** Air (Standard Sea Level)

### Meshing Strategy
A quad-dominant mesh was generated. Edge sizing was applied to the airfoil geometry to capture the highly-curved leading and trailing edges. *Note: Due to local hardware constraints for this baseline pipeline validation, a coarse global mesh was utilized. Future iterations would include 10-15 inflation layers to fully capture boundary layer friction.*

![Mesh Setup]([meshFSAE.jpeg])

---

## 📊 Results & Aerodynamic Data

The simulation ran for 47 iterations before reaching successful convergence (residuals dropped below the 1e-3 threshold). 

### 1. Force Coefficients
The mathematical console output yielded the following coefficients, confirming massive downforce generation typical of an FSAE rear wing architecture:

* **Coefficient of Lift ($C_l$):** -1.497
* **Coefficient of Drag ($C_d$):** 0.215
* **Lift-to-Drag Ratio (L/D):** ~6.96

![Convergence Residuals]([Insert your residuals image name here, e.g., residuals.png])

### 2. Static Pressure Contour
The pressure contour clearly illustrates a high-pressure stagnation point at the leading edge and a massive high-pressure zone on the upper surface pushing downward. Conversely, the lower surface exhibits a strong low-pressure (suction) zone, validating the $C_l$ output.

![Static Pressure]([Insert your pressure contour image name here, e.g., pressure.png])

### 3. Velocity Magnitude Contour
The velocity contour demonstrates Bernoulli's principle, with localized flow acceleration under the suction surface of the wing. A visible low-velocity wake is also present trailing from the sharp edge, directly correlating to the calculated drag coefficient.

![Velocity Magnitude]([Insert your velocity contour image name here, e.g., velocity.png])

---

## 🏁 Conclusion
This 2D analysis successfully validates the ANSYS Fluent CFD pipeline for motorsport applications. The Selig S1223, when inverted at a 15° AoA, operates as a highly efficient downforce generator, yielding a theoretical L/D ratio of nearly 7:1 at standard FSAE cornering speeds.
