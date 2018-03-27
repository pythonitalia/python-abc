# If - Else

In un programma le istruzioni vengono eseguite nell'ordine in cui sono scritte nel codice. 

Per poter eseguire una parte di questo codice solo in alcuni casi si utilizza l'istruzione di controllo  `if`/`else`.

_Ricorda, in python [l'indentazione](Syntax.md#indentazione) è molto importante!_

La sintassi di base di `if` è:

```python
if condizione:                                         
    comandi_da_eseguire
```

Esiste poi la possibilità di eseguire altri comandi se la condizione non risulta soddisfatta aggiungendo l'istruzione `else`.

```python
if condizione:                                         
    comandi_da_eseguire
else:
    diversi_comandi_da_eseguire
```

Nel caso in cui ci siano più condizioni da valutare è possibile aggiungere `elif` (contrazione di "else if").

```
if condizione_1:                                         
    comandi_da_eseguire
elif condizione_2:                                         
    comandi_da_eseguire
elif condizione_3:                                         
    comandi_da_eseguire
else:
    diversi_comandi_da_eseguire
```

In quest'ultimo caso il "ramo" di comandi in `else` verrà eseguito solo se nessuna delle condizioni precedentemente valutate risulterà positiva.

Un esempio in Python:

```python
numero=5                                         
if numero > 10:
    print("numero è maggiore di 10")
elif numero < 10:
    print("numero è minore di 10")
else:
    print("numero è uguale a 10.")
```

Darà come risultato:

```python
numero è minore di 10                                
```

## Espressioni condizionali 

Un'espressione condizionale, conosciuta in altri linguaggi tramite gli operatori ternari, è la possibilità di eseguire un determinato comando solo se una condizione risulta vera, altrimenti eseguirne un altro.

La sintassi è: `<expression1> if <condition> else <expression2>`

Un tipico esempio è l'assegnazione condizionale. Nel seguente esempio alla variabile `isApple` verrà assegnata las stringa `'Yes'` solo se la condizione `fruit == 'Apple'` sarà `True`, altrimenti sarà assegnata la stringa  `'No'`

```python
fruit = 'Apple'
isApple = 'Yes' if fruit == 'Apple' else 'No'
```

---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
