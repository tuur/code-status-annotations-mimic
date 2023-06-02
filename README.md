# code-status-annotations-mimic
For 1174 MIMIC-III (Version: 1.4) [1] discharge summaries, the in-text mentions of patient's do-not-resuscitate and/or do-not-intubate status or full code status were annotated.

## Background
Do-not-resuscitate (DNR) and do-not-intubate (DNI) code status during hospital stay are important predictors for several clinical outcomes like length of hospital stay, survival, and disease progression. The annotation work was part of a project aiming to assess the impact of using NLP tools while conducting an association study [3].

## Methods
In a first round, both authors each annotated half of the 1174 discharge summaries. In a second round, both authors checked each other's annotations. Any disagreements were discussed and resolved. The annotations were performed using the freely available open source Brat annotation tool [2].

## Data Description
The annotations consist of three labels:

FULL (indicating full code)
DNR_DNI (indicating do-not-resuscitate and/or do-not-intubate)
OTHER (any other code status mentions, e.g., comfort measures)
The selection process of the 1174 discharge summaries is described in an arXiv article [3], and corresponds to a subset of the patients in the N2C2 NLP Challenge on extraction of social determinants of health [4]. 

## Usage Notes
The BRAT annotation format was used (.ann files). An example (23327.ann) is:

T1    FULL 8163 8172    full code
T2    DNR_DNI 8429 8436    DNR/DNI
This format contains one annotated mention per row. Per row first an event id is given (for row 1: T1), then 4 spaces, then the annotated label (for row 1: FULL), then one space followed by the character index of the start of the annotated span (for row 1: 8163), then another space, followed by the end of the annotated span (for row 1: 8172), followed by another four spaces and the annotated text (for row 1: full code).

The actual discharge summaries are not in this repository. The file names correspond to the EVENTROWID of the MIMIC-III (Version: 1.4) NOTEEVENTS table, and can in this way be linked to the MIMIC-III discharge summaries (e.g., file 23327.ann corresponds to EVENTROWID 23327 in the NOTEEVENTS table).

When using these data, please cite the original publication:
- Sushil, Madhumita, et al. "Cross-institution text mining to uncover clinical associations: a case study relating social factors and code status in intensive care medicine." arXiv preprint arXiv:2301.06570 (2023).

## Release Notes
Version 1 (initial upload).

## Ethics
Due to the nature of the work, which involved the use of de-identified data obtained from a publicly available dataset, and the fact that the shared annotations do not contain identifiable information (the clinical notes are not included, only the labels) ethical review was not performed.

## Acknowledgements
This research was funded by the Dutch Research Council, as part of the project “RAISE: Responsible AI Science Explorations” (Grant Number NWA.1418.22.008).

## Conflicts of Interest
None declared

## References
1) Johnson AE, Pollard TJ, Shen L, Lehman LW, Feng M, Ghassemi M, Moody B, Szolovits P, Anthony Celi L, Mark RG. MIMIC-III, a freely accessible critical care database. Scientific data. 2016 May 24;3(1):1-9.
2) Stenetorp P, Pyysalo S, Topić G, Ohta T, Ananiadou S, Tsujii JI. BRAT: a web-based tool for NLP-assisted text annotation. InProceedings of the Demonstrations at the 13th Conference of the European Chapter of the Association for Computational Linguistics 2012 Apr (pp. 102-107).
3) Sushil M, Butte AJ, Schuit E, van Smeden M, Leeuwenberg AM. Cross-institution text mining to uncover clinical associations: a case study relating social factors and code status in intensive care medicine. arXiv preprint arXiv:2301.06570. 2023 Jan 16.
4) Lybarger K, Yetisgen M, Uzuner Ö. The 2022 n2c2/UW Shared Task on Extracting Social Determinants of Health. arXiv preprint arXiv:2301.05571. 2023 Jan 13.
