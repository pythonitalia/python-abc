# Funzioni

Puoi considerare una funzione come un piccolo programma contenuto nel tuo codice che può essere richiamato più volte per eseguire operazioni ripetitive.

Ad una funzione è possibile passare degli "argomenti" variabili ad ogni chiamata.

Infine, una funzione, può restituire un valore con `return`.
Se si sta utilizzando python dal suo prompt questo valore verrà scritto sulla console. 
Se si sta eseguendo un programma il risultato di una funzione può essere assegnato ad una variabile o utilizzato come argomento per altre funzioni.

In Python si utilizza `def` per creare le funzioni.

Il seguente esempio crea una funzione con due argomenti chiamati `x` e `y`. Scrive sulla console il loro valore e restituisce la loro somma.

```python
def aggiungi(x, y):                                    
    print("x è {} e y è {}".format(x, y))
    return x + y  
```

Eseguendo la funzione appena creata si avrà il seguente risultato:

```python
>>> risultato_1 = aggiungi(2, 3)                          
x è 2 e y è 3
>>> risultato_2 = aggiungi(100, 50)
x è 100 e y è 50
>>> print(risultato_1)
5
>>> print(risultato_2)
150
```

## Argomenti 

Se eseguo `aggiungi(5,6)`, `x` avrà valore 5 e `y` sarà 6, poiché questo è l'ordine definito alla creazione della funzione.
È possibile però cambiare l'ordine degli argomenti specificando direttamente chiave e valore durante la chiamata ad una funzione.

```python
>>> aggiungi(y=6, x=5)                                 
x è 5 e y è 6
11
```

Puoi definire funzioni che accettino un numero non definito di argomenti definindo la funzione con un argomento preceduto da un asterisco:

```python
def varargs(*args):                                    
    return args
```

All'interno della funzione la variabile `args` sarà di un tipo particolare chiamato tupla.
Questa variabile conterrà tutti i parametri passati alla funzione (leggi la pagine relativa alle [liste](Type_List.md) e alle [tuple](Type_Tuple.md)).

```python
>>> varargs(1, 2, 3)                                   
(1, 2, 3)
```

Puoi definire funzioni che accettino un numero variabile di coppie chiave/valere come argomento devi definire la funzione con un argomento preceduto da due asterischi:

```python
def keyword_args(**kwargs):                           
    return kwargs
```

All'interno della funzione la variabile `kwargs` sarà di un tipo particolare dizionario.
Questa variabili conterrà tutti i paramentri inviati come coppie chiave/valore  (leggi la pagine relativa ai [dizionari](Type_Dictionary.md)).

```python
>>> keyword_args(alpha=40, beta=50)                  
{'beta': 50, 'alpha': 40}
```

Puoi utilizzare entrambi i metodi in una volta: 

```python
def all_the_args(*args, **kwargs):
    print(args)
    print(kwargs)

>>> all_the_args(10, 20, alpha=40, beta=50 )          
(10, 20)
{'beta': 50, 'alpha': 40}
```

Quando chiami una funzione, puoi fare l'opposto di `args`/`kwargs`.
Usa \* per sviluppare gli argomenti posizionale ed usa \*\* per espandere gli argomenti parola chiave.

```python
>>> args = (1, 2, 3, 4)                                
>>> kwargs = {"a": 3, "b": 4}
>>> all_the_args(*args)
>>> all_the_args(**kwargs)
>>> all_the_args(*args, **kwargs)
```

## Return di valori multipli

Una funzione può restituire valori multipli, tutte le variabili indicate dopo il return verranno restituite in un singolo oggetto tupla (le parentesi sono opzionali). 

```python
def swap(x, y):                                        
    return y, x

>>> swap(1, 2)                                         
(2, 1)
```

## Visibilità delle variabili 

La visibilità di una variabile, o "variable scope", è la parte di un programma in cui una variabile può essere utilizzata. 
Una variabile definita all'interno di una funzione, detta variabile locale, può essere utilizzata solo all'interno di quella funzione.
Una variabile definita all'esterno della funzione, variabile globale, potrà essere utilizzata all'interno di una funzione solo se richiamata tramite `global`.

```python
x = 5                                                  

def set_x(num):                                        
    # La variabile locale x non è la variabile globale x 
    x = num    # => 43
    print(x)   # => 43

def set_global_x(num):                                 
    global x
    print(x)   # => 5
    x = num    # la variabile globable x è ora 6
    print(x)   # => 6

>>> print(x)
5
>>> set_x(43)
43
>>> print(x)
5
>>> set_global_x(6)
5
6
>>> print(x)
6
```

## Funzioni anonime

Le funzioni anonime sono funzioni senza nome create in fase di esecuzione del programma.
Per creare una funzione anonima si utilizza il costrutto `lambda`.

Un esempio di funzione (elevamento alla seconda) definita con un nome:

```python
def pow(x):                                            
     return x**2

>>> pow(8)                                             
64
```

Equivalente funzione ma anonima con `lambda`:

```python
>>> pow = lambda x: x**2                               
>>> pow(8)
64
```

La definizione lambda non include un `return`, è l'espressione stessa definita in lambda che viene restituita. 

È possibile inserire una definizione `lambda` ovunque sia prevista una funzione e non è necessario assegnarla a una variabile.

Di seguito un esempio di `lambda` utilizzato per creare funzioni durante, l'esecuzione del programma, ognuna con caretteristiche differenti.

```python
>>> def crea_incrementatore (n):                       
...     return lambda x: x + n
...
>>> incr10 = crea_incrementatore(2)
>>> incr5 = crea_incrementatore(5)
>>>
>>> incr10(30)
32
>>> incr5(30)
35
```

Spesso le funzioni anonime trovano il loro miglior utilizzo con `map`, `filter` e `reduce`.

Esempio utilizzando una lista e il precendete esempio di funzione anonima (elevamente alla seconda)

```python
>>> lista = [1,2,3,4]                                    
>>> list(map(lambda x: x**2, lista))
[1, 4, 9, 16]
```

Un esempio di un filtro che lascia passare solo valori maggiori di 5:

```python
>>> list(filter(lambda x: x > 5, [3, 4, 5, 6, 7])) 
[6, 7]
```

---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
