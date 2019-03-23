# Subword-based-Text-Recognition
Motivations are as follows:
1. We can regard the long word as a combination of several sub-elements, which may be beneficial for the lexicon-free case that is more flexible in real life where word component is free from lexicon.
2. We can relieve the pressure of memory by LSTM, i.e., LSTM only need to remember the root and affix rather than the big number of whole-words requiring lots of samples, and is friendly to gradient propagation.

Some examples which show the weakness of word-based methods like CRNN:
