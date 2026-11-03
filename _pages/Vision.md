---
layout: single
title: "Research Vision"
permalink: /vision/
date: 2026-11-03
categories: pages
toc: true
toc_label: "Vision"
toc_icon: "compass"
---

My research program is on the engineering and discovery of advanced separation materials. My long-term goal is to develop machine learning algorithms for separations that do two things: build surrogate models for structure–state–property prediction (by 'state' I am referring to the conditions a property depends on, such as temperature, pressure, and mixture composition), and design the molecular structure for a given target property (the inverse problem). Molecular simulation supplies the data these models learn from. I do care about closing the loop, so that structures proposed by the models are validated in silico or experimentally and the results feed back into the models, but developing the models and algorithms in the first place, and applying them to separation problems, comes first. The three thrusts below are my short-term plan, followed by where I see the program going in the long term (year 4 and beyond).

<figure>
  <a href="/assets/images/vision_platform.png"><img src="/assets/images/vision_platform.png" alt="Machine learning for separations: a surrogate model shown as a structure-by-state property heatmap, and inverse design from a target to a candidate, with molecular simulation supplying data and validation feeding back"></a>
  <figcaption>Machine learning for separations at the centre: surrogate models that map structure and state to property, and inverse design, both trained on simulation data; validation in silico or by experiment feeds back.</figcaption>
</figure>


### Molecular simulation of separation materials
* Generate adsorption, diffusion, and permeability data for mixtures across pressure, temperature, and composition (most separations of industrial interest involve mixtures, while most of the available data is for single components)
* Extend simulation protocols to chemically heterogeneous MOFs and water-containing mixtures, building on my CFC-GCMC work on water vapor adsorption
* Explore electrostatic patterning as a design handle for water vapor harvesting and separation

**Example project: CO<sub>2</sub>/CH<sub>4</sub> competitive adsorption.** Natural-gas and biogas upgrading both come down to taking CO<sub>2</sub> out of CH<sub>4</sub>, and how an adsorbent does this depends on pressure as much as on composition. In my active learning work on Cu-BTC (Digital Discovery, 2023), CO<sub>2</sub> behaves very differently depending on how much of it is in the feed. When CO<sub>2</sub> is dilute, it takes the charged sites first and its uptake climbs quickly at low pressure. As the pressure rises and the pores fill, CH<sub>4</sub> begins to replace it, roughly one molecule for another, so the CO<sub>2</sub> uptake rises and then falls; above about 140 bar the pores hold more CH<sub>4</sub> molecules than CO<sub>2</sub>, although CO<sub>2</sub> is still several times more concentrated in the pores than in the gas. When CO<sub>2</sub> is most of the feed, the pores fill with CO<sub>2</sub> at low pressure and stay full, with almost no CH<sub>4</sub>. I want to map this across pressure, temperature, and composition with mixture GCMC, and decompose the energy into guest–host electrostatics, guest–host dispersion, and guest–guest terms, together with where each molecule sits, so that it is clear which interaction controls the uptake and selectivity in each regime.

<figure>
  <a href="/assets/images/vision_co2_ch4.png"><img src="/assets/images/vision_co2_ch4.png" alt="CO2 (solid) and CH4 (dashed) uptake in mmol/g against pressure from a CO2/CH4 mixture in Cu-BTC at 240 K (mixture GCMC): at 11.6% CO2 the CO2 uptake rises then falls as CH4 replaces it, and CH4 overtakes CO2 near 140 bar; at 98% CO2 the pores fill with CO2 and stay full while CH4 stays near zero; and the interactions that drive it: electrostatics, CO2-CO2 attraction and CH4 competition"></a>
  <figcaption>CO<sub>2</sub> (solid) and CH<sub>4</sub> (dashed) uptake from a CO<sub>2</sub>/CH<sub>4</sub> mixture in Cu-BTC at 240 K, in mmol/g (mixture GCMC data from the Digital Discovery 2023 paper): with 11.6% CO<sub>2</sub>, the CO<sub>2</sub> uptake peaks near 30 bar and then falls as CH<sub>4</sub> replaces it, and CH<sub>4</sub> overtakes CO<sub>2</sub> near 140 bar; with 98% CO<sub>2</sub> the pores fill with CO<sub>2</sub> and stay full, with almost no CH<sub>4</sub>. Right: the interactions that drive it.</figcaption>
</figure>


**Example project: separating the C<sub>8</sub> aromatics.** p-Xylene (the precursor to terephthalic acid, and therefore to PET) has to be separated from o-xylene, m-xylene, and ethylbenzene, whose boiling points sit within about 8 °C of each other, with p- and m-xylene only 0.7 °C apart. Distillation therefore cannot isolate p-xylene, and the split is done today by crystallization or simulated moving-bed adsorption. I want to use mixture GCMC and molecular dynamics to screen MOFs for this separation: shape selectivity (channels that admit the slim p-xylene and keep out the bulkier o- and m-xylene) handles the xylenes, while ethylbenzene, about as slim as p-xylene, has to be separated by adsorption selectivity, which mixture GCMC captures.

