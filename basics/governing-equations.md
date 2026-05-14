# Governing Equations in CFD

*By Rehan Hidayat | Mechanical Engineering Graduate*

---

## Overview

Governing equations in CFD are mathematical statements of three 
fundamental physical principles:

1. **Conservation of Mass**
2. **Conservation of Momentum** (Newton's Second Law)
3. **Conservation of Energy**

Together, the conservation of mass and conservation of momentum 
equations are commonly referred to as the **Navier-Stokes equations** 
— which describe how fluid properties change over space and time.

![Navier-Stokes Equations](https://www.grc.nasa.gov/www/k-12/airplane/Images/nseqs.gif)
*Source: NASA Glenn Research Center*
> 📎 Reference: [Navier-Stokes Equations — NASA Glenn Research Center](https://www.grc.nasa.gov/www/k-12/airplane/nseqs.html)

---

## 1. Conservation of Mass
*Also known as the Continuity Equation*

**Simple meaning:**
> What goes in must come out — mass cannot randomly appear or disappear.

In fluid flow, this means the amount of fluid entering a system must 
equal the amount leaving it. Mass is always conserved, never created 
or destroyed.

---

## 2. Conservation of Momentum
*Based on Newton's Second Law of Motion*

**Simple meaning:**
> Fluid moves, speeds up, or changes direction only when a force 
> pushes or pulls it.

This equation describes how forces — like pressure, gravity, and 
viscosity — act on a fluid and determine how it flows and accelerates.

---

## 3. Conservation of Energy
*Also known as the Energy Equation*

**Simple meaning:**
> Total energy is always balanced — it cannot be destroyed, 
> only changed from one form to another.

In fluid systems, energy moves between kinetic energy (motion), 
pressure energy, and thermal energy — but the total always remains 
constant.

---

## The Navier-Stokes Equations

The combination of Conservation of Mass and Conservation of Momentum 
forms the **Navier-Stokes equations** — the core mathematical 
foundation of CFD.

These equations govern:
- How velocity changes over space and time
- How pressure distributes through a fluid
- How viscosity affects fluid motion

Almost every CFD simulation — from airflow over a wing to fluid 
through a pipe — is built on solving these equations numerically.

---

## Why This Matters in CFD

CFD software like ANSYS Fluent solves these equations numerically 
across thousands or millions of small cells in a mesh. The result 
is a detailed picture of how fluid behaves throughout the entire 
geometry being studied.

---

*"Understanding these equations is understanding the language 
that fluids speak."*

---

*Last updated: May 2026*
*Part of my [CFD Fundamentals](../README.md) documentation*
