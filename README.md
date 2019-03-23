# Subword-based-Text-Recognition
Motivations are as follows:
1. We can regard the long word as a combination of several sub-elements, which may be beneficial for the lexicon-free case that is more flexible in real life where word component is free from lexicon.
2. We can relieve the pressure of memory by LSTM, i.e., LSTM only need to remember the root and affix rather than the big number of whole-words requiring lots of samples, and is friendly to gradient propagation.

Some examples which show the weakness of word-based methods like CRNN (suffered from their memory on the lexicon in trainset):

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo4.jpg)
h---e-r--l-o-w-o--r-i-d--- => herloworid

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo5.jpg)
h------ee---l---l---o----- => hello

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo6.jpg)
w-------o---r---l---d----- => world

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo7.jpg)
t---o-bb-e-f-u--l-u-u--n-- => tobefuluun

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo8.jpg)
ff----u---u---u--u---n---- => fuuuun

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo9.jpg)
t-eed-e-sfllav-r-en-ceeu-l => tedesflavrenceul

![Image text](https://github.com/ccx1997/Root-Affix-based-Text-Recognition/blob/master/imgs/demo10.jpg)
s--t-l-aa-w---r-e-n--c-e-- => stlawrence

