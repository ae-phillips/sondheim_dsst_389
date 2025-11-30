# “Love” in Stephen Sondheim’s lyrical corpus: An exploration through tf-idf, sentiment analysis, and topic modeling

*This project explores lyrical themes and sentiment in Stephen Sondheim's musicals using R for my DSST 389: Advanced Data Science final project at the University of Richmond (April 2025).*

## Overview
In order to perform my planned textual analysis, I had to create my own corpus of Sondheim musicals. To do this, I manually copy-and-pasted lines from eight shows into their own separate data sets and imported them to R. In terms of criteria, I chose his most famous shows, in combination with shows that have won the Tony Award for Best Musical. In my data tidying, I removed stop words and character names, and I also edited iterations of similar words for clarity of analysis (e.g., all “pies” became “pie”).

Through initial data exploration, I identified ‘love’ as the most frequent term in the corpus as a whole, and I used multiple textual analysis methods to explore the significance of ‘love’ in Sondheim’s corpus. First, I used tf-idf to explore important terms for each show and then used sentiment analysis (AFINN) to provide more context for the shows and their relationship to each other. Finally, with topic modeling, I returned to the topic of ‘love’ and explored important terms across the entire corpus, as well as between the contrasting individual shows. 

## Tools
- R / Quarto
- tidyverse
- tidytext
- dplyr
- stringr
- tidymodels
- glmnet
- kknn
- ggplot2
- ggrepel
- and more! --> check the .qmd file for all packages

## Results

I first completed a preliminary tf-idf analysis of Sondheim's shows to highlight their highly specific subject matters and provide context for future "love" analysis.

<img width="903" height="669" alt="image" src="https://github.com/user-attachments/assets/c30cae8f-400b-4a62-87f7-eb9c968bf1ff" />



