Requirements
============

* python3

Quick Start
===========

1. Clone repo and run code:
```
$ git clone git@github.com:eliwjones/symbiont.git
$ cd symbiont
$ ./random > my_random_data.bin
```

2. Press random keys on keyboard.  When the keypress buffer is full enough, it will extract random data to flush to stdout.  When you have enough bytes for your tastes, CTRL-C to exit:
```
Press keys to harvest entropy (CTRL-C to exit):
Total bytes harvested: 191
Total bytes harvested: 382
eliwjones@LAPTOP-P7Q7FKRN:~/github/eliwjones/symbiont$
```

3. View your random data:
```
$ xxd my_random_data.bin
00000000: af32 4718 69e2 9772 94fd f403 702c 3922  .2G.i..r....p,9"
00000010: c689 f7f4 cbec 0f12 aa12 4d93 5414 ea1e  ..........M.T...
00000020: c2db bb0e e8c6 929e 8ab1 8eaf 643e 5bbe  ............d>[.
00000030: 3693 79a5 2874 56f5 940e b8f3 9d15 3fb5  6.y.(tV.......?.
00000040: 1060 dd97 b2dd 38cf 83d2 2a11 6623 dcfb  .`....8...*.f#..
00000050: 90cc 43ae a4fb ab85 9f85 dd38 bef3 66ec  ..C........8..f.
00000060: 66fd 9d03 bffb 38dd 0a82 b277 d0d8 d294  f.....8....w....
00000070: ddd9 0733 7c87 8653 ea33 ae54 e097 bf73  ...3|..S.3.T...s
00000080: 9166 3025 8e04 e752 1de2 a16f 7a4e 291e  .f0%...R...ozN).
00000090: 4228 658e ef15 9871 f148 4f89 7860 6d53  B(e....q.HO.x`mS
000000a0: 68ac a252 89ce fe17 8116 e444 703e 58ed  h..R.......Dp>X.
000000b0: 6639 ad38 e944 df9d d6fe 0375 0066 6b7f  f9.8.D.....u.fk.
000000c0: c950 6b57 22b7 4676 4229 0414 3ba0 aba5  .PkW".FvB)..;...
000000d0: aeac c460 63b4 0afb f775 6eef 30cc 3cd4  ...`c....un.0.<.
000000e0: efaf 56e1 1f14 8dc2 795e 2aef 99b6 99f3  ..V.....y^*.....
000000f0: 6912 a654 23ec 9243 9d17 2dbc 2554 7b21  i..T#..C..-.%T{!
00000100: 507b 24ae 1310 a6bc 4905 944c 0950 37b2  P{$.....I..L.P7.
00000110: 8502 980d 69c9 1ce2 5e84 50af c2a9 8229  ....i...^.P....)
00000120: 993e c4ca 3592 0234 b84a 610a 64e1 f200  .>..5..4.Ja.d...
00000130: e76d df1c 063f defa b305 e3fa c7e8 2982  .m...?........).
00000140: e49a 642d 9102 ae2c bd05 37f8 fe8c b7e1  ..d-...,..7.....
00000150: 6e8f db5d db39 ab55 dbd9 46a3 377a 34e3  n..].9.U..F.7z4.
00000160: f5c7 5fae 6eb0 c7f8 fdae e919 a87c f2d3  .._.n........|..
00000170: 1ce8 353f 5fcb 69a2 f40f f75e 53a3       ..5?_.i....^S.
```

Notes
=====

This has only been tested on Ubuntu Linux and Mac OS.

FAQ
===

1. Why aren't there more sources of entropy?

   Multiple sources of entropy just serve to mask the interesting parts of this puzzle.  We are interested in taking a signal that is attempting to be random and then ensuring that it is as random as possible.
   
   Also, it would take much longer to do right and this is time limited.

2. Why bother compressing the keystroke buffer?

   Compressing the buffer of keypresses helps us dodge issues like the user typing the same set of keys over and over during entropy harvesting (e.g. 'jkjkjkjkjkjkjk').  It also serves to highlight the link between compression and randomness (and randomness and the axioms of systems).

   See Gregory Chaitin's [META MATH!](https://arxiv.org/pdf/math/0404335.pdf) for a fun exploration of this.
