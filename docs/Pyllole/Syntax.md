# Sintassi

* `Bello è meglio di brutto`
* `Esplicito è meglio di implicito`
* `Semplice è meglio di complesso`
* `Complesso è meglio di complicato`
* `La leggibilità è importante`

Questi cinque principi, presi da [Lo Zen di Python](Zen.md), fanno capire quanto in Python la forma sia importante tanto quanto la sintassi.

In Python ogni comando si scrive su una singola riga e non necessita di particolari caratteri di termine (altri linguaggi necessitano, per esempio, di `;`). 
Se si vogliono scrivere più comandi sulla stessa riga è possibile dividerli utilizzando il `;`, ma non farlo.

## Identificatori

I nomi utilizzati per identificare variabili, funzioni, classi e moduli devono iniziare con una lettera o con un trattino basso `_`, può poi contenere lettere, cifre e caratteri di sottolineatura. Python è un linguaggio di programmazione case sensitive, cioé i caratteri maiuscoli e quelli minuscoli sono considerati come se fossere due lettere differenti. Quindi `nome` e `Nome` sono considerate due variabili differenti.

Ci sono delle convenzioni relative alla denominazione degli identificatori di Python:

* I nomi delle classi iniziano con una lettera maiuscola, tutti gli altri identificatori iniziano con una lettera minuscola
* Un identificatore che inizi con un trattino basso indica che si tratta di un identificatore privato
* Un identificatore che inizi con due trattini bassi indica che si tratta di un identificatore fortemente privato
* Se l'identificatore inizia e finisce con due trattini bassi allora è un nome speciale definito nel linguaggio.


## Indentazione

In Python la forma è così importante che per delimitare i blocchi di codice, al posto di utilizzare negli altri linguaggi le parentesi, si utilizza l'indentazione.

L'indentazione è l'inserimento di spazi vuoti all'inizio di una riga, normalmente si utilizza per far capire, a chi legge un programma, che certe parti di codice fanno riferimento ad un ciclo (`for`, `while`) o ad un controllo condizionale (`if`/`else`).

Questo è un esempio di funzione in C:

```C
int fattoriale(int x) {
    if (x == 0) {
        return(1);                   
    } else {
        return(x * fattoriale(x-1));
    }
 }
```

La stessa funzione in Python:

```Python
def fattoriale(x):
    if x == 0:
        return 1
    else:
        return x * fattoriale(x-1)
```

Sbagliare l'indentazione genera un `IndentationError`, le linee guida indicano che l'indentazione va fatta utilizzando 4 spazi, non tabulature. 

## Istruzioni multilinea

L'interprete considera ogni riga come un'istruzione intera, è possibile tuttavia usare il carattere `\` per indicare che l'istruzione continua anche sulla linea successiva. 

Questo:

```Python
totale = primo + secondo + terzo
```

Può anche essere scritto così:

```Python
totale = primo + \
         secondo + \
         terzo
```

Le istruzioni contenute nelle parentesi [], {} o () non necessitano del carattere `\` per continuare sulle righe successive:

```Python
frutta = ['Arancia', 'Pesca', 'Ananas',
        'Fragole', 'Albicocca']
```        

## Virgolette

Le virgolette, o apici, servono per definire stringhe di caratteri.
Python accetta indistintamente virgolette singole ('), doppie ("), basta che si utilizzino le stesse per l'inizio e la fine della stringa. Inoltre le virgolette triple (''' o """) vengono utilizzate per definire una stringa su più righe. 

```Python
parola = 'gatto'
frase = "Questa è una frase."
paragrafo = """ Questo è un paragrafo
composto da più righe e frasi."""
```

## Commenti e documentazione

I commenti all'interno del codice, parti testuali descrittive che vengono ignorate dall'interprete, sono molto utili e si scrivono facendoli precedere da `#`.

I commenti vanno scritti su allo stesso livello di indentazione del codice che si sta commentando. È meglio evitare i commenti sulla stessa linea del codice.


```python
#! /usr/bin/python3

import os

# Qui assegno un nome a una variabile
mia_var="pippo"
```

È possibile scrivere documentazione, più lunga di una singola riga di commento, scrivendo il testo racchiuso tra `"""`.

```python
#! /usr/bin/python3

def mia_funzione(*args)
    """ Questa funzione restituisce ...
        Gli argomenti ...   
    """
```

## Moduli e importazione 

Un modulo è un file Python contenente definizioni di variabili, funzioni e classi, che possono essere importati in altri programmi.

Ci sono due distinti modi, e sintassi, per importa i moduli, il primo, `import module` permette di importare un intero modulo.

```python
>>> import math
>>> math.pow(2,10)
1024.0
```

Il secondo permette di importare da un modulo solo alcune determinate definizioni:

```python
>>> from math import pow, log
>>> pow(2,10)
1024.0
```

è inoltre possibile "rinominare" un modulo o una definizione importata in questo modo:

```python
>>> import math as m
>>> m.pow(2,10)
1024.0
```

```python
>>> from math import pow as potenza
>>> potenza(2,10)
1024.0
```

I moduli sono oggetti, ognuno ha un attributo built-in `__name__` il cui contenuto dipende da come state utilizzando il modulo. 

* Se si importa un modulo, allora `__name__` sarà il nome del file senza l'estensione `.py`.  
* Se eseguite il modulo come un programma indipendente, `__name__` avrà il valore default speciale `__main__`.

### Stile di imporazione

Le importazioni dei moduli dovrebbero essere all'inizio del file e suddivise su più righe, un import distinto per ogni modulo.
Dovrebbero anche essere importante seguendo l'ordine: librerie standard, importazioni da terzi e infine applicazioni locali.


## Convenzioni nella scrittura del codice

Esistono delle linee guida per la scrittura del Codice python definite nel [PEP 8 - Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/).

