[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0) [![License: CC BY-NC-SA 3.0](https://img.shields.io/badge/License-CC_BY--NC--SA_3.0-lightgrey.svg)](https://creativecommons.org/licenses/by-nc-sa/3.0/)

# Universal Decompositional Semantics (UDS) and Child Speech

## Hello and welcome! <img src="https://raw.githubusercontent.com/MartinHeinz/MartinHeinz/master/wave.gif" width="30px">

Caroline Gish | cngish98@comcast.net

---

## Overview

This project was undertaken by **Caroline Gish** for the course project in the Data Science for Linguists 2022 course.

The overall goal of this project was to see how the UDS semantic annotation framework was equipped to handle child speech. 

To read what my classmates had to say about my project during the semester, be sure to visit my [project guestbook](https://github.com/Data-Science-for-Linguists-2022/Class-Lounge/blob/main/guestbooks/guestbook_caroline.md)!

Data were sourced from the both the [Decomp repository](https://github.com/decompositional-semantics-initiative/decomp) of the Decompositional Semantics Initiative and the [CHILDES](https://childes.talkbank.org/) child language component of the TalkBank system.


## Directory

### Main repository files

- [**`final_report.md`**]() 
- [`README.md`](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/README.md) is what you are currently reading! It contains an overview of my project, links to all files, and information on the licensing and works cited.
- [`presentation_gish.pdf`](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/presentation_gish.pdf) is a PDF copy of my presentation slides for the presentation I gave in the [2022 Data Science for Linguists](https://naraehan.github.io/Data-Science-for-Linguists-2022/) class. These slides do not contain any of my notes, so please feel free to contact me for more information about them!
- [`progress_report.md`](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/progress_report.md) contains three different progress reports each detailing my project progress over the course of the semester.
- [`project_plan.md`]() is my initital project plan that I proposed at the beginning of the semester.
- [`LICENSE.md`](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/LICENSE.md) is the license for the code elements of the repository.
- [`LICENSE-cc.md`](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/LICENSE-cc.md) is the license for the non-code elements of the repository.
	


### Subdirectories

- [`code_notebooks/`](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/tree/main/code_notebooks) - contains all of my Jupyter notebooks (`.ipynb` files) and license information for the PyLangAcq library and Decomp toolkit I used
	- [`childes_exploration.ipynb`](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/code_notebooks/childes_exploration.ipynb) is my all my code dedicated to the CHILDES dataset
	- [`UDS_exploration_CRC`]() is all my code dedicated to the UDS dataset
- [`data_samples/`](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/tree/main/data_samples) contains samples of the CHILDES CHAT data separated into subdirectories by child grade level. The full dataset is available on [this page](https://childes.talkbank.org/access/Eng-NA/Hicks.html).
- [`resources/`](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/tree/main/resources) is a collection of handy resources and notes for ease of access
- [`visualizations/`](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/tree/main/visualizations) contains an example of a UDS graph and my plot graphs saved as `.png` files



## Licenses 

- The code content of this repo is covered by the [GNU General Public License v3](https://www.gnu.org/licenses/gpl-3.0.en.html), and the non-code content of this repo is covered under the [CC BY-NC-SA 3.0 license](https://creativecommons.org/licenses/by-nc-sa/3.0/).


## Citations

[The Universal Decompositional Semantics Dataset and Decomp Toolkit](https://aclanthology.org/2020.lrec-1.699) (White et al., LREC 2020)

ACL version: Aaron Steven White, Elias Stengel-Eskin, Siddharth Vashishtha, Venkata Subrahmanyan Govindarajan, Dee Ann Reisinger, Tim Vieira, Keisuke Sakaguchi, Sheng Zhang, Francis Ferraro, Rachel Rudinger, Kyle Rawlins, and Benjamin Van Durme. 2020. [The Universal Decompositional Semantics Dataset and Decomp Toolkit](https://aclanthology.org/2020.lrec-1.699/). In *Proceedings of the 12th Language Resources and Evaluation Conference*, pages 5698–5707, Marseille, France. European Language Resources Association.

Hicks, D. (1990). Kinds of texts: Narrative genre skills among children from two communities. In A. McCabe (Ed.), *Developing narrative structure*. Hillsdale, NJ: Erlbaum.

Additional references that go along with Hicks, D. (1990) include:

Berman, R. A. and D. I. Slobin (1994). *Relating events in narrative: A crosslinguistic de-velopmental study*. Hillsdale, NJ, Lawrence Erlbaum Associates.

Heath, S. (1983). *Ways with words: Language, life and work in communities and classrooms*. Cambridge, Cambridge University Press.

Quirk, R., S. Greenbaum, et al. (1972). *A grammar of contemporary English*. London, Longman.