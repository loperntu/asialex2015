---
title       : 'Measuring Leixcal Age'
subtitle    : 'based on Big and Deep Data'
author      : 'Shu-Kai Hsieh, National Taiwan University'
job         : 'AsiaLex 2015, PolyU, Hong Kong'
logo        : lope.png
biglogo     : lopen.png
license     : by-sa
framework   : io2012        # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : [mathjax, quiz, bootstrap]    # {mathjax, quiz, bootstrap}
ext_widgets: {rCharts: [libraries/widgets/nvd3]}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
bibliography: /Users/shukai/LOPE_LexInfo/BIB/myRef.bib
github      : {user: loperntu, repo: asialex2015}



---
## Motivation (X): Age Guessing 



<img src="assets/img/ageguess.png" alt="Drawing" style="width: 600px;"/>

<!--
OPENING: 介紹自己，研究興趣 
I'm particularly interested in applications of natural language processing in lexicography for building better dictionaries and keeping dictionaries up to date.
-->

---
## Motivation (O): Lexical Age Guessing


<img src="assets/img/neo.png" alt="Drawing" style="width: 700px;"/>





--- bg:#FFFAF0
## Outline

1. Introduction
2. Previous works on Neologisms
3. Measuring Lexical Age
4. Conclusion


---
## Outline

1. __`Introduction`__
2. Previous works on Neologisms
3. Measuring Lexical Aging 
4. Conclusion




---
## Background  | Neologism brings challenges to Lexicography 

> Big data has Big impact on Lexicography?

<!-- > Next time you run a Google search, think about the fact that it's just one of 2 million that Google will receive in that minute. In the same amount of time, Facebook users post 684,478 pieces of content. Crazier still, online shoppers spend an average of 272,070 every minute. That's over 391 million every day — quite the chunk of change.-->

