---
layout: single
title: "Research"
permalink: /Research/
date: 2023-7-21
categories: pages
toc: true
toc_label: "Project"
toc_icon: "columns"
---
My primary research lies in the intersection of computational simulation methods, machine learning models, and material science. I am deeply interested in applying the right computational methodology to discover stucture-property relationships of material system. In my PhD program, I have been mostly involved in gas-solid systems but I am open to investigate other systems as well. Some of the projects I have been involved are listed below (For publications please refer to the publication page):

### Investigating the role of electrostatic distribution in tuning water vapor adsorption using idealized nanoporous materials (currently in-peer review)
* Applied an advanced monte carlo protocol (continuous fractional component grand canonical monte carlo), abbreviated as CFC-GCMC to find equilibriated water loadings at the desired operating conditions (in terms of temperature and pressure)
* Found a special case of an electrostatic configuration than can make the nanopore adsorb water at much lower pressure and this behaviour is proportional to charge strength |q| (when I say 'configuration' I am referring to arrangement of charges in a different order but of same magnitude) 
* Analysis on local environment reveals a unique behaviour of this configuration in terms of host-adsorbate energies (coulombic part), hydrogen bonding, as well as orinetational order
For details, we encourge to read the ChemRxiv paper
[[Github]]([https://github.com/mukherjee07/Active-Learning-for-multicomponent-adsorption-in-a-MOF/tree/main/](https://github.com/mukherjee07/water_vapor_adsorption_modeling))
[[ChemRxiv]]([https://doi.org/10.1039/D3DD00106G](https://chemrxiv.org/engage/chemrxiv/article-details/67cb6e7a6dde43c908fa6f65))
![TOC](https://github.com/user-attachments/assets/bfb3935f-e10e-40c4-aa3f-f920372dceef)


### Active learning for efficient navigation of multi-component gas adsorption landscapes in a MOF
* Designed a Active learning workflow to predict gas mixture adsorption in MOFs (CO<sub>2</sub>-CH<sub>4</sub>, Xe-Kr, and H<sub>2</sub>S-CO<sub>2</sub>).
* Developed an accuracy-based protocol as a stoppage criteria for the Active learning on gas mixture
adsorption in MOFs for a pressure-mole fraction and also for pressure-mole fraction-temperature phase
space (CO<sub>2</sub>-CH<sub>4</sub>, Xe-Kr, and H<sub>2</sub>S-CO<sub>2</sub>). For more details, visit the github page of the project.
[[Github]](https://github.com/mukherjee07/Active-Learning-for-multicomponent-adsorption-in-a-MOF/tree/main/)
[[Publication]](https://doi.org/10.1039/D3DD00106G)
{% include figure image_path="/assets/images/AL_Outline_new.png" caption="Active learning workflow for modeling gas mixtures adsorption in a MOF" %}

### Sequential design of Pure component adsorption simulation in MOFs
* Implemented an Active learning protocol (using Gaussian Process regressions) to predict CH<sub>4</sub> and CO<sub>2</sub> adsorption in a Cu-BTC metal-organic framework (MOF) for a temperature-pressure phase space, and demonstrated a reduction of 97-98% of the total data requirement with comparable accuracy to high-fidelity monte carlo simulations. For more details, visit the github link or the publication landing page of the project.
[[Github]](https://github.com/mukherjee07/Sequential-design-adsorption-for-small-molecules-in-MOFs)
[[Publication]](https://pubs.rsc.org/en/content/articlelanding/2022/me/d1me00138h/unauth)
{% include figure image_path="/assets/images/AL_workflow.png" caption="Active learning workflow for modeling single component gas adsorption in a MOF" %}

### Discovery of nanoporous materials for a multi-purpose gas sensor from the CoRE MOF database (collaborated with Jack Gonzalez)
* Led and assisted an undergraduate student, Jack Gonzalez, to calculate selectivity of 30 gas mixtures (all combinations of CO<sub>2</sub>, N<sub>2</sub>, N<sub>2</sub>O, O<sub>2</sub>, CH<sub>4</sub>, and H<sub>2</sub>O) on the CoRE-MOF database (> 9000 structures), performed the structure-property analysis, and recommended MOF candidates for gas sensing. For more details, visit the github link or the publication landing page of the project.
[[Github]](https://github.com/JackTGonzalez/Sensor-Modeling)
[[Publication]](https://pubs.acs.org/doi/abs/10.1021/acs.jced.2c00443)
{% include figure image_path="/assets/images/TOC.png" caption="Computational workflow for discovery of sensor candidate materials from the CoRE database" %}

### Machine learning and descriptor selection for the computational discovery of metal-organic frameworks (Review Project)
* Through my literature review work, a paper was published which highlighted how machine learning and specific descriptors (chemical or physical features fed to a machine learning model) were used to design and discover new MOFs. The papers also includes many pedagogical introduction to the field of MOFs, Machine learning, feature selection, as well commentary on the future of the domain.
[[Publication]](https://www.tandfonline.com/doi/full/10.1080/08927022.2021.1916014)
{% include figure image_path="/assets/images/ML_workflow_final.png" caption="Typical computational workflow adopted for building ML model for MOF related systems" %}
