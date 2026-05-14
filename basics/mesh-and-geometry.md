# Mesh and Geometry in CFD

*By Rehan Hidayat | Mechanical Engineering Graduate*

---

## What is a Mesh?

A mesh is a collection of small geometric shapes that divide a 
continuous fluid domain into millions of tiny, separate sub-regions 
called cells or elements.

Think of it like this:
> Imagine painting a detailed portrait by dividing the canvas into 
> a grid of small squares and painting each square individually. 
> The smaller the squares, the more detailed and accurate the result.
> CFD works exactly the same way.

---

## Why Do We Need a Mesh?

The governing equations of fluid dynamics are written as 
**partial differential equations (PDEs)**. Computers cannot solve 
complex differential calculus across a continuous 3D space directly.

The mesh solves this problem by converting those complex PDEs into 
a system of simple **algebraic equations** that a computer can solve 
— cell by cell, across the entire domain.

Without a mesh, CFD simulation is mathematically impossible on 
a computer.

---

## Mesh Quality: Coarse vs Fine

Choosing the right mesh size is one of the most critical decisions 
in any CFD simulation. It directly affects both accuracy and 
computational cost.

| | Coarse Mesh | Fine Mesh |
|---|---|---|
| **Cell Size** | Large | Small |
| **Number of Cells** | Few | Many |
| **Accuracy** | Low | High |
| **Computational Cost** | Cheap | Expensive |
| **Solver Speed** | Fast | Slow |

### ⚠️ Too Coarse
- Results become **inaccurate**
- Important flow features are missed
- The solution does not represent real physics

### ⚠️ Too Fine
- **Numerical errors** accumulate across too many cells
- **Convergence issues** arise — the solver struggles to reach 
  a stable solution
- Simulation can take many hours depending on case complexity
- Both problems can occur simultaneously

### ✅ The Goal: Mesh Independence
The ideal mesh is one where refining it further no longer 
significantly changes the results. This is called a 
**mesh independence study** — a critical validation step 
in any serious CFD work.

---

## Types of Mesh

**Structured Mesh**
- Cells arranged in a regular, organized pattern
- Simple and computationally efficient
- Less flexible for complex geometries

**Unstructured Mesh**
- Cells arranged irregularly
- More flexible for complex geometries like pipes and drainage systems
- More common in real engineering applications

**Hybrid Mesh**
- Combination of structured and unstructured mesh
- Used when different regions of the domain need different approaches

---

## Key Takeaway

> The mesh is the bridge between physical geometry and numerical 
> computation. A good mesh balances accuracy and computational cost 
> — and getting it right is both a science and an engineering skill.

---

*Last updated: May 2026*
*Part of my [CFD Fundamentals](../README.md) documentation*
