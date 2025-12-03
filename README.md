# Inverse Design and Experimental Validation in the Ba-Ti-O System Using MatterGen and MatterSim

Colette Abadie, Rebecca Gracia, Hongrui Zhang, Brendon Jaeger

CH752 Advanced Topics in Chemical Physics/ENGMS508 Computational Material Science

Instructor: James Chapman

December 3rd, 2025

## Author Contributions
Colette Abadie: Contributed to writing the project design proposal. Successfully configured and executed MatterGen and MatterSim on Google Colab for shared group access. Cleaned, organized, and annotated the codebases for both MatterGen and MatterSim. Consolidated all MatterGen-generated CIF files into an organized directory structure, relaxed all structures through MatterSim, and organized all MatterSim relaxation outputs. Contributed to the writing of the final document, and oral presentation.

Rebecca Gracia: Contributed to writing the project design proposal and created the workflow figures used in the project outline and final document. Generated all 800 structures using MatterGen. Wrote the full validation pipeline, including downloading Crystallography Open Database (COD) structures, converting formats, and comparing them with the relaxed structures. Contributed to writing the final document and oral presentation.

Hongrui Zhang: Proposed the project idea and drafted the initial project description and design proposal. Contributed to configuring MatterGen on Google Colab and cleaning portions of the code. Contributed to writing the final document and presentation.

Brendon Jaeger: Contributed to writing the project design proposal, created and maintained the GitHub repository, and uploaded all project files to the GitHub. Prepared outlines for both the final written report and the oral presentation. Contributed to a substantial portion of the writing across all documents.

## Project Overview
This repository contains the complete code and all input and output files for Inverse Design and Experimental Validation of the Ba-Ti-O System. Using Microsoft Research’s MatterGen generative model and MatterSim relaxation engine, we generated and relaxed 800 crystal structures and validated 134 BaTiO3 structures against experimental and DFT references from the Crystallography Open Database (COD). 

## Repository Structure
508-Final-Project-Group-1/ \
├── README.md                          # This file\
├── notebooks/\
│   ├── 01_MatterGen_Generation.ipynb  # Structure generation pipeline\
│   ├── 02_MatterSim_Relaxation.ipynb  # Geometry relaxation pipeline\
│   ├── 03_File_Consolidation.ipynb    # CIF file organization\
│   └── 04_Validation_Pipeline.ipynb   # COD comparison and validation\
├── data/\
│   ├── generated_structures/         	# Raw MatterGen outputs (800 CIF files)\
│   ├── combined_cif/                 	# Consolidated and renumbered CIF files\
│   ├── relaxed_structures/            	# MatterSim relaxed structures (134 files)\
│   ├── cod_references/                	# COD reference structures (57 files)\
│   └── validation_results/            	# Match classification outputs\
├── results/\
│   ├── energy_summary.csv         	# Single-point energies before relaxation\
│   ├── relaxation_summary.csv      	# Relaxation energies and metadata\
│   ├── validation_summary.csv      	# Match quality metrics (RMSD, angles, volume)\
│   └── figures/                       	# Generated plots and visualizations\
├── docs/\
│   ├── Final_Document.pdf          	# Complete written report\
│   ├── Project_Proposal.pdf          	# Initial design proposal\
│   └── Presentation.pdf             	# Final presentation slides\
└── requirements.txt                  	# Python package dependencies

## Project Summary
### Objective:
Evaluate the effectiveness of MatterGen and MatterSim for inverse design of stable inorganic materials by:\
Generating 800 Ba-Ti-O structures with MatterGen\
Relaxing structures to local energy minima with MatterGen\
Validating geometric accuracy against experimental COD references\
Achieving at least 65% validation rate for verifiable structures

### Key Results:
Generated: \
800 structures in Ba-Ti-O chemical system\
134 structures matched BaTiO3 target stoichiometry\
57 structures matched COD references\
7 exact\
48 near\
2 similar\
Identified 77 potentially novel phases with no COD match\
Exceeded 65% validation goal

## Computational Performance:
Platform: Google Colab with NVIDIA T4 GPU\
Generation Time: ~1 minute per structure (MatterGen)\
Relaxation Time: ~15 seconds per structure (MatterSim)\
Platform: Visual Studio Code with CPU\
Validation Time: ~1 second per structure (7min for 800 structures)

## Installation and Setup
### Prerequisites

Python 3.10+\
CUDA-capable GPU\
Google Colab account for notebook execution

## Environment Setup

### Clone this repository

git clone https://github.com/bjaeger5/508-Final-Project-Group-1.git \
cd 508-Final-Project-Group-1
### Install dependencies
pip install -r requirements.txt

## Key Dependencies

torch==2.5.1+cu121 \
pytorch-lightning==2.0.6 \
ase==3.25.0 \
pymatgen==2024.1.26 \
mattersim \
numpy<2.0 \
hydra-core==1.3.1 \
pandas \
matplotlib \
tqdm 

