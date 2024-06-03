# Identification of Stone Deterioration Patterns with Large Multimodal Models. 
[![Paper](https://img.shields.io/badge/REDAI-Project-yellow)]()[![Paper](https://img.shields.io/badge/version-1.0-blue)]() <br>
[![Paper](https://img.shields.io/badge/CS-Paper-b31b1b?logo=arxiv&logoColor=red)](https://arxiv.org/) 

[Corradetti Daniele](https://ualg.academia.edu/DanieleCorradetti) & José Delgado Rodrigues
*Grupo de Fisica Matematica, Instituto Superior Tecnico, Av. Rovisco Pais, Lisboa, 1049-001, Portugal*<br>
*Departamento de Matematica, Universidade do Algarve, Campus de Gambelas, Faro, 8005-139, Faro, Portugal*<br>

This repository is aimed to collect the data and code used for *Identification of Stone Deterioration Patterns with Large Multimodal Models* by Daniele Corradetti & José Delgado Rodrigues. 

## Overview
The conservation of stone-based cultural heritage sites is a critical concern for preserving cultural and historical landmarks. With the advent of Large Multimodal Models (e.g. those developed by OpenAI GPT-4omni, Anthropic Claude 3 Opus and Google Gemini 1.5 Pro) is becoming increasingly important to define the operational capabilities of these models. In this work, we systematically evaluate the abilities of the main foundational multimodal models to recognize and classify anomalies and deterioration patterns of the stone elements that are useful in the practice of conservation and restoration of world heritage. After defining a taxonomy of the main stone deterioration patterns and anomalies, we asked the foundational models to identify a curated selection of 354 highly representative images of stone-built heritage, offering them a careful selection of labels to choose from. The result, which varies depending on the type of pattern, allowed us to identify the strengths and weaknesses of these models in the field of heritage conservation and restoration.
 <div>
  <img src="https://github.com/neuraldl/DLAtypicalSerotoninergicCells/blob/main/images/Figure2.png" alt="Figure 2" width="368" style="display:inline-block;" />
  <img src="https://github.com/neuraldl/DLAtypicalSerotoninergicCells/blob/main/images/Figure3.png" alt="Figure 3" width="400" style="display:inline-block;" />
</div>

## Introduction 

The preservation of cultural heritage sites is a critical challenge in the fields of archaeology, historic preservation, and conservation science. Stone monuments, buildings, and artefacts are subject to a wide range of deterioration processes over time, including weathering, erosion, biological growth, salt crystallization, and human-induced damage (Doehne & Price, 2010). Identifying and classifying these deterioration patterns is essential for developing effective conservation strategies and interventions. 

In recent years, advances in artificial intelligence and machine learning have opened up new possibilities for automated analysis of stone-built heritage. In particular, the development of large multimodal models (LMM) - i.e., AI systems that can process and generate multiple types of data, including text, images, and audio (Yin et al., 2023) - has the potential to revolutionize the way we study and preserve the world’s stone-built heritage. Indeed, it is important to immediately note the difference between these models and those resulting from specific neural networks dedicated to identifying specific deterioration patterns as they were usually developed prior to 2022. Indeed, these neural networks were classical examples of narrow artificial intelligence (Morris et al., 2023) visual recognition systems created ad hoc for specific stone deterioration patterns through transfer learning from neural networks structured for specific segmentation and classification problems (most existing studies have focused on narrow, specialized tasks like crack detection or material classification, often using small datasets and custom-built algorithms cfr. Oses et al, 2014; Câmara et al., 2023; Mishra & Lourenço, 2024). On the other hand, the current LMMs, such as OpenAI’s GPT-4omni, Anthropic’s Claude 3 Opus, and Google’s Gemini 1.5 Pro, aim to achieve a general model capable not only of recognizing all specific deterioration patterns with the same model but also of performing complex diagnoses through linguistic operations or special cognitive architectures and potentially suggesting specific interventions (e.g., Saab et al., 2024; Brown et al., 2020).

Despite the extensively studied abilities of these LMMs, the specific skills and limitations of models for heritage conservation applications have not been systematically evaluated. The increasing integration of these models into human operational workflows thus necessitates an extensive and systematic evaluation of how state-of-the-art multimodal models perform on a diverse range of stone pathologies and anomalies, using large, representative image sets.

## Evaluating the Large Multimodal Models

Deterioration patterns are the visible signs of the processes that continually take place in any built object. By their nature, deterioration processes are not visible and it is through the signs they impose or originate that scientists and professionals interpret and resolve them. In this sense, the correct observation and identification of existing patterns is the first and most important action that conservation professionals must take care of. Traditionally, this step is carried out through direct inspection of the object, which involves exhaustive observation of exposed surfaces and detailed documentation of all relevant data collected. Having automatic processing of observational data and correct identification of deterioration patterns would be a relevant improvement in the preparation of conservation interventions, which could end up being a high cost/benefit option that would contribute to making conservation activities more affordable and attractive. The objective of this study is to obtain an AI tool capable of correctly identifying deterioration patterns, graphically documenting their distribution throughout the object, and calculating areas and estimating costs to carry out the corresponding conservation intervention. Before embarking on designing a dedicated AI tool to specifically address the project’s objectives, we decided to systematically evaluate the performance of three of the last generation LMMs on stone deterioration patterns recognition, which required a comprehensive benchmarking study. The preparation of the test involved two key steps: creating a taxonomy of stone deterioration patterns and selecting a representative set of images for each pattern. In some preliminary trials, LMMs were allowed to use an open taxonomy, which showed that patterns were described in colloquial terms that varied from case to case, even when they described the same pattern. 

To avoid ambiguity in interpretations as much as possible and to focus the description made by LMMs, a comprehensive taxonomy of stone deterioration patterns relevant to world heritage conservation has been defined. It is largely based on the ICOMOS-ISCS Glossary of deterioration patterns (ICOMOS 2008), with some adaptations to better meet the needs of this activity, following the consensus gathered in a quick consultation with some professionals in the area. After careful evaluation of the many terms currently used to describe such patterns, the following list was selected:

*Abrasion, adherent deposit, algae, alveolisation, biological colonisation, black crust, blistering, chipping, contour spalling, corrosion of inserted elements, crack, craquele, dark diffuse biocolonisation, deformation, degraded joint filling, detachment of mortar layer, differential erosion, discolouration, efflorescence, encrustation, erosion, film flaking, fracture, fragmentation, gap, graffitti, granular disintegration, lichens, loose deposit, misalignment elements, moist area, moss, open joint, patina, perforation, pitting, plant, powdering, soiling, spalling, staining, sugaring, thin black deposit, unaesthetic joint filling, unaesthetic patch repair.*
