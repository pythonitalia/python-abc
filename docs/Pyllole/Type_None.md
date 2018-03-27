# Tipi: None 

`None` è un particolare tipo di dato che indica un valore nullo, l'assenza di dati. 
`None` non è uguale a `False`, non è `0` e non è una string vuota. 

```python
>>> type(None) 
<class 'NoneType'>
```

```python
>>> None == '' 
False
>>> '' == None
False
>>> 0 == None
False
>>> False == None
False
>>> None is None
True
```

È possibile assegnare `None` a qualsiasi variabile ma non si possono creare altri oggetti di tipo `NoneType`. 
Ogni varibile il cui valore è `None` punta allo stesso, ed unico, oggetto `None`.
Per comparare un oggetto a `None` si deve quindi utilizzare `is`, non `==`.

```python
>>> "etc" is None
False
>>> None is None
True
```

In una valutazione booleana `None` viene considerato `False`.

```python
>>> bool(None) 
False
>>> not None
True
```

---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
