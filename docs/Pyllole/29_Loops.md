# Cicli

_Prima di studiare i cicli e gli iteratori assicurati di conoscere le [liste](53_Type_List.md)._

Per ripetere una determinata azione più volte e/o su più elementi si utilizzano le istruzioni `for` e `while` per costruire dei _"cicli"_.

Il programma ripeterà il codice all'interno del ciclo per un numero di volte determinato da una determinata condizione.

_Ricorda, in python [l'indentazione](11_Syntax.md#indentazione) è molto importante!_


## For

I cicli `for` scorrono gli elementi di un oggetto iterabile, per esempio una lista, ripetendo il codice per ogni elemento.

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

I cicli `for` possono scorrere anche i numeri rappresentati da un oggetto `range`.

`range(stop)` restituisce un oggetto `range` che rappresenta una sequenza di numeri interi a partire da `0`, fino a `stop` escluso, con passo `1`. Per esempio, `range(4)` rappresenta i numeri `0`, `1`, `2`, `3`.

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

La funzione `range()` permette di specificare anche il valore iniziale e il passo.

`range(start, stop)` rappresenta una sequenza di interi a partire da `start`, fino a `stop` escluso, con passo `1`.

`range(start, stop, step)` permette di specificare il passo, che può essere positivo o negativo, ma non zero. Il valore finale `stop` è sempre escluso.

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

I cicli `while` ripetono il codice finché la condizione indicata è vera.

```python
x = 0
while x < 4:
    print(x)
    x += 1
```

**Nota**: La sintassi `x += 1` è la versione compatta di `x = x+1`

### Esempio pratico
**Ciclo while per riproporre la richiesta di dati in caso di errore di immissione**

La funzione `input()` acquisisce un valore inserito da tastiera in formato stringa. A volte è necessario che il dato acquisito sia un numero, in questi casi si utilizzano le funzioni `int()` o `float()` per convertirlo.

Si può quindi  utilizzare `try`/`except` per controllare che sia stato inserito un dato valido, ma per riproporre la domanda in caso di errore è necessario creare un ciclo.

Nel seguente esempio ripetiamo la richiesta finché `numero` è `None`, cioè finché non è stato acquisito un intero valido. Se la conversione fallisce, viene gestita l’eccezione `ValueError` e `numero` rimane `None`. Anche `0` è un valore intero valido e permette di terminare il ciclo.

```python
numero = None

while numero is None:
    try:
        numero = int(input("Inserisci un numero intero: "))
    except ValueError:
        print("Il dato inserito non è un numero intero")
```

---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
