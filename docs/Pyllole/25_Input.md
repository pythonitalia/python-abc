# Input

La funzione `input()` permette di interagire con la console e fornire dei dati, tramite tastiera, al programma.

L'argomento passato alla funzione `input(prompt)` è la stringa che viene mostrata sulla console in attesa dell'inserimento dei dati.

```python
>>> input("Inserisci la tua età: ")
Inserisci la tua età: 
```

Il programma resterà in attesa dell'inserimento di un dato finché non verrà premuto il tasto invio.

La funzione restituisce ciò che è stato inserito tramite tastiera.

```python
>>> age=input("Inserisci la tua età: ")
Inserisci la tua età: 42
>>> print(age)
42
```

### Valore restituito

La funzione `input()` restituisce sempre una stringa, se si vuole utilizzare il risultato come dato numerico è necessario convertirlo utilizzando le funzioni [int() o float()](Type_Number.md).

```python
>>> stringa = input("Inserisci un numero intero: ")
Inserisci un numero intero: 42
>>> numero=int(stringa)
```
**Importante**: se la stringa passata a `int()` non è convertibile in un intero, Python genererà un'errore, è quindi consigliabile gestire l'eccezione con [try/except](Try_Except.md)

**Nota**: nelle versioni 2.x l'attuale funzione input() si chiamava raw_input(). La funzione input() di Python2 esiste ma ha un comportamento differente da quello qui descritto.

Vedi l'esempio pratico nella pagina [try/except](Try_Except.md) per come gestire l'errata conversione.

Vedi l'esempio pratico nella pagina [cicli](Loops.md) per come ripetere input() finché il valore è corretto.
