# Tipi: Numeri

I numeri possono essere interi `int` o decimali `float`, i decimali vengono rappresentati con il punto come separazione tra la parte intera e quella decimale.
Python 3 ha anche altri tipi numerici, come le frazione e i numeri complessi, ma in questa breve introduzione non verranno trattati.


```python
>>> type(3)
<class 'int'>
```

```python
>>> type(3.0)
<class 'float'>
```

Le **operazione matematiche di base** si fanno come ci si aspetta

```python
>>> 1 + 1 
2
>>> 8 - 1
7
>>> 10 * 2
20
>>> 35 / 5
7.0
```

Il risultato di una divisione è sempre un numero decimale `float`

```python
>>> 10.0 / 3
3.3333333333333335
```

L'**operatore `//` esegue una divisione tra interi** restituendo un risultato intero. 
I valori della divisione possono essere sia interi che decimali. 
Il risultato, nonostante possa essere sia di tipo intero che decimale, sarà sempre arrotondato ad un intero.

```python
>>> 5 // 3 
1
>>> 5.0 // 3.0
1.0
```

I valori della divisione tra interi possono essere sia positivi che negativi. 
È importante però sapere che nel caso di numeri negativi il risultato sarà arrotondato per eccesso.

```python
>>> 10 / 1.45 
6.8965517241379315
>>> 10 // 1.45
6.0
>>> 10 // -1.45
-7.0
```


L'**operatore `%` restituisce il resto** (modulo) di una divisione

```python
>>> 7 % 3 
1
```

L'**operatore `**` esegue un elevamento a potenza** (x alla y-esima potenza)

```python
>>> 2**3 
8
```

Le parentesi, come in matematica, indicano la precedenza nell'elaborazione dei calcoli


```python
>>> (1 + 3) * 2
8
>>> 1 + (3 * 2)
7
```

È possbile convertire una stringa in numero tramite le funzioni cast `int()` e `float()`.
Python genererà un'eccezione nel caso si passi alle funzioni cast una stringa non convertibile in numero.

```python
>>> a="323"
>>> type(a)
<class 'str'>
>>> a=int(a)
>>> a
323
>>> type(a)
<class 'int'>
>>> a="pippo"
>>> int(a)
Traceback (most recent call last):
 File "<stdin>", line 1, in <module>
ValueError: invalid literal for int() with base 10: 'pippo'
```

---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
