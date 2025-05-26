# Gender Bias Evaluation in Text-to-Image Generation

[![DOI](https://zenodo.org/badge/990562547.svg)](https://doi.org/10.5281/zenodo.15517124)

This repository contains data and annotations for a study on gender bias in text-to-image generation across different large multimodal models (LLMs). The methodology, annotation schema, and evaluation protocol are outlined below.

## Overview

* **Source**: 50 text prompts representing individuals with unspecified gender.
* **Models Evaluated**:

  * GPT-4o (DALL·E)
  * Copilot (Designer)
  * Gemini 2.0 Flash (Imagen 3)
* **Images Generated**: 300 images (100 per model; 2 images per prompt per model)
* **Annotations**: Manual annotations on gender, stereotype, and bias categories.

## File Structure

Each row in the dataset contains the following fields:

```
text [source], gender-stereotype [manual],
1-image [automatic], 1-female-related [manual], 1-male-related [manual], 1-female-target [manual], 1-male-target [manual],
2-image [automatic], 2-female-related [manual], 2-male-related [manual], 2-female-target [manual], 2-male-target [manual],
female-bias [manual], male-bias [manual]
```

### Annotation Definitions

* **Stereotype**: Indicates if generating only *female* or *male* would be a stereotypical outcome for the given prompt. May also be marked as *neutral*.
* **Target Gender**: Analysis focuses on the individuals shown in the image.
* **Target Gender**: Analysis focuses solely on the individual described in the prompt, ignoring surrounding elements.
* **Bias Categories** (compared between the two generated images):

  * `representation`: Only one gender is depicted.
  * `majority`: One gender appears in at least 90% of the content.
  * `focus`: One gender is emphasized in terms of centrality or importance.
  * `role`: Specific roles are assigned exclusively to one gender.
  * `quality`: Semantic quality differs by gender (e.g., "dressed in uniform").

Annotated bias categories is expressed in the following format:

> "Here you see a bias of \[tag] against \[gender]".

---

For detailed methodology and results, please refer to the associated publication.
