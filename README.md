# Multitask Machine Learning-Based Prediction of Natural Compound Inhibitory Activities Targeting Mycobacterium tuberculosis Virulence Proteins
Tuberculosis (TB) remains a leading cause of global mortality, further complicated by multi-drug resistant strains. This project implements a Multitask Deep Learning approach to accelerate the early phase of drug discovery. By utilizing Graph Convolutional Networks (GCN), the model predicts the inhibitory activity (IC_50) of ligands against 10 essential Mycobacterium tuberculosis (MTB) virulence proteins simultaneously.+1The model leverages shared chemical features across multiple targets to improve prediction accuracy, particularly for targets with sparse experimental data.
# Technical Workflow
Data Curating & Labeling: Ligand data was sourced for 10 MTB targets (ClpC1, DprE1, FtsZ, InhA, GyrB, ClpC1, KatG, KasA, PanK, PanKB, RpoB ). Bioactivity was binarized based on a 1000 nM (1 \mu M) threshold for IC_50 values to define "active" vs "inactive" compounds.
# Molecular Featurization
Instead of traditional fingerprints, I used DeepChem’s ConvMolFeaturizer, which represents molecules as graphs (atoms as nodes, bonds as edges)
# Architecture
A GraphConvModel was built to perform multitask classification using Graph Convolutional layers followed by Batch Normalization and Dropout (0.3) to prevent overfitting. and for optimization, Adam optimizer with a learning rate of 0.001 was used.
# Deployment Readiness
The model, featurizer, and task list were serialized (exported as .zip, .pkl, and .json) for integration into a web-based screening tool.
# Performance Results
The model achieved high predictive power across all 10 targets, with a Mean Test ROC-AUC of 0.94. The model demonstrates a weighted average F1-score of 0.76, indicating robust performance in identifying active compounds even across diverse protein targets
# Impact of this project
This research contributes to computational drug discovery by Enabling a rapid prioritization of natural compounds for experimental validation and contribute in Reducing the time and expense associated with traditional high-throughput screening. it also Providing an open-access framework for researchers in low-resource settings to identify new anti-TB leads.
