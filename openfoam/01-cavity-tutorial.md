# OpenFOAM Tutorial 01: Lid-Driven Cavity Flow

*By Rehan Hidayat | Mechanical Engineering Graduate*
*Environment: OpenFOAM v2312 on WSL2 (Windows)*

---

## What is This Case?

The lid-driven cavity is the "Hello World" of CFD.
It simulates fluid inside a square box where the top wall moves
horizontally — creating a rotating vortex inside the cavity.

It is the standard benchmark case used to:
- Verify that a CFD solver is working correctly
- Learn the basic OpenFOAM workflow
- Understand boundary conditions and solver setup

---

## Case Setup

| Parameter | Value |
|-----------|-------|
| Geometry | 0.1m × 0.1m × 0.01m square cavity |
| Mesh | 20 × 20 structured grid (400 cells) |
| Solver | icoFoam (incompressible, laminar) |
| Simulation time | 0.5 seconds |
| Time step | 0.005 seconds |

---

## OpenFOAM Case Structure

Every OpenFOAM case follows this exact structure:
cavity/
├── 0/                  # Initial & boundary conditions
│   ├── U               # Velocity field
│   └── p               # Pressure field
├── constant/           # Physical properties & mesh
│   └── transportProperties  # Fluid viscosity
└── system/             # Simulation controls
├── blockMeshDict   # Mesh generation instructions
├── controlDict     # Time control & output settings
├── fvSchemes       # Numerical discretization schemes
└── fvSolution      # Linear solver settings

---

## Step-by-Step Workflow

### Step 1 — Copy the Tutorial Case

```bash
mkdir -p ~/openfoam-learning
cp -r $FOAM_TUTORIALS/incompressible/icoFoam/cavity/cavity ~/openfoam-learning/
cd ~/openfoam-learning/cavity
```

### Step 2 — Generate the Mesh

```bash
blockMesh
```

**What this does:**
- Reads `system/blockMeshDict`
- Creates a structured 20×20 mesh
- Defines 3 boundary patches: `movingWall`, `fixedWalls`, `frontAndBack`

**Output confirms:**
- 400 cells, 882 points, 1640 faces generated successfully

### Step 3 — Run the Simulation

```bash
icoFoam
```

**What this does:**
- Reads initial conditions from `0/`
- Solves Navier-Stokes equations at each time step
- Writes results to folders `0.1`, `0.2`, `0.3`, `0.4`, `0.5`

**Key output to watch:**
- Residuals decreasing → solution converging ✅
- Courant Number below 1 → simulation stable ✅

### Step 4 — Visualize Results

```bash
touch cavity.foam
```

Then open `cavity.foam` in ParaView:
1. File → Open → navigate to cavity folder
2. Click Apply
3. Change color field from `Solid Color` to `U` (velocity)
4. Press Play ▶️ to animate

---

## Understanding the Results

**Velocity field (U):**
- High velocity near the moving top wall
- A large primary vortex forms in the center of the cavity
- Smaller secondary vortices appear in the bottom corners

**Residuals:**
- Started high at Time = 0.005 (Initial residual = 1)
- Decreased consistently toward zero
- Confirms the solver converged to a stable solution

**Courant Number:**
- Stayed below 1 throughout (max ~0.852)
- This confirms the time step was small enough for numerical stability

---

## Key Concepts Learned

| Concept | Description |
|---------|-------------|
| Case structure | Every OpenFOAM case has `0/`, `constant/`, `system/` |
| blockMesh | Tool to generate structured meshes from dictionary |
| icoFoam | Solver for incompressible laminar flow |
| Residuals | Measure of how well equations are satisfied |
| Courant Number | Measure of numerical stability |
| ParaView | Post-processing tool to visualize CFD results |

---

## What's Next?

- Refine the mesh to 40×40 and compare results
- Change the moving wall velocity and observe vortex behavior
- Try the `cavity/cavityFine` tutorial for higher resolution

---

*Last updated: May 2026*
*Part of my [CFD Fundamentals](../README.md) documentation*
