---
layout: single
title: "Research Vision"
permalink: /vision/
date: 2026-10-31
categories: pages
toc: true
toc_label: "Vision"
toc_icon: "compass"
---
My long-term goal is to build a closed-loop discovery platform for separation materials, one in which molecular simulation, thermodynamic theory, data-efficient machine learning, reinforcement learning, and experiment each cover a weakness of the others. Simulations supply mechanistic data, theory imposes physical structure, surrogate models make prediction fast enough to search, reinforcement learning proposes new candidates, and measured permeabilities feed back to retrain the surrogates and reshape the reward. The three thrusts below are how I plan to build it over the first three years, followed by where I see it going in the longer term.

<figure>
  <a href="/assets/images/vision_platform.png"><img src="/assets/images/vision_platform.png" alt="Closed-loop discovery platform: molecular simulation, thermodynamic theory, surrogate models, reinforcement learning and experiment arranged in a loop"></a>
  <figcaption>The closed-loop discovery platform: each stage covers a weakness of the others.</figcaption>
</figure>

### Thrust 1: Molecular simulation of separation materials
* Generate adsorption, diffusion, and permeability data for mixtures across pressure, temperature, and composition (most separations of industrial interest involve mixtures, while most of the available data is for single components)
* Extend simulation protocols to chemically heterogeneous MOFs and water-containing mixtures, building on my CFC-GCMC work on water vapor adsorption
* Explore electrostatic patterning as a design handle for water harvesting

**Example project: separating the C<sub>8</sub> aromatics.** p-Xylene (the precursor to terephthalic acid, and therefore to PET) has to be separated from o-xylene, m-xylene, and ethylbenzene, whose boiling points sit within about 8 &deg;C of each other. Distillation is therefore impractical, and the split is done today by crystallization or simulated moving-bed adsorption. I want to use mixture GCMC and molecular dynamics to screen shape-selective MOFs (frameworks whose channels admit the slim p-xylene and keep out its bulkier isomers) for this separation.

<figure class="half">
  <a href="/assets/images/vision_c8_isomers.png"><img src="/assets/images/vision_c8_isomers.png" alt="The four C8 aromatic isomers and their boiling points"></a>
  <a href="/assets/images/vision_mof_channel.png"><img src="/assets/images/vision_mof_channel.png" alt="Schematic of a shape-selective MOF channel passing p-xylene"></a>
  <figcaption>Left: the four C<sub>8</sub> aromatic isomers and their boiling points. Right: a shape-selective MOF channel (schematic).</figcaption>
</figure>

### Thrust 2: Data-efficient, trustworthy surrogates
* Add uncertainty quantification and calibration to GC-MPNN-type models, so that every prediction comes with an honest error bar
* Separate confident interpolation from unreliable extrapolation (the leave-one-gas-out results showed that a model can rank an unseen gas correctly while getting its scale wrong, and I want the model itself to flag when this happens)
* Build active-learning criteria on top of thermodynamically consistent models

**Example project: a multi-fidelity surrogate.** Simulation data is cheap and plentiful but carries systematic bias (force fields are approximate), while experimental data is accurate but scarce. I want to build a single model that learns from both (when I say 'multi-fidelity' I am referring to exactly this: one model trained together on cheap-but-approximate and scarce-but-accurate data), and that uses its own uncertainty to decide where the next experiment or simulation should be spent.

<figure class="half">
  <a href="/assets/images/vision_multifidelity.png"><img src="/assets/images/vision_multifidelity.png" alt="Illustrative multi-fidelity surrogate with uncertainty band, simulation points, experiments and the next experiment"></a>
  <a href="/assets/images/vision_data_fusion.png"><img src="/assets/images/vision_data_fusion.png" alt="Simulation and experiment fused into one uncertainty-aware model"></a>
  <figcaption>Left: a multi-fidelity surrogate with its uncertainty band (illustrative data). Right: fusing simulation with experiment, and placing the next experiment where &sigma; is largest.</figcaption>
</figure>

### Thrust 3: Physics-informed inverse design
* Generate candidate MOFs and polymers with reinforcement learning, with synthesizability, stability, and physics penalties built into the reward rather than checked afterwards
* Develop differentiable coarse-graining for membrane morphology and transport
* Combine learned models with real adsorbed solution theory, group contribution, and self-consistent field theory (SCFT)

**Example projects.** Design MOFs and polymers for water-vapor harvesting and for multicomponent gas mixtures. Further out, I am interested in rare-earth element separation, which is attracting growing attention because of critical-mineral supply. Neighbouring lanthanides (for example Nd and Dy, both used in permanent magnets) differ in ionic radius by only about a picometre per element, so telling them apart calls for ligand-functionalized MOFs and polymers whose binding pocket fits one neighbour better than the next.

<figure class="half">
  <a href="/assets/images/vision_inverse_design.png"><img src="/assets/images/vision_inverse_design.png" alt="An RL generator designing MOFs and polymers for water harvesting, gas mixtures and synthesizability"></a>
  <a href="/assets/images/vision_rare_earths.png"><img src="/assets/images/vision_rare_earths.png" alt="The lanthanide series with Nd and Dy highlighted, and a binding pocket that fits Dy3+ but not Nd3+"></a>
  <figcaption>Left: reinforcement learning designing MOFs and polymers for a target. Right: rare-earth separation, where neighbouring lanthanides are nearly identical.</figcaption>
</figure>

### Timeline
**Years 1&ndash;3**

* Reliable surrogates: uncertainty, calibration, and transfer to new species and conditions
* Integrated adsorption, diffusion, and permeability datasets
* Multiscale models: differentiable coarse-graining of gas&ndash;polymer systems

**Years 4&ndash;10**

* The closed-loop discovery platform in routine use
* Process-level design for natural-gas sweetening, CO<sub>2</sub> capture, H<sub>2</sub>S removal, and H<sub>2</sub> purification
* Bio-separations and hybrid mechanistic&ndash;machine learning bioprocess models
* Datasets, models, and workflows released openly for others to build on

If any of this overlaps with what you work on, I would be glad to talk; my contact details are on the [home page](/).
