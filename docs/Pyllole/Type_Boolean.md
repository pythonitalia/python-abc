# Tipi: Boolean

I valori booleani `True` e `False` sono primitive del linguaggio e si scrivono sempre con la prima lettera maiuscola.

```python
>>> type(True)
<class 'bool'>
>>> type(False)
<class 'bool'>
```

L'operatore `not` restituisce il valore inverso a quello in entrata

```python
>>> not True
False
>>> not False
True
```

L'operatore `and` restituisce True se tutti gli operandi sono True,

```python
>>> True and False
False
>>> True and True
True
```

L'operatore `or` restituisce True se almeno uno degli elementi è True

```python
>>> True or False
True
>>> False or False
False
```

Le primitive booleane `True` e `False` hanno come corrispettivo i numeri interi `0` e `1`.

```python
>>> 0 == False
True
>>> 1 == True
True
>>> 7 == True
False
>>> 7 == False
False
```

Attenzione a non confondere le operazioni booleane tra interi con le operazioni bit a bit (bitwise) and/or che invece utilizzano come operatori `&` e `|`.


L'operatore di uguaglianza `==` restituisce True se i valori confrontati sono uguali

```python
>>> 1 == 1
True
>>> 2 == 1
False
```

L'operatore di disuguaglianza `!=` restituisce True se i valori confrontati sono diversi

```python
>>> 1 != 1
False
>>> 2 != 1
True
```

L'operatore di confronto `<` restituisce True se il primo valore è minore del secondo

```python
>>> 1 < 10
True
```

L'operatore di confronto `<=` restituisce True se il primo valore è minore o uguale al secondo

```python
>>> 1 > 10
False
```

L'operatore di confronto `>` restituisce True se il primo valore è maggiore del secondo

```python
>>> 2 <= 2
True
```

L'operatore di confronto `>=` restituisce True se il primo valore è maggiore o uguale al secondo

```python
>>> 2 >= 2
True
```

I confronti possono essere concatenati!

```python
>>> 1 < 2 < 3
True
>>> 2 < 3 < 2
False
```

L'operatore `is` restituisce `True` se due variabili si riferiscono allo stesso oggetto. Spesso si confonde `is` con `==`, ma quest'ultimo confronta invece solo il valore contenuto nelle variabili. 

```python
>>> alpha = [1, 2, 3, 4] # alpha punta ad una nuova lista [1, 2, 3, 4]
>>> beta = alpha         # beta punta a ciò a cui punta alpha
>>> beta is alpha
True                     # True poiché alpha e beta puntano allo stesso oggeto
>>> beta == alpha
True                     # True poiché alpha e beta indicano lo stesso oggeetto
>>> beta = [1, 2, 3, 4]  # beta ora punta ad una nuova lista [1, 2, 3, 4]
>>> beta is alpha
False                    # False poiché alpha e beta non puntano allo stesso oggetto 
>>> beta == alpha
True                     # True poiché il contenuto degli oggetti è uguale
```

In una valutazione booleana `None`, `0` e `str`/`list`/`dict`/`tuple` vuoti 
vengono considerati `False`. Tutti gli altri valori sono considerati `True`.

```python
>>> bool(None)
False
>>> bool(0)
False
>>> bool("")
False
>>> bool([])
False
>>> bool({})
False
>>> bool(())
False
```

---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
