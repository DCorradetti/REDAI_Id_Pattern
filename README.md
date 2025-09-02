# Identification of Stone Deterioration Patterns with Large Multimodal Models.
[![Paper](https://img.shields.io/badge/J._Cultural_Heritage-Paper-blue)](https://doi.org/10.1016/j.culher.2024.11.017) [![Paper](https://img.shields.io/badge/Multi--Agent_System-arXiv:2508.13872-b31b1b?logo=arxiv)](https://arxiv.org/abs/2508.13872) <br>
[![Paper](https://img.shields.io/badge/REDAI-Project-yellow)]() [![Paper](https://img.shields.io/badge/NEW_RELEASE-Multi--Agent_System-brightgreen)]() [![Paper](https://img.shields.io/badge/version-2.0-blue)]() <br>
	
[![PWC](https://img.shields.io/badge/Paper-Code-lightgrey)](https://paperswithcode.com/sota/image-classification-on-id-pattern-dataset?p=identification-of-stone-deterioration)

[Corradetti Daniele](https://ualg.academia.edu/DanieleCorradetti) & [José Delgado Rodrigues](https://www.researchgate.net/profile/Jose-Rodrigues-39)  <br><br>
*STAP Reabilitação Estrutural, SA, Rua General Ferreira Martins 8 - 9B, Algés, 1495-137, Portugal*<br>
*Grupo de Fisica Matematica, Instituto Superior Tecnico, Av. Rovisco Pais, Lisboa, 1049-001, Portugal* <br>
*Departamento de Matematica, Universidade do Algarve, Campus de Gambelas, Faro, 8005-139, Faro, Portugal* <br>

This repository is aimed to collect the data and code used for *Identification of Stone Deterioration Patterns with Large Multimodal Models* by Daniele Corradetti & José Delgado Rodrigues. 

[![Paper](https://img.shields.io/badge/TEST-Id_Pattern-yellow)]() Test Id_Pattern for evaluating LMMs available here [Test_Id_Pattern](https://github.com/DCorradetti/REDAI_Id_Pattern/tree/main/Test_JDR) <br>
[![Paper](https://img.shields.io/badge/RESULTS-Id_Pattern-blue)]() Results of GPT-4omni, Gemini 1.5 Pro, Claude 3 Opus available here [Results](https://github.com/DCorradetti/REDAI_Id_Pattern/tree/main/results) <br>

---
## Overview
The conservation of stone-based cultural heritage sites is a critical concern for preserving cultural and historical landmarks. With the advent of Large Multimodal Models (e.g. those developed by OpenAI GPT-4omni, Anthropic Claude 3 Opus and Google Gemini 1.5 Pro) is becoming increasingly important to define the operational capabilities of these models. In this work, we systematically evaluate the abilities of the main foundational multimodal models to recognize and classify anomalies and deterioration patterns of the stone elements that are useful in the practice of conservation and restoration of world heritage. After defining a taxonomy of the main stone deterioration patterns and anomalies, we asked the foundational models to identify a curated selection of 354 highly representative images of stone-built heritage, offering them a careful selection of labels to choose from. The result, which varies depending on the type of pattern, allowed us to identify the strengths and weaknesses of these models in the field of heritage conservation and restoration.

<img src="https://github.com/DCorradetti/REDAI_Id_Pattern/blob/main/results/World%20Heritage2.png?raw=true" width="800" />

---
## Introduction 

The preservation of cultural heritage sites is a critical challenge in the fields of archaeology, historic preservation, and conservation science. Stone monuments, buildings, and artefacts are subject to a wide range of deterioration processes over time, including weathering, erosion, biological growth, salt crystallization, and human-induced damage. Identifying and classifying these deterioration patterns is essential for developing effective conservation strategies and interventions. 

In recent years, advances in artificial intelligence and machine learning have opened up new possibilities for automated analysis of stone-built heritage. In particular, the development of large multimodal models (LMM) has the potential to revolutionize the way we study and preserve the world’s stone-built heritage. Unlike earlier specialized neural networks (a form of narrow AI), modern LMMs like GPT-4o, Claude 3 Opus, and Gemini 1.5 Pro aim to be general models capable of recognizing a wide range of deterioration patterns and performing complex diagnoses.

Despite the extensively studied abilities of these LMMs, their specific skills and limitations for heritage conservation applications have not been systematically evaluated. This project aims to address that gap by providing an extensive and systematic evaluation of how state-of-the-art multimodal models perform on a diverse range of stone pathologies.

---
## Evaluating the Large Multimodal Models

The correct observation and identification of deterioration patterns is the first and most important step for conservation professionals. Automating this process would be a significant improvement, making conservation activities more affordable and attractive. Our objective is to develop an AI tool that can correctly identify deterioration patterns, document their distribution, and estimate the areas for intervention.

Before building a dedicated tool, we first decided to benchmark the performance of three last-generation LMMs. This involved two key steps: creating a taxonomy of stone deterioration patterns and selecting a representative set of images. To avoid ambiguity, we defined a comprehensive taxonomy based on the ICOMOS-ISCS Glossary, which includes the following 41 patterns:

*Abrasion, adherent deposit, algae, alveolisation, biological colonisation, black crust, blistering, chipping, contour spalling, corrosion of inserted elements, crack, craquele, dark diffuse biocolonisation, deformation, degraded joint filling, detachment of mortar layer, differential erosion, discolouration, efflorescence, encrustation, erosion, film flaking, fracture, fragmentation, gap, graffitti, granular disintegration, lichens, loose deposit, misalignment elements, moist area, moss, open joint, patina, perforation, pitting, plant, powdering, soiling, spalling, staining, sugaring, thin black deposit, unaesthetic joint filling, unaesthetic patch repair.*

---
## Initial Results with Foundational Models
Our initial tests showed that the best-performing foundational model was OpenAI's **GPT-4o**, which correctly identified the target pathology in **42.1%** of cases. It was followed by **Gemini 1.5 Pro** at **38.9%** and **Claude 3 Opus** at **24.3%**.

<img src="https://github.com/DCorradetti/REDAI_Id_Pattern/blob/main/results/ResultComparison4.png?raw=true" width="600" />
<img src="https://github.com/DCorradetti/REDAI_Id_Pattern/blob/main/results/PathologiesByModel_Percentage.png?raw=true" width="600" />

Interestingly, no single model was the best across all categories. For example, Gemini 1.5 Pro was superior in identifying patterns like *abrasion* and *alveolisation*. These initial results demonstrate that while these models have enormous capabilities, they are not yet prepared for practical use in heritage conservation, where accuracy approaching 100% is necessary for reliable deployment.

---
## Update: The RED.AI Id-Pattern Multi-Agent System 💡
Building on our initial findings, we developed a more advanced, **multi-agent system** called `Id-Pattern` as part of the `RED.AI` (Reabilitação Estrutural Digital através da AI) project. This new approach addresses the limitations of monolithic foundational models, such as "hallucinations," difficulty adhering to specialized terminology, and opaque decision-making processes.

### A New Agentic Architecture
Instead of relying on a single AI, the `Id-Pattern` system simulates a collaborative team of experts. The architecture consists of **five specialized AI agents**:
1.  **Lithologist**: Focuses on stone type, texture, and porosity.
2.  **Pathologist**: Expert in classifying degradation patterns.
3.  **Environmental Expert**: Evaluates factors like rain, wind, and pollution.
4.  **Conservator-Restorer**: Identifies previous interventions.
5.  **Diagnostic Coordinator**: Synthesizes all inputs into a final, integrated diagnosis.

Each agent, powered by OpenAI's `o4-mini` model, follows a three-phase workflow:
1.  **Individual Analysis**: Each agent formulates a preliminary diagnosis based on its specialty, guided by a rigid protocol and a **Retrieval-Augmented Generation (RAG)** system that provides specialized knowledge from technical documents.
2.  **Multidisciplinary Discussion**: The agents share their findings and comment on each other's work, simulating a technical meeting.
3.  **Consensus**: The Diagnostic Coordinator synthesizes the discussion, resolves conflicts, and produces a final, consensus-based diagnosis with a confidence level.

### New Results: A Leap in Performance
We tested this new system on a challenging set of 27 images containing multiple, complex deterioration patterns. The results show a dramatic improvement over the single foundational model.

| System | True Positives (TP) | False Positives (FP) | False Negatives (FN) | Precision | Recall (Sensitivity) | F1-Score |
| :--- | :---: | :---: | :---: | :---: | :---: | :---: |
| Foundational (o4-mini-high) | 73 | 51 | 126 | 58.9% | 36.7% | 45.2% |
| **Id-Pattern (Multi-Agent)** | **149** | **51** | **65** | **74.5%** | **69.6%** | **72.0%** |

The most significant gain is in **Recall (Sensitivity)**, which nearly doubled from 36.7% to **69.6%**. This means the multi-agent system is far more effective at identifying all present pathologies and drastically reduces omissions. The overall **F1-Score** also jumped from 45.2% to **72.0%**, confirming the `Id-Pattern` system is significantly more robust, balanced, and reliable for diagnostic tasks.

---
## Conclusions and Future Developments
These results indicate that a multi-agent approach is highly suitable for improving the automatic diagnosis of stone deterioration. The next phase of our research will focus on interpreting the causes of false positives and exploring new, even more robust agent architectures.

---
## Publications & Citing this Work

If you use the data or findings from this project in your research, please cite the relevant publications:

**For the Multi-Agent System (RED.AI Id-Pattern):**

> Corradetti, D., & Delgado Rodrigues, J. (2025). *RED.AI Id-Pattern: First Results of Stone Deterioration Patterns with Multi-Agent Systems*. arXiv preprint arXiv:2508.13872. [https://doi.org/10.48550/arXiv.2508.13872](https://doi.org/10.48550/arXiv.2508.13872)

```bibtex
@misc{corradetti2025redai,
    title={{RED.AI Id-Pattern: First Results of Stone Deterioration Patterns with Multi-Agent Systems}}, 
    author={Daniele Corradetti and José Delgado Rodrigues},
    year={2025},
    eprint={2508.13872},
    archivePrefix={arXiv},
    primaryClass={cs.CV}
}
```

For the initial benchmarking of foundational models:

Corradetti, D., & Delgado Rodrigues, J. (2025). Identification of stone deterioration patterns with large multimodal models. Definitions and benchmarking. Journal of Cultural Heritage, 71, 175-183. https://doi.org/10.1016/j.culher.2024.11.017
```bibtex
@article{corradetti2025identification,
  title={Identification of stone deterioration patterns with large multimodal models. Definitions and benchmarking},
  author={Corradetti, Daniele and Rodrigues, Jos{\'e} Delgado},
  journal={Journal of Cultural Heritage},
  volume={71},
  pages={175--183},
  year={2025},
  publisher={Elsevier},
  doi={10.1016/j.culher.2024.11.017}
}
```
