# Universal Decompositional Semantics and Child Speech

---

A project by **Caroline Gish** | cngish98@comcast.net

## Overview

### Table of contents

- [Introduction](#0-Introduction)
	- [Overall](#01-Overall)
	- [History and process of project](#02-History-and-process-of-project)
- [Background](#1-Background)
	- [UDS](#11-UDS)
	- [Decomp toolkit](12-decomp-toolkit)
	- [How do UDS and Decomp work?](#13-how-do-uds-and-decomp-work)
- [Data sourcing, cleaning, and what is of interest](#2-Data-sourcing-cleaning-and-what-is-of-interest)
	- [UDS and Decomp](#21-UDS-and-Decomp)
	- [CHILDES](#22-CHILDES)
- [Analysis](#3-Analysis)
	- [How it started](#31-How-it-started)
	- [How it ended up](#32-How-it-ended-up)
- [Conclusion](#4-Conclusion)
	- [On "try" constructions](#41-on-try-constructions)
	- [On UDS](#42-on-uds)
- [Citations](#5-Citations)
- [Extras](#6-extras)

## 0 Introduction

### 0.1 Overall

Up until recently, the state of semantic annotation frameworks has been limited to several independently-existing frameworks, each of which take a prototypical approach to semantic representation and annotation. These frameworks require highly-trained annotators to provide accurate annotations, and while they perform well for the cases they were built on, they are brittle in cases of (1) non-prototypical instances for a certain category, (2) a single instance fitting into multiple categories, and (3) capturing instances not considered at the time of the framework's design. Additionally, while there are many different semantic annotation datasets that take a decompositional approach, they are not utilized to their fullest extent due to the lack of a unified interface for the resources.

The Universal Decompositional Semantics (UDS) framework with the UDS dataset and Decomp toolkit, developed under the larger efforts of the Universal Decompositional Semantics Initiative, was created to provide a unified semantic parsing resource with robust coverage for non-prototypical instances. 

This project aims to explore the UDS framework and dataset to see how it handles the particular linguistic phenomena of "try" constructions that will be further expounded upon in the [data](#2-Data-sourcing-cleaning-and-what-is-of-interest) and [analysis](#3-Analysis) sections.

*For the rest of the report, "Decomp" refers to the Universal Decompositional Semantics Initiative, "UDS" refers to the framework, and the "Decomp toolkit" refers to the toolkit packaged with the UDS dataset.*

### 0.2 History and process of project

To my frustration and disappointment, this project ultimately proved quite challenging for me. I started out thinking that I would easily be able to navigate the UDS dataset with its built-in methods due, in part, to my relative lack of exploration when initially proposing the project and due, mainly, to the in-depth documentation I saw was provided along with the dataset and toolkit. This led me to want to both explore what UDS had to offer in terms of a novel semantic annotation framework *and* leverage it against another dataset comprising non-prototypical speech instances to see how it could handle such instances. As such, I chose a second dataset, the Hicks narrative corpus from the CHILDES databank system. 

As I began to attempt navigating and exploring the UDS dataset with the Decomp toolkit, I quickly learned that it was not as straightforward as I though it would be (and I knew going in that it would take some tinkering with). See my [progress reports](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/progress_report.md) for updates. After multiple [failed attempts](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/code_notebooks/archived_notebooks/uds_exploration.ipynb) and then a few only semi-successful attempts to even install the toolkit and import the corpus, I realized I needed external help and went to my professor, Dr. Na-Rae Han, for assistance. She graciously helped me work through some aspects of the dataset that were relevant to my exploration, and I ended up having to import the UDS dataset through [Pitt's Center for Research Computing](https://crc.pitt.edu/) OPEN ONDemand interface and do all my coding work through that. We concluded that the UDS dataset, while providing ample semantic information, should not accessed by the general public or a single student for the best results. 

Because it took so long to even access the information contained in the UDS dataset, the analysis portion of my project suffered, and though I was able to begin analysis on a specific linguistic phenomenon, I was unable to come to any solid conclusions regarding it.

Overall, my project became much less about child speech and much more about understanding what UDS has to offer and is aiming to accomplish in terms of semantic annotation resources. As a result, my final project ended up being very description-of-dataset, exploration, and qualitative-analysis heavy. 

## 1 Background

### 1.1 UDS 

The UDS dataset and Decomp toolkit were initially introduced with the release of the paper, aptly titled, ["The Universal Decompositional Semantics Dataset and Decomp Toolkit"](https://aclanthology.org/2020.lrec-1.699.pdf), which is a combined effort between many different people working in the Semantics field. In the words of the authors, UDS 
> unifies five high-quality, decompositional semantics-aligned annotation sets within a single semantic graph specification—with graph structures defined by the predicative patterns produced by the PredPatt tool and real-valued node and edge attributes constructed using sophisticated normalization procedures.

The goals of the Decompositional Semantics Initiative and the UDS dataset are to decompose more complex semantic classes into simple properties (that are still linguistically motivated) so that semantic annotation takes the form of many simple questions (able to be answered by native speakers) about phrases in context. In doing so, Decomp hopes to provide a semantic framework that is more robust and can parse non-prototypical cases.

An example of one of these sentences and potential simple questions asked about it are:

	S: The mug broke. 

	Q: Did the mug break?
	Q: Was the mug changed?
	Q: Did someone break the mug?
	Q: Did the mug move?

Crowd-sourced annotators can get to properties such as volition, change of state, causation, etc. by answering straightforward questions like those above without having to know what each of these properties mean. Annotators can easily answer with "probably yes" or "probably no" to any of these questions and provide how confident they are in each of their binary answers.

### 1.2 Decomp toolkit

The novelty of the Decomp toolkit that comes packaged with the UDS dataset is that it can take all the data for the sentences and represent them graphically. Here is an example of one of the fancy Decomp graphs:

<figcaption align = "center"><b>Fig.1 - Decomp graph</b></figcaption>

![Decomp graph](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/visualizations/uds-graph.png)

The blocks with purple headings pop up upon mouse-over of the various colored shapes denoting different kinds of nodes and edges (there are only three of these boxes being shown here currently because it is a static image). Information such as dependency relation and part of speech tags are not shown in the graph, but they are available in the dataset. 

*I was interested in generating these visualizations for the specific sentences with "try" constructions I was investigating, but I was never able to import the visualization model due to package incompatibilities.*

### 1.3 How do UDS and Decomp work?

The UDS dataset is comprised of three annotation layers built on English Web Treebank (EWT).

1. syntactic graphs: gold standard [Universal Dependencies (UD)](https://universaldependencies.org/) parses of the EWT
2. semantic graphs: predicate-argument structures extracted from the parses deterministically using PredPatt
3. semantic types: predicates, arguments, and their relationships from decompositional semantics aligned datasets 

Among the many, many things you can do with the Decomp toolkit, you are able to get the semantic nodes of a sentence. These semantic nodes, more specifically, are either a predicate node or an argument node.

<figcaption align = "center"><b>Fig.2 - Development sentence 539</b></figcaption>
<img src="https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/visualizations/dev_sent-539.png" alt="image of development sentence 539: I tried to do it on the HRonline web-site, but the procedure is too complicated." width="900"/>

<figcaption align = "center"><b>Fig.3 - Predicates and arguments for sentence ewt-dev-539</b></figcaption>
<img src="https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/visualizations/predArg_dev-539.png" alt="Predicates and arguments for sentence ewt-dev-539" width="300"/>

Development sentence 539 has three predicate nodes and five argument nodes. 


## 2 Data sourcing, cleaning, and what is of interest

### 2.1 UDS and Decomp

Because the UDS dataset is an established dataset and I utilized it more so as a semantic annotation framework instead of individual data points, I did not clean or augment it; I instead wanted to leverage it with another dataset to see how the framework performed. Before diving into the deep waters that are the UDS dataset, I needed to hone in on one specific linguistic phenomenon that I could further explore *using* UDS, and here is where the second dataset comes in. 


### 2.2 CHILDES

The dataset I chose to work with providing non-prototypical instances was the [CHILDES Narrative English Hicks Corpus](https://childes.talkbank.org/access/Eng-NA/Hicks.html). [CHILDES](https://childes.talkbank.org/) is the child language component of the [TalkBank System](https://talkbank.org/) organized by Brian MacWhinney at Carnegie Mellon University. Data in TalkBank, and therefore CHILDES, use the CHAT representation. I used the [PyLangAcq library for Language Acquisition Research in Python](https://pylangacq.org/index.html) to work with the CHILDES dataset because it provides easy access to the CHAT format (`.cha`) files. 

The Hicks Narrative Corpus is comprised of narratives by elementary-age children collected by researcher Deborah Hicks. The children were shown a shortened version of the silent film, “The Red Balloon,” and asked to tell the film's events in three different ways: as a news reporter, as a sportscaster, and as a storyteller. The narrative data were coded by utterances for linguistic forms that might mark genre differences in the coding tier of the data. 

There were many idiosyncrasies in the Hicks corpus that I had to keep in mind. Many of the child utterances were missing a coding tier, and many [codes listed out](https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/resources/coding_scheme.md) in the research description were not present in any of the coding tiers. Additionally, the coding tier annotations did not line up with the tokens, so it was challenging to figure out to what the annotations were related. 

I needed to pick a specific [linguistic phenomenon](https://nbviewer.org/github/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/code_notebooks/childes_exploration.ipynb#5.-Linguistic-phenomenon-of-interest) to take back to the UDS framework, so I grepped my way through all the Hicks corpus files on the command line, as you do, to get a better sense of what was going on. I noticed that the code `$modv`, which stands for "modal verb", was present a lot in the coding tier.


<figcaption align = "center"><b>Fig.4 - modv code in %cod tier</b></figcaption>
<img src="https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/visualizations/modv.png" alt="modv code in %cod tier" width="500"/>

When we think of modals, we typically think of words like “can” “should” ”may” that signify a varying degree of ability, willingness, etc. to do or undertake a certain action. The Hicks corpus distinguishes these, though, from modal verbs, and the sentences annotated with $modv almost always contain some form of “try to”. 


<figcaption align = "center"><b>Fig.5 - "try" constructions in terminal</b></figcaption>
<img src="https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/visualizations/try-terminal.png" alt="try constructions in terminal" width="600"/>

"try" constructions are most likely so prevalent in the Hicks corpus because of the nature of the task (getting kids to talk about something they have just watched) and probably has something to do with the kids not wanting to say something actually happened with certainty because they only witnessed what happened in a video, not in real life. This phenomenon is probably highly affected by the narrative task, and therefore, it’s not really true spoken speech, however it still provides an interesting point of analysis because there are varying degrees to which the action being "tried" is actually undertaken or completed.

<figcaption align = "center"><b>Fig.6 - formatted "try" constructions</b></figcaption>
<img src="https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/visualizations/try-formatted.png" alt="formatted try constructions" width="600"/>

In this sentence above, we know, as humans, that the running action did occur to some extent, but maybe not to the fullest extent: a completed action. Even so, though the running past was ultimately unsuccessful, it did occur to some extent. How could the UDS framework apply to this phenomenon and how could computers potentially handle this?


## 3 Analysis

### 3.1 How it started


From my project plan:

> The main, true, analysis part will involve me looking into how the CHILDES dataset aligns with the UDS framework. UDS is supposedly better for capturing the semantics of words as the average person would understand. I will take what the original researchers (who collected the narrative corpus) were looking at and analyze it within the framework of the UDS dataset. I think an interesting aspect of the narrative corpus to do this with will be the differences in "verb forms, aspectual markers, timemarkers and logical connectors," as well as the event descriptions since the UDS dataset seems like it can offer complex information about these linguistic aspects


### 3.1 How it ended up

I ended up analyzing "try" constructions, and I thought about them a bit in terms of modality. To what extent does/did the speaker, reader, or listener of the sentence believe the action associated with the "try" predicate took place? 

I began by sifting through all the sentences in the dataset for the ones that contained the verb "try," and then further filtered those down to keep only the sentences that had "try" predicates with predicates dependent on them with the xcomp relation (see [this image of the CoNLL-U format](#6-extras) for a look at the dependencies). These sentences take the form of "try to...", but not "try and..." or "try OBJ".


<figcaption align = "center"><b>Fig.7 - Chart showing the distribution of "try" forms in the specified sentences</b></figcaption>
<img src="https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/visualizations/try-forms.png" alt="bar chart showing try form distribution" width="400" align="center"/>

Above is the breakdown of "try" forms in the 157 sentences containing a "try" predicate and an xcomp relation dependent predicate. To see this distribution of forms was interesting, but I did not do anything further with it in my analysis.

For my main analysis, I took a closer look at [Universal Decompositional Semantic types and node type subspaces](https://decomp.readthedocs.io/en/latest/data/semantic-types.html). I figured that factuality, genericity, and event_structure would be useful, but I also ended up looking at time. Here is the section of my Jupyter notebook in which I [explore these subspaces](https://nbviewer.org/github/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/code_notebooks/UDS_explore_CRC.ipynb#6.-Closer-look-at-node-type-subspaces-(of-interest)). 

These attributes are derived from the crowd-sourced annotations. The annotations are binary (YES/NO) answers in response to the simple questions about the phrase, and then along with them, there is a 1-5 confidence rating that gets normalized. These values make up the attribute value. Not getting into the exact mixed models that compute these values, I took more positive values as "yes" answers and more negative values as "no" answers.

The confidence is the researcher confidence score dealing with how accurate the researcher believes the annotators' responses to be. There will be a lower confidence score if the annotator responses are more variable. These confidence value exist on [0,1].

#### Selected sentences

I was not ultimately able to format the UDS data in a way that would allow me to look at overall telicity, factuality, event structure, and duration attribute values for the "try" predicates and the predicates dependent on "try" in the xcomp relation separately. This is a major flaw of my analysis, and I recognize that my project is not complete without it, however it was something that I worked for and could not achieve. 

In order to have something to show the information of interest, though not in the desired format, I created two tables one highlighting "try" predicates and one highlighting xcomp predicates, each containing the same four sentences. 

**Table.1 - selected sentences with information about "try" predicates**

|ID  | Text  | Telic  | Hypothetical  | Factual  | Duration |
|---|---|---|---|---|--- |
| ewt-train-133  | Musharraf has been **trying** to purge his officer corps of the substantial number of al - Qaeda sympathizers .  | 1.2817955017089844  |  -0.7177 | 1.2194  |months |
| ewt-train-796  |  He was **trying** to buddy with Archibald and impress him . | -1.0961610078811646  |  -1.4712 | 1.1012  |minutes, days, weeks |
|  ewt-train-1267 | Can a policeman open fire on someone **trying** to kill him ?  | -1.0745666027069092  |   1.1862 |  -1.1975 | minutes|
|  ewt-train-917 |  Afshari , who was posted in Germany and was responsible for receiving Mujahedeen children during the gulf war , said that when the German government **tried** to absorb Mujahedeen children into their education system , the Mujahedeen refused . |  -1.098742961883545 | -1.1216  | 1.0583  | days, weeks, months|


**Table.2 - selected sentences with information about predicates dependent on "try" with xcomp relation**

|ID  | Text  | Telic  | Hypothetical  | Factual  | Duration |
|---|---|---|---|---|--- |
| ewt-train-133  | Musharraf has been trying to **purge** his officer corps of the substantial number of al - Qaeda sympathizers .  | -1.1354095935821533   | 0.4279  |  0.2707 | weeks, months|
| ewt-train-796  | He was trying to **buddy** with Archibald and impress him .  | -1.0745365619659424  | -1.1904  | 0.9635  | days, weeks, years |
|  ewt-train-1267 | Can a policeman open fire on someone trying to **kill** him ?  | -1.098722219467163  |   -1.281 |  -1.2075 | minutes|
| ewt-train-917  | Afshari , who was posted in Germany and was responsible for receiving Mujahedeen children during the gulf war , said that when the German government tried to **absorb** Mujahedeen children into their education system , the Mujahedeen refused .  | -1.0988761186599731  | 0.9725  | 1.0999   | months, years|  


The "trying" occurs in all of these sentences (they all have a positive factuality value) except for the one with a high positive value for "hypothetical." This aligns with what I understand of the sentence - the sentence is asking a hypothetical question about something that has not occurred. 

I do not know what to make of the telicity values from these sentences. The "try" predicates and the xcomp dependent predicates follow the same trend for all except the first sentence where the "try" predicate has a positive telic value and the xcomp predicate has a negative telicity value. In my opinion, the "trying" in "Musharraf has been trying to purge" is no more a completed action than the "purging." I think I would have to look more into the "has been" that precedes the "try" predicate for more information about the behavior of the "try" predicate. 

The duration attributes were something that I did not consider until the end, but I would like to go back and look at them to see how my intuition with these aligns with what the values are in the dataset. I would also like to see what questions were asked and what responses were given during the annotation process.

## 4 Conclusion

### 4.1 On "try" constructions

Overall, I was not able to reach any firm conclusions about the "try" constructions, but what I was seeing in the dataset was exactly what I felt about the sentences as well. It is pretty amazing that crowd-sourced annotations could be as strong as they are, but, then again, it makes sense given the set-up of the tasks with the simple questions, because native speakers usually "have a feel" for what is going on in an event even if they aren't able to explicate it as a linguist would. I for sure want to continue my analysis of "try" constructions within the context of the UDS framework to reach some more conclusive results.


### 4.2 On UDS

The sheer amount of semantic information the UDS dataset provides all in one place sets it apart from other semantically annotated datasets. Though I hinted at (some of) the frustration I had when developing and completing this project, the frustration stemmed not from the content of the UDS dataset itself, but from knowing there was an abundance of rich semantic information that I was unsure of how to access. I was fascinated by the node type subspace information that was available for the predicates and arguments, and it is all the more fascinating that the attribute values for each of them come from crowd-sourced annotations. I think the UDS framework has the capabability to be an extremely valuable semantic resource, though I would like to see more evidence of how it could potentially work for other languages since it is built on Universal Dependencies.

In the future, I would love to return to my work with the UDS dataset, figure out how to access the information I couldn't for this project, and further explore the semantic data available for the words and phrases in the dataset. 


## 5 Citations

Aaron Steven White, Elias Stengel-Eskin, Siddharth Vashishtha, Venkata Subrahmanyan Govindarajan, Dee Ann Reisinger, Tim Vieira, Keisuke Sakaguchi, Sheng Zhang, Francis Ferraro, Rachel Rudinger, Kyle Rawlins, and Benjamin Van Durme. 2020. [The Universal Decompositional Semantics Dataset and Decomp Toolkit](https://aclanthology.org/2020.lrec-1.699/). In *Proceedings of the 12th Language Resources and Evaluation Conference*, pages 5698–5707, Marseille, France. European Language Resources Association.

Hicks, D. (1990). Kinds of texts: Narrative genre skills among children from two communities. In A. McCabe (Ed.), *Developing narrative structure*. Hillsdale, NJ: Erlbaum.


## 6 Extras


[CoNLL-U format](https://universaldependencies.org/format.html)

<figcaption align = "center"><b>Fig.8 - CoNLL-U format for sentence ewt-dev-539</b></figcaption>
<img src="https://github.com/Data-Science-for-Linguists-2022/UDS-child-speech/blob/main/visualizations/conllu_dev-539.png" alt="CoNLL-U format for sentence ewt-dev-539" width="800"/>
