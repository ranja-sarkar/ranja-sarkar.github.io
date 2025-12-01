---
tags: [nlp, llm]
---

Ranja Sarkar

<img width="554" height="155" alt="22" src="https://github.com/user-attachments/assets/6f3aa923-5473-429c-b73f-497a6344ffac" />


If represented in a Venn diagram, the AI superset has two major subsets - Natural language processing (NLP) and machine learning (ML). Deep learning (DL) or neural networks forms a sub-subset and generative AI is a subset of DL having substantial intersection with NLP.  

<img width="359" height="151" alt="11" src="https://github.com/user-attachments/assets/6ab64b0f-1db1-45fb-b827-7ec9b435e358" />


One would ask, where is Data Science? 

Well, we humans create value with data and it is what we call Data Science that takes many forms. We start with a business problem and work toward an appropriate data-backed solution. AI is part of Data Science. 

Coming back to the Venn diagram, the [remaining space](https://open.substack.com/pub/ranjas/p/artificial-intelligence) in the AI superset would have transfer learning, reinforcement learning, hyperpersonalization.

With NLP, several tasks like topic classification, sentiment analysis, relationship extraction, and entity recognition can be accomplished. The input data for NLP can multimodal like  text, audio, video. I will write about text data here.

📌 **NLP**

NLP involves transforming raw text data into a format that the machine understands. In NLP, each text sentence is called a document and collection of documents is referred to as text corpus.  

✅ Data pre-processing or text cleaning (by regular expressions) comprises of tokenization, stemming & lemmatization

Tokenization is the process of breaking text into individuals words or tokens. Normalizing the text would entail removing punctuations and stopwords, one may or may not utilize it depending on the use case.  Stemming means reducing a word to its stem (root word), it removes the morphological affixes from words, leaving only the root word. 

<img width="634" height="161" alt="01" src="https://github.com/user-attachments/assets/d0d1c718-4b73-4a01-b2a2-1ae45651ad28" />

The stem in lemmatization belongs to a valid word in the language. 

<img width="761" height="184" alt="02" src="https://github.com/user-attachments/assets/6d2a9962-bd23-4722-b9ba-2b6ccf113710" />

Good old **python**](https://www.nltk.org/) libraries like **nltk**, spacy, gensim, textblob can be used to tokenize input text as well.

<img width="477" height="110" alt="03" src="https://github.com/user-attachments/assets/7040db22-9a07-4507-aa04-2d47c946ca4d" />

These days we have [tokenizers](https://github.com/huggingface/tokenizers) by [Hugging Face](https://huggingface.co/) available to do the same. Hugging face also has a [playground](https://huggingface.co/spaces/Xenova/the-tokenizer-playground) to experiment with different tokenizers. 

<img width="256" height="110" alt="05" src="https://github.com/user-attachments/assets/9109a56b-7368-477c-b79c-183fb6812797" />

✅ Part-Of-Speech (POS) tagging can be rule-based, statistical or based on deep learning 

This is usually done for entity recognition from a corpus.

✅ Vectorization is word embedding, which is converting the tokens into numbers. In [embeddings](https://madewithml.com/courses/foundations/embeddings/), we have fixed length representations for the tokens in a text regardless of the number of tokens in the vocabulary. 

N-grams can be used when we want to preserve sequence information in the text data (what word is likely to follow a given one). Unigram (N=1) however does not contain any sequence information (a word is considered individually). 

The **classical approach** of converting text into numeric vectors is to use the **Bag-of-words (BoW)** method. The principle of BoW is to take all the unique words/tokens from the text and create a text corpus called vocabulary. Using the vocabulary, each sentence/document can be represented as a vector consisting of ones and zeros, depending on whether a word from the vocabulary is present in the sentence or not. With one-hot encoding, each token is represented by an array of vocabulary size but with embeddings, each token now has the shape of an embedding dimension. 

-----

In [transformer architecture](https://github.com/ranja-sarkar/LLM-RAG/blob/main/attention.pdf) which underlies **large language models (LLMs)**, a positional encoding matrix is created to represent all the possible positions a word/token can take. 

Positional encoding is used to provide a relative position for each token in a sequence. When reading a sentence, each word in the sentence is dependent on the words around it. For example, some words have different meanings in different contexts, so a model should understand these variations and the words that each word relies on for context. 
In the architecture, the values in the representation are not fixed binary values but changing floating points allowing for fine-grained learned representations.

-----

Now coming back to the classical approach, two sentences are said to be similar if they contain similar set of words. To add more context to the vocabulary, tokens may be grouped together. This method is called N-gram approach. An N-gram is a sequence of N tokens for example, a bigram is a sequence of two words. Once the vocabulary is chosen, occurrences of the grams must be counted. The downside of BoW approach is that popular or frequent words become too important.

<img width="473" height="233" alt="101" src="https://github.com/user-attachments/assets/4790dfc4-4ecb-4a7f-87f6-d593d5565c64" />


A better method called **term frequency-inverse document frequency (TF-IDF)** is used. TF-IDF consists of TF that captures the importance of the word wrt the length of the sentence and IDF which captures in how many sentences the gram occurs wrt the total number of sentences, thus highlighting the rarity of the word. If N is the total number of documents, n is the number of documents containing the word or keyword, IDF = log(N/n).

<img width="478" height="112" alt="102" src="https://github.com/user-attachments/assets/1e5e0dab-d462-4704-a0d0-a8454a8c9117" />

A word has a higher TF-IDF score if it occurs more (frequently) in a document but occurs less or infrequently in the corpus. The TF-IDF score determines how unique the word is in the corpus.

A lexical (keyword) search result is scored by similarity methods like TF-IDF whose scales are usually unbounded, while a semantic (vector) search result is scored by distance methods like cosine similarity etc. whose scales are within a closed interval.

The journey from lexical search to semantic search to a more advanced hybrid search is about how information retrieval can be improved. Hybrid search is sort of a ‘sum’ of lexical search and semantic search and when done right, can yield more relevant results than either. The methods used to merge the lexical and semantic search results to get to a hybrid search query have been well explained in the article by [Elastic Search service](https://www.elastic.co/search-labs/blog/hybrid-search-elasticsearch).

Other hybrid search engines are Snowflake Cortex Search and Azure AI Search. One can enhance search experience by combining the precision of keyword search and the context understanding of semantic search by crafting hybrid search queries. 

📌 **Machine Learning**

Post pre-processing and feature extraction, the data is ready to be consumed that is, models can be trained with the data.

A **supervised learning** model learns patterns from the features to predict the labels. We perform classification tasks with labelled data, for example detection of spam emails wherein the model is trained with emails that have labels (spam and no-spam). Typical supervised learning algorithms used for text classification are (multinomial) [Naive Bayes](https://colab.research.google.com/drive/1KP4h2GylP6bH9H0q_W0k6gQokWXasY9-) and logistic regression.  

**Unsupervised learning** encompasses 

1. **clustering** algorithms like (agglomerative/bottom-up) [hierarchical clustering](https://scikit-learn.org/stable/modules/clustering.html#hierarchical-clustering) (connectivity-based), kmeans clustering (centroid-based), density-based clustering (DBSCAN, [OPTICS](https://scikit-learn.org/stable/auto_examples/cluster/plot_optics.html)) 

2. automated **text summarization** and **topic modeling**

**Text summarization**, as the name suggests is creating summary of a corpus. Summarization algorithms like [Latent Semantic Analysis (LSA)](https://www.datacamp.com/tutorial/discovering-hidden-topics-python) perform best with big and long documents. 

<img width="669" height="258" alt="11" src="https://github.com/user-attachments/assets/2f06f6fa-fc07-4833-bc89-b7eb7db52c1d" />


**Topic modeling** focuses on extracting themes from a collection of text documents (when texts are diverse). Topic models are probabilistic models. They are developed using linear algebraic methods such as singular value decomposition (SVD) to uncover latent semantic structures from texts wherein matrix factorization divides a feature matrix into smaller components. 

<img width="534" height="267" alt="22" src="https://github.com/user-attachments/assets/6cfd8f25-0735-4285-8eb7-7b9b05c288b2" />

Algorithms such as [Latent Dirichlet Allocation (LDA)](https://scikit-learn.org/stable/modules/generated/sklearn.decomposition.LatentDirichletAllocation.html#sklearn.decomposition.LatentDirichletAllocation), LSA take advantage of inear algebra to divide a document into topics (clusters of words). The resulting vector contains all topics with weights. Similar content can be grouped by their topics (text classification).  

LDA is a conditional, probabilistic form of topic modeling which uncovers the latent topics (themes) characterizing a collection of documents. If we have two topics, Topic 1 and Topic 2, the scores attached to each word are the probability of that keyword appearing under a topic across the whole corpus.

<img width="155" height="96" alt="33" src="https://github.com/user-attachments/assets/9776af16-ef34-4a30-a69a-93c6b2e04861" />

📌 **Tokens to neural networks to LLMs**

LLMs make use of the transformer architecture and Generative AI is backed by LLMs. LLMs are trained on a vast amount of text data. The input is a huge number of tokens with which massive neural networks are trained. 

*LLMs split the text (input sequence/sentence) into tokens, convert them into vector embeddings.*

*LLMs use positional embeddings to track token order.* 

Positional encoding is typically introduced as a set of additional vectors that are added to the embeddings. A positional encoding vector is created for each position so each position has a unique representation, before being fed into the network. Feedforward neural networks apply non-linear transformations to the token representations, allowing capture of complex patterns and relationships. 

*The self-attention mechanism in a transformer architecture allows each word to attend to every other word in the sequence, weighing the importance for the current token.
The cross-attention mechanism on the other hand allows looking across a related sequence. Self-attention operates in multiple attention heads to capture different relationships between tokens. Cross-attention is also multi-headed. The activation function softmax is used to calculate attention weights in the multi-head attention mechanism.*

-----

The families of the transformer architecture are encoder-only, decoder-only, and [encoder-decoder](https://magazine.sebastianraschka.com/p/understanding-encoder-and-decoder). An encoder network looks across the input sequence and the decoder network looks across a sequence of representations from the encoder. The **GPT (generative pre-trained transformer)** series developed by OpenAI has a decoder-only architecture, has unidirectional (left to right) context handling, and used primarily for text generation and summarization. 

-----

A transformer processes input sequences in parallel, making it efficient for training and inference. It has better long-range interaactions and makes it deeper (in layers) than Recurrent Neural Networks (RNNs) in practice.  It needs less training time than that needed by RNNs which also run into limitations in retaining context when the “distance” or range between pieces of information in an input is long.

💡 **A transformer is one of the most important sequence modeling improvements of the past decade.**

📌 **GPTs to Agents**




![llp](https://github.com/user-attachments/assets/547b6a55-b3b9-4385-bb13-430c9bf08667)
