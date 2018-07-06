etagger
====

### description

- original git repository
  - https://github.com/monikkinom/ner-lstm

- modification
  - modified for tf version(1.4)
  - removed unnecessary files
  - fix bugs for MultiRNNCell()
  - refactoring .... ing
    - split model.py, train.py, inference.py

### pre-requisites

- data
  - [download](https://github.com/mxhofer/Named-Entity-Recognition-BidirectionalLSTM-CNN-CoNLL) 
  - place train.txt, dev.txt, test.txt in data dir

- glove embedding
  - [download](http://nlp.stanford.edu/data/glove.6B.zip)
  - unzip to 'embeddings' dir

### how to 

- convert word embedding to pickle
```
$ python embvec.py --emb_path embeddings/glove.6B.50d.txt --emb_dim 50
```

- check max sentence length
```
$ python check_sentence_length.py
train, max_sentence_length = 113
dev, max_sentence_length = 109
test, max_sentence_length = 124
```

- train
```
$ python train.py --emb_path embeddings/glove.6B.50d.txt.pkl --emb_dim 50 --sentence_length 125 --class_size 5 
```
