# Moduli

Quando si creano programmi complessi per migliorarne leggibilità, manutenzione e riusabilità è preferibile suddividerlo in diversi file. 
Python utilizza i moduli proprio per permetterti di utilizzare ciò che hai definito in un file all'interno di un altro script.

Un modulo è un file contenente dichiarazioni e definizioni Python, ciò che viene definito in un modulo può essere importato in altri moduli o dal modulo principale.

Il nome del modulo sarà il file (senza il suffisso `.py`). 

All'interno di un modulo, il nome del modulo (come stringa) è disponibile come valore della variabile globale `__name__`. 

Per importare un modulo:

```python
>>> import math                                        
>>> print(math.sqrt(16))
4.0
```

Puoi ottenere specifiche funzione da un modulo

```python
>>> from math import ceil, floor                       
>>> print(ceil(3.7))
4.0
>>> print(floor(3.7))
3.0
```

Puoi importare tutte le funzioni da un modulo
Attenzione: questo non è raccomandato

```python
>>> from math import *
```

Puoi abbreviare i nomi dei moduli

```python
>>> import math as m                                   
>>> math.sqrt(16) == m.sqrt(16)
True
```

Potete scoprire quali funzioni e attributi sono definiti in un modulo

```python
>>> import math                                        
>>> dir(math)
['__doc__', '__loader__', '__name__', '__package__', ...]
```

**Attenzione**: Se nella cartella corrente hai uno script chiamato math.py, Python caricherà quello invece del modulo math. Questo succede perchè la cartella corrente ha priorità sulle librerie standard di Python


---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
