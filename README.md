# SUSCTF-misc
misc自用wp

##checkin
不得不吐槽给机器人发了个信息就被ban了的迷惑情况......



##misound
```python
# coding=utf-8
from random import randint
from math import floor, sqrt
from sys import flags
#已知提示可知_为95，e*_即为101*95，映射到silenteye上可发现101*95=369*26+1
#通过sstv解出的字母转换为ascii码后，发现倒数第二位为66，66-ord('A')=1
#得出转换关系s*hint=sle*26+[ord(stv)-ord('A')]
sle = "207 359 220 224 352 315 359 374 290 310 277 507 391 513 423 392 508 383 440 322 420 427 503 460 295 318 245 302 407 414 410 130 369 317"
hint = "AnEWmuLTiPLyis_etimes_wiLLbEcomE_B"
stv = "NQHFEAOUUUSHTCWJQRFLFNMKGQAOLDWBBI"
sle = sle.split(' ')
flag = ''
for i in range(len(sle)):
    num = ord(stv[i])-ord('A') #常数
    hint1 = ord(hint[i])
    sle1 = int(sle[i])
    s = chr(round((sle1 * 26 + num)/hint1))
    flag += s
print(flag)
```
