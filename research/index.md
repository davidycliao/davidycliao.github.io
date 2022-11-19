# Research


<br/><br/>


<div style="text-align: justify">


My research projects include:  *a PhD dissertation on legislative politics in Taiwan*, *quantitative studies of party misperception and political ideology*, and *computational methods applied to social media and contemporary China*.  


</div>


<div style="text-align: center">

## PhD Dissertation: 

</div> 

<div style="text-align: center">

### ***“Electoral Reform, Distributive Politics, and Parties in the Taiwanese Congress”***  


<div style="text-align: justify">

**Abstract**

Estimating the preference of parties and politicians is key to understanding interparty relations, polarisation, and electoral competition. This thesis investigates how the 2008 Taiwan electoral reform from a single non-transferable voting system (SNTV) to single-member districts (SMD) impacts the behaviour of legislators and their electoral strategies by analysing historic roll calls and parliamentary questions. I present several pieces of empirical evidence to answer the following research questions: (1) Does the electoral reform mitigate intraparty competition and increase party cohesion? (2) Does the reform reduce regional particularism expressed in parliamentary questions but increase the promises of universalism policies? Last, many legislators changed careers to become municipal mayors due to the reduced number of seats after the reform. (3) Do mayors having longer years of career in congress correspondingly assist the municipalities to receive more distributive spending? The thesis applies ideal point estimation and natural language processing techniques currently deployed by the frontier study of legislatures and strengthens the understanding of Taiwan party politics and party competition inside the congress (the Legislative Yuan). With the unique legislative data covering the pre- and post-reform periods, the reform did not immediately reduce intraparty competition but shortly polarised interparty relations, leaving congress in chaos during the transition. However, legislators' incentive to run on personal votes by asking particularistic parliamentary questions decreased while attention to regulatory policies increased after the reform. Last, the thesis finds municipalities whose mayors with longer careers spent in the legislature are more likely to be allocated higher distributive benefits. The effect is even more substantial if those mayors had previously been connected to the legislative standing committees. 

<!-- <p align="center">
<style>
img {
  border: 1px solid #ddd;
  border-radius: 4px;
  padding: 5px;
  width: 150px;
}
</style>
  <img width="500" height= "110"  src="https://raw.githack.com/davidycliao/erdp/main/paper/images/seven_legis.png" >
  <img width="500" height= "110" src="https://raw.githack.com/davidycliao/erdp/main/paper/images/partywhip_mean.png">
  <img width="500" height= "110"  src="https://raw.githack.com/davidycliao/erdp/main/paper/images/minor_postions_year.png">
  <img width="500" height= "110"  src="https://raw.githack.com/davidycliao/erdp/main/paper/images/major_postions_year.png" >

</p> -->

