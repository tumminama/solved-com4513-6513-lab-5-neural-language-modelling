Download Link: https://assignmentchef.com/product/solved-com4513-6513-lab-5-neural-language-modelling
<br>
assignment, you will implement a neural language model.

<h1>N-Gram Neural Language Modelling</h1>

First, you need to download the code for N-Gram Language Modelling from here <a href="https://sheffieldnlp.github.io/com4513-6513/labs/word_embeddings_tutorial.py">https://sheffieldnlp.github.io/com4513</a><a href="https://sheffieldnlp.github.io/com4513-6513/labs/word_embeddings_tutorial.py">6513/labs/word_embeddings_tutorial.py</a><a href="https://sheffieldnlp.github.io/com4513-6513/labs/word_embeddings_tutorial.py">.</a> Second, read the documentation for it here <a href="http://pytorch.org/tutorials/beginner/nlp/word_embeddings_tutorial.html">http://pytorch.org/tutorials/ </a><a href="http://pytorch.org/tutorials/beginner/nlp/word_embeddings_tutorial.html">beginner/nlp/word_embeddings_tutorial.html</a>

<ul>

 <li>Run <sub>py </sub>on a Linux/Unix-based machine, i.e. Ubuntu or MacOS with PyTorch installed (see instruction in Lab 0). <strong><sub>Note 1: </sub></strong>You do not have to implement the CBOW model presented at the end of the file. [0 marks]</li>

 <li>Describe in your report the neural network language model using mathematical equations, fully detailing the dimensionsality of each parameter (<strong><sub>Hint: </sub></strong>it is a kind of multilayer perceptron). You could use a table to summarise the dimensionality of each layer of the network. [2 marks]</li>

 <li>Modify the code given in <sub>py </sub>to model the following toy training set (<strong>Tip: </strong>You need to create a list of sentences, where each sentence is represented as a list of tokens. You need to include start/end of sentence tokens):

  <ul>

   <li>The mathematician ran .</li>

   <li>The mathematician ran to the store .</li>

   <li>The physicist ran to the store .</li>

   <li>The philosopher thought about it .</li>

   <li>The mathematician solved the open problem .</li>

  </ul></li>

 <li><strong><sub>Run a Sanity check: </sub></strong>make sure your model can learn how to predict correctly your training data. Take the sentence

  <ul>

   <li>The mathematician ran to the store .</li>

  </ul></li>

</ul>

and check that for every trigram (i.e. context and prediction) you get the right answer. Does it work? You need to play with the hyper-parameters, such as learning rate, epoch number etc. You will observe some variance in the results, so find and report hyper-parameters that get the correct results in 5 consecutive runs. Among others, your model should be predicting for the context “START The” the word “mathematician”. Why is this happening instead of predicting “physicist”? [3 marks]

<ul>

 <li><strong><sub>Test: </sub></strong>Given a sentence with a gap

  <ul>

   <li>The ______ solved the open problem. which is more likely to fill it in: “physicist” or “philosopher”?</li>

  </ul></li>

</ul>

Get the model to predict this correctly by changing the hyper-parameters (and report them). Discuss whether this would be possible with the bigram ML model from lab 2. Ensure that the model is predicting correctly for the right reason, i.e. that the embeddings for “physicist” and “mathematician” are closer together than the embeddings for “philosopher” and “mathematician”. Use cosine similarity for this (it is implemented in PyTorch, check the API documentation). [3 marks]