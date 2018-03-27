# Variabili

## Dati

**Alla fine puoi realizzare un programma per il disegno o un videogioco ma, fondamentalmente, un programma è solo elaborazione di dati.**

La sintassi dei linguaggi di programmazione permette di spostare ed elaborare dati in infiniti modi, ma prima di tutto devi sapere cosa sono i dati.

All'interno della memoria del tuo PC tutti i dati sono _byte_, gruppetti di 8 _bit_, che possono assumere un valore tra 0 e 255. Naturalmente se utilizzo due byte insieme posso rappresentare un numero più grande (da 0 a 65535).

A seconda di come i byte vengono utilizzati e interpretati è possibile rappresentare sia numeri più grandi sia altri tipi di dati, per esempio un testo o una immagine.

Potremmo decidere che i numeri da 65 a 90 indicano le lettere dell'alfabeto, così per memorizzare un testo mi basterà scrivere i byte relativi ad ogni sua lettera. Potremmo altresì decidere che il nero è 0 e il bianco è 255, in mezzo tutte le sfumature di grigio e così poter memorizzare un'immagine.

Così nascono gli standard, dall'ASCII a UTF-8, dalle GIF alle PNG, tutti i modi per rappresentare testo, immagini e suoni sono fondamentalmente byte interpretati da algoritmi.

Ogni linguaggio di programmazione ha i suoi tipi di dati con le proprie particolari caratteristiche, ma in generale i tipi di base sono:

* [Booleani](Type_Boolean.md): 0 o 1, chiamati anche False o True
* [Numeri interi](Type_Number.md): in grado di rappresentare, a seconda del numero di byte utilizzati, i numeri interi da -N a +N
* [Numeri decimali](Type_Number.md): numero in virgola mobile, indica il metodo di rappresentazione approssimata dei numeri reali
* [Stringhe](Type_String.md): sequenze di caratteri (lettere, numeri e simboli) che formano un testo

Esistoni inoltre molti tipi di dati complessi, dagli array agli oggetti, ma per il momento è meglio fermarsi a questi.


## Le variabili

A livello astratto una variabile è un contenitore in cui puoi inserire valori, e modificarli, durante l'esecuzione del tuo programma.

Più o meno in tutti i linguaggi di programmazione, per assegnare un valore ad una variabile, si utilizza una sintassi tipo:

```python
nome="Pippo"
```

In realtà **una variabile non è _il contenitore_ ma solo un soprannome che si dà ad una zona di memoria**. 

In Python, per gran parte dei tipi, assegnare un nuovo valore ad una variabile non vuol dire modificare il valore di una zona di memoria, ma far "puntare" il nostro "soprannome" ad una nuova zona di memoria con un nuovo contenuto.  
Questa operazione è del tutto trasparente per il programmatore, ma è una cosa molto importante da sapere quando si realizzano programmi in cui le performance contano.

_Per uteriori informazioni su questo argomento cercare in rete "[Python immutable types](https://www.google.it/search?q=python+immutable+types)"_

### Nomi e convenzioni delle variabili

In Python i nomi delle variabili possono essere di qualsiasi lunghezza e possono usare lettere maiuscole o minuscole, il carattere di sottolineatura `_`  e le cifre da 0 a 9. 
I nomi delle variabili non possono iniziare con una cifra e non possono essere uguali alla parole riservate del linguaggio Python, come ad esempio `if`, `else`, `and`.
I nomi delle variabili sono case sensitive, cioé i caratteri maiuscoli e quelli minuscoli sono considerati come se fossere due lettere differenti. Quindi `nome` e `Nome` sono considerate due variabili differenti.

Infine, come convenzione per migliorare la leggibilità del codice, si suggerisce di dare alle variabili un **nome minuscolo con le eventuali parole separate dal carattere di sottolineatura `_`**. 


### Tipizzazione

Il programma, quando viene eseguito, deve sapere quanto spazio di memoria dovrà "assegnare" ad una variabile. Lo spazio utilizzato da un numero intero è differente da quello utilizzato da una stringa. 
Per questo molti linguaggi di programmazione necessitano che una variabile sia inizializzata, prima di essere utilizzata, assegnandogli un determinato tipo. Questi linguaggi si definiscono _tipizzati_.

**Python è un linguaggio tipizzato dinamicamente**, non c'é bisogno di inizializzare una variabile prima di utilizzarla, è possibile cambiare tipo alla variabile in qualunque momento semplicemente assegnandogli un differente valore.

Di seguito assegnamo valori differenti alla variabile nome ed utiliziamo la funzione `type()` per vedere che cambia tipo senza alcun problema.

```python
>>> nome="Pippo"
>>> type(nome)
<class 'str'>
>>> nome=7
>>> type(nome)
<class 'int'>
```


È comunque necessario che una variabile sia stata "creata", assegnandogli un valore, prima di utilizzarla all'interno del programma.

```python
>>> if (my_var==2):
...    print("my_var è uguale a 2")
...
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'a' is not defined
```

**Importante**: qui sopra abbiamo anticipato un esempio di controllo `if` in cui c'é `my_var==2`. 
Il doppio carattere uguale `==` è sempre un operatore di uguaglianza, non una assegnazione (vedere [operatori booleani]()).

### Casting

Il _casting_ in programmazione è la conversione di un dato da un tipo ad un altro.

Potremmo avere una variabile a cui è assegnato il valore `"123", anche se sembra un numero, come già suggeriscono le virgolette, in realtà si tratta di una stringa (magari acquisita tramite [input](Input.md)).

Se volessi trattare questo `"123"` come se fosse un numero, e sommargline ad esempio un altro, dovrei prima trasformalo in un intero. 
Per convertire in intero una stringa, o un float, si utilizza la funzione `int()`.

```
>>> my_var="123"
>>> print(int(my_var)+20)
143
```

C'è una funzione di casting per ogni tipo di dato, molto usate sono, ad esempio, `str()`, `float()`, `list()` o `dict()`.

## Tutto è un oggetto

Senza voler anticipare concetti troppo avanzati, sappi solo che in Python ogni tipo è un oggetto.
Se in altri linguaggi una stringa è solo uno spazio contenente i byte relativi ai caratteri che la compongono, in Python è un oggetto più complesso con relativi medoti e proprietà.