**Keywords**：*electoral reform, single-member districts (SMDs), roll call, political polarization*  <br> 
**Documents**: [`slides`]() | [`thesis`](https://github.com/davidycliao/phd-thesis/blob/main/Yen_Chieh_Liao_PhD_Dissertation.pdf)

<br> 

(The PhD dissertation project is supported by the 2021 Taiwanese Overseas Pioneers Grant from *Ministry of Science and Technology Taiwan*, August 2021 - August 2022)

</div>


<br/><br/>

<div style="text-align: center">

## Working Papers and *In-Progress* : 

</div>

---

<div style="text-align: justify">

**Estimating Politically Expressive Preference with Context-Aware Named Entities** ([<span style="color:#778899">with Thomas Saalfeld and David Beck, University of Bamberg & LACAN Research Group</span>](https://projectlacan.wordpress.com))

Ideological positions of political parties are commonly measured using text scaling
 methods, such as Wordfiish (Slapin and Proksch 2008) and Wordscore (Laver,
Benoit, and Garry 2003; Lowe 2008; Lowe and Benoit 2013). These analysis methods 
are not only useful for extracting latent dimension of parties and politicians,
but also for testing political theories, e.g., intra-party competition (Haber 2015;
Däubler and Benoit 2015), and party positionings (e.g. Catalinac 2017; Proksch
and Slapin 2010). Concerns have been raised around the performances in internal 
validity (Bruinsma and Gemenis 2019), and around the assumptions that both
Wordscores and Wordfish make of their input data (Egerod and Klemmensen 2020;
Proksch and Slapin 2009). In this paper, we propose a novel estimation strategy
that augments the text scaling methods used in political science with named entity
recognition (NER) that recognizes various types of entity objects. We first extract
named entities using state-of-the-art language models in German and English and
scale them with Wordfish Model. We illustrate our strategy using the case of parliamentary 
debates on the topics of immigration issues discussed in the UK House
of Commons and the German Bundestag from 2014 to 2019. Party positions are
estimated and validated with the Chapel Hill Expert Survey (CHES). We find
that (1) parties’ positions estimated by our approach are highly consistent with the
CHES expert's judgment, and (2) our approach achieves better internal validity
in terms of perplexity performance than the basic text scaling model without the
pre-processing step using NER.


**Keywords**：*flairNLP, CHES, Named Entity Recognition, parliamentary debates, wordfish, wordscore, party cohesion*

</div>

---

<div style="text-align: justify">

**Factionalism and the Red Guards under Mao’s China: Ideal Point Estimation Using Text Data** (with Yi-Nung Tsai, National Chengchi University; Daniel Tene, Univeristy of Essex;  Dechun Zhang, Leiden University )

In this paper, we design a new strain of text scaling method, Swordfish (__Slogan-featured Wordfish__), that takes advantage of the TextRank 
algorithm to extract the most representative political slogans in a given context and estimates _Wordfish_ with those extracted text variables. We test this method using the case of the Great Proletarian Cultural Revolution in China and the historical archive of handwritten big-character posters and self-printed tabloids from 1966. We estimate student protests' ideal points by analyzing expressed political views in propaganda publications. Our findings point to evidence of factional re(de)alignments within the movement and demonstrate how the students from different educational backgrounds followed Mao Zedong and Xiaohongshu 小紅書 (Little Red Book) and then fell into armed conflicts that divided families, the classes and the society. The results estimated by our approach are shown to be consistent with the representative qualitative literature of factionalism regarding the Cultural Revolution.</div>

</div>

**Keywords**：*Red Guards, TextRank, wordfish* <br> 

**Documents**: [`slides`](https://raw.githack.com/davidycliao/redguards/master/slides/slides.pdf) | [`paper`](https://raw.githack.com/davidycliao/redguards/master/slides/paper.pdf)

---

<div style="text-align: justify">

**State-led Nationalism: Measuring China’s Online Nationalists on Weibo** (with [<span style="color:#778899"> Dechun Zhang, Leiden University</span>](https://www.universiteitleiden.nl/en/staffmembers/dechun-zhang#tab-1))

Measuring Chinese nationalism on social media is essential to understand the operation of propaganda strategies used by
the government to advance advertisements in its legitimacy and governance in China. 
This research note follows the literature on Chinese nationalism and operationalizes major nationalistic 
concepts commonly found in Sina Weibo (China's most popular social media platform). 
We introduce a machine classifier that identify nationalistic attributes and its probability of being categorized as an attitude of belligerent nationalism on Weibo. 
We train our model using comments and posts from China's state-controlled media, *People's Daily*, on more than one million spanning 
different political incidents through 2018 to 2022. The training source consists of 13,200 Weibo comments, 4,871 nationalistic comments and 8,329 non-nationalistic comments, respectively. 
With CNN trained on top of the BERT layer, the model performance achieves 91\% in F1-Score and 92\% in the weighted average, respectively. 
Recommendations are also included on applying our machine classifier to related textual sources for future research on Chinese politics.

**Keywords**：*Chinese  nationalists*、*nationalism*、*CNN*、*BERT* 、*Weibo* 

</div>

---

<div style="text-align: justify">

**Party Misperception, Party-voter Incongruence and Political Distrust** (with Royce Carroll, Essex; Li Tang, Middlesex University London)

To what extent do misperceptions of party positions affect voters' perception of representation and satisfaction with democracy? This paper offers an explanation using the case of the UK and data from the British Election Survey (BES) and the Chapel Hill Expert Survey (CHES). We show that voters' perceptional gaps in understanding party positions contribute to political incongruence between party and voters, subsequently deteriorating their trust and satisfaction with government. From our analysis, the misperceptions about UK parties increase both perceived and actual incongruence between voters and parties, with those with higher perceptional gaps demonstrating higher party–voter incongruence. This perceptional gap further contributes to citizen distrust and dissatisfaction towards the political system. 

**Keywords**：*income inequality, Chapel Hill Expert Survey, party misperception, political trust* <br> 
**Documents**: [`slides`]() | [`paper`](https://raw.githack.com/davidycliao/figures/master/Party_Misperception__Party_voter_Incongruence_and_Political_Distrust.pdf) 

</div>

---


<div style="text-align: justify">


**Measuring Party Cohesion on Parliamentary Question Keywords** ([<span style="color:#778899"> co-authored with Calvin Yu-Ceng Liao, Post Doctoral Research Fellow at Taiwan Studies Center, National Chengchi University</span>](https://sites.google.com/view/calvin-yuceng-liao/home))

Understanding the positions of parties and legislators is key to conceptualizing party cohesion and their representation in most democracies. This study is to measure intra-party heterogeneity and variability in issue attention by looking at what and why legislators are more likely to oversight the ministry officials on one specific topic or another during the question time. We answer this question using the case of Taiwan Legislative Yuan, and data on written parliamentary questions through an electoral reform from 1993 to 2020. We estimate the position of each legislator on the left-right dimensions using the keywords extracted from the questions that legislators request for information on policies and activities of ministries from executive officials. We document how the electoral reform shapes legislators' ideological position and variability on their issue attentions: party cohesion increases when high variability in issue attention in Single Member District (SMD) and decreases when low variability under Single Non-transferable Vote (SNTV). These findings shed new light on providing a different approach to estimating party cohesion as well as to understanding the changes of political behaviour in representation and political accountability through the electoral reform.

**Keywords**：*party cohesion, intra-party heterogeneity, electoral reform, parliamentary questions*

</div>

---


<div style="text-align: justify">

**官僚團體如何「重寫」意識形態陳述：以《人民日報》習近平思想的評論為例** (與蔡儀儂)

意識形態體系在維繫中共政權的執政穩定，長期扮演了重要角色。雖然 部分觀察透過分析中共制定意識形態的過程，指出官定的意識形態非鐵板一塊，而是黨內政治衝突的折衷結果。
不過，類似研究卻較少觸及意識形態建 構完成後，黨內的官僚組織，如何透過各自的話語體系，將意識形態「改寫」成符合其利益偏好的政治陳述。
在本文，我們以《人民日報》習近平外 交思想的報刊評論為例，並根據 Tsai 與 Kao(2013)發展的「寫作組」概 念，在資料蒐集過程根據評論作者，標記其所屬官僚組織。
在分析策略上，我們結合「自動摘要生成技術」(Automated Text Summmerization)與分析空 間點估計的 Wordfish 泊松空間模型(Poisson Scaling Model)。
在預期發現，我們認為這些討論習近平外交思想的評論，會依據不同作者所屬的不同官僚 組織差別，在關鍵詞的使用存在差異，這反映其代表官僚組織，透過差異性 的話語敘事，標示其政治立場。
整體而言，我們的研究呈示了官僚組織，透 過意識形態「包裝」其利益表達的陳述政治(discourse politics)。

**Keywords**：*意識形態分析*、*文本資料研究*、*習近平思想*

</div>

---


<div style="text-align: justify">

**Topic Models for Political Short Texts: An Application, Validation and Compromises** (with [<span style="color:#778899"> Julia, Ju Yuon Park, Univeristy of Essex</span>](http://www.juyeonpark.com))

</div>




<br/><br/>

<!-- 
<div style="text-align: center">

## Prior Research Before PhD:

</div> 



<div style="text-align: justify">

**2016 亦敵亦友:臺灣民眾 對中國印象的評價《社會科學論叢》23(1):63-105** （與吳重禮、楊和縉）


本文援引研究種族議題（或族群政治）兩個相互競逐的理論—「接觸理論」（contact theory）和「團體威脅論」（group threat theory）—作為研究架構，套用於臺灣和中國民眾的接觸經驗，檢證在兩岸人民交流互動益形密切之際，臺灣民眾對於中國的整體印象，是否會因為接觸頻繁而增進瞭解，提升好感？或者，因為接觸和溝通機會的增加，反而影響臺灣民眾對於中國印象產生負面觀感？作者擷取「2012年總統大選後國內民意對兩岸關係與大陸政策之觀點及變化」電話訪問資料，採取「因素分析」（factor analysis）將民眾對於中國大陸的好惡程度印象區分為「既定印象」、「政治印象」，以及「經濟印象」三個面向，並以「迴歸模型」（regression models）和「有序勝算對數模型」（ordered logit model）進行檢驗。本研究貢獻在於，透過實證結果顯示，在「既定印象」和「政治印象」方面，猶如研究預期，泛綠陣營支持者和本省籍選民對於中國抱持較為負面的觀感，其餘不同社會人口特徵的選民並無顯著差異；值得強調的是，在「經濟印象」方面，泛綠陣營支持者和獨立選民對於中國印象並沒有顯著差異。在結論中，本文摘述實證分析要點，並提出中國印象的研究意涵。

**Keywords**：*中國印象*、*接觸理論*、*團體威脅論*、*統獨議題*, *政黨認同*

**Documents**: [`paper`](https://www.airitilibrary.com/Publication/alDetailedMesh?DocID=19956584-201610-201611230014-201611230014-61-95) 

</div>


---

<div style="text-align: justify">

**2016 原民會主委的補助款？檢視「基本設施維護費」在原住民55個鄉、鎮、市、區分配的實證分析《台灣原住民族研究學報》 4(2):23-63**

誰從政治場域中獲得比較多的政策利益？或在政策過程中，能明確主導利益分配？是分配政治研究中時常被提出來討論的研究議題。有鑑於此，本文以分配政治的實證研究為理論基礎，分析專責原住民族公共事務的中央行政機關－「行政院原住民族委員會」－補助全國55 個平地與山地原住民鄉、區、鎮、市的「基本設施維持費」，檢視由原住民委員會補助偏鄉經濟發展的政策方案是否會受到政治、族群（平地或山地身分別）、或族別因素所影響？綜合實證分析結果，在控制若干影響因素後，總統選舉得票表現較為脆弱的鄉、鎮、市、區，所獲得補助金額比例明顯高於其他原住民地區。換言之，基本設施維持經費對於中央行政部門來說，不僅是一種調節地方財政發展的政策工具，同時能幫助總統攏絡對手陣營支持者、擴大選票支持的手段。在後續的結論中，本文摘述實證分析要點，並提出影響政策利益分配的研究意涵。


**Keywords**：*分配政治與政策*、*原住民族*、*團體威脅族群政治論*、*基本設備維持費*, *行政院原住民族委員會*

**Documents**: [`paper`](https://www.airitilibrary.com/Publication/alDetailedMesh?DocID=P20161117001-201612-201702140019-201702140019-23-63&PublishTypeID=P001) 


</div>

---

<div style="text-align: justify">

**2015 The Rationale for Supporting Nuclear Power: Analysis of Taiwanese Public Opinion Survey _International Relations ofthe Asia-Pacific_ 15 (1): 147-176**（Su, Xiaochen, Chung-li Wu, Yen-chieh Liao, Tai-De Lee, and Chen Tsao)

The future of nuclear energy use has become increasingly contentious across the world. This is especially the case in Taiwan, which simultaneously suffers from the instabilities associated with fossil fuel imports and widespread public doubts about the government's ability to handle a Fukushima-scale disaster, while also being increasingly dependent on nuclear energy. This study employs the 2013 Taiwan Election and Democratization Study (TEDS) survey on the Lungmen Nuclear Power Plant to gauge public opinion on the nuclear issue. The results demonstrate that while the public tends to be pro-nuclear when they are informed about the financial consequences of abandoning nuclear power and reassured about safety concerns, opponents of nuclear power, though numerically fewer, tend to be more vocal. Further research is needed to determine the exact logic of the public's decision making, based on a more precise set of preconditions.

**Documents**: [`paper`](https://academic.oup.com/irap/article-abstract/15/1/147/2937074?redirectedFrom=fulltext) 


</div>

---

<div style="text-align: justify">

**2014 原住民議員與補助款的分配 誰比較多？誰又比較少？為什麼？《台灣原住民族研究學報》 4卷2期: 27-45**

在國內，分配政治研究將進發展了近十年，累積相當多的實證研究的基礎，不過以原住民籍民意代表為觀察對象或針對原鄉補助款分配為議題的研究卻付之闕如。鑑此，本文使用臺東縣政府所公布95年度-100年度「議員建議補（捐）助案件」的補助款資料，以「分配政治研究」過去所關心的數項問題應用在台灣原住民的代議制度，並系統性地比較平地原住民議員與山地原住民議員的分配政治行為。從整體的研究結果來說，政黨、資深程度與委員會召集委員等制度性因素對於原住民議員爭取建議案的影響效果不是相當明顯，但諸多選舉因素仍左右原住民議員爭取超額的補助款，而這也意味著原住民議員的利益分配型態與過去一般分配研究存有顯著地差異性。

**Keywords**：*族群政治*、*原住民研究*、*縣議員建議款*

**Documents**: [`paper`](https://www.airitilibrary.com/Publication/alDetailedMesh?DocID=P20161117001-201406-201611180016-201611180016-27-45&PublishTypeID=P001) 


</div> -->

