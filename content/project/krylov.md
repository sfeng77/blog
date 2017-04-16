+++
# Date this page was created.
date = "2016-04-27"

# Project title.
title = "Krylov"

# Project summary to display on homepage.
summary = "Accelerated Krylov Solver for Multiorbital Kanamori Hamiltonian."

# Optional image to display on homepage (relative to `static/img/` folder).
# image_preview = "bubbles.jpg"

# Tags: can be used for filtering projects.
# Example: `tags = ["machine-learning", "deep-learning"]`
tags = ["phi", "physics"]

# Optional external URL for project (replaces project detail page).
# external_link = "http://www.institute.loni.org/lasigma/package/ising/"

# Does the project detail page use math formatting?
math = true

# Optional featured image (relative to `static/img/` folder).
[header]
# image = "gpu.jpg"
# caption = "A NVIDIA TESLA GPU card."

+++
This project is sponsered by LA-SIGMA.

## Released Package 
http://www.institute.loni.org/lasigma/package/krylov/

## Purpose
This code is a Krylov Solver using the Arnoldi iteration for Kanamori Hamiltonian. it is used for calculating the exponential of matrices in a Continuous Time Quantum Monte Carlo (CTQMC) solver on systems equipped with an intel Xeon Phi. This solver calculates the following quantity:

$exp(-H*t)*v$

where:
H is a sparse matrix that represents the Kanamori Hamiltonian in the CTQMC solver. t is a scalar. v is a vector.

## Systems
The code was developed and tested on a computer equipped with the following software packages: Red Hat Enterprise Linux Version 6.6, GCC 4.4.7, intel ICC composer_xe_2013_sp1.1.106, and intel MKL composer_xe_2013_sp1.2.144.

## Contents
The code provided here is a highly tuned implementation of the Krylov solver designed for a very specific hamiltonian matrix. This tool is comprised of two different codes, an initialization code which is executed on the CPU, and a Xeon Phi native library which is integrated in the main CTQMC code. This package also has a simple test using provided sample inputs (hamiltonians of 5 and 6 orbitals)

## Acknowledgments
This code was developed by Roozbeh Karimi, Sheng Feng, Jian Tao, Ka-Ming Tam, David Koppelman, Juana Moreno, and Mark Jarrell. This work was supported in part by the National Science Foundation under the NSF EPSCoR Cooperative Agreement No. EPS-1003897 with additional support from the Louisiana Board of Regents.



