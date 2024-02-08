---
title: "Using Transformer-based Language Models to Identify Group Randomized Trial Publications"
collection: publications
permalink: /publication/pubclassifier
date: 2024-12-12
venue: 'tbd'
#paperurl: 'https://link.springer.com/article/10.1007/s00477-013-0780-4'
citation: 'Aghaarabi, E., Murray, D.'
---
## Abstract
Identifying various categories of randomized trial publications from the extensive body of annual publications remains a substantial challenge for the public health community. Monitoring recently published articles in the field is crucial for staying informed about the latest developments and advancements. Using simple search queries to retrieve publications of this type often results in lower sensitivity, making it challenging to identify many positive examples. Text classification has been widely used for categorizing biomedical documents, including research articles, clinical notes, and patient records, into predefined topics. While classical and deep learning models have been previously employed for classifying biomedical publications and identifying various types of randomized trial publications, the use of state-of-the-art language models has yet to be explored within the public health community. Pre-trained language models within the biomedical domain do exist; however, when employed directly for predicting categories in specialized tasks, their performance tends to be suboptimal. There is a necessity to fine-tune these models to enhance their effectiveness for specific tasks. In this research, we present a novel classifier framework which is developed by fine-tuning a pre-trained bidirectional encoder representation from a transformer model known as BiomedBERT. Our approach aims to accurately identify Group Randomized Trials (GRTs), Individually Randomized Group-Treatment Trials (IRGTs), and Stepped Wedge Group-Randomized Trials (SWGRTs) within the biomedical literature. The proposed methodology shows promising results in effectively identifying publications related to the mentioned group randomized trials. 

Our proposed model delivers remarkable results on unseen data, with sensitivity and specificity scores for each class as follows: Non-randomized trials (0.92 and 0.95), GRTs (0.94 and 0.94), IRGTs (0.87 and 0.98), and SWGRTs (0.94 and 0.99), respectively. This model offers a valuable tool for the community to directly identify publications within the mentioned domains 
