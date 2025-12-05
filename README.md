# Authorial Filtering and Computational Models: A Dynamic Analysis of Umberto Eco’s Foucault’s Pendulum through a Fluid-Dynamics-Inspired Framework

Source code of the framework presented in *Authorial Filtering and Computational Models: A Dynamic Analysis of Umberto Eco’s Foucault’s Pendulum through a Fluid-Dynamics-Inspired Framework*, accepted at CHR 2025.

> Authorial-filtering plays a crucial role in constructing literary meaning. It is the narrative act of selectively activating, suppressing, or leaving certain information latent within a story. Umberto Eco's Foucault's Pendulum stands as a paradigmatic case of this phenomenon, as it exemplifies  a narrative  wherein presence and absence, action and potentiality, remain in constant flux through intra- and intertextual interplay. In this preliminary study, we propose a novel computational framework inspired by fluid dynamics to detect authorial-filtering information within literary texts. Applying this approach to Foucault's Pendulum, our results reveal how narrative motifs and topics flow, diffuse, and react throughout the text, closely mirroring the qualitative interpretations of domain experts. Our proposed framework not only sheds new light on Eco’s complex narrative mechanisms but also advances computational narratology by providing an interpretable model for digital literary analysis.

The  source code is available in the [Main.ipynb](Main.ipynb) file. The paper is available [here](https://anthology.ach.org/volumes/vol0003/authorial-filtering-computational-models-dynamic-s/).


## Input Data

The framework is designed to work with any literary text, but in this study we applied it to the Italian edition of Umberto Eco's *Foucault's Pendulum*. The following description refers to this specific case study, but the framework can be adapted to other texts by modifying the input data structure accordingly.

The code automatically:
1. Loads and preprocesses each `.docx` file
2. Normalizes specific names (e.g., "JacopoBelbo" → "Jacopo Belbo")
3. Fixes formatting issues (removes unwanted hyphens and spaces)
4. Segments text into paragraphs
5. Filters out empty or invalid paragraphs
6. Organizes content by chapter for analysis
7. Loads stopwords from the specified file for text preprocessing

To run the model, you need the following input files:

### 1. Chapter Files

The framework expects input files to be organized in a specific directory structure:

```
./
├── Chapter1_KETEL/
│   ├── C1_1.docx
│   ├── C1_2.docx
│   └── ...
├── Chapter2_HOKMAH/
│   ├── C2_1.docx
│   ├── C2_2.docx
│   └── ...
├── Chapter3_BINA H/
│   ├── C3_1.docx
│   ├── C3_2.docx
│   └── ...
└── Chapter4_HESED/
    ├── C4_1.docx
    ├── C4_2.docx
    └── ...
```

**Naming Convention:**
- **Directory names**: `Chapter{N}_{CHAPTER_NAME}` where:
  - `N` is the chapter number (1, 2, 3, 4)
  - `CHAPTER_NAME` corresponds to the chapter identifier:
    - Chapter 1: `KETEL`
    - Chapter 2: `HOKMAH` 
    - Chapter 3: `BINA H`
    - Chapter 4: `HESED`

- **File names**: `C{N}_{SECTION}.docx` where:
  - `N` is the chapter number
  - `SECTION` is the section number within that chapter (1, 2, 3, etc.)

**File Content Requirements:**
Each `.docx` file should contain the actual text content of the book section in Microsoft Word format (.docx) with standard UTF-8 encoding.

### 2. Ontology File

A JSON dictionary contains semantic relationships and entities for analysis. The file must be named `ontology.json`. For an example of this file's structure, we refer to our paper.



### 3. Stopwords File
A plain text file with one stopword per line. The file must be named `stopwords.txt`. Since we used the italian version of the novel, we employed Italian stopwords for text pre-processing.

## Output

The framework generates several types of visualizations and analyses to understand topic flow and authorial filtering patterns:

### Heatmap Visualization
The heatmap shows the temporal evolution of topic strengths across the text. Each row represents a paragraph, and each column represents a topic. The color intensity indicates the strength of each concept at different points in the narrative, revealing how themes emerge, peak, and fade throughout the text.

### Sankey Diagram
The Sankey diagram visualizes the flow of topics and entities through the narrative.  This visualization reveals the complex interconnections and transformations of narrative elements, highlighting Eco's sophisticated authorial filtering techniques.  We refer to our paper for further details.


## Requirements

All required Python packages as specified in [requirements.txt](requirements.txt). 


## References
If you use our code, please cite us:
```
@article{afzangari,
  title = {Authorial Filtering and Computational Models: A Dynamic Analysis of Umberto Eco's \\textit\{Foucault's Pendulum\} through a Fluid-Dynamics-Inspired Framework},
  author = {Lorenzo Zangari and Davide Picca and Riccardo Fedriga},
  year = {2025},
  journal = {Anthology of Computers and the Humanities},
  volume = {3},
  pages = {1123--1136},
  editor = {Taylor Arnold, Margherita Fantoli, and Ruben Ros},
  doi = {10.63744/yVYI1Je9wQvM}
}

```
