# Evolutionary Branching of Social Preferences in a Public Good Provision Game

**Guillaume Cheikbossian** (CEE-M, Université de Montpellier) and **Jorge Peña** (Toulouse School of Economics)

This repository contains the [Pluto.jl](https://plutojl.org/) notebook that produces the figures in the paper:

> G. Cheikbossian and J. Peña, "Evolutionary branching of social preferences in a public good provision game," *working paper*, 2026.

## Files

- [`notebook_preference_branching_figures.jl`](notebook_preference_branching_figures.jl) implements individual-based Wright-Fisher simulations of the adaptive dynamics of the other-regarding preference trait λ and produces Figures 1 and 2 of the paper.
- [`figure1_samples.csv`](figure1_samples.csv) and [`figure2_samples.csv`](figure2_samples.csv) contain the simulated individuals plotted in Figures 1 and 2: 100 individuals sampled every 100 generations, with columns `run`, `generation` and `trait` (λ).

### What the notebook does

- Implements the CES public goods game and the interior Nash equilibrium payoff (Proposition 1).
- Computes the singular preference trait λ\* (Proposition 2) and the branching threshold σ̄(α, β, n) (Lemma 1).
- Runs Wright-Fisher simulations for a finite population of N = 5,000 individuals over T = 20,000 generations.
- **Figure 1**: varies the complementarity parameter σ ∈ {0.7, 0.3, 0.1} for group size n = 2, illustrating convergence to benevolence, convergence to malevolence, and evolutionary branching.
- **Figure 2**: fixes σ = 0.16 and compares group sizes n = 2 and n = 4, illustrating how larger groups suppress branching.

## Reproducing the figures

By default (`rerun_simulations = false` in the parameter cell), the notebook redraws Figures 1 and 2 from the two CSV files, which takes a few seconds.

Setting `rerun_simulations = true` re-runs the simulations (random seed 123, about 1.5 minutes) and overwrites the CSV files. With the package versions recorded in the notebook, this reproduces the published samples exactly (tested with Julia 1.13). Other package versions may give a different random realization of the same process.

## Running the notebook

1. Install [Julia](https://julialang.org/downloads/). The notebook's package environment was recorded with Julia 1.11.7. With Julia 1.12 or later, loading the packages may print an error about `MbedTLS_jll`; it does not affect the results.
2. Install Pluto:
   ```julia
   using Pkg; Pkg.add("Pluto")
   ```
3. Launch the notebook:
   ```julia
   using Pluto; Pluto.run()
   ```
4. Open `notebook_preference_branching_figures.jl` from the Pluto interface. All package dependencies are managed automatically via the notebook's built-in environment. The figures are saved as PDF files next to the notebook.

## Dependencies

The notebook uses the following Julia packages (all installed automatically by Pluto):

- `Distributions`, `Random`, `StatsBase` — simulation
- `StatsPlots`, `LaTeXStrings` — plotting
- `DataFrames` — snapshot storage

## License

Code released under the [MIT License](LICENSE).
