Developers Workshop 2016 Report
===============================

June 20 - 24, 2016

University of Washington, School of Aquatic and Fisheries Sciences

Seattle, Washington, USA

![alt text](images/DevWS6.png "Autodifferentiation is cool!")

Description
===========

This report summarises the events of the 6th ADMB Developer’s Workshop, a meeting held at the University of Washington School of Aquatic and Fisheries Sciences, Seattle Washington. The meeting was attended by many ADMB and TMB core developers and were joined by invited European and American experts. These experts introduced their experiences in software development for similar types of challenges. The meeting was held in the typical informal style, allowing open group discussions and demonstrations of new features, possible improvements, and current issues. Meeting participants spent considerable time working in sub-groups, each of which tackled a related set of priority issues for the ADMB project. 

Participants are included in an appendix to this document. Jim Ianelli chaired the majority of the workshop, with much assistance from Arni Magnusson and Mollie Brooks.  Gavin Fay and Johnoel Ancheta along with others acted as rapporteur and compiled and edited this report. An ADMB foundation meeting was held at the conclusion of the workshop and new members and board was appointed.
The workshop was broadcast via the internet to allow for remote participation.

Agenda
======

The main **objectives** of the workshop are

* Plan and develop instructional videos
* Coordinate between TMB and ADMB Projects
* Further develop MCMC implementations
* Review new website design (converted from plone to wordpress)
* Hold an ADMB Foundation meeting

Schedule
--------

The following outlined the agenda and schedule that was followed.

**Monday, June 20**

_Opening and Instructional Videos_

|Time|Speaker|Activity|
|:---|:------|:-------|
|9:00AM||Opening: revision and approval of agenda; assignment of repporteurs|
|10:00AM|Arni Magnusson|ADMB-IDE, rolling out version 11.5, people willing to help out? Also, a quick review of TMB-IDE.|
|11:00AM|Discussion|
|1:00PM||**Lunch**|
|2:30PM|Mollie Brooks|The glmmTMB package for flexible mixed models in R|
|3:30AM|Jim Thorson|Progress with spatio-temporal analysis of multivariate  (e.g., species or sizes) data using TMB, and how statistical developments might help|
|4:30PM||Discussion|
|5:00PM||**End**|

**Tuesday, June 21**

_Miscellaneous Topics_

|Time|Speaker|Activity|
|:---|:------|:-------|
|9:00AM||Overview of R packages based on ADMB and TMB. Discuss potential new R package, `TMBextras`. Also write up (or find existing write-up?) description of how to create a user-level C++ library.|
|10:00AM|Chair Hans Skaug|Creation of Instructional videos|
|11:00AM||Split into breakout groups|
|Noon||**Lunch**|
|1:00PM||Breakout groups|
|2:00-3.00PM||*PLENARY SESSION:* Subgroups report on initial ideas, progress, and goals|
|3:00-5:00PM||Breakout groups|
|5:00PM||**End**|

**Wednesday, June 22**

_TMB / ADMB Coordination_