<figure class="half">
  <a href="/assets/images/vision_c8_isomers.png"><img src="/assets/images/vision_c8_isomers.png" alt="The four C8 aromatic isomers and their boiling points"></a>
  <a href="/assets/images/vision_mof_channel.png"><img src="/assets/images/vision_mof_channel.png" alt="Schematic of a shape-selective MOF channel passing p-xylene"></a>
  <figcaption>Left: the four C<sub>8</sub> aromatic isomers, drawn to scale, and their boiling points; p- and m-xylene boil only 0.7 °C apart. Right: a shape-selective MOF channel (schematic).</figcaption>
</figure>


### Data-efficient, trustworthy surrogate machine learning models
* Add uncertainty quantification and calibration to GC-MPNN-type models, so that every prediction comes with an error bar
* Develop and compare probabilistic models for this: GNN ensembles, Gaussian process regression (GPR), NGBoost, Bayesian neural networks, and others
* Separate confident interpolation from unreliable extrapolation (the leave-one-gas-out results showed that a model can rank an unseen gas correctly while getting its scale wrong, and I want the model itself to flag when this happens)
* Build active-learning criteria on top of thermodynamically consistent models

**Example project: a multi-fidelity surrogate.** Simulation data is cheap and plentiful but carries systematic bias (force fields are approximate), while experimental data is accurate but scarce. I want to build a single model that learns from both ('multi-fidelity' here means exactly this: one model trained together on cheap-but-approximate and scarce-but-accurate data), built on the probabilistic models above, and that passes its predictions and their uncertainty to an acquisition function that decides where the next experiment or simulation should be spent. Sampling where σ is largest is one choice of acquisition function; expected improvement, upper confidence bound, or a cost-aware rule are others.

<figure class="half">
  <a href="/assets/images/vision_multifidelity.png"><img src="/assets/images/vision_multifidelity.png" alt="Illustrative multi-fidelity surrogate with uncertainty band, simulation points and experiments, above an acquisition strip: expected improvement picks the next simulation or experiment, away from where sigma is largest"></a>
  <a href="/assets/images/vision_data_fusion.png"><img src="/assets/images/vision_data_fusion.png" alt="Simulation and experiment fused by probabilistic models: GNN ensembles, GP regression, NGBoost, Bayesian neural networks and others; an acquisition function picks the next simulation or experiment"></a>
  <figcaption>Left: a multi-fidelity surrogate with its uncertainty band (illustrative data); below it, an acquisition function (expected improvement here) picks the next point, which need not be where σ is largest. Right: probabilistic models (GNN ensembles, GP regression, NGBoost, Bayesian NNs and others) fusing simulation with experiment, with an acquisition function picking the next simulation or experiment.</figcaption>
</figure>


### Physics-informed inverse design
* Generate candidate MOFs and polymers with reinforcement learning, with synthesizability, stability, and physics penalties built into the reward rather than checked afterwards
* Develop differentiable coarse-graining for membrane morphology and transport

**Example projects.** Design MOFs and polymers for water vapor harvesting and for multicomponent gas mixtures. Further out, I am interested in rare-earth element separation, which is attracting growing attention because of critical-mineral supply. Neighbouring lanthanides (for example Pr and Nd, both used in NdFeB permanent magnets) differ in ionic radius by only about a picometre, so telling them apart calls for adsorbents whose binding site fits one neighbour better than the next, whether ligand-functionalized MOFs and polymers or lanthanide-binding proteins such as lanmodulin.

<figure class="half">
  <a href="/assets/images/vision_inverse_design.png"><img src="/assets/images/vision_inverse_design.png" alt="An RL generator designing MOFs and polymers for water vapor harvesting, gas mixtures and synthesizability"></a>
  <a href="/assets/images/vision_rare_earths.png"><img src="/assets/images/vision_rare_earths.png" alt="The lanthanide series with neighbouring Pr and Nd highlighted, and a binding pocket that fits Nd3+ better than the slightly larger Pr3+"></a>
  <figcaption>Left: reinforcement learning designing MOFs and polymers for a target. Right: rare-earth separation, where neighbouring lanthanides are nearly identical.</figcaption>
</figure>


### Timeline
**Short term**

* Reliable surrogates: uncertainty, calibration, and transfer to new species and conditions
* Inverse design: reinforcement learning that generates MOFs and polymers for a target property, with synthesizability and stability built into the reward
* Mixture adsorption, diffusion, and permeability datasets, starting with CO<sub>2</sub>/CH<sub>4</sub> and the C<sub>8</sub> aromatics
* Multiscale models: differentiable coarse-graining of gas–polymer systems

**Long term (year 4 and beyond)**

* Process-level design for natural-gas sweetening, CO<sub>2</sub> capture, H<sub>2</sub>S removal, and H<sub>2</sub> purification
* Bio-separations and hybrid mechanistic–machine learning bioprocess models
* Datasets, models, and workflows released openly for others to build on

If any of this overlaps with what you work on, I would be glad to talk; my contact details are on the [home page](/).
