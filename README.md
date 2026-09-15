# Verification notebooks

Symbolic and numerical checks for the bachelor's thesis *El formalismo ODM en sistemas híbridos clásico-cuánticos* (Santiago Puyol Miano, director Jesús Clemente Gallardo, Universidad de Zaragoza, 2026). The appendix «Cuadernos de SageMath para verificar» of the thesis describes each notebook.

Each notebook runs from top to bottom without manual input and stops with an `AssertionError` if an identity fails. The stored outputs come from a complete run.

| Notebook | Kernel | What it checks |
|---|---|---|
| `C1_ehrenfest_to_pdes.ipynb` | SageMath | the chain rule for commutators; the quantum Hamiltonian and the Liouvillian obtained from the commutator equations; the bracket {x_q, p_q} = ħκ of the κ-identification |
| `C2_symplectic_rotation.ipynb` | SageMath | ξ ∈ sp(4,ℝ), g_α = exp(αξ) and g_αᵀ J g_α = J; the pullback of Θ along g_α; why only the endpoints of α(κ) are fixed; which of x̂_q, p̂_q act by multiplication |
| `C3_polarization_curve.ipynb` | SageMath | the curve P_α = g_α · P_0 is Lagrangian for every α, ends at the von Neumann polarization and tends to P_0 as α → 0; figure of the curve |
| `C4_oscillator_family.ipynb` | SageMath | Ĥ_qc(κ) = ħL̂ for every κ when U is quadratic; figure of the motion along the energy ellipse |
| `C5_metaplectic_intertwiner.ipynb` | Python | the metaplectic operator U(g_α) at intermediate α: equivariance, unitarity, group law, Mehler kernel at α = π/2 |
| `C6_potential_theta_alpha.ipynb` | Python | θ_α = (g_α⁻¹)*Θ = Θ + du_α vanishes on the leaves of P_α for every α; conjugation by U(g_α) in a Fock basis |
| `C7_kappa_limit_on_solutions.ipynb` | Python | the limit κ → 0 in the variables (x, λ_p): principal part, Taylor expansion and bound of the remainder, convergence of solutions at rate κ² |

## Notation

Ξ = T*ℝ² with coordinates (x, p, λ_x, λ_p), symplectic form Ω = dx∧dλ_x + dp∧dλ_p and potential Θ = λ_x dx + λ_p dp. The auxiliary operators satisfy [x̂, λ̂_x] = [p̂, λ̂_p] = i. κ ∈ [0, 1] is the control parameter of ODM (κ = 0 classical, κ = 1 quantum), and α ∈ [0, π/2] is the rotation angle of the symplectic transformation g_α, with α(κ) = πκ/2. The κ-identification is x̂_q = x̂ − (ħκ/2) λ̂_p, p̂_q = p̂ + (ħκ/2) λ̂_x.

## Running

C1–C4 need SageMath (tested with 10.8). C5–C7 need Python 3 with sympy and numpy (tested with sympy 1.14 and numpy 2.4). To run a notebook non-interactively:

```bash
jupyter nbconvert --to notebook --execute --inplace C1_ehrenfest_to_pdes.ipynb
```

C3 and C4 write their figures to `figures/`.
