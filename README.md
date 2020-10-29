

import nltk 
from nltk.corpus import state_union
from nltk.tokenize import PunktSentenceTokenizer

train_text=state_union.raw("2005-GWBush.txt")
sample_text=state_union.raw("2006-GWBush.txt")

custom_sent_tokenizer=PunktSentenceTokenizer(train_text)

tokenized=custom_sent_tokenizer.tokenize(sample_text)

def process_content():
    try:
        for i in tokenized:
            words=nltk.word_tokenize(i)
            tagged=nltk.pos_tag(words)
            
            chunkGram=r"""Chunk: {<RB.?>*<VB.?>*<NNP><NN>?}"""
            
            chunkParser=nltk.RegexpParser(chunkGram)
            chunked=chunkParser.parse(tagged)
            print(chunked)
            
    except Exception as e:
        print(str(e))
        
process_content()


Chinking #6

train_text=state_union.raw("2005-GWBush.txt")
sample_text=state_union.raw("2006-GWBush.txt")

custom_sent_tokenizer=PunktSentenceTokenizer(train_text)

tokenized=custom_sent_tokenizer.tokenize(sample_text)
def proc_content():
    try:
        for i in tokenized:
            words=nltk.word_tokenize(i)
            tagged=nltk.pos_tag(words)
            
            chunkGram=r"""Chunk: {<.*>+})<VB.?|IN|DT|TO>+{"""
            
            chunkParser=nltk.RegexpParser(chunkGram)
            chunked=chunkParser.parse(tagged)
            print(chunked)
            
    except Exception as e:
        print(str(e))
        
proc_content()


1 train_text=state_union.raw("2005-GWBush.txt")
      2 sample_text=state_union.raw("2006-GWBush.txt")
      3 
      4 custom_sent_tokenizer=PunktSentenceTokenizer(train_text)
      5 

NameError: name 'state_union' is not defined
