[From Chris's Blog post](http://www.juliabloggers.com/differentialequations-jl-2-0-state-of-the-ecosystem/)

Stiff solvers

Let’s start by talking about stiff solvers. As of right now, we have the all of the standard solvers (CVODE, LSODA, radau) wrapped in the packages Sundials.jl, LSODA.jl, and ODEInterface.jl respectively. These can all be used in the DifferentialEquations.jl common interface, meaning that it’s mostly abstracted away from the user that these aren’t actually Julia codes. However, these lower level implementations will never be able to reach the full flexibility of the native Julia solvers simply because they are restricted in the types they use and don’t fully expose their internals. This is fine, since our benchmarks against the standard Runge-Kutta implementations (dopri5, dop853) showed that the native Julia solvers, being more modern implementations, can actually have performance gains over these older methods. But, we need to get our own implementations of these high order stiff solvers.

Currently there exists the Rosenbrock23 method. This method is similar to the MATLAB ode23s method (it is the Order 2/3 Shampine-Rosenbrock method). This method is A and L stable, meaning it’s great for stiff equations. This was thus used for testing event handling, parameter estimation, etc.’s capabilities and restrictions with the coming set of stiff solvers. However, where it lacks is order. As an order 2 method, this method is only efficient at higher error tolerances, and thus for “standard tolerances” it tends not to be competitive with the other methods mentioned before. That is why one of our main goals in DiffEq 3.0 will be the creation of higher order methods for stiff equations.

The main obstacle here will be the creation of a library for making the differentiation easier. There are lots of details involved here. Since a function defined using the macros of ParameterizedFunctions can symbolically differentiate the users function, in some cases a pre-computed function for the inverted or factorized Jacobian can be used to make a stiff method explicit. In other cases, we need autodifferentiation, and in some we need to use numerical differentiation. This is all governed by a system of traits setup behind the scenes, and thus proper logic for determining and using Jacobians can immensely speed up our calculations.

The Rosenbrock23 method did some of this ad-hocly within its own method, but it was determined that the method would be greatly simplified if there was some library that could handle this. In fact, if there was a library to handle this, then the Rosenbrock23 code for defining steps would be as simple as defining steps for explicit RK methods. The same would be true for implicit RK methods like radau. Thus we will be doing that: building a library which handles all of the differentiation logic. The development of this library, DiffEqDiffTools.jl, is @miguelraz ‘s Google Summer of Code project. Thus with the completion of this project (hopefully summer?), efficient and fully compatible high order Rosenbrock methods and implicit RK methods will easily follow. Also included will be additive Runge-Kutta methods (IMEX RK methods) for SplitODEProblems. Since these methods double as native Julia DAE solvers and this code will make the development of stiff solvers for SDEs, this will be a major win to the ecosystem on many fronts.