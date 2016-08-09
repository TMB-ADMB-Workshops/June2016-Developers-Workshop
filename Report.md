#Developers Workshop 2016 Report

June 20 - 24, 2016

School of Aquatic and Fisheries Sciences

Seattle, Washington, USA

![alt text](images/DevWS6.png "Autodifferentiation is cool!")


##Introduction
This report summarises the events of the 6th ADMB Developer’s Workshop, a meeting held at the University of Washington School of Aquatic and Fisheries Sciences, Seattle Washington. The meeting was attended by many ADMB and TMB core developers and were joined by invited European and American experts. These experts introduced their experiences in software development for similar types of challenges. The meeting was held in the typical informal style, allowing open group discussions and demonstrations of new features, possible improvements, and current issues. Meeting participants spent considerable time working in sub-groups, each of which tackled a related set of priority issues for the ADMB project. 

Participants are included in an appendix to this document. Jim Ianelli chaired the majority of the workshop, with much assistance from Arni Magnusson and Mollie Brooks.  Gavin Fay and Johnoel Ancheta along with others acted as rapporteur and compiled and edited this report. An ADMB foundation meeting was held at the conclusion of the workshop and new members and board was appointed.
The workshop was broadcast via the internet to allow for remote participation.

##Objectives
The main obectives of the workshop included to
* Plan and develop instructional videos
* Coordinate between TMB and ADMB Projects
* Further develop MCMC implementations
* Review new website design (converted from plone to wordpress)
* Hold an ADMB Foundation meeting

##Presentations on activities
Thursday of the workshop was devoted to a series of presentations on alternative approaches (e.g., Stan) and activities
where ADMB/TMB are being actively used.

[Gavin Fay's experience using TMB with GPU card is available on the githup repository.](
https://github.com/TMB-ADMB-Workshops/June2016-Developers-Workshop/blob/master/presentations/tmb_with_gpus/TMB_with_GPU_Fay_20160624.pdf)    

[Bob Carpenter's presentation on Stan implementation and issues]( 
https://github.com/TMB-ADMB-Workshops/June2016-Developers-Workshop/blob/master/presentations/stan-admb-talk-2016.pdf)    


## New website
The workshop reviewed the new website design and developed text describing expanded roles of the Foundation to
help support the TMB activities and embrace alternative approaches to software development.
http://admb-project-org.admb-foundation.org/

##Discussion topics and breakout sessions
The group discussed and developed a list of topics to be covered in breakout sessions:     
  * ADMB-IDE 11.5     
  * cppad_mixed     
  * instructional videos     
  * Nvidia GPU     
  * TMB  with GPU     
  * Non-normal RE (rotational Bayes)     
  * Cross validation methods     
  * MCMC (Riemann with Langevin updates)     
  * XSSA demo of Sibert     
  * GLMM/TMB Package: another distribution could be added; hurdle model generalized Poisson     
  * Atomic functions and use of derivatives within the template (e.g., newton raphson's within the template)     
  * Debugging demonstration and documentation reference     
  * Posfun in TMB     
  * Protocol for contributing code     
  * Website issues     

The following lists activities and progress for the breakout groups.

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

The following will also be scheduled if they aren’t already:
   * Debugging demonstration and documentation reference
   * Everyone
   * glmmTMB publication planning


Website
   * Add dtu aqua and coin-r  in footer

##Agenda and timing
The following outlines the agenda and schedule that was followed.

_Monday, June 20_ __Opening and Instructional Videos__

|Time|Activity|
|:---|:-----------|:--------------------------------------------|
|9:00AM|Opening: revision and approval of agenda; assignment of repporteurs|
|10:00AM|Arni Magnusson: ADMB-IDE, rolling out version 11.5, people willing to help out? Also, a quick review of TMB-IDE.|
|11:00AM|Discussion|
|1:00PM|Lunch|
|2:30PM|Mollie Brooks: The glmmTMB package for flexible mixed models in R|
|3:30AM|Jim Thorson: Progress with spatio-temporal analysis of multivariate  (e.g., species or sizes) data using TMB, and how statistical developments might help|
|4:30PM|Discussion|
|5:00PM|End|

_Tuesday, June 21_ __Miscellaneous Topics__

|Time|Activity|
|:---|:-----------|:--------------------------------------------|
|9:00AM|Overview of R packages based on ADMB and TMB. Discuss potential new R package, `TMBextras`. Also write up (or find existing write-up?) description of how to create a user-level C++ library.|
|10:00AM|Creation of Instructional videos - Chair Hans Skaug|
|11:00AM|Split into breakout groups|
|Noon|Lunch|
|1:00PM|Breakout groups|
|2:00-3.00PM|*PLENARY SESSION:* Subgroups report on initial ideas, progress, and goals|
|3:00-5:00PM|Breakout groups|

_Wednesday, June 22_ __TMB / ADMB Coordination__

|Time|Activity|
|:---|:--------------------------------------------|
|9:00AM|Johnoel Ancheta |Website: review new [WordPress alternative to Plone](http://admb-project-org.admb-foundation.org/)|
| |Breakout sessions|
|5:00PM|End|

_Thursday, June 23_ __The use of AD in statistical software__

|Time|Speaker|Title|
|---|-----------|--------------------------------------------|
|9:00AM|David Fournier |The use of higher order AD to develop a multinomial like M estimator for the analysis of compositonal data with an application to fisheries management models |
|10:00AM|Brad Bell|cppad_mixed: A C++ Package for Laplace Approximation of Mixed |
|11:00AM||Break |
|11:30AM|Bob Carpenter|Implementation and Application of Reverse-Mode Autodiff in Stan|
|1:00PM| **Lunch** |
|2:00PM|Kasper Kristensen |TMB: Automatic Differentiation and Laplace Approximation|
|3:00PM|Cole Monnahan|Hamiltonian Monte Carlo in ADMB and TMB: current status and future directions|
|4:00PM|Matthew Supernaw|ATL and Higher-Order Reverse Mode AD|
|5:00PM||End of day|


_Friday, June 24_ __Foundation Meeting and Conclusion__

|Time|Activity|
|---|---|
|9:00AM|Discussion: How can the TMB and ADMB Projects support one another (Chair Jim Ianelli)|
| |Outreach|
| |More training workshops|
| |Fund raising|
| |Possible relocation of project|
|2:00PM|ADMB Foundation Meeting|
||Discuss Articles of Incorporation|
||Relocation of project|
||Election of officers|
|4:00PM|End|


##Participants
|Name|Notes|
|---|---|
|Dave Fournier|Otter Research|
|John Sibert|ADMB Project, JIMAR, University of Hawaii|
|Jim Ianelli||
|Steve Martell||
|Anders Nielsen||
|Hans Skaug||
|Arni Magnusson||
|Kasper Kristensen| Developer TMB | 
|Brad Bell| Developer cppad |
|Mollie Brooks||
|Matthew Supernaw| Developer atl |
|Teresa A'mar||
|Chris Grandin||
|Casper Berg||
|Cole Monnahan||
|Jim Thorson||
|Bob Carpenter|Stan Project|
|Johnoel Ancheta|ADMB Project, JIMAR, University of Hawaii|
|Gavin Fay||
|Allan Hicks|IPHC|
|Kyle Foreman||
|Rick Methot||

