# Come usare Python

Una volta installato Python ci sono due fondamentali modi per utilizzarlo:

* Tramite l'interprete Python
* Creando uno script

---

## Interprete Python

Eseguendo direttamente Python viene attivata la modalità intereattiva dell'interprete (REPL), un'interfaccia per scrivere ed eseguire immediatamente i comandi del linguaggio Python. Il REPL si presenta semplicemente con un _prompt_ `>>>` in attesa di un comando.

A seconda di come, cosa e dove è stato installato Python, potrebbe essere necessario specificare quale versione si vuole eseguire. Ad oggi molte versioni pre-installate eseguono Python 2.7 di default, in questi casi è necessario specificare `python3` per eseguire l'ultima versione.

```
$ python
Python 2.7.13 (default, Nov 24 2017, 17:33:09)
[GCC 6.3.0 20170516] on linux2
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

```
$ python3
Python 3.5.3 (default, Jan 19 2017, 14:11:04)
[GCC 6.3.0 20170118] on linux
Type "help", "copyright", "credits" or "license" for more information.
>>>
```

All'interno dell'interprete è possibile inviare comandi Python che vengono eseguiti man mano che vengono scritti (riga per riga).

```python
>>> salve="Ciao"
>>> print(salve)
Ciao
```

Se si utilizzano istruzioni che prevedono più linee di codice, come i cicli o la definizione di funzione, l'interprete segnalerà che non ha ancora iniziato a interpretare i comandi forniti cambiando il prompt in `...`.

Naturalmente, in questi casi, si deve fare molta attenzione all'[indentazione](Syntax.md#indentazione).

```python
>>> for a in range(3):
...   print(a)
...
0
1
2
```

All'interno dell'interprete tutti i valori restituiti da funzioni e metodi vengono scritti sulla console.

Prendiamo come esempio un'ipotetica funzione che dati due dati scrive sullo schermo una frase e restituisce la loro somma.

```python
>>> def miei_dati(x,y):
...     print("I miei dati sono {} e {}".format(x,y))
...     return x+y
```

Eseguendo questa funzione dall'interprete si vedrà quanto segue:

```python
>>> miei_dati(20,30)
I miei dati sono 20 e 30
50
```

Giustamente viene scritta la frase con i due valori, ma in più l'interprete scrive anche ciò che la funzione restituisce.
Questo valore, nella normale esecuzione di uno script, o viene volontariamente utilizzato (assegnandolo ad una variabile o come argomento per un'altra funzione), o viene semplicemente ignorato. 


### Aiuto e documentazione 

Direttamente dall'interprete è possibile richiedere "aiuto" relativamente ad ogni tipo, metodo o funzione (nota: per uscire dall'help premere `q`).

```python
>>> help(print)

Help on built-in function print in module builtins:

print(...)
    print(value, ..., sep=' ', end='\n', file=sys.stdout, flush=False)

    Prints the values to a stream, or to sys.stdout by default.
    Optional keyword arguments:
    file:  a file-like object (stream); defaults to the current sys.stdout.
    sep:   string inserted between values, default a space.
    end:   string appended after the last value, default a newline.
    flush: whether to forcibly flush the stream.
(END)

```

Un'altro aiuto diretto nell'interprete è dato dalla funzione `dir()`, in grado di elencare i metodi disponibili per un determinato oggetto.

```python
>>> dir(int)
['__abs__', '__add__', '__and__', '__bool__', '__ceil__', ...]
```

---

## Creare uno script

Creare uno script significa creare un file contenente un programma Python. Questo file/programma potrà poi essere eseguito direttamente o importato da altri programmi.

Per creare un file script **basta un semplice [editor di testo](Pyllole/Development_Environment.md)**, nulla di più. Studiando Python è meglio evitare complessi ambienti di sviluppo (IDE), quando si conoscerà il linguaggio e si svilupperanno veri programmi, si potrà decidere di utilizzarli per ottimizzare il proprio lavoro.

Il file script di python hanno estensione _.py_, crea un tuo file, chiamiamolo _prova.py_ e comincia a programmare.

La prima riga di uno script è chiamata _shebang_ (ma anche _sha-bang_ o _hashbang_) e indica quale inteprete utilizzare (la cartella e l'eseguibile Python).

```python
#! /usr/bin/python3
print('Hello, world!')
```

Una volta salvato il tuo file python.py puoi eseguirlo richiamandolo con python.

```bash
$ python3 ./prova.py
Hello, world!
```

Se al file sono stati dati i permessi di esecuzione, è anche possibile eseguirlo direttamente.

```bash
$ ./prova.py
Hello, world!
```

*Attenzione*: per eseguire direttamente un file _.py_ in Linux si devono prima assegnare al file i permessi di esecuzione con `chmod +x ./prova.py`. Windows e macOs necessitano che i file _.py_ siano associati all'interprete Python.

Eseguendo il file `prova.py` viene generato il file `prova.pyc` che, per spiegarla semplicemente, è una versione del programma trasformata in _bytecode_ pronta per essere eseguita dall'interprete Python.

### Sintassi e stile di scrittura

Consulta la pagina relativa alla [sintassi di base](Syntax.md) per cominciare a conoscere il linguaggio python.

Anche se al momento è prematuro, sappi che in Python anche lo stile di scritture del codice è importante ed è definito nel [PEP 8 - Style Guide for Python Code](https://www.python.org/dev/peps/pep-0008/).