- Influx of neologisms: a new word is created every 98 minutes (Global Language Monitor). An estimated 800 to 1,000 neologisms are added to English language dictionaries each year (in the 20th century alone, more than 90,000 words have been added). (http://www.languagemonitor.com/no-of-words/) 

<!-- Editors of the third edition of the OED, to be completed by 2037, estimate that the rate of inclusion of new words into the OED are about 4,000 per year.
-->


- Without the lack of adequate empirical tools, even the *word-watching website* can only observe from the sidelines.

--- &twocol
## Background  
### Neologism brings challenges to Lexicography 

> (Algeo,1993) points out that even those words that do make it into dictionaries often fall out of usage. 58% of the new words collected in the *Britannica Book of the Year* between 1944 and 1976 were not rewarded with a dictionary entry (quoted from (Cook, 2010))  

<!-- The majority of new words in fact fail to become established in language. (Algeo,1993) -->


*** =left
<img src="assets/img/uxorious1.png" alt="Drawing" style="width: 500px;"/>




*** =right
<img src="assets/img/ux.png" alt="Drawing" style="width: 500px;"/>



---
## No more **uxorious**? who said that?!

<img src="assets/img/uxorious.png" alt="Drawing" style="width: 500px;"/>
<img src="assets/img/ux-google.png" alt="Drawing" style="width: 500px;"/>


--- &twocol
## An Embarrasing Lexicographical Example

*** =left 

> All dictionaries will turn out to be diachronic/historical ones? (if no one retired)


*** =right


<img src="assets/img/moe.jpg" alt="Drawing" style="width: 300px;"/>

#### An example of MOE Chinese Dictionary APP: full of 'desuetude' 
#### 11 new words out of 3 paragraphs randomly picked.

<img src="assets/img/moe-test.png" alt="Drawing" style="width: 700px;"/>




---
## Since when has Google become a Dictionary!?

> Millennial. hipster. yuppie. muppie. Henry, and now, yuccie.

<img src="assets/img/hipster.png" alt="Drawing" style="width: 700px;"/>



---
## Neologism brings challenges to Linguistics 
### Lexicalization and Language Change

- Language in use is a dynamically developing system adapting to its ever-changing social environment.

- 'The diachronic, gradual and individual process by means of which novel lexemes and lexical units become a permanent addition to the lexicon of speakers and the language community is labeled **establishment** (Schmid, 2011).

- The process of establishment has been studied in terms of *lexicalization* (the process by which new items that are considered 'lexical' come into being) (Brinton and Traugot, 2005) and *institutionalization* (from socio-pragmatic perspective) (Lipka, 1977).
  - __adoption into the lexicon__
  - __falling outside the productive rules of grammar__


---
## The Emergent Lexicon 

- Lexicon is understood as *a finite list of forms and the possibilities for combining them*

- Functionalistic take on the (Mental) Lexicon (,if any):
    - 'our understanding of both language structure and use is enhanced by the recognition that memory for language is highly affected by language use' (Bybee,1998).
    - The memory representation of language consists of units that can constitute utterances or intonation units, i.e., not just words, but also phrases and constructions. 

- It is the __formulation__ that annoies linguists.


---

## The Emergent Lexicon 

$$
\mathbf{Change}_{a,b} = \mathbf{A} \succ \mathbf{B}
$$

$$
\mathbf{Change}_{a,b} = \mathbf{A} \succ 
 \begin{Bmatrix}
  A \\
  B 
 \end{Bmatrix}
 \succ \mathbf{(B)}
$$

`Most attention were paid to the questions "What is in the arrow?" and "How does change come about?"`

--- 

## The Emergent Collective Lexicon:

Lexicographically, we can define

- **diffusion** denotes the 'dynamic spread of novel formations across the language and its speakers'; while **conventionalization** refers to the 'dynamic socio-pragmatic process by means of which a linguistic innovation becomes established in the language and the speech community' (Kerremans, 2015).

<!-- the former facilitate subsequent retrieval from memory; the latter implies the establishment in the mental lexicon -->
<!-- Lexicalization (and grammaticalization) 談的是如何進場 -->

<!-- 網路時代的海量數據引出了語言單位的**生命力**指標量度需求（能活多久或為何退場--> 

- we need a reference measure of lexical age ("vitality" or "durability") for words to help justify their inclusion/exclusion in dictionaries. BUT note!! [pressing `p`]

*** =pnotes
<q>Old words never die, they just fade away</q>

In some cases words might be *dead* to all purposes, but could revived by the media periodically for the purpose of *irony* or *parody*.



---
## Questions to be answered 
  
**Big Three** (Brinton and Traugott, 2005)

1. The constraint problem: what is the set of possible changes and linguistic conditions for change?
2. The transition problem: what are the interesting stages that define the path by which A gives rise to B?
3. The actuation problem: how does change start, when and where does it start ('actuation') and how does it spread through the system ('actualization')?

  
**Missing**
  
<a class="btn btn-large btn-danger" rel="popover" data-content="How does words survive? what is the life cycle? When to be recorded in Dictionary?" data-original-title="" id='example'>The survival problem</a>



<!--
---
## Our Question | What's the Successful Story of, the Words?

- (not) the morphological rules of coining new words, or the revival of old usage (..)
- how they sustained and expanded their meanings and functions (evolve into polysemy)
-->


---
## Outline

1. Introduction
2. __`Previous works on Neologisms`__
3. Our approach
4. Conclusion




---
## Previous Works

- Linguistic Approach
- Psycholinguistic Approach
- Applied lexicological Approach
- Computational linguistic Approach


--- bg:#F0FFF0
## Linguistic approach | Neologism and Lexicalization

- Lexicalization is viewed as the way to enrich the lexicon. Lipka (1990) "..the phenomenon that a complex lexeme once coined tends to become a single lexical unit, a simple lexeme."
- Neologisms (new entries in the inventory) can be seen as the results of the *conception of lexicalization*.
- The production of neologisms encompasses a wide variety of linguistic processes, both sybchronic and diachronic.
- Mechanisms involved: *create, modify, combine,* or *separate* existing units, and thus lexicalization would seem to include opposing directions of change leading to greater or lesser **dependency** and greater or lesser **compositionality**.



--- bg:#F0FFF0
  
## Linguistic approach | Neologism Classification
  
(`Renouf's classification` 2013) 

  * __lexical neology__ (i.e., newly-coined lexical items) e.g, [Arab Spring](http://www.google.com/trends/explore#q=Arab%20spring&cmpt=q);
  
```
Note: various morphological mechnisms for lexical neology (Cook, 2010): 
'lexical blends'  (e.g., 'webisode' is a blend of web and episode), 
'text messaging forms'  (e.g., 'any1' for anyone).
```
  
  * __semantic neology__ (i.e., new sense of word) e.g, 'troll' (an individual who posts inflammatory, rude, and obnoxious comments to an online community); 'sick' (mean ‘excellent’, an amelioration)
  * __grammatical neology__ (i.e., neologisms that change grammatical class).  [friend](http://www.wordnik.com/words/friend)



*lexical neology* and *semantic neology* can be identified in a text corpus at surface level by automatic means (by comparing existing lexicon and discovering the change in collocational environments), while *grammatical neology* can be identified at a post-processing stage of semantic neology.


--- &radio

## Examples of Popular Culture Neologisms

[Staycation] : type of neologism? morphological strategy?

1. _lexical neology_
2. semantic neology
3. grammatical neology


*** .hint
Lexical Blends

*** .explanation
> A vacation at home or in the immediate local area.




---
## Psycholinguistic | Neologism and Lexical Memory

> How do neologisms leave the memory trace in our mental lexicon? (frequencies of exposure, types of neologisms, ...)


- (De Vaan, Schreuder, and Baayen, 2007) For the neologisms, a stepwise mixed-effect regression analysis resulted in a model with significant main effects of **Length**, and **Number of Synsets**. As for the existing words, ratings increased with increasing Length ($\hat{\beta}$ = 0.238, t(877) = 2.805, p = .0051) and decreased for increasing Numbers of Synsets ($\hat{\beta}$ = −0.560, t(877) = −3.359, p = .0008). 

> What we are concern about is the collective mental lexicon (constrained by real world / social communication)


---
## Leixogrpahy in Practice
> How do you decide whether a new word should be included in an Oxford dictionary?

- Previously it was a paradox: in order to find usages of a previously undocumented word suspected of being new, one would have to wait until it was encountered during reading (Barnhart, 1985).

- Corpus-based/aided method changed lexicographer's works. (Atkins and Rundell, 2008)

<!--The Collins COBUILD English Language Dictionary broke new ground in lexicography by being the first dictionary to be based entirely on corpus evidence (Sinclair, 1987).
-->



---
## Lexicogrpahy in Practice

(Metcalf, 2004) : FUDGE factors for determining whether a word will remain in usage


$$latex
\Sigma (\mathcal{F}_{0-2}, \mathcal{U}_{0-2}, \mathcal{D}_{0-2}, \mathcal{G}_{0-2}, \mathcal{E}_{0-2})
$$

- F: Frequency
- U: Unobtrusiveness
- D: Diversity of users and situations
- G: Generations of other forms and meanings
- E: Endurance of the concept to which the word refers.


---
## Leixogrpahy in Practice

(Barnhart, 2007): 

$$latex
\mathcal{V} * \mathcal{F} * \mathcal{R} * \mathcal{G} * \mathcal{T}
$$

- V: the number of forms of *w*
- F: the frequency of *w*
- R: the number of sources in which *w* occurs
- G: the number of genres in which *w* occurs
- T: the time span over which *w* has been observed.

---
## Corpus-based Applied Lexicology 
### Stages

<!-- newly-coined words vs established words found in a dictionary-->

- (Renouf 2013) based on 1.2 billion words corpus from UK newspaper (1989-2011) proposed the Life cycle of a word as *birth, settling down, obsolescence, death, and re-birth*.
- (Kerremans, 2014) proposes four stages of conventionalization: *creation, consolidation, establishment*.

> Our terminology: difussion and stablization


---
## Corpus-based Applied Lexicology 
### Frequency effects

- **Word Frequency** takes the lead in explaning the success story of words, life stages and the prediction force of whether a word may be survived after being coined.

- Word frequency variations take place both due to external and internal factors. 
  - Product-words (P-words) : driven exogenously by events that are external to the group, such as product releases.
  - Slang-words (S-words): more endogenously influenced by the social values and language patterns of the communication group.

- The frequency of a word in short-time scale should be determined by the amount of *being used by different individuals* (**indexicality**) and *the range of being used in different topics* (**topicality**).

---
## Corpus-based Applied Lexicology 
### Quantitative Laws


- Quantitative studies have brought to significant progress in the understanding of word's *life-stage statistics* (originated, evolved, die out) and *language evolution*.

- Different statistical model of word usage frequency dynamics have been proposed.
  - e.g., (Altmann, Whichard, and Motter, 2013) reveals strong relation between changes in word *dissemination* and changes in *frequency*; (Petersen, Tenenbaum, Havlin, et al., 2012) ... 
  

> Since neologisms are expected to be rather infrequent due to the recency of their coinage, methods for lexical establishment that rely solely on statistical distributional information are not well-suited for learning the linguistic properties of neologisms, particularly those which have very low frequency. (Cook, 2010)



--- {class: class, tpl: tabs}

## Computational Approach | Novel word sense detection

<!-- 
http://cs.unb.ca/~ccook1/elex2013.pdf
-->


*** {class: active, id: language resources}

You need **corpus and lexicon** are the prerequisite for an empirical surveys. A *reference* corpus will make the identification task simpler: An *unseen* word is matched against the corpus so that it is pinpointed at its first occurrence, and deemed to be a candidate for neologism. (cf. *hapax legomena*)

*** {id: algorithms}

<img src="assets/img/pipeline.png" alt="Drawing" style="width: 450px;"/>

Use **collocational information** to (semi-) automatically determine the candidate's usage and definition.



---
## Outline

1. Introduction
2. Previous works on Neologism
3. __`Our Approach`__
4. Conclusion


---bg:#F0FFF0
## Our Concern

- Do we have the chance to develop a stabalization measure of neologisms that indicate whether they are likely to remain in usage, (and therefore should be included in a dictionary)?

- What's the role of linguistic knowledge in this exploratory process?


---
## Our Approach | Going deep with big data

- Tsunami of linguistic data; massive influx of neologisms is unavoidable

<!-- However, because of a lack of precise knowledge of the value embedded within this huge crush of data, many businesses have been stuck in the “data for data’s sake” trap .... Deep data? another industry buzzword?--> 

- Deep data trumps Big data : "Deep Data framework– an approach based on the premise that a small number of information-rich data streams, leveraged properly, can yield more value than masses of captured data"

- Machine learning on big corpus data | Human exploiting the deep linguistic knowledge based on even small number of usages.
<!-- write a googlebook ngram shiny for demo -->


---
##  Language Resources used 

- Google Book ngram corpus (training data to gain insight)
- UDN (The United Daily News): provides newswires over several years in Taiwan.
- Word list from MOE (1997) 
- PTT corpus as neologism sensor: the most popular discussion forum in Taiwan (over than 20,000 boards and 1.5 million users, more than 10,000 articles are posted/day.)
- DeepLex




---
## Google Book Ngram Corpus (GBNC): Overview

- Google Book project of digitized texts containing about 6% (over 8 million books) of all books ever printed. 
- N-gram corpus extracted from the project include distributions of n-grams in books written over the past 200 years.

<!-- 可考慮 googlebook ngramr -->



---
## [Culturomics](http://www.culturomics.org/), Lexicography, and Big Data


> Analysis of this corpus enables us to investigate cultural trends quantitatively. We survey the vast terrain of 'culturomics,' focusing on linguistic and cultural phenomena that were reflected in the English language between 1800 and 2000. We show how this approach can provide insights about fields as diverse as **lexicography**, the **evolution of grammar**, collective memory, the adoption of technology, the pursuit of fame, censorship, and historical epidemiology.(*Science, 331(6014): 176–82*, 2011).


--- &twocol

## Google Books for Culturomics

*** =left 
#### The evolution of grammar

- Competition between regular and irregular verbs: It took 200 years for the fastest-moving verb ("chide") to go from 10% to 90%.


*** =right

<img src="assets/img/gngram.png" alt="Drawing" style="width: 900px;"/>
<!--
<iframe src='assets/img/gngram.png' width=800px height=250px>
</iframe> 
-->

---
## World Knowledge, Language, and Big Data

- Google's Provides Free Access (via BigQuery) to GDELT project
- Danger of de-contextualization though.



---
## Our Linguistic Toolbox | DeepLex 

> * It takes the functional position (usage-based view) in determining units and patterns (in Chinese), as well as the ontological grounding on the relation between linguistic objects and situations (bits of reality). (Langacker 1987, 1988, 1999; Croft 2002; Tomasello 2003; Bybee 2006, 2010)

> * Lexical data at different levels are modularized (only for practical reasons), such as syntax-semantics module, emotion module, discourse and pragmatic module, diachronic module, etc. Researchers from different fields can initiate a new cooperation based upon. 

---
    
## The Deep Lexicon Project: Variables

| **Module.Variable**        | **Description**                       |
|---------------------|---------------------------------------|
| `concept.sense`     | word sense number from [Chinese Wordnet, CWN](http://lope.linguistics.ntu.edu.tw/cwn2/), please [help](http://lope.linguistics.ntu.edu.tw/cwikin/)       |
| `concept.gloss`     | sense definitions from CWN    |
| `concept.relations` | lexical semantic relations      |
| `emotion.polarity`  | polarity of descriptive emotional words|
| `emotion.location`  | location collocates of emotion  |
| `emotion.cause`     | cause collocates               |
| `emotion.result`    | resulting event collocates        |
| `emotion.time`      | time collocates        |
| `frequency.asbc`    | frequency of Sinica Corpus|
| `frequency.plurk`   | frequency of Plurk Corpus       |
| `frequency.childes` | frequency of CHILDES Corpus  |
| `frequency.ptt`     | frequency of PTT                    |

**AND MANY OTHERS!** modules in progress: Affect, Aquisition, Semantics, Familiarity, Orthography, Ontology, Socio-Psychology, Neurolinguistics . . . . . . . . . . . .  

<!--
- phonological module
- morpho-syntactic module
- semantic-pragmatic module
- sociolinguistic module
- affective module
- ontology module
-->




---
## Time-series Modeling: a pilot study for short-term frequency
### Our First Approach (Liu, Hsieh, and Prévot, 2013)

- PTT Corpus [`http://lopen.linguistics.ntu.edu.tw/PTT`]-based (2005-2012, three hot discussion boards), preproceesed. 
- 25 rators with $\kappa$ =0.45 ('moderate agreement').

<img src="assets/img/flowchart_ptt.png" alt="Drawing" style="width: 800px;"/>


---
## Time series predictive model

<iframe src='assets/img/timeseries.png' width=200px height=90px>
</iframe> 



---
## Results and Discussion

- These large, short-term fluctuations add an important new dimension to the study of the long-term dynamics of language, as any novel expression must survive in the short term to survive in the long term. (Altmann, 2011). `But short-term frequency data do not reveal the difference between diffusion and stablization`.

<img src="assets/img/ptt.freq.png" alt="Drawing" style="width: 900px;"/>


---
## Results and Discussion

How many years to be observed ?

- (Chang 2008; Wang 2010) proposed to use normalized frequency within a year or so to judge whether a once diffused new word is conventionalized is using or is failed to be captured; (Xu,1999) proposed that 10 years should be the criteria.

- Since the Surface Frequency measure is quite low for all neologisms, hard to be a good indicator for stablization index.

__________

**Findings**: the frequency of a word in short-time scale should be observed through the frequency variations: amount of *being used by different individuals* (user IDs), frequencies per month;  *the range of being used in different topics* (boards), etc.



--- .centrepre &vcenter

## DeepLEX is in

<!--詞彙不像人，可以離群索居，成就自己的意義。詞彙的意義是透過系統間的關係相對定義出來的。
因此我們認為應該關注詞彙的社會行為。-->

<a class='example'>Question</a>

          #################
    Which linguitic factors / combinations maximally explain the lexical establishment? 
          #################

  

---
## Our 2nd Approach | Targets 

<!-- BORN :The time span over which a word has been used —the date between the first citation-->

1. Use `google book ngram` as training data (to infer the 'laws'), and `ptt` corpus as test data.
2. Use `DeepLex` as guidebook.
3. Focus only on three classes of words: 
  * words that are `newly diffused` (for about just 1 years).
  * words that were considered `new words` (coined around 20 years ago).
  * words that are assumed to be `conventionalized` (since before 1950).
  
  ```
  Proper nouns are ruled out, for they are mostly propelled into the media glare due to 
  a certain external event or popular preoccupation. 
  ```
<!-- fashion word, 不處理。-->

---
## Our 2nd Approach | Hypothesis

<!-- words that are `inactivated`.-->


  - Language as ecosystem: words **cooperating as well as competing** for the attention of the language users, which could be best explained in terms of their *social behaviors across time*.
  - Linguistic knowledge can be exploited to infer their survival chance in the system.

---
## Exploratory Regression Modeling of the Life Stage of Diffusion and Stabilization

- `Constant U` (Wang, 2010; 2015) as dependent variable for 384 lexical items with 19 predictor variables under 6 dimensions (semantics, syntax, morphology, pragmatics-ontology, phonology, sociolinguistics).
- Multiple linear regression and logistic model with backward variable selection and AIC criterion were used (82% variations explained with $R^{2}$=0.80)

---
## Residual Analysis 


<img src="assets/img/residual.png" alt="Drawing" style="width: 900px;"/>


---
## Results | Discovering Influential Factors 

What are the driven (linguistic) factors for a lexical item to enter the *collective mental lexicon*?

- **semantic and pragmatic** dimensions significantly explain words of 3rd type (before 1950) `stabilization`
- **syntactic ('co-text')** dimensions significantly explain words of 2rd type (coined around 1997) `diffusion`




___________
Other General **Findings**:

* Words in competition with established words (but not many!) are more likely to succeed. ($\rightarrow$ in competition case the denotatum is well established, so only the new form need to run for supporting from speakers, while in non-competition case both need to be accepted). Echoed with (Boulanger, 2002), quoted from Cook (2010)).
* Importance of the their social network


---
## Toward Finding the Linguistic Niche 
### in the Lexical Social Network

- (Altmann et al., 2011) proposed the concept of *niche*, defined as the relationship between the word and the characteristic features of the environments in which it is used.
    - Two important aspects of the size of the word niche to be quantified: **the range of individuals using the word** and **the range of topics it is used to discuss**.
    - Controlling for word frequency, they show that these aspects of the word niche are strong determinants of changes in word frequency.
    
<!-- Using Internet discussion communities as model systems, -->

- (Baayen,2008) developed measure of `the age of a verb` on the basis of an etymological disctionary, and found that **neighborhood density if the stem** is a predictor for the age of a verb.

<!-- You can imagine that In the no-competition case, both the new word and new referent must be accepted.-->



---
## Distributed Social Network of Neologisms
### Summarized in SNA's parlance 

- Make friends, as many/varied as you can 
- Compete with established ones if you can 

Resulting in the

1. Frequency Diversity (e.g., the dissemination of words across individuals/generations/topics/boards/...)

2. Strength of Social Ties

3. irreplaceable Niche (when different forms compete to express the same meaning)

```
The Secret of Long-Living Words
```



---
## Magic Formular identified :-)

**Measure of Inclusion**: (Hseih et al. forthcoming)
$$latex
\mathcal{I} = \ln( \alpha \mathcal{F} + \beta \frac{S}{P}) 
$$

- F: `frequency diversity within short-term time span` (revised constant U)
  - cross-boards frequency $\frac{mean}{SD}$ * cross-month frequency $\frac{mean}{SD}$ (from various sources,i.e.ptt and newspapers)

- S: `syntagtic lexical network` via *collocation variations* ($\frac{type}{token}$)
- P: `paradigmatic lexical network` via *distributional proximity*

<!--
1. some of these properties may play a larger role in determining a word’s importance for inclusion in a dictionary than others. A supervised machine learning algorithm could be used to learn an optimal weighting for the various properties. 
2. it may also be the case that applying a non-linear transformation to the values for the properties—such as the natural logarithm—could make the values more informative; taking the natural logarithm has the effect of emphasizing the differences between smaller values, which may be particularly important in the case of frequency, since neologisms are expected to have relatively low frequency.

syntagmatic: can be viewed as a words that occur consecutively in text;
-->

<!--
![plot of chunk block2](assets/fig/block2-1.png) 
-->




---
## More on *distributional proximity*

- In addition to previous efforts that exploit the syntagmatic patterns of a candidate neologism (e.g., via `collocate profile`), we also propose to incorporate paradigmatic patterns (via creating `social network` of the candidate).
- Distributional model to the proximity revised from Sketch Engine's Thesaurus algorithm. (using `dependency relations` instead).


<img src="assets/img/sketch.png" alt="Drawing" style="width: 900px;"/>








--- .nobackground .quote

<q> Dictionary as A Mashup : Am I asking too much of lexicographers? </q>

- 'Design' instead of 'Compile': equipped with linguistic annotation craft
- Mobile, customized, ... the trend no need to resist 

<!-- Variative in the normative -->

```
user experience, etymology, stablization score/lexical age, picture, pronunciations,....
a matter of creativity!   
```

Chinese WordMap [http://lopen.linguistics.ntu.edu.tw/cwm]

---
## Dynamaic Neocrawler, Sketch and Estimation


- Crawl the posts/articles from PTT/newspapers on a daily base.
- Compare with entries in Deeplex, filter out (through rules and manual check) the candidate neologisms.
- Sketch the profile, calculate the I score.
- Crowd weighting.




--- 
## Prototypical System 

NeoCilin: <http://lopen.linguistics.ntu.edu.tw:12345/>
<!-- A case study of using DeepLex to leverage the Big data. We pick up every new lexical data stream if it ... -->
<!--Instead of going down the big data path, where there's a lot of data you could potentially analyze, but for relatively little incremental gain, we instead [focus on] the bare minimum that tells us the most about a building
-->

<img src="assets/img/neocilin.png" alt="Drawing" style="width: 900px;"/>



---
## Issues Remained:

- Variant forms and spellings: (text normalization: to convert all instances of a word in its various forms to a single canonical form? (e.g., google-googled; 頗喝-頗ㄏ)
- Computational cost is VERY HIGH.






---
## Conclusion

* **New paradigm of Doing Lexicography with B & D:**
  - Big linguistic data can help machine training of the understanding/inference of the global lexical behaviour (e.g., semantic changes).
  - Deep linguistic knowledge can help identify the stabalization process of neologisms, and we have proposed a reproducible, dynamically updated measure for lexical stablization.

<!-- New words are expected to be low frequency due to the recency of their coinage, and therefore purely distributional information is not reliable in this case.  
-->

  

* **Limits and Future works include:**

  - Evaluate the results 
      - against lexicographers/crowds.
      - by calculating the *I* score of all the entries in the dictionary. 
  - Work on semantic neology (漂亮 vs 正) and automatic re-ordering of senses (in Wordnet)

<!-- neologism as forms which have been recently added to the language vs 'established forms in a dictionary' is an questionable contrast--> 

<!-- This thesis sets the stage for further research into automatic detection of lexical age ... which have not been extensively considered in lexicography. -->

---
## Acknowledgement

> 王伯雅 (Amber Wang) 劉純睿 (Owen Liu)


---
## Reference

[1] E. G. Altmann, Z. L. Whichard and A. E. Motter. "Identifying
Trends in word frequency dynamics". In: _Journal of Statistical
Physics_ 151.1-2 (2013), pp. 277-288.

[2] B. S. Atkins and M. Rundell. _The Oxford guide to practical
lexicography_. Oxford University Press, 2008.

[3] D. K. Barnhart. "A calculus for new words". In: _Dictionaries:
Journal of the Dictionary Society of North America_ 28.1 (2007),
pp. 132-138.

[4] V. M. Boulanger. _What Makes a Coinage Successful?: The
Factors Influencing the Adaptation of English New Words_. UMI
Dissertation Services, 2002.

[5] C. P. Cook. "Exploiting linguistic knowledge to infer
properties of neologisms". PhD thesis. University of Toronto,
2010.

[6] L. De Vaan, R. Schreuder and R. H. Baayen. "Regular
morphologically complex neologisms leave detectable traces in the
mental lexicon". In: _The Mental Lexicon_ 2.1 (2007), pp. 1-24.

[7] D. Kerremans. _Web of New Words_. Peter Lang, 2014.

[8] T. Liu, S. Hsieh and L. Prévot. "Observing Features of PTT
Neologisms: A Corpus-driven Study with N-gram Model." In:
_ROCLING_. Ed. by H. e. a. Yang. 2013.

[9] A. A. Metcalf. _Predicting new words: The secrets of their
success_. Houghton Mifflin Harcourt, 2004.

[10] A. M. Petersen, J. Tenenbaum, S. Havlin, et al. "Statistical
laws governing fluctuations in word use from word birth to word
death". In: _Scientific reports_ 2 (2012).















