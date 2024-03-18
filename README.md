# Advanced Topic Modeling Research: Tweets

## Background:
This advanced topic modeling research project is an expansion of a classic NLP [project](https://github.com/Jenni-Hawk/NLP_TopicModeling/blob/main/NLP_Presentation.pdf) that I conducted that uncovered the key topics amongst 34,000 tweets. At that time, LSA with TF-IDF was  the best performing of the traditional NLP models. Given the rapid pace of NLP advancements it was important to test newer, more modern algorithms. Various sentence transformers and LLMs were also tested.

## Primary Objectives: 
- Increase confidence in business decision making when using topic modeling algorithms to understand consumers by testing different algorithms. 
- Conduct research on topic modeling algorithms to determine which can best uncover topics and deliver high human coherency. 

#### Algorithms Tested Against Each Other:
- LSA with TF-IDF
  - Took top 75% of tweets based on probability
- BERTopic vs KeyBERT
- [BERTopic + GPT4](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/BERTopic_GPT4_retweets_copy.ipynb)
- [BERTopic + Llama 2](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/Llama2_retweets_BAAI.ipynb) (Llama-2-13b-chat-hf)
- Sentence Transformers Tested
  - all-MiniLM-L6-v2
  - BAII/bge-small-en
    
#### How will performance of each model be determined?</ins>
- LSA vs BERTopic will be quantitatively scored based on how well humans interpret the coherence of topics.
- For each model, a random sampling of content is taken from each topic. 'Intruder' content is randomly injected into each topic. Humans are asked to identify the intruder content. Scoring is based correctly identify the intruder content. This indicates the strength of coherence of a topic that an algorithm creates.
  - [BERTopic Scoring Code](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/BERTopic_Scoring_WITH_RETWEETS.ipynb)
  - [LSA Scoring Code](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/LSA_Scoring_WITH_RETWEETS_Intruders.ipynb)

#### Research Findings
- BERTopic greatly outperformed LSA on human topic coherence scoring
- GPT4 appeared to be more accurate than Llama2 in delivering topic labels but Llama2 is a solid fallback to OpenAI in this particular use case.
  - It would be interesting to dive deeper into understanding LLM performance in topic labeling and get a quantitative understanding of this through a human preference scoring methodology. One issue arount this is the stochastic nature of OpenAI. While OpenAI promised developers a seed state for reproducibility it hadn't yet materialized when I last checked on it. 
- [Case Study: Business Audience](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/Tweets%20Case%20Study%20Tech.pdf)
- [Test Summary Sheet](https://github.com/Jenni-Hawk/Advanced_Topic_Modeling/blob/main/Test%20Summary.pdf)

#### Secondary Objective
- Determine the impact of including retweets versus removing retweets
- Findings: Given how people use Twitter to express themselves, removing duplicates does not provide an accurate understanding of what the top topics are from a volume perspective. This volume perspective is critically important for business people to understand the scale and influence of a topic. As a best practice for tweet analysis, I recommend removing duplicate tweets as a secondary step in the analysis process (not a first step) to double check that different topics don't clearly emerge when duplicates are removed. 



