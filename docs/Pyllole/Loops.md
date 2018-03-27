# Cicli

_Prima di studiare i cicli e gli iteratori assicurati di conoscere le [liste](Type_List.md)._

Per ripetere una determinata azione più volte e/o su più elementi si utilizzano le istruzioni `for` e `while` per costruire dei _"cicli"_.

Il programma ripeterà il codice all'interno del ciclo per un numero di volte determinato da una determinata condizione.

_Ricorda, in python [l'indentazione](Syntax.md#indentazione) è molto importante!_


## For

I cicli `for` iterano sulle liste, cioé ripetono un codice per ogni elemento all'interno di una lista.

Il seguente codice:

```python
for animale in ["cane", "gatto", "topo"]:              
    print ("{0} è un mammifero".format(animale))
```

Genera il seguente risultato:

```python
cane è un mammifero                                    
gatto è un mammifero
topo è un mammifero
```

I cicli for posso iterare anche dal risultato di una funzione `range()`.

Infatti `range(numero)` restituisce una lista di numeri da zero al numero dato

Il codice:

```python
for i in range(4):
    print (i)
```
Scriverà:

```python
0                                                      
1
2
3
```

La funzione `range()` ha anche altri paramentri opzionali.

`range(lower, upper)` restituisce una lista di numeri dal più piccolo `lower` al più grande `upper`.

`range(lower, upper, step)` restituisce una lista di numeri dal più piccolo `lower` al più grande `upper` incrementando del valore `step`.

Il codice: 

```python
for i in range(10,30,5):
    print (i)
```

Scriverà:

```python
10                                                      
15
20
25
```

## While

I cicli `while` vengono eseguiti finchè la condizione indicata viene a mancare.

```python
x = 0                                               
while x < 4:
    print(x)
    x += 1  
```

**Nota**: La sintassi `x += 1` è la versione compatta di `x = x+1`

### Esempio pratico
**Ciclo while per riproporre la richiesta di dati in caso di errore di immissione**

La funzione `input()` acqusisce un valore inserito da tastiera in formato stringa. A volte è necessario che il dato acquisito sia un numero, in questi casi si utilizzano le funzioni `int()` o `float()` per convertirlo. 

Si può quindi  utilizzare `try`/`except` per controllare che sia stato inserito un dato valido, ma per riproporre la domanda in caso di errore è necessario creare un ciclo.

Nel seguente esempio ripetiamo la richiesta finché a `numero` non viene assegnato un valore.

```python
numero=None                                                                        
while not numero:
    try:
              numero=int(input("Inserisci un numero intero: "))
    except:
        print("Il dato inserito non è un numero intero")
```

---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
