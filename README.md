# PyTubular: Python module for the evaluation of probability densities and exit rates in the tubular ensemble

## About

This module contains both sympy-based symbolic and numpy-based numerical tools for one-dimensional Fokker-Planck dynamics in a small time-dependent domain.

More specifically, for a given drift $a(x,t)$ and diffusivity $D(x,t)$ we consider the Fokker-Planck equation

$$\partial_t P = - \partial_x \left( a P\right) + \partial_x^2 \left(D P\right),$$

on a time-dependent domain $x \in [x_l(t), x_r(t)]$, and with time-dependent absorbing boundary conditions

$$P(x_l(t),t) = P(x_r(t),t) = 0$$

for the density $P(x,t)$. Due to the absorbing boundary conditions, the total density within the domain, given by $$P(t) = \int_{x_l(t)}^{x_r(t)}dx\,P(x,t),$$ is a decaying function of time.

This python module implements perturbative analytical results for both the decay rate of the density, $$\alpha = - \frac{\partial_t P(t)}{P(t)},$$ as well as the normalized density within the domain,
$$P^N(x,t) = \frac{ P(x,t)}{P(t)}.$$

For simplicity, we in the previous section used $x_l$, $x_r$ to parametrize the instantaneous domain of the Fokker-Planck equation. In the examples, and in the python module, we instead use the center path $$\varphi(t) = (x_r(t) + x_l(t))/2$$ and the radius $$R(t) = (x_r(t) - x_l(t))/2$$ of the instantaneous domain. We refer to the center path also as reference path, and the time-dependent domain as tube.

## Examples

PyTubular comes with several illustrative example notebooks, which are located in the subfolder [examples/](examples/). In particular, the examples are
* [Analytical perturbative exit rate vs numerical simulations.ipynb](examples/Analytical%20perturbative%20exit%20rate%20vs%20numerical%20simulations.ipynb): In this notebook we compare the perturbative exit rate from a small tube to the results of direct numerical simulation of the Fokker-Planck equation (which are performed using the python module [fokker-planck](https://github.com/juliankappler/fokker-planck)).
* [Sympy vs numpy implementation of exit rate.ipynb](examples/Sympy%20vs%20numpy%20implementation%20of%20exit%20rate.ipynb): In this notebook we show that the sympy-based symbolic and numpy-based numerical implementations of the perturbative exit rate, which are both contained in PyTubular, yield identical predictions.
* [Most probable tube.ipynb](examples/Most%20probable%20tube.ipynb): In this notebook we find the most probable tube for a barrier crossing. 

## Installation

PyTubular requires sympy and numpy, the most probable tube example furthermore uses the cma package for minimizing multidimensional functions. To install these requirements as well as PyTubular, you can run the following commands.

```bash
>> git clone https://github.com/juliankappler/PyTubular.git
>> cd PyTubular
>> pip install -r requirements.txt
>> pip install .
```

## References

[to be added once the papers are on arXiv]