# like_math

## 0x00 题面

经典的 RSA 算法求解, 题目给出了`p`, `q`, `e`, `c`, 让我们求 m

```
q=12106336658010389134561518797826786644628703483746530426502241762315458584564363822664931919110777650399983937704328098885103718797696015272648786264768477，
p=12962714722654750396330602541478380793704558761845902654113449131429542068478625485006207362626416709875951595546085553043216283852235276592511589141684619，
e = 8582803，
c=98331774696618436305378724276209087114551457901670417608980331967679759882177360865225996705229657264683036750207337158980257842479941725238085677042084860575319933715526700368578973160777644619972166232675800432243169641095859647952452372603563449968679765435785928187782173687196891567650774616589410240859
```

## 0x01 求解

这里使用了 python 进行求解,

```python
import RSATools

q=12106336658010389134561518797826786644628703483746530426502241762315458584564363822664931919110777650399983937704328098885103718797696015272648786264768477
p=12962714722654750396330602541478380793704558761845902654113449131429542068478625485006207362626416709875951595546085553043216283852235276592511589141684619
e = 8582803
c=98331774696618436305378724276209087114551457901670417608980331967679759882177360865225996705229657264683036750207337158980257842479941725238085677042084860575319933715526700368578973160777644619972166232675800432243169641095859647952452372603563449968679765435785928187782173687196891567650774616589410240859

fn = (p-1)*(q-1)
n = p*q

d = RSATools.getPrivate(p, q, e)

flag = RSATools.Decrype(c, d, n)
print(RSATools.HexToStr(hex(flag)))
```