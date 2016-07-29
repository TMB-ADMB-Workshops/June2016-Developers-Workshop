#Developers Workshop 2016 Report

June 20 - 24, 2016

School of Aquatic and Fisheries Sciences

Seattle, Washington, USA

﻿Put your name below 2 or 3 topics  for breakout groups below.Then we’ll try to organize the schedule accordingly.


ESSENTIALLY DONE (add notes about outcome)
* R package of contributed functions 
   * Kasper added a directory called “TMB_contrib_R” to “kaskr” github page 
      * He’s working on a function as part of package to install these into right place so they get compiled
   * Contains subdirectories that can be installed using devtools R package installer
   * Examples include:
      *  Jim Thorson added TMBdebug
      * Gavin is working on TMBphase using example code from Mollie
         * Phasing within an optimizer
         * Function with normal inputs, passed via “...”, plus two additional arguments, “phase” and “optimizer”
         * Optimizer by default is nlminb
         * phase is a tagged list where missing elements are populated with a vector of 1s, and non-missing elements are integers, and where the optimizer loops through values of phase while progressively changing map to turn on parameters
         * Function works, needs testing.
         * https://github.com/gavinfay/TMBphase
         * devtools::install_github(“gavinfay/TMBphase”)
         * GF tested using thetalogistic example.
         * Example usage in Roxygen documentation for TMBphase()
         * Not implemented choice of optimizer yet.
      * Maybe Cole will add TMBmcmc
      * It would be nice to have an AIC function that works as AIC(fit <- nlminb(mod$par, mod$fn, mod$gr)). See TMBAIC at https://github.com/kaskr/adcomp/wiki/FAQ
         * THIS has now been added to TMBhelper in the user-contributed directory
      * It would be nice to have an elem_prod() function.
* Kasper created a function allowing contributed cpp code to be used in a TMB model. See example https://github.com/kaskr/example_cpp#example_cpp
   *  Thorson, Kasper, Mollie (testing Friday)


* Example presentation of Atomic functions and use of derivatives within the template (during Kasper’s presentation)


* Double checked Mathew’s AD example comparing gradients with ADMB and TMB 
   * Mathew, Kasper


* Begin planning spatio-temporal textbook using TMB
   * Thorson, K/C-asper, Anders, Hans
* Option to suppress warnings from CHOLMOD during optimization 
   * Casper, Kasper, Brad.
   * Notes: Now the warnings are disabled by default. They can be activated by adding
newtonOption(obj,silent=FALSE). However, you will know that they would have been generated if “ustep” is less than one.
* Fix sdreport() for singular hessian cases (avoid crash, just output NaN)
* Created TMB Users google group so that users can answer each other’s questions


* Website issues
   * John, Johnoel, Mollie
   * Frontpage text of draft website revised http://admb-project-org.admb-foundation.org/
   * Additional logos needed in footer


CURRENTLY ACTIVE
* Instructional videos
   * Mollie, Hans, Arni
* ADMB-IDE 11.5
   * Arni, Chris, Cole, Johnoel (in lunch area)
* TMB  with GPU
   * Arni, Gavin, Teresa
* Brainstorm a website and foundation name


* Discuss getting better sparseness detection in ADMB
   * Kasper, Matt, Dave
* posfun in TMB
   * See GitHub issue #7; admb version has posfun2 that may be C3.
   * Dave, Cole, Jim T
* HAPPENING SOON
* Model selection (e.g. Cross validation methods, Conditional AIC, 1 step predict)
   * Mollie
   * See adcomp/tmb_examples/validation
* Try to run ATL, theta-logistic example
   * Arni
* Try to run cppad_mixed, using cppad without the TMB layer
   * Brad, Arni, Ianelli, Hans, Teresa
* Rank order -1 problem
* Script for non-R folks
* 3rd order derivatives
* NUTS algorithm to be added to ADMB
* Sparseness detection
* Parallelization; Dave has open CL version of the function minimizer that could be used as an example of how the GPU approach might be beneficial


NEED HELP
* Get install_github() to do source("install_windows.R") when Windows is detected
* MCMC (Riemann with Langevin updates)(after Cole’s presentation)
   * Bob
* Non-normal RE (rotational Bayes)  
* Create TMB page on Wikipedia
*   



The following will also be scheduled if they aren’t already:
   * Debugging demonstration and documentation reference
   * Everyone
   * glmmTMB publication planning


Website
   * Add dtu aqua and coin-r  in footer
