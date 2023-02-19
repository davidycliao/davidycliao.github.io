# Estimating Politically Expressive Preference with Context-Aware Named Entities


<div style="text-align: justify">
Text scaling methods, such as Wordfish, are commonly used to capture the ideological positions of political parties. These methods not only extract latent dimensions of parties but also test political theories, such as intra-party competition (Haber 2015; Däubler and Benoit 2015) and the impact of institutional changes on party positioning (Catalinac 2017). However, concerns have been raised about their internal validity (Bruinsma and Gemenis 2019), the assumptions of input text on a single dimension (Egerod and Klemmensen 2020; Proksch and Slapin 2009), and semantic representations (Sylvester et al. 2022; Liao et al. 2022). To address these concerns, this paper proposes a novel estimation strategy that combines the unsupervised scaling method used in political science with named entity recognition (NER) and the BERT sentiment model (Guhr 2020). The approach involves extracting contextually weighted Named Entities using state-of-the-art language models in German and English and measuring MPs' ideological preference with Wordfish. This approach recognizes various entity objects that are contextually adjusted by the language tone in the corpus. The strategy is illustrated using the case of parliamentary debates on immigration issues discussed in the UK House of Commons and the German Bundestag from 2010 to 2019. Party positions are estimated and validated with the Chapel Hill Expert Survey (CHES) in 2010, 2014, and 2019. The results show that (1) the positions estimated by the weighted NER approach are highly consistent with the CHES experts' judgment and (2) the approach achieves better internal validity in terms of perplexity performance than the basic text scaling model without the pre-processing step using named entity recognition.

**Keywords**：*NER, SpaCy, NLP, BERT Sentiment Model* 


</div>

