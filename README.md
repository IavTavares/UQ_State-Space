# UQ_State-Space
Quantification of model discrepancy, aka epistemic uncertainty in the ML community, in state-space models using Gaussian processes.



**Context**: 
In any scientific context  researchers, in their pursuit of how reality works, have to make some modelling assumptions, by assuming a certain function for the process generating the data. This usually means that the researcher is assuming that the data is drawn from a certain distribution.  However, these assumptions may be severely inadequate, depending on the context. Hence the need to quantify this inadequacy, which may also be called model discrepancy.

In Macroeconomics, there's a real need for this type of quantification, ever since the financial crisis the 2007-2008 showed some of the limitations of its theoretical models, usually stated in a state-space form.



**Problem Statement**:
 How to quantify the inadequacy of a state-space model in the Macroeconomic context?



**Answer:**
We'll try to quantify that model discrepancy using a Gaussian Process, in a Bayesian perspective.


For more information, check out the pdfs in the repository. 


FullGP.nb - In this Mathematica Notebook, I use the full Gaussian Process(GP). I say full because in another one I use an approximation to the GP. In the simulations, certain mathematical operations required the matrices to be positive-definite. However, due to machine precision, certain matrices were not. Hence, I had to build from scratch an algorithm that made sure we could find new approximate matrices, which were PD and maintained that property whenever needed. This created two computational bottlenecks, at the learning and filtering phase.

ApproxGP.nb - In this notebook, I use a functional approximation to the GP, which makes the filtering of the main algorith run much faster. However, there's a trade-off. We lose some accuracy in our predictions, when comparing with the full GP.
