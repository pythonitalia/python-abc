
# Tipi: Stringhe

Le stringhe sono insiemi di caratterie, frasi, racchiuse tra apici `'` o doppi apici `"`.

`"Questa è una stringa"`
`'Anche questa è una stringa'`

```python
>>> type("Questa è una stringa")
<class 'str'>
>>> type('Anche questa è una stringa.')
<class 'str'>
```

Le stinghe possono essere unite tramite l'operatore della somma `+`. Ma cerca di non farlo.

```python
>>> "Hello "+"world!"
'Hello world!'
```

Le stringhe (ma non le variabili contenenti stringhe) possono essere unite anche senza l'operatore `+`

```python
>>> "Hello " "world!"  
'Hello world!'
```

Una stringa può essere considerata come una lista di caratteri, in quanto tale ogni carattere può essere raggiunto tramite un indice.

```python
>>> "Questa è una stringa"[0]  
'Q'
```

È possibile conoscere la lunghezza di una stringa grazie alla funzione `len()`

```python
>>> len("Questa è una stringa")
20
```

## Formattazione delle stringhe

In Python esistono differenti modi per formattare le stringhe.

### Il metodo .format()

Il tipo stringa ha un metodo `format()` per formattare le stringhe.
In questo esempio le variabili `name` e `food` vanno a completare la stringa riempiendo i campi (segnalati dalle parentesi grafe) nell'ordine in cui vengono passate al metodo `.format()`.
   
```python
>>> name="John"
>>> food="le lasagne"
>>> "{} vuole mangiare {}".format(name, food)
'John vuole mangiare le lasagne'
```

È possibile dare un numero ai "campi" da riempire e ripetere così all'interno della stringa gli argomenti passati a `.format()`:

```python
>>> "{0} be nimble, {0} be quick, {0} jump over the {1}".format("Jack", "candle stick")
'Jack be nimble, Jack be quick, Jack jump over the candle stick'
```

È possibile usare dei nomi al posto dei numeri degli argomenti

```python
>>> "{nome} vuole mangiare {cibo}".format(nome="Bob", cibo="le lasagne") 
'Bob vuole mangiare le lasagne'
```

### L'operatore di interpolazione `%`

Un altro stile di formattazione delle stringhe è dato dall'operatore `%` in grado di mettere in relazione una formattazione (in formato stringa) e dei valori. 

```python
>>> "%s possono essere %s" % ("Le stringhe", "interpolate") 
'Le stringhe possono essere interpolate'
```

Quosto modo è al momento meno utilizzato, per saperne di più si può consultare la pagina [string-formatting](https://docs.python.org/3/library/stdtypes.html?highlight=string%20interpolation#printf-style-string-formatting) della guida ufficiale.

### Formatted string literals - f-string

Da Python 3.6 sono state aggiunte le _Formatted string literals_ o più semplicemente _f-string_, vengono indicate con una `f` prima della stringa vera e propria e permettono una formattazione in stile template.

```python
>>> name = 'John'
>>> food = 'le lasagne'
>>> f'Si chiama {name} e ama {food}.'
Si chiama John e ama le lasagne.
```

Con le _f-string_ è possibile anche eseguire delle espressioni all'interno del template.

```python
>>> name = 'John'
>>> seven = 7
>>> f'''Il suo nome è {name.upper()}
...ed ha {6 * seven} anni.'''
'Il suo nome è John ed ha 42 anni.'
```



---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