|Time|Speaker|Activity|
|:---|:------|:-------|
|9:00AM|Johnoel Ancheta|Website: review new [WordPress alternative to Plone](http://admb-project-org.admb-foundation.org/)|
|||Breakout sessions|
|1:00PM|| **Lunch** |
|||Breakout sessions|
|5:00PM||**End**|

**Thursday, June 23**

_The use of AD in statistical software_

|Time|Speaker|Title|
|:---|:------|:----|
|9:00AM|David Fournier |The use of higher order AD to develop a multinomial like M estimator for the analysis of compositonal data with an application to fisheries management models |
|10:00AM|Brad Bell|cppad_mixed: A C++ Package for Laplace Approximation of Mixed |
|11:00AM||Break |
|11:30AM|Bob Carpenter|Implementation and Application of Reverse-Mode Autodiff in Stan|
|1:00PM|| **Lunch** |
|2:00PM|Kasper Kristensen |TMB: Automatic Differentiation and Laplace Approximation|
|3:00PM|Cole Monnahan|Hamiltonian Monte Carlo in ADMB and TMB: current status and future directions|
|4:00PM|Matthew Supernaw|ATL and Higher-Order Reverse Mode AD|
|5:00PM||**End**|


**Friday, June 24**

_Foundation Meeting and Conclusion_

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
|4:00PM|**End**|

Discussions
===========

ADMB-IDE
--------
Arni also presented the status of ADMB-IDE 11.5 and a sub-group was formed to help w/ maintenance of this package that is commonly used.

Presentations
-------------

Thursday of the workshop was devoted to a series of presentations on alternative approaches (e.g., Stan) and activities
where ADMB/TMB are being actively used.

Gavin Fay's experience using TMB with GPU card is [available](https://github.com/TMB-ADMB-Workshops/June2016-Developers-Workshop/blob/master/presentations/tmb_with_gpus/TMB_with_GPU_Fay_20160624.pdf) on the githup repository.

Bob Carpenter's [presentation](https://github.com/TMB-ADMB-Workshops/June2016-Developers-Workshop/blob/master/presentations/stan-admb-talk-2016.pdf) on Stan implementation and issues.

New website
-----------

The workshop reviewed the new website design and developed text describing expanded roles of the Foundation to
help support the TMB activities and embrace alternative approaches to software development.

http://admb-project-org.admb-foundation.org/

The website was discussed further during the breakout groups.

Topics for breakout sessions
----------------------------

The group discussed and developed a list of topics to be covered in breakout sessions:     
  * ADMB-IDE 11.5     
  * cppad_mixed     
  * instructional videos     
  * Nvidia GPU     
  * TMB with GPU
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

Relative to these tasks, the following lists activities and progress for the breakout groups.

* R package of contributed functions 
   * Kasper added a directory called “TMB_contrib_R” to “kaskr” github page 
      * He’s working on a function as part of package to install these into right place so they get compiled
   * Contains subdirectories that can be installed using devtools R package installer
   * Examples include:
      * Jim Thorson added TMBdebug
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
      * Maybe Cole will add TMBmcmc, which would entail moving the MCMC code currently in the TMB package into TMBmcmc.
      * It would be nice to have an AIC function that works as AIC(fit <- nlminb(mod$par, mod$fn, mod$gr)). See TMBAIC at https://github.com/kaskr/adcomp/wiki/FAQ
         * THIS has now been added to TMBhelper in the user-contributed directory
      * It would be nice to have an elem_prod() function.
* Kasper created a function allowing contributed cpp code to be used in a TMB model. See example https://github.com/kaskr/example_cpp#example_cpp
   *  Thorson, Kasper, Mollie (testing Friday)

Discussions
-----------

Bob Carpenter and Brad Bell led discussions about autodiff in general and announced that there will be a workshop in
Oxford (still time to submit a poster abstract).

Nuts in ADMB
------------
Cole Monnahan led discussions about the current state and future directions of Hamiltonian Monte Carlo in both TMB and ADMB. This included the prospect of adding Riemannian HMC and "variational inference." Bob Carpenter noted the difficulties with ADVI, but that RHMC is very promising for models up to hundreds of parameters with very difficult posterior geometries. Thus, the short-term goals are to get NUTS with adaptation of the step size and mass matrix in both TMB/ADMB. The longer term would be to get RHMC updates working with NUTS. Cole, Dave and Johnoel will work toward this goal over the next 6 months.

An example presentation of Atomic functions and use of derivatives within the template (during Kasper's presentation)

Matthew's AD example comparing gradients with ADMB and TMB was double checked.

Several began planning spatio-temporal textbook using TMB.

The following additional items were noted:
* Include an option to suppress warnings from CHOLMOD during optimization 
   * Notes: Now the warnings are disabled by default. They can be activated by adding
newtonOption(obj,silent=FALSE). However, you will know that they would have been generated if “ustep” is less than one.
* Fix sdreport() for singular hessian cases (avoid crash, just output NaN)

* Website issues
   * John Sibert, Johnoel, Mollie
   * Frontpage text of draft website revised http://admb-project-org.admb-foundation.org/
   * Additional logos needed in footer

It was noted that there would be advantages to having sparseness detection built into ADMB as it is with TMB.

The topic of model selection approaches (e.g. Cross validation methods, Conditional AIC, 1 step predict) was raised and it was noted that in the directory:
   adcomp/tmb_examples/validation an example exists.

A sub-group endeavored torun cppad_mixed, using cppad without the TMB layer
while another group led by Anders developed a simple script to show that TMB can be used for non-R folks.

###Other topics
* Rank order -1 problem
* 3rd order derivatives
* NUTS algorithm to be added to ADMB
* Sparseness detection
* Parallelization; Dave has open CL version of the function minimizer that could be used as an example of how the GPU approach might be beneficial

* Get install_github() to do source("install_windows.R") when Windows is detected
* Non-normal RE (rotational Bayes)  
* Create TMB page on Wikipedia

   * Debugging demonstration and documentation reference
   * Everyone
   * glmmTMB publication planning

Accomplishments
===============

* Successfully configured the ADMB linux server for GPU development support.   
Kasper tested and ran numerical functions using R and GPU which showed speed improvements compared to non-gpu runs.
* An exellent instructional video was developed by Mollie, Hans, and Arni.
* Created [TMB Users google group](https://groups.google.com/forum/#!forum/tmb-users) so that users can answer each other's questions rather than load up the "issues" on the github repository.

Priorities
==========

Tasks
-----

* Automate ADMB-IDE builds  
_for Arni and Johnoel_
* Move ADMB Website to another web host  
_for Sibert and Johnoel_
* Documenting the source code
* Add DTU Aqua in footer to ADMB website  
_for Johnoel_
* Provide instructional video youtube link  
_for Hans Skaug, Arni and Mollie_

Potential new features
----------------------

* Implement NUTS algorithm into ADMB   
_for Cole, Dave Fournier and Johnoel_

Participants
============

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
|Athol Whitten|Remote participation|
|Jeff Laake|Remote participation|
