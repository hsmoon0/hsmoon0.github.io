---
title: "Research Overview"
permalink: /research/
author_profile: true
---

My work spans systems neuroscience, multimodal neuroimaging, and machine
learning to reveal mechanisms underlying Alzheimer’s disease risk,
neurodegeneration, and brain aging. I work across mouse behavior, transcriptomics, 
connectomics, imaging biomarkers, and deep learning pipelines. 




## 1. Olfactory Neuroscience of Alzheimer’s Disease Risk in APOE Mouse Models

**Related Publication:**  
Moon et al., 2025 — https://doi.org/10.3390/brainsci15080863

I studied how Alzheimer’s disease risk first emerges in the sensory systems, particularly
the olfactory circuit, one of the earliest and most vulnerable networks affected in AD.
My work combines behavioral neuroscience, high resolution diffusion MRI, tractography,
and blood-to-brain transcriptomics to dissect how APOE genotype, age, immune background,
and diet shape odor-guided behavior and its underlying neural circuits. I conducted a comprehensive battery of olfactory assays, including odor salience across
multiple concentrations, habituation/dishabituation to assess novelty detection, and
short, long, and extended term odor memory. These paradigms capture perceptual
sensitivity, learning, exploratory drive, and memory consolidation. Across APOE cohorts,
aging and high-fat diet intensify olfactory deficits in APOE4 carriers, whereas APOE2
mice show greater behavioral resilience. Memory tasks reveal that APOE4 mice exhibit
the least improvement from short to long term odor memory and the steepest decline
from 24 h to 48 h, indicating weaker consolidation and retention. In contrast, APOE2 mice
maintain stronger extended term memory across age and diet conditions. These patterns highlight genotype-specific sensory cognitive
vulnerability within olfactory-hippocampal networks.

To understand the neural basis of these behavioral changes, I pair behavioral testing with
ex vivo high resolution diffusion MRI (45 μm isotropic), microstructural mapping, and
connectome reconstruction. This approach reveals genotype and age-related
alterations in olfactory-limbic areas, including the piriform cortex, amygdalo piriform
transition area, entorhinal cortex, hippocampus, and subicular complex which are regions that
support odor memory and are among the earliest affected by AD pathology. Blood and
brain RNA-seq further identify eigengene modules whose expression patterns mirror
diffusion and connectivity changes in these regions, with enrichment for synaptic signaling,
ion homeostasis, neurotransmitter regulation, and glutamatergic processes.

The key finding from this line of work is that olfactory behavior provides an early and
highly sensitive window into Alzheimer’s disease vulnerability. Reduced novelty
detection, slower habituation, and weaker long term and extended term odor memory in
APOE4 mice closely align with microstructural disruption in piriform, entorhinal,
hippocampal, and subicular circuits that are essential for odor learning and recognition.
Elastic Net multiset CCA reveals diffusion subnetworks within these regions that
account for a substantial portion of variance in odor guided behaviors (up to 24%). 
Blood eigengene modules also track microstructural changes in these same 
olfactory-limbic pathways, linking peripheral molecular signatures to central 
sensory cognitive decline. Together, this work establishes olfactory behavior, 
olfactory memory circuits, and their associated transcriptomic patterns as 
a translatable biomarker axis for early Alzheimer’s disease risk.



### Multimodal Imaging of Olfactory-Limbic Circuit Vulnerability

<img src="/images/figure4_part1.png" alt="Hierarchical clustering of diffusion and volumetric microstructure across olfactory–limbic regions including piriform, entorhinal, hippocampal, and subicular areas, revealing risk-associated regional groupings." width="800">

**Figure. Multimodal imaging and network analysis reveal olfactory–limbic circuits shaped by Alzheimer’s disease risk factors.**  
The first panel shows clustering of diffusion and volumetric microstructure across key
olfactory and memory-associated regions. The second panel shows high-weight multimodal
connections identified by Elastic Net multiset CCA that explain a substantial portion of
variance in odor-guided behaviors.

---


## 2. Feature Attention Graph Neural Network for Brain Age Estimation

**Related Publication:**  
Moon et al., 2024 — https://doi.org/10.1162/imag_a_00245

I develop computational models that reveal how Alzheimer’s disease risk alters the aging trajectory of the brain, focusing on large scale structural networks measured with diffusion MRI. In this work, I introduced the Feature Attention Graph Neural Network (FAGNN), a multimodal deep learning architecture designed to capture subtle, heterogeneous alterations in full brain connectomes. The model integrates structural connectivity, spatial learning behavior from Morris water maze trajectories, and demographic and genetic risk factors such as APOE genotype, diet, sex, and humanized NOS2 status. A core part of the framework is the Quadrant Attention Module, which processes each quadrant of the connectome separately and assigns importance score to individual connections, enabling the model to identify hemispheric and interhemispheric patterns that reflect early neurobiological changes linked to Alzheimer’s disease risk.

This integrated structure allowed the FAGNN to achieve a high level of accuracy, with a mean absolute error of 31.85 days, outperforming simpler baseline models and demonstrating the value of fusing connectomic, behavioral, and risk factor information. By comparing predicted brain age with chronological age, the model revealed that high-fat diet and humanized NOS2 accelerate aging trajectories, particularly in older mice, and that the effects of APOE genotype interact with these environmental and immune-related variables. The attention maps generated by the model highlighted connections involving the cingulum, corpus callosum, striatum, hippocampus, thalamus, hypothalamus, cerebellum, and piriform cortex. These pathways are known to support sensory integration, memory, and cross-hemispheric communication and showed significant age-dependent differences when examined using diffusion MRI metrics such as fractional anisotropy and return-to-origin probability.

These results demonstrate that brain aging is not uniform but instead concentrates within interconnected networks linking limbic, basal ganglia, and interhemispheric systems. The FAGNN framework shows how structural connectivity can be used to quantify accelerated or resilient aging in mouse models of Alzheimer’s disease risk, offering a mechanistic understanding of how aging, genetic and environmental factors reshape subtle white matter pathway changes before overt and visible pathology appears.



### Overview of the FAGNN Architecture

<img src="/images/fagnn_figure1.png" alt="Overview of the Feature Attention Graph Neural Network architecture integrating traits, behavior, and structural connectomes. The model processes risk factor traits through a 1D CNN, spatial learning behavior through a 2D CNN, and diffusion MRI tractography-derived connectomes through a Graph Neural Network with a Quadrant Attention Module, ultimately combining outputs through a fully connected block to estimate brain age and identify influential connections." width="900">

**Figure.** Schematic illustration of the Feature Attention Graph Neural Network (FAGNN) for brain age estimation.  

The model integrates three major data domains: risk factor traits, behavior, and structural connectomes. Traits such as age, sex, APOE genotype, humanized NOS2 status, and diet are processed through a 1D CNN that extracts patterns reflecting global influences on aging. Behavioral metrics derived from Morris water maze trajectories (distance, search strategies, learning curves) are processed through a 2D CNN to capture task-relevant cognitive signatures. Structural connectivity matrices derived from diffusion MRI tractography are passed through the Quadrant Attention Module (QAM), which divides each connectome into four quadrants, applies multi-head attention to score edges within each quadrant, then recombines them to form a weighted graph for GNN processing. Outputs from the CNN modules and the attention weighted GNN are fused through a fully connected block to generate a predicted brain age. By comparing predicted brain age to chronological age, the model identifies accelerated or resilient aging trajectories and highlights subnetworks whose connectivity patterns most strongly reflect Alzheimer’s disease risk. This architecture allows the model to capture both global influences on aging and connectome-level alterations across limbic, basal ganglia, and interhemispheric pathways.

---

