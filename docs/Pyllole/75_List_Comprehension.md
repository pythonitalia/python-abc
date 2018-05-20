# List Comprehension

_Prima di approfondire le "List Comprehension" assicurati di conoscere le [liste](Type_List.md), [set](Type_Set.md) e [dizionari](Type_Dictionary.md)._

La sintassi per le _list comprehension_ consente, in modo semplice ed elegante, di costruire sequenze da altre sequenze. 

Limitatamente alle loro possibilità sono un semplice, e più comprensibile, sostituto alla funzione lambda e alle funzioni `map()`, `filter()` e `reduce()`. 

Una _list comprehension_ è formata da:

* Una sequenza (oggetto iterabile)
* Una variabile che rappresenti ogni elemento nella sequenza
* Un'espressione opzionale di controllo/elaborazione
* Un'espressione di output che produce elementi dell'elenco di output dai membri della sequenza di input che soddisfano il predicato.

Nel seguente esempio data una lista si trasformerà in una lista in cui ogni elemento è moltiplicato per due, ma solo se è un numero intero

```python
>>> sequenza=[1,2,3,'a',4, 3.2]                                                    
>>> nuova_lista=[elemento*2 for elemento in sequenza if isinstance(elemento,int)]
>>> print(nuova_lista)
[2, 4, 6, 8]
```

In cui:

* `sequenza` è l'oggetto iterabile
* `elemento` assume di volta in volta il valore di ogni elemento nella lista
* `if isinstance(elemento,int)` è l'espressione opzionale di controllo/elaborazione
* `elemento\*2` è l'espressione di output
