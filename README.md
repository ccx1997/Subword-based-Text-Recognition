# Subword-based-Text-Recognition
Motivations are as follows:
1. We can regard the long word as a combination of several sub-elements, which may be beneficial for the lexicon-free case that is more flexible in real life where word component is free from lexicon.
2. We can relieve the pressure of memory by LSTM, i.e., LSTM only need to remember the root and affix rather than the big number of whole-words requiring lots of samples, and is friendly to gradient propagation.

Some examples which show the weakness of word-based methods like CRNN (suffered from their memory on the lexicon in trainset):

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo1.jpg)
aa------u----t--o---l--d----e---n---t--ii-f--y---- => autoldentify

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo2.jpg)
i---d----ee--n---t--ii-f--y---- => identify

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo3.jpg)
m------a--t-h--l--y--p-e---- => mathlype

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo4.jpg)
t----y--p--e---      => type

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo5.jpg)
cc-------a----r---e----y---o-----v----v----e---r---k---d---ll-llo----w-----hh--f-- => careyovverkdllowhf

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo6.jpg)
v------e---r---k--   => verk

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo7.jpg)
v------e----f---     => vef

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo8.jpg)
h------o----o---o----c----o---o----o----c--k----- => hooocooock

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo9.jpg)
0--------0-----0-----0-----0-----0-----0-----0-----0-----0------ => 0000000000

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo10.jpg)
g-----o---o---o---c---o---o---o---o--g---l--e--- => gooocoooogle

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo11.jpg)
l----u--u---u--d---a--g---a--y--u---c--k--- => luuudagayuck

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo12.jpg)
y-----o--u---d----d---a---d--- => youddad

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo13.jpg)
g------i--v--e--l-l---e---f---i--v--e--- => givellefive

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo14.jpg)
e----mm------e---    => eme

The memory got by LSTM can help to recognize some ambiguous character (e.g., l, o) using the context in one hand, but in other hand limit the ability to recognize out-of-vocabulary words which have somewhat different compositional styles from words in training set.

So we decide to use subword-based method to make RNN only care about the sub-region of a whole word to approach the problem above. It can probabaly reduce the needs of large amount of training data since a word in our method should consist of subwords, showing more intelligence in processing text line.
