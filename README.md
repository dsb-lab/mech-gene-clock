# Parametric modeling of mechanical effects on circadian oscillators
This model describes a genetic clock that considers inputs from mechanical sources. A modified Goodwin model is used to describe the relationship between clock genes Bmal1 and Rev-ErbA. Bmal1 mRNA activates the transcription of Rev-ErbA mRNA, which then produces Rev-ErbA protein, which circles back and represses the expression of Bmal1 mRNA. This three-part loop allows for oscillatory behavior with regular 24 hour periods for the mRNA and protein of Bmal1 and Rev-ErbA. The model was compared to experimental results from Abenza et al. 2023.

goodwin_model_base.ipynb
Contains the deterministic system of differential equations for the Goodwin model. The system is numerically integrated using odeint (scipy package). Time series and Fourier analysis are shown for two parameter sets, one of which realistic periods of oscillation and concentrations of molecules.
https://docs.scipy.org/doc/scipy/reference/generated/scipy.integrate.odeint.html

model_added_saturation.ipynb
Contains the deterministic system Goodwin model with saturation added in the Z-variable. The system is numerically integrated using odeint (scipy package). Time series and Fourier analysis are shown for three values of alpha_1, which represents the amount of YAP/TAZ. The middle value of alpha_1 produces time series with persistant oscillations. The low and high values of alpha_1 cause the system to settle to a steady state.
https://docs.scipy.org/doc/scipy/reference/generated/scipy.integrate.odeint.html

stochastic_simulations.ipynb
Applies the next reaction method to the model with added saturation. First, simulations are run for normal and high values of alpha_1 (representing normal and high amounts of YAP/TAZ). Next, simulations are run for gradually increasing values of alpha_1. 

bifurcation_xppaut_a1.ode
bifurcation_xppaut_b2.ode
bifurcation_xppaut_b3.ode
bifurcation_xppaut_k1.ode
The ```.ode``` files are to be processed with XXPAUT (https://sites.pitt.edu/~phase/bard/bardware/xpp/xpp.html). These files contain the system of differential equations and define the parameters. Each separate .ode file is used to generate the bifurcation diagram for the given parameter.

**References**
* Kennedy KE, Abenza JF, Rossetti L, Trepat X, Villoslada P, Garcia-Ojalvo J. Parametric modeling of mechanical effects on circadian oscillators. arXiv preprint arXiv:2306.14005. 2023 Jun 24.
* Abenza JF, Rossetti L, Mouelhi M, Burgués J, Andreu I, Kennedy K, Roca-Cusachs P, Marco S, García-Ojalvo J, Trepat X. Mechanical control of the mammalian circadian clock via YAP/TAZ and TEAD. J Cell Biol. 2023 Sep 4;222(9):e202209120. doi: 10.1083/jcb.202209120. Epub 2023 Jun 28. PMID: 37378613; PMCID: PMC10308087.
