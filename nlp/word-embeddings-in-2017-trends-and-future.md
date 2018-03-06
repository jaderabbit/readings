# Word Embeddings in 2017: Trends & Future Directions

URL: http://ruder.io/word-embeddings-2017/index.html

## Subword-level embeddings

- Augment with subword-level information for many applications. 
- Do so using character n-grams
- Character n-grams fom basis of Facebook's fastText classifier
- Leverage state-of-the-artlanguage model
- Tensorflow 1 Billion Word Benchmark Language model: https://github.com/tensorflow/models/tree/master/research/lm_1b
- Take word vectors and append a character level LSTM. Why though?


## OOV Handling

- Out of vocab words and how to handle them - i.e. words not seen during training. 
- Use "subword level embeddings"
- Initialize the embedding of OOV words as the sum o their context words. Then only refine the OOV words with a high learning rate. Unclear if it scles
- Train a character-based model to explicitly recreate pre-trained embeddings. Why though?

## Evaluation

- Hard to evaluate on intrinsic tasks
- Better evaluated on extrinsic tasks

## Multi-sense embeddings

- Criticism of word embeddings: don't capture POLYSEMY. i.e. The coexistence of many possible meanings for a word or phrase.
-ACL 2016 tried to learn separate embeddings for multiple sense of a word
- Pilehvar 2017 shows multi-sense outperformed randomly initialized word embeddings, but outperformed by pre-trained word embeddings
- Since neural machine translation using word embeddings have done so well, it seems that our models are expressive enough to contextualize and disambiguate words in context without relying on dedicated disambiguation pipeline/multisense
- Need to understand how well models can disambiguate

## Beyond words as points
- Critisize that words can be captured by points - perhaps miss nuances, therefore other representations?
- Vilnis & McCallum (2015) propose that each word is modelled as a probability distribution - allows us to represent uncertainy.
- Athiwaratkun & Wilson (2017) use multimodal distributions to deal with polysemy, uncertainty, entailment
- Others alter the embedding space - Mickel and Kiela (2017) embed words in a hyperbolic space to learn hierarchical representations. 

## Phrases and multi-word expressions

- WE fail to capture meanings of phrases
- Mikolov et al 2013 propose Phrase embeddings and people have tried working on it. 
- Explicitly modelling phrases has so far not shown significant improvements on downstream tasks to justify the complexity. 

## Bias

- Male gender stereotypes for example
(I heard about a solution for this on Linear Digressions. Much read and ammend)

## Temporal Dimension

- The laws of semantic change
-  (Hamilton et al., 2016; Bamler & Mandt, 2017; Dubossarsky et al., 2017)

## Lack of theoretical understanding:

- Little work on gaining better theoretical understanding of WE space & its properties.
- (Save for insight that word2vec + skip gram negative sampling implicitly factorized a PMI matrix - Levy 2014)
- Arora et al (2016) propose a new generative model for WE, treading corpus generation as a random walk of a discoourse vector and establish theory motivations regarding the behaviour
- Gittens provide thorugh theoretical justification of additive compositionaliy. Show skip-gram word vects are optimal from a information-theoretical sense.
- Mimno 2017 reveal interesting relations between WE and embeddings of context words (they're not evenly dispersed across vector space, but occupy a narrow cone that is diametrically opposite to the context word embeddings)
- The location & properties of WE is lacking

## Task and domain-specific embeddings

- Want to adapt embeddigs pre-trained on large news corpora to capture characteristics of our target domain, but still retain all relevant existing knowledge 
- Lu & ZHeng 2017 proposed a regularized skip-gram model for learning cross-domain embeddings. 
- augment pre-trained embeddings with existing knowledge encoded in semantic lexicons.
- You can inject such relations into embedding space by "retro-fitting" (Faruqui 2015). Injecting additional prior knowledge into word-embeddings such as word similarity https://arxiv.org/pdf/1705.07425.pdf Niebler et al 2017. 
- Wu et al (2017) propose a general word embeding model beyond NLP. StarSpace: Embed All The Things! https://arxiv.org/pdf/1709.03856.pdf

## Embeddings for multiple languages

- A promising direction is to develop methods that learn cross-lingual representations with as few parallel data as possible, so that they can be easily applied to learn representations even for low-resource languages. For a recent survey in this area, refer to Ruder et al. (2017) https://arxiv.org/pdf/1706.04902.pdf
MUST READ

## Embeddings based on other context:
- Not sure I follow much of this

## Conclusions

- Interested in reading further for embeddings for low-resource languages
- Interested in sublevel word embeddings and uses



