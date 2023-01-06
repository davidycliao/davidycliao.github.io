# Estimating Politically Expressive Preference with Context-Aware Named Entities


<div style="text-align: justify">

Ideological positions of political parties are commonly measured using text scaling methods, such as Wordfiish (Slapin and Proksch 2008) and Wordscore (Laver, Benoit, and Garry 2003; Lowe 2008; Lowe and Benoit 2013). These analysis methods are not only useful for extracting latent dimension of parties and politicians, but also for testing political theories, e.g., intra-party competition (Haber 2015; Däubler and Benoit 2015), and party positionings (e.g. Catalinac 2017; Proksch and Slapin 2010). Concerns have been raised around the performances in internal validity (Bruinsma and Gemenis 2019), and around the assumptions that both Wordscores and Wordfish make of their input data (Egerod and Klemmensen 2020; Proksch and Slapin 2009). In this paper, we propose a novel estimation strategy that augments the text scaling methods used in political science with named entity recognition (NER) that recognizes various types of entity objects. We first extract named entities using state-of-the-art language models in German and English and scale them with Wordfish Model. We illustrate our strategy using the case of parliamentary debates on the topics of immigration issues discussed in the UK House of Commons and the German Bundestag from 2014 to 2019. Party positions are estimated and validated with the Chapel Hill Expert Survey (CHES). To evaluate the performance of extracted entities scaled in our estimation strategy, we cross-validate our method by performing multiple LDA topic models. Then, we shuffle the corpus randomly and split them into k groups by folds. We take one of folds as test set while using remaining folds as a train set. Afterwards, the average perplexity scores extracted from a series of topic numbers are used to evaluate the quality of estimation between the basic Wordfish model and our approach. We find that (1) parties' positions estimated by our approach are highly consistent with the CHES expert\textquotesingle s judgment, and (2) our approach achieves better internal validity in terms of perplexity performance than the basic text scaling model without the pre-processing step using NER.

**Keywords**：*NER, flair, NLP* 


</div>

