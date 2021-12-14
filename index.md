---
layout: default
---

Throughout the decade, depression has become a common mental disorder worldwide with a growing of affected population. As indicated by WHO, approximately 3.8% of population, 280 million, suffered from depression. Among all, 10.7% of adults and 15% of young people has reported depressive emotion, with 70% of them take anxiety and depression as their major problems in US. As depression is one of the priority conditions covered by WHO for its severeness and high prevalence rate, we would like to focus our research on analysis of the potential factors that affect depression.

## How can we tell the depression?
A growing body of evidence shows that people with depression use language differently. Many studies have unveiled a class of words that can help accurately predict whether someone is suffering from depression. The most robust language marker of depression is the frequency of using first-person singular pronouns, such as I and my. Moreover, specific negative descriptors are linked to the tendency of depression.

Under this context, we have applied **sentiment analysis** to automatically sort text data from Quotebank by positive, negative, and neutral sentiments. The further goals of our project are 
- Analyzing the correlation between the frequency of using negative words and seasons 
- Analyzing the change in the number of negative words each year, and identifying whether the growing number of negative words is related to significant events by date. For example, if we can identify more negative words in 2020 due to the occurrence of COVID-19.

### Research Questions
As the dataset of Quotebank contains data from 2015 to 2020, which enables us to perform statistical analysis along the period, we would like to take advantage of this to analyze the time expansion property. We will focus on analyzing the relationship between the amounts of the language markers and the effects of change of season and significant events.  The detailed questions are as follows:  

1.	It is only until recently that people started to be more and more aware of mental condition. Therefore, we are going to figure out if there is a growing attention to mental condition in society as the disorder prevails by the following keywords: mental illness, psychopath, depression, mental disorder.
2.	Can we see a growing population affected by depression with our text-based detection method in accordance with the statistical results?
3.	Seasonal Affective Disorder (SAD) is a form of depression that occurs in fall and winter due to the decrease of sunlight while recover when spring and summer hit again. We will discuss the effect by looking into the difference between the four seasons.
4.	Apart from SAD, January is known as the most depressing month of the year. As a result of the due dates of credit card bills are usually January, people find themselves overwhelmed by the economics pressure. We will investigate this phenomenon, especially compared with other winter months.
5.	The major events that occurred would also affect people’s emotion. Therefore, we will analyze the impact of these events comparing the data before and after given a certain period, depends on the lasting time of the event, such as COVID-19 pandemic.

### Method

#### Label sentiment by applying analysis packages
We have applied Textblob, the rule-based sentiment analysis tool, to label 100 sentences from Quotebank. Furthermore, we analyzed (1) the polarity and (2) the subjectivity of these sentences.  
  
However, when we drew the positive and negative words into a word cloud, we found that the classification of some words may not be very accurate. For example, some neutral nouns, such as “people,” “time,” and “also,” appeared in the positive word cloud.  
  
Therefore, in the next step, we will consider building a custom model to get more control over the output. One possible package is TensorFlow Hub, a repository of trained machine learning models ready for fine-tuning and deployable anywhere.

#### Word and phrase extraction
We will determine the frequency with which users used specific words or two-word phrases (bigrams) by using open-source Python-based language analysis. For example, we will count the number of the negative words that have been proven to be linked to depression, such as first-person singular pronouns (I, me, and my), ruminating thinking language markers (a lot, lot), and sad expression markers (miss, loss, alone).

#### Topic Modeling
We want to categorize different negative words, such as anxiety, ruminating thinking, and a class of somatic complaints. One possible method is applying latent Dirichlet allocation (LDA). Hopefully, LDA can produce clusters of words in the same context across Quotebank, yielding semantically coherent topics.
 | Potential Topics | Language markers |
 |---|---|
 | Depression mood | Tears, cry, pain |
 | Loneliness | Miss, much, baby |
 | Hostility | Hate, ugh, fuckin |
 | Rumination | Mind, a lot, lot |
 | Anxiety | Scared, upset, worry |
 | Somatic complaints | Hurt, head, bad |
 | Medical references | Hospital, pain, surgery |

## Conclusion

### Reference
