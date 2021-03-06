# GSoC '17

Code before pondering.
Multipurpose Learning.

## GSoC goals:

- [ ] Refactor ODEqs and SDEqs into DiffEqDiffTools
- [ ] Unit tests for PRs into DiffEqDiffTools
- [ ] Review JuliaDiffEq/DifferentialEquations.jl#159
- [ ] Refactor JuliaDiffEq/OrdinaryDiffEq.jl@8318c0f
* The abstraction of the Shampine Matlab ODE Suite paper is the key goal for project. [Many things spring off from this.](http://people.eecs.berkeley.edu/~wkahan/Math128/ODEsuite.pdf)
- [ ] Read tests and get on implementing ODEs as test cases
### Docs
- Handle Latex stuff in [the DiffEq](http://docs.juliadiffeq.org/stable/types/ode_types.html#Mathematical-Specification-of-an-ODE-Problem-1) docs and elsewhere.
### Pre-GSoC - Community bonding time
- [ ] Know who people are, what the repos and packages are, know them as a user.
- [ ] List 30 packages, people
- [ ] DiffEqVerse
- [ ] [DPSanders awesome class notebooks](https://github.com/dpsanders/FisicaComputacional2017_2)
- [ ] JuliaDiff - know big players, big repos, how to use forwarddiff well.
- [ ] ForwardDiff.jl
- [ ] Calculus.jl
- [ ] FiniteDiff.jl
- [ ] OrdinaryDiffEq.jl
- [ ] StochasticDiffEq.jl
- [ ] NLsolve.jl
- [ ] Roots.jl 
- [ ] Plots.jl
- [ ] Setup up me [own package](http://www.stochasticlifestyle.com/finalizing-julia-package-documentation-testing-coverage-publishing/)
- [ ] Get through [UCIDataScienceInitiative](https://ucidatascienceinitiative.github.io/IntroToJulia)



## Examples to do:

- [ ] Work through Euler (May9 discussion, DiffEq lobby) and Jacobians
- [ ] [UCIDataScienceInitiative](http://ucidatascienceinitiative.github.io/IntroToJulia/) Projects and such
- [ ] [fempoisson example](http://docs.juliadiffeq.org/latest/tutorials/fempoisson_example.html)
- [ ] DevDocs use case and walkthrough

## Stretch goals

- [ ] Complex autodifferentiation for physics - so then it probably can be a straightforward application of ForwardDiff to build those equations from a Hamiltonian
- Euler-Langrange
- he'll need to dig into how the diffeq functions are differenitated which is all about handling closures and that jazz it's the same idea to differentiate H(p,q) so that would be a good exercise then the internals would make a lot more sense.
- [ ] Turbo DiffEqPhysics
- [ ] katthyat qmech
- [ ] shutz and misner
- [ ] wonsheok shin EM
- [ ] add old methods for didactic purposes

## Open problems:

- [ ] Connect well to LSODA

## Other GSoCs:

- [ ] @shivin9 - speed up elliptics PDEs
- [ ] Yannis - FEM
- [ ] Ying Bo - BVP

## Taking care of the little things:

- [ ] Typos in all DiffEqDocs et al
- [ ] Graph of DiffEq dependencies

## Side Projects
- [ ] Document Cassette
- [ ] Add cool functions to Calculus.jl (J, H, P, Spherical Harmonics)
- [ ] Circuits and Graphs?
- [ ] Geometric Optics
- [ ] Coord Transforms - Elliptic, Parabolic, Hyperbolic, and combos
- [ ] More dimensional Tensors
- [ ] Measurements, Unitful, Data Frames
- [ ] SICP
- [ ] SICM
- [ ] Cormen
- [ ] Functional Diff Geo
- [ ] Deep Learning + Calc + Abramowitz + Books
- [ ] Aerodynamics and Deep Learning and Flow
- [ ] Interval Arithmetic and DiffEq
- [ ] TaylorIntegration in DiffEq
- [ ] complicacada con autodiff 
- [ ] Famous formulas in physics
- [ ] geometrized/quantized units/ cgs/kms/dynas / astronomical / Planck
- [ ] Unitful plots in DiffEq
- [ ] [shortunits.jl](https://github.com/Keno/SIUnits.jl/blob/master/src/shortunits.jl) needs some love with physical constants and metaprogramming magics for [all of the prefixes](http://www.npl.co.uk/reference/measurement-units/si-prefixes/).
