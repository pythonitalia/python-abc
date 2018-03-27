# Try - Except

_Ricorda, in python [l'indentazione](Syntax.md#indentazione) è molto importante!_

Le eccezioni (exception) sono errori rilevati durante l'esecuzione di un programma.

Puoi pensare ad un'eccezione come ad un allarme che avvisa di una determinata condizione o evento e, se non gestisto, ferma l'esecuzione del programma.

Nell'esempio qui sotto viene generata un'eccezione `NameError`, questo accade poiché la variabile riga non è stata inizializzata prima di essere utilizzata.

```python
>>> 4 + (riga*3)   
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'riga' is not defined
```

Gestire le eccezioni significa "intercettare" gli errori e applicare le giuste contromisure affinché il programma continui la sua corretta esecuzione. 
Per far questo si utilizza `try`/`except`,  puoi semplicemente immaginarlo come _"prova del codice e, a seconda dell'errore, esegui un codice riparatore"_.

Se cerco di aprire un file che non esiste Python generarà un'eccezione:

```python
>>> filename="myfile.txt"  
>>> f = open(filename, 'r')
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
FileNotFoundError: [Errno 2] No such file or directory: 'test.txt'
```

Con `try`/`except` provo ad aprire il file e in caso di errore comunico il problema all'utente finale in modo più chiaro.

```python
filename="myfile.txt"  
try:
    f = open(filename, 'r')
except:
    print('Impossibile aprire il file ', filename)
```

È possibile anche definire diversi casi a seconda del tipo di eccezione che è stata generata. Inoltre, con `else`, è possibile definire un codice da eseguire solo nel caso in cui non avvenga nessun errore. Infine con `finally` si può indicare un codice da eseguire in qualunque caso.

Nel seguente esempio si cerca di aprire un file, leggerne il contenuto e convertirlo in un numero intero (nota: quando si legge da un file si leggono stringhe).
Si controlleranno poi due eccezioni, una relativa all'apertura del file e una relativa alla conversione in numero intero.
Un `except` senza indicata una determinata eccezione intercetterà tutti gli altri errori.
Il codice in `else` verrà eseguito solo se non sono state generate eccezioni.
Infine, in qualunque caso, si scriverà "Fine" sulla console.

```python
try:
    f = open('myfile.txt')
    s = f.readline()
    i = int(s.strip())
except OSError as err:
    print("OS error: {0}".format(err))
except ValueError:
    print("Errore: il file non contiene un numero intero!")
except:
    print("Errore inaspettato!")
else:
    print("Il file contiente il numero "+str(i))
    f.close()
finally: 
    print("Fine")
```

### Esempio pratico
**Conversione e controllo risultato di input()**

Se si vuole utilizzare il risultato della funzione `input()`, che è sempre una stringa, come dato numerico è necessario convertirlo utilizzando le funzioni [int() o float()](Type_Number.md). Il valore immesso potrebbe però non essere convertibile in un numero, in questo caso la funzione di conversione usata genererà un'errore che è meglio gestire.

```python
stringa = input("Inserisci un numero intero: ") 
try:
    numero=int(stringa)
except:
    print("Il dato inserito non è un numero intero")
```

Vedi l'esempio pratico nella pagina [cicli](Loops.md) per come ripetere il controllo finché il valore è corretto.
