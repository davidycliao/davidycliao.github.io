# [Script] Parallelly Run Udpipe in R


## 1. NLP in UDpipe  

<div style="text-align: justify">

The NLP workflow mostly consists of tokenization, parts of speech tagging, lemmatization and dependency parsing. [UDpipe](https://github.com/ufal/udpipe) is one of my favourite NLP library, initially designed in C++ dealing with multiple tasks in text processing. I highly recommend UDpipe because this not only works faster but also work well with pipe function, which can help R user organize own workflow. Now UDpipe is also available in CRAN hosted by [Jan Wijffels](https://cran.r-project.org/web/packages/udpipe/vignettes/udpipe-annotation.html). The package also provides well-explained [vignettes](https://bnosac.github.io/udpipe/docs/doc0.html) in various NLP techniques and made such resources openly accessible to a newbie. Here, I  demonstrate how to implement parrel computing in your code and make a tailored function for your analysis. 

</div>

## 2. Prerequisites

### Speech Dataset: UK Parliarment 
|      Countries          |     Period      | 
|-------------------------|:---------------:|
| The UK House of Commons | 1988/11-2019/01 | 

Source: ParlSpeech2 (Rauh and Schwalbach 2002)

**R script**
```{r}
str(Corp_HouseOfCommons)
```

**R console**
```
'data.frame':	1956223 obs. of  11 variables:
 $ date          : chr  "1988-11-22" "1988-11-22" "1988-11-22" "1988-11-22" ...
 $ agenda        : chr  "Queen's Speech" "First Day [Debate On The Address]" "First Day [Debate On The Address]" "First Day [Debate On The Address]" ...
 $ speechnumber  : int  1 2 3 4 5 6 7 8 9 10 ...
 $ speaker       : chr  "CHAIR" "CHAIR" "Giles Shaw" "John Maples" ...
 $ party         : chr  NA NA "Con" "Con" ...
 $ party.facts.id: num  NA NA 1567 1567 1516 ...
 $ chair         : logi  TRUE TRUE FALSE FALSE FALSE FALSE ...
 $ terms         : num  74 55 2511 1470 2768 ...
 $ text          : chr  "I have to acquaint the House that this House has this day attended Her Majesty in the House of Peers, and that "| __truncated__ "It may be for the convenience of the House if I announce the proposed pattern of the remaining days of the deba"| __truncated__ "I beg to move,. That an humble Address be presented to Her Majesty, as follows: Most Gracious Sovereign, We, Yo"| __truncated__ "I am delighted to second the motion. When I had recovered from the pleasant surprise of being asked to make thi"| __truncated__ ...
 $ parliament    : chr  "UK-HouseOfCommons" "UK-HouseOfCommons" "UK-HouseOfCommons" "UK-HouseOfCommons" ...
 $ iso3country   : chr  "GBR" "GBR" "GBR" "GBR" ...

```
### (2) necessary libraries 

<div style="text-align: justify"> 
Most of the time we need to load many libraries to achieve one goal, then are being confused by those library functions. So, I suggest to set up a function to categorize them. </div>

|                              Packages                          |      Aims       |        
|----------------------------------------------------------------|-----------------|
| `readxl` , `lubridate` ,`tidyr` ,`stringr` ,`tidyverse`        | tidy up data               | 
| `parallel` ,`future`, `future.apply` ,`doParallel`, `furrr`    | Parallel computing         |
| `udpipe`                                                       | NLP tool kits              |


**R script**

```{r}
pkg_install = function(pkg){
  new.pkg = pkg[!(pkg %in% installed.packages()[, "Package"])] 
  if (length(new.pkg)) 
    install.packages(new.pkg, dependencies = TRUE)
  sapply(pkg, require, character.only = TRUE, USE.NAMES = TRUE)}
```

**R script**
```
pkg_install(nlp_toolkits)
```

**Console**
```
> udpipe 
> TRUE 
```
---
**R script**
```
pkg_install(wrangling_toolkits)
```
**Console**
```{r}
> readxl lubridate     tidyr   stringr  tidytext    scales tidyverse 
>   TRUE      TRUE      TRUE      TRUE      TRUE      TRUE      TRUE 
```

**R script**
```c
pkg_install(pkg_parallel)
```
**Console**
```{r}
> parallel       future future.apply   doParallel        furrr 
>     TRUE         TRUE         TRUE         TRUE         TRUE 
```
## 3. Computing Competitions 

#### (1) no paralleled setting

This is script that I modified from [Jan Wijffels](https://bnosac.github.io/udpipe/docs/doc0.html).

**R script**
```{r}
set.seed(5)
ho_textdf <- Corp_HouseOfCommons %>%
  rowid_to_column("ID") %>%
  sample_n(ID, size = 1000, replace = TRUE)

system.time({
udmodel <- udpipe_download_model(language = "english")
udmodel_english <- udpipe_load_model(file = udmodel$file_model)
hoc_parse <- udpipe_annotate(udmodel_english, x = ho_textdf$text, doc_id = ho_textdf$ID)  
hoc_pasrsed <- as.data.frame(hoc_parse, detailed = TRUE)
hoc_pasrsed})
```

**Console**
```
>    user  system elapsed 
> 227.330   3.389 233.483 
```

#### (2) Parallel computing type 1

**R script**
```{r}
system.time({
udmodel <- udpipe_download_model(language = "english")
udmodel_english <- udpipe_load_model(file = udmodel$file_model)
annotate_splits <- function(x, file) {
  ud_model <- udpipe_load_model(file)
  x <- as.data.table(udpipe_annotate(ud_model, 
                                     x = x$text,
                                     doc_id = x$ID))
  return(x)
}
plan(multiprocess, workers = detectCores())
corpus_splitted <- split(ho_textdf , seq(1, nrow(ho_textdf), by =  round(nrow(ho_textdf) / detectCores())))
annotation <- future_lapply(corpus_splitted, annotate_splits, file = udmodel_english$file)
hoc_pasrsed <- rbindlist(annotation)
hoc_pasrsed})

```


```
>   user  system elapsed 
>  5.305   1.578  48.922 
```

#### (3) Parallel computing type 2

**R script**
```{r}
speech_tag = function (textdata, textvar, lang,...) {
  textdata[[textvar]] = iconv(textdata[[textvar]], to = "UTF-8",sub = "")
  textdata = textdata %>%
    mutate(year = year(date)) %>%
    split(.$year)
  if (lang == "English"){udmodel_lang <- udpipe_load_model(file = udpipe_download_model(language = "english")$file_model)$file}
  if (lang == "German"){udmodel_lang <- udpipe_load_model(file = udpipe_download_model(language = "german")$file_model)$file }
  if (lang == "Spanish"){udmodel_lang <- udpipe_load_model(file = udpipe_download_model(language = "spanish")$file_model)$file }
  if (lang == "Dutch"){udmodel_lang <- udpipe_load_model(file = udpipe_download_model(language = "dutch")$file_model)$file }
  if (lang == "Czech"){udmodel_lang <- udpipe_load_model(file = udpipe_download_model(language = "czech")$file_model)$file }
  if (lang == "Finnish"){udmodel_lang <- udpipe_load_model(file = udpipe_download_model(language = "finnish")$file_model)$file }
  if (lang == "Swedish"){udmodel_lang = udpipe_load_model(file = udpipe_download_model(language = "swedish")$file_model)$file }
  if (lang == "Denish"){udmodel_lang = udpipe_load_model(file = udpipe_download_model(language = "denish")$file_model)$file }
  future::plan(future::multiprocess, workers = parallel::detectCores()-1)
  Sys.sleep(0.1) 
  annotation = future.apply::future_lapply(textdata, function(x, file) {
    ud_model = udpipe::udpipe_load_model(file)
    x = data.table::as.data.table(udpipe::udpipe_annotate(ud_model, x = x$text, doc_id = x$ID))
    return(x)}, file = udmodel_lang) %>%
    rbindlist()%>%
    mutate(doc_id = as.integer(doc_id)) %>%
    as.data.frame()
  Sys.sleep(0.1) 
  return(annotation)}

ho_textdf <- Corp_HouseOfCommons %>%
  rowid_to_column("ID") %>%
  sample_n(ID, size = 1000, replace = TRUE)

system.time({
hoc_pasrsed <-speech_tag(textdata = ho_textdf, textvar = "text", lang = "English")
})
```
**Console**
```
>  user  system elapsed 
>  7.068   2.362  76.236 
```

#### (4) Let's compare those outputs 
|                         |    user   |  system   |  elapsed   |    
|-------------------------|:----------|:----------|:----------:|
| no paralleled setting   |  227.330  |  3.389    | 233.483    |
| type 1                  |  5.305    |  1.578    |  48.922    |
| type 2                  |  7.068    |  2.362    |  76.236    |

#### (5) Gentle advice: 

- Do not run the whole batch of speech dataset on `AWS EC2` if you are not ready for it, from my personal experience. You might end up eating pasta until your monthly payment comes next time.

- Please cite Straka and  Strakov's work , big thank to [UDpipe](http://ufal.mff.cuni.cz/udpipe) research group; as well as [Wijffels](https://cran.r-project.org/web/packages/udpipe/index.html) to  make this efforts openly.  


