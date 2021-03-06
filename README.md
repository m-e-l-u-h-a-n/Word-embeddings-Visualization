**Name:** Purushottam Tiwari
**Roll No.:** 19074029
**Branch:** CSE(IDD)

### Description of the Lab Task:
The aim of this task was training word vectors using different algorithms like skipgram, continuous bag of word(cbow) and GloVe and using them for spelling error detection.
I have described the code for each algorithm one by one:

#### Skipgram:
The code for this is contained in `skipgram.ipynb` notebook.
* We first import all the required libraries.
* Then we load the data which we first processed to contain only space separated words. Data is loaded using `LineSentence` from `gensim` library.
* Then we train the model for the loaded data with following parameters:
	 - Window size: 5
	 - min_count: 5
	 - threads: 8
	 - sg: 1  # for skipgram training
* Then we save the model using model.save() so that we can use it later for visualization plot. We comment this line to avoid saving it repeatedly.
* As the model is saved so we load it using `Word2Vec.load()` and then for an idea of the correctness of our vector embeddings we find the some most similar vectors to king.
* In next step we try to get a complete space **TSNE** plot for our word vectors. For this we manipulate the dimensions of vectors and and get a corresponding dataframe for our transformed word vectors.
* For most similar words plot we select a few words and then get their most similar embedding from the model. Then these are plotted to get most words visualization.

#### Cbow:
Nearly all of the steps for this were same except for `sg=0` while initializing model for training using `Word2Vec`. So for sake of brevity I have written same steps as for skipgram again here.

#### GloVe:
The code for this is contained in `glove.ipynb` notebook.
* We first clone [https://github.com/stanfordnlp/GloVe](https://github.com/stanfordnlp/GloVe).
* Then inside cloned folder we run `make` from terminal.
* Then inside this folder it contains a file `demo.sh` which we modify by changing `CORPUS=train.txt` and `MAX_ITER=50`  so as our corpus is `train.txt` then from terminal we run this script using `bash glove.sh`.
* Running above script generates a vector file `vectors.txt` . These are desired glove word embeddings.
* Now  for visualizing in `glove.ipynb` we load this `vectors.txt` and modify it to convert in a form so that it can be represented as a model generated using `gensim` . 
* Above step is done using `KeyedVectors.load_word2vec_format(word2vec_output_file, binary=False)` . This is function provided by `gensim` library.
* Then we save the model using model.save() so that we can use it later for visualization plot. We comment this line to avoid saving it repeatedly.
* After this steps of visualization using **TSNE** and **PCA** plots are almost same as for skipgram and cbow because we have converted it to a model which can be represented as one which is generated using gensim.
* As the model is saved so we load it using `Word2Vec.load()` and then for an idea of the correctness of our vector embeddings we find the some most similar vectors to king.
* In next step we try to get a complete space **TSNE** plot for our word vectors. For this we manipulate the dimensions of vectors and and get a corresponding dataframe for our transformed word vectors.
* For most similar words plot we select a few words and then get their most similar embedding from the model. Then these are plotted to get most words visualization.

### Results/Visualizations and summaries:
Visualizations of the plots for word embeddings are:

#### Skipgram:
Visualizations for this are contained in `skipgram.ipynb` file as plots created using `matplotlib` .
These visualizations include:
* complete space visualization(**TSNE** plot)
* complete space visualization(**PCA** plot)
* most similar word representation(**TSNE** plot)
*  most similar word representation(**PCA** plot)

#### cbow:
Visualizations for this are contained in `skipgram.ipynb` file as plots created using `matplotlib` .
These visualizations include:
* complete space visualization(**TSNE** plot)
* complete space visualization(**PCA** plot)
* most similar word representation(**TSNE** plot)
*  most similar word representation(**PCA** plot)

#### GloVe:
Visualizations for this are contained in `skipgram.ipynb` file as plots created using `matplotlib` .
These visualizations include:
* complete space visualization(**TSNE** plot)
* complete space visualization(**PCA** plot)
* most similar word representation(**TSNE** plot)
*  most similar word representation(**PCA** plot)
