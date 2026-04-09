# Evolutionary Branching of Social Preferences in a Public Good Provision Game

**Guillaume Cheikbossian** (CEE-M, Université de Montpellier) and **Jorge Peña** (Toulouse School of Economics)

This repository contains the [Pluto.jl](https://plutojl.org/) notebook that produces the figures in the paper:

> G. Cheikbossian and J. Peña, "Evolutionary branching of social preferences in a public good provision game," *working paper*, 2026.

## Notebook

[`notebook_preference_branching_figures.jl`](notebook_preference_branching_figures.jl) — implements individual-based Wright–Fisher simulations of the adaptive dynamics of the other-regarding preference trait λ, and produces Figures 1 and 2 of the paper.

### What the notebook does

- Implements the CES public goods game and the interior Nash equilibrium payoff (Proposition 1).
- Computes the singular preference trait λ\* (Proposition 2) and the branching threshold σ̄(α, β, n) (Lemma 1).
- Runs Wright–Fisher simulations for a finite population of N = 5,000 individuals over T = 20,000 generations.
- **Figure 1**: varies the complementarity parameter σ ∈ {0.7, 0.3, 0.1} for group size n = 2, illustrating convergence to benevolence, convergence to malevolence, and evolutionary branching.
- **Figure 2**: fixes σ = 0.16 and compares group sizes n = 2 and n = 4, illustrating how larger groups suppress branching.

## Running the notebook

1. Install [Julia](https://julialang.org/downloads/) (version 1.11 or later).
2. Install Pluto:
   ```julia
   using Pkg; Pkg.add("Pluto")
   ```
3. Launch the notebook:
   ```julia
   using Pluto; Pluto.run()
   ```
4. Open `notebook_preference_branching_figures.jl` from the Pluto interface. All package dependencies are managed automatically via the notebook's built-in environment.

## Dependencies

The notebook uses the following Julia packages (all installed automatically by Pluto):

- `Distributions`, `Random`, `StatsBase` — simulation
- `StatsPlots`, `LaTeXStrings` — plotting
- `DataFrames` — snapshot storage

## License

Code released under the [MIT License](LICENSE).
