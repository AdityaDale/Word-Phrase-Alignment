# Word-Phrase-Alignment

The topic for our major project is “Word-Phrase Alignment”. The main objective of this project is to develop software tools and a scheme for building a word or phrase-aligned corpus of English and Hindi optimally using existing open resources.

This project aims to modify the current method of training deep learning models from sentence level to word/phrase level. The Current method of training deep learning model for translation uses parallel corpus (i.e. a parallel corpus is a set formed by a text and its translation) which is on a sentence level. But this method requires a very large corpus to train the model which makes it difficult to get expected results from a smaller set of data. So if we can convert the parallel corpus to word/phrase structure level it will be easier to train and get a better result from a deep learning model. So comparatively model will require a small-sized corpus for training, eventually, it will reduce the time to train a model, as the size of data is reduced. It will also give more human control over the traditional model.

The project is a part of research at the International Institute of Information Technology Hyderabad, under Anusaarka Lab for their open-source machine translation tool. We are working on the possibility of automating the task of alignment of words/phrases of the translated sentence in order to map these words/phrases with the words/phrases with the same meaning in the source sentence.

--------------------------------------------------------------------------------------------------------------------------------

1. removeNoise.py
   Usage: It is used to remove noise/unwanted text from the corpus.
   Command to run:
   python removeNoise.py fileName

--------------------------------------------------------------------------------------------------------------------------------

2. parser-modification
   
   PATH setting for stanford parser:
   --------------------------------
   Please set the path to stanford parser in the following file.

   'parser-modification.sh'

   for e.g.
   stanford_parser_path='/home/sriram/phrase-alignment/stanford-parser-full-2020-11-17'

   RUN:
   ----
   sh parser-modification.sh input

   OUTPUT:
   -------
   output comes in the standard output.

   For e.g. for the given input sentence "A big fat boy is eating a lot of fruits"

   output will be as follows.

   [[['A'], ['big'], ['fat'], ['boy']], [['is'], [['eating'], [[['a'], ['lot']], [['of'], [['fruits']]]]]], ['.']]
   [['A'], ['big'], ['fat'], ['boy']]
   [['is'], [['eating'], [[['a'], ['lot']], [['of'], [['fruits']]]]]]
   [['eating'], [[['a'], ['lot']], [['of'], [['fruits']]]]]
   [[['a'], ['lot']], [['of'], [['fruits']]]]
   [['a'], ['lot']]
   [['of'], [['fruits']]]

--------------------------------------------------------------------------------------------------------------------------------

3. Sent2table
   
   Usage: This Program collects the details of each node in a sentence tree and returns it in a tabular format.

   To use the Sent2table.py python script you just need to create constituency parse of the sentence and just have to paste it inside parse.txt then run

   Command: python sent2table.py

   we have mention one example in this folder with output for reference.

--------------------------------------------------------------------------------------------------------------------------------

4. Treebank

   Treebank is a collection of manually parsed sentences. It is used as a training dataset for parser to learn parsing.
   
   Using LUCY Treebank we manually generated parse of a sentence and cross check it with parse of Stanford Parser and you can see both Parse tree that we created and of Stanford  
   Parser in the Treebank folder.

