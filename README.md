# “Love” in Stephen Sondheim’s lyrical corpus: An exploration through tf-idf, sentiment analysis, and topic modeling

*This project explores lyrical themes and sentiment in Stephen Sondheim's musicals using R for my DSST 389: Advanced Data Science final project at the University of Richmond (April 2025).*

## Introduction: Stephen Sondheim

Stephen Sondheim is one of Broadway’s most beloved and successful lyricists/composers. He is a Tony Award, Academy Award, and Grammy Award winner, with a corpus of work ranging from Broadway musicals to television and movie scores. Sondheim’s shows are known for their exploration of relationships, morality, and love – heavily facilitated by Sondheim’s lyrical verbosity and musical complexity. In an interview with *The New York Times Magazine*, Sondheim reflected that “[he had] always conscientiously tried not to do the same thing twice,” which was no easy feat when competing in a Broadway market that had turned “corporate” and “cookie-cutter.” Because of this, even though Sondheim grapples with similar themes in his shows, his characters and narratives feel brand new every time, ranging from homicidal barbers in the 18th century, to fairytale characters lost together in the forest, to musings on marriage in affluent New York social circles, to the complex inner world of 19th-century artists.

## Project Overview
Sondheim’s shows grapple with life’s hard questions, and his lyrics often trend toward the existential, allowing the audience to sympathize with broad themes – despite the often hyperspecific nature of Sondheim’s shows. Through initial data exploration, I identified **‘love’ as the most frequent term in the corpus as a whole**, and I used multiple textual analysis methods to explore the significance of ‘love’ in Sondheim’s corpus. First, I used tf-idf to explore important terms for each show and then used sentiment analysis (AFINN) to provide more context for the shows and their relationship to each other. Finally, with topic modeling, I returned to the topic of ‘love’ and explored important terms across the entire corpus, as well as between contrasting individual shows. 

## Data Description
In order to perform my planned textual analysis, I had to create my own corpus of Sondheim musicals. To do this, I manually copy-and-pasted lines from eight shows into their own separate data sets and imported them to R. In terms of criteria, I chose his most famous shows, in combination with shows that have won the Tony Award for Best Musical.

During data tidying:
- I removed stop words  
- I removed character names  
- I standardized similar word iterations for clarity (e.g., all “pies” became “pie”)  

These cleaned datasets formed the basis for my analysis.

## Methods/Results

### tf-idf
In an interview with *The Paris Review*, Sondheim said, “Two of the hardest words in the language to rhyme are life and love. Of all words!” Unfortunately for Sondheim, both “love” and “life” are in the top five most-used words in the corpus.

<img width="511" height="350" alt="image" src="https://github.com/user-attachments/assets/0489f4b5-aa89-4d3d-b0c9-34d3b604430d" />

Because these terms have such high frequencies, they receive **low tf-idf scores** when comparing shows. This boosts show-specific terms and helps highlight the uniqueness of each musical, providing useful context before my next analyses. 

<img width="761" height="701" alt="image" src="https://github.com/user-attachments/assets/5eda81e6-c766-4f23-bdf0-84c04b60e027" />

### Sentiment Analysis

Next, I moved to sentiment analysis to provide additional show contexts before interpreting topic models. Sondheim’s shows portray a wide variety of sentiment. The **average sentiment for the entire corpus is 0.0596**, and it's somewhat surprising that *Into the Woods* and *Sweeney Todd* — despite their violence and darker themes — do not average in the negatives.

<img width="702" height="441" alt="image" src="https://github.com/user-attachments/assets/7245929c-8c08-4c5c-bb04-7b17fe983cec" />

Interestingly, the ANOVA output shows that differences between average mean sentiment across musicals are **not statistically significant** (p = 0.443). One important consideration is that audience perception of “tone” is heavily influenced by music and orchestration. For example:
- *Sweeney Todd* contains many songs in minor keys  
- *Company* features brighter, major-key orchestrations  

Therefore, even if the lyrics themselves do not differ dramatically in sentiment, this analysis cannot account for the influence of musical setting.

### Topic Modeling
Next, I use topic modeling to explore how “love” appears throughout the corpus — first in a global model, then in two individual show models.

<img width="780" height="483" alt="image" src="https://github.com/user-attachments/assets/b6585436-7f66-48d1-a880-8b4c5941cf19" />

After exploring models with 5–15 topics, I selected **10 topics**, as they provided the most cohesive overview of how “love” functions in Sondheim’s lyrics (in my somewhat qualified opinion). A couple
of shows definitely skew the top terms, but this is to be expected due to unequal term frequency of ‘love’ between shows. As shown in Figure 5, Passion, Follies, and Company all contributed the most instances of ‘love’ to this model. For example, “marry” and “ready” can be attributed to Company because grappling with the implications of marriage, loneliness, and love is a central theme of the show.

<img width="760" height="508" alt="image" src="https://github.com/user-attachments/assets/4e5091d3-6ae6-4621-b1d1-7e0b6c743644" />

#### Passion vs. Sweeney Todd
To compare extremes, I created topic models for two shows that have higher frequencies of “love” but differ greatly in sentiment:
- *Passion:* highest frequency of “love” (n = 90) and highest average sentiment (0.1338)  
- *Sweeney Todd:* lower frequency of “love” (n = 22) and lower average sentiment (0.0099)

As shown in Figure 7, Passion’s exploration of love is broader, more ‘cliche’, and contains terms that one would expect (e.g., “happiness,” “mine,” “beautiful”, etc.). However, there are hints of darker themes through words like “unhappy” and “forgive,” suggesting a more complex attitude toward love than apparent at first glance.

<img width="776" height="484" alt="image" src="https://github.com/user-attachments/assets/558a16bb-17e2-401d-af84-8237809e3636" />

Contrastly, as shown in Figure 9, in Sweeney Todd, ‘love’ is associated with a plethora of terms, obvious and not. For example, “heaven,” “wait,” and “nice” are fairly innocent, but the topic of love in Sweeney Todd becomes more complex when we consider words like “worst,” “trouble,” and “harm.” The presence of these negative words speaks to the pain that Sweeney (and other characters) feel when grappling with love, and Sondheim uses Sweeney Todd to explore how love and morality intertwine – for good and ill.

<img width="772" height="483" alt="image" src="https://github.com/user-attachments/assets/25e188f9-fd30-46ea-89db-49f7862cb70e" />

## Conclusion
As explored above, Sondheim’s lyrical corpus is diverse, and his characters and narrative perspectives are often highly specific. Despite this (or because of this), his work navigates broad themes of love and life in accessible, meaningful, and emotionally powerful ways.

“Love” emerged as the most common word in the corpus, and through tf-idf, sentiment analysis, and topic modeling, I highlighted the varied ways Sondheim explores love through unique characters and narratives. Shows with more positive average sentiment (e.g., *Passion*) still approach love with complexity, balancing more “cliché” terms (like “happiness” and “mine”) with brooding or difficult ones (“unhappy,” “forgive”). Shows with more negative average sentiment (e.g., *Sweeney Todd*) blend hopeful and melancholy language (“heaven” vs. “harm,” “nice” vs. “trouble”), illustrating the intricate nature of Sondheim’s lyric writing and storytelling.

Importantly, as previously mentioned, lyrics only tell part of the story when examining love – without the context of orchestration, staging, and acting, we cannot explicate the full story of Sondheim’s narrative intent. Nonetheless, analyzing his lyrics separately provides important insight into his lyrical genius.
