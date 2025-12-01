---
tags: [nlp, llm]
---

Ranja Sarkar

<img width="554" height="155" alt="22" src="https://github.com/user-attachments/assets/6f3aa923-5473-429c-b73f-497a6344ffac" />


If represented in a Venn diagram, the AI world underwent a change with the advent of generative AI (genAI). Natural language processing (NLP) and machine learning (ML) remain major subsets in the AI superset. The deep learning (DL) set has genAI as a subset having substantial intersection with NLP.  

<img width="359" height="151" alt="11" src="https://github.com/user-attachments/assets/6ab64b0f-1db1-45fb-b827-7ec9b435e358" />


One would ask, where is Data Science? 

Well, we humans create value with data and it is what we call Data Science that takes many forms. We start with a business problem and work toward an appropriate data-backed solution. AI is part of Data Science. 

Coming back to the Venn diagram, the [remaining space](https://open.substack.com/pub/ranjas/p/artificial-intelligence) in the AI superset would have transfer learning, reinforcement learning, hyperpersonalization.

With NLP, several tasks like topic classification, sentiment analysis, relationship extraction, and entity recognition can be accomplished. The input data for NLP can multimodal like  text, audio, video. I will write about text data here.

📌 **NLP**

NLP involves transforming raw text data into a format that the machine understands. In NLP, each text sentence is called a document and collection of documents is referred to as text corpus.  

1. Data pre-processing or text cleaning comprises of tokenization, stemming & lemmatization

<img width="947" height="194" alt="00" src="https://github.com/user-attachments/assets/45699eed-cd58-4940-b6a3-de6ff6b67958" />

Tokenization is the process of breaking text into individuals words or tokens. Normalizing the text would entail removing punctuations and stopwords, one may or may not utilize it depending on the use case.  Stemming means reducing a word to its stem (root word), it removes the morphological affixes from words, leaving only the root word. 

<img width="634" height="161" alt="01" src="https://github.com/user-attachments/assets/d0d1c718-4b73-4a01-b2a2-1ae45651ad28" />

The stem in lemmatization belongs to a valid word in the language. 

<img width="761" height="184" alt="02" src="https://github.com/user-attachments/assets/6d2a9962-bd23-4722-b9ba-2b6ccf113710" />

Good old **python libraries** like **nltk**, spacy, gensim, textblob can be used to tokenize input text as well.

<img width="477" height="110" alt="03" src="https://github.com/user-attachments/assets/7040db22-9a07-4507-aa04-2d47c946ca4d" />

These days we have [tokenizers](https://github.com/huggingface/tokenizers) by [Hugging Face](https://huggingface.co/) available to do the same. Hugging face also has a [playground](https://huggingface.co/spaces/Xenova/the-tokenizer-playground) to experiment with different tokenizers. 

<img width="256" height="110" alt="05" src="https://github.com/user-attachments/assets/9109a56b-7368-477c-b79c-183fb6812797" />


2. Part-Of-Speech (POS) tagging can be rule-based, statistical or based on deep learning 

This is usually done for entity recognition from a corpus.

3. Vectorization is word embedding which is converting the tokens into numbers. In [embeddings](https://madewithml.com/courses/foundations/embeddings/), we have fixed length representations for the tokens in a text regardless of the number of tokens in the vocabulary. 

![llp](https://github.com/user-attachments/assets/547b6a55-b3b9-4385-bb13-430c9bf08667)
