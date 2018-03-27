# Tipi: Dizionari

_Prima di studiare i dizionari assicurati di conoscere le [liste](Type_List.md)._

Un dizionario è come una lista che ha un nome al posto dell'indice, è un insieme di coppie chiave-valore. 

**Importante**: le coppie chiave-valore in un dizionario non sono ordinate o ordinabili.

Se in una lista è possibile accedere ad un dato in questo modo:

```python
>>> li[3]
4
```

In un dizionario potrò accedervi così:

```python
>>> persona['nome']
Pippo
```

Un variabile di tipo dizionario di crea in questo:

```python
>>> empty_dict= {}
```

Si può anche definire direttamente un dizionario pre-caricato

```python
>>> filled_dict = {"uno": 1, "due": 2, "tre": 3}
```

**Importante**: le chiavi  dei dizionari devono essere di tipo immutabile. Questo per assicurare che le chiavi possano essere convertite in chiavi hash costanti per un risposta più veloce.

```python
>>> invalid_dict = {[1,2,3]: "123"}
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
TypeError: unhashable type: 'list'
```

I valori, invece, possono essere di qualunque tipo

```python
>>> valid_dict = {(1,2,3):[1,2,3]}
```

Si accede ai valori indicando la chiave tra `[]`

```python
>>> filled_dict["uno"]
1 
```

Puoi ottenere tutte le chiavi di un dizionario con `keys()` (come oggetto iterabile). Per averle in formato lista è necessario  utilizzare `list()`.

**Importante**: Nei dizionari l'ordine delle chiavi non è garantito. Il tuo risultato potrebbe non essere uguale a questo.

```python
>> list(filled_dict.keys())
['uno', 'tre', 'due']
```

Puoi ottenere tutti i valori di un dizionario con `values()` (come oggetto iterabile). 
Anche in questo caso, per averle in formato lista, è necessario utilizzare `list()`. Anche in questo caso, come per le chiavi, l'ordine non è garantito

```python
list(filled_dict.values())
[1, 3, 2]
```

Controlla l'esistenza delle chiavi in un dizionario con `in`

```python
>>> "uno" in filled_dict
True 
>>> 1 in filled_dict
False
```

Cercando una chiave non esistente genera un `KeyError`

```python
>>> filled_dict["quattro"]
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
KeyError: 'quattro'
```


sa il metodo `get()` per evitare `KeyError`

```python
>>> filled_dict.get("uno")
1
>>> filled_dict.get("quattro")
```


Il metodo `get` supporta un argomento di default quando il valore è mancante

```python
>>> filled_dict.get("uno", 4)
1
>>> filled_dict.get("quattro", 4)
4
```

`setdefault()` inserisce un valore per una chiave in un dizionario solo se la chiave data non è già presente

```python
>>> filled_dict.setdefault("cinque", 5)
5
>>> filled_dict.setdefault("cinque", 6)
5
```

Aggiungere una coppia chiave->valore a un dizionario

```python
>>> filled_dict.update({"quattro":4})
>>> filled_dict
{'uno': 1, 'tre': 3, 'quattro': 4, 'cinque': 5, 'due': 2}
```

Un altro modo:

```python
>>> filled_dict["sette"] = 7
>>> filled_dict
{'sette': 7, 'tre': 3, 'cinque': 5, 'due': 2, 'uno': 1, 'quattro': 4}
```

Rimuovi una chiave da un dizionario con `del`

```python
>>> del filled_dict["uno"]
>>> filled_dict
{'sette': 7, 'tre': 3, 'cinque': 5, 'due': 2, 'quattro': 4}
```

Da Python 3.5 puoi anche usare ulteriori opzioni di spacchettamento

```python
>>> {'a': 1, **{'b': 2}}
{'a': 1, 'b': 2}
```

---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
