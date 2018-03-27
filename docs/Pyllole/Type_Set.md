# Tipi: Set

_Prima di studiare i set assicurati di conoscere le [liste](Type_List.md)._

I set sono come le liste ma non possono contenere doppioni.

Un set si inizializza in questo modo:

```python
>>> empty_set = set()  
>>> empty_set
set()
>>> type(empty_set)
<class 'set'>
```

Inizializzare un set con un dei valori ha una sintassi molto simile all'inizializzazione di un dizionario.

```python
>>> some_set = {1, 1, 2, 2, 3, 4}  
>>> some_set
{1, 2, 3, 4}
```

Come le chiavi di un dizionario, gli elementi di un set devono essere di tipo immutabile

```python
>>> invalid_set = {[1], 1} 
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
>>> valid_set = {(1,), 1}
```


Aggiungere uno o più elementi ad un set con il metodo `.add()`

```python
>>> some_set.add(5)
>>> some_set
{1, 2, 3, 4, 5}
```

Fai intersezioni su un set con `&`

```python
>>> other_set = {3, 4, 5, 6}   
>>> some_set & other_set  
{3, 4, 5}
```

Fai unioni su set con `|`

```python
>>> some_set | other_set   
{1, 2, 3, 4, 5, 6}
```

Fai differenze su set con `-`

```python
>>> {1, 2, 3, 4} - {2, 3, 5}   
{1, 4}
```


Effettua la differenza simmetrica con `^`

```python
>>> {1, 2, 3, 4} ^ {2, 3, 5}   
{1, 4, 5}
```

Controlla se il set a sinistra contiene quello a destra

```python
>>> {1, 2} >= {1, 2, 3}
False
```

Controlla se il set a sinistra è un sottoinsieme di quello a destra

```python
>>> {1, 2} <= {1, 2, 3}
True
```


Controlla l'esistenza in un set con `in`

```python
>>> 2 in some_set  
True
>>> 10 in some_set
False
```


---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
