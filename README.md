Requirements
============

* python3

Quick Start
===========

1. Clone repo and run code:
```
$ git clone git@github.com:eliwjones/symbiont.git
$ cd symbiont
$ ./random
```

2. Press random keys on keyboard.  When the keypress buffer is full enough, it will extract random data to flush to stdout.
```
mrz@mrzsss:~/eliwjones/symbiont$ ./random
Press keys to harvest entropy (CTRL-C to exit):
                                               O�	ҸK�W��O9�[F[���c�`���W��E�@T�$����/:�pH��Bi�ň7�c�T|@U��Z��䪋zjm����;1�#ws/`��'�QIO�	��P-+�
           ��z��4��y���~P)��r������:���Y�!�y�����׫��re�̙�`~����B;��L�}(T���Ĳ��J(v�"I��cx�D����B����w�
                               ��}z�·
                                     ��ؘ�2ݻZ�]Ш{�LV�m�\��Уq!�����<��D��J��Jq
mrz@mrzsss:~/eliwjones/symbiont$
```

Notes
=====

This has only been tested on Ubuntu Linux.

FAQ
===

1. Why aren't there more sources of entropy?

   Multiple sources of entropy just serve to mask the interesting parts of this puzzle.  We are interested in taking a signal that is attempting to be random and then ensuring that it is as random as possible.
   
   Also, it would take much longer to do right and this is time limited.

2. Why bother compressing the keystroke buffer?

   Compressing the buffer of keypresses helps us dodge issues like the user typing the same set of keys over and over during entropy harvesting (e.g. 'jkjkjkjkjkjkjk').  It also serves to highlight the link between compression and randomness (and randomness and the axioms of systems).

   See Gregory Chaitin's [META MATH!](https://arxiv.org/pdf/math/0404335.pdf) for a fun exploration of this.
