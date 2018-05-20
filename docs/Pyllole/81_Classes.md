# Classi

Per creare una classe si utilizza l'istruzione `class`

```python
class Human: 
    # Un attributo della classe. E' condiviso tra tutte 
    # le istanze delle classe
    species = "H. sapiens"

    # Si noti che i doppi underscore iniziali e finali denotano 
    # gli oggetti o attributi utilizzati da Python ma che vivono 
    # nel namespace controllato dall'utente.
    # Metodi, oggetti o attributi come: __init__, __str__, 
    # __repr__, etc. sono chiamati metodi speciali (o talvolta 
    # chiamati "dunder methods").
    # Non dovresti inventare tali nomi da solo.

    def __init__(self, name):
        # Assegna l'argomento all'attributo name dell'istanza
        self.name = name

    # Inizializza una proprietà
    self._age = 0

    # Un metodo dell'istanza. Tutti i metodi prendo "self"
    # come primo argomento
    def say(self, msg):
        print("{name}: {message}".format(name=self.name, message=msg))

    # Un altro metodo dell'istanza
    def sing(self):
        return 'yo... yo... microphone check... one two... '

    # Un metodo della classe è condiviso fra tutte le istanze
    # Sono chiamati con la classe chiamante come primo argomento
    @classmethod
    def get_species(cls):
        return cls.species

    # Un metodo statico è chiamato senza classe o istanza 
    # di riferimento
    @staticmethod
    def grunt():
        return "*grunt*"

    # Una property è come un metodo getter.
    # Trasforma il metodo age() in un attributo in sola lettura,  
    # che ha lo stesso nome 
    @property
    def age(self):
        return self._age

    # Questo metodo permette di modificare una property
    @age.setter
    def age(self, age):
        self._age = age

    # Questo metodo permette di cancellare una property
    @age.deleter
    def age(self):
        del self._age
```

Quando l'interprete Python legge un sorgente esegue tutto il suo codice.
Il controllo su `__name__` assicura che questo blocco di codice venga eseguito solo quando questo modulo è il programma principale.

```python
if __name__ == '__main__':
    # Crea un'istanza della classe
    i = Human(name="Ian")
    i.say("hi")                     # "Ian: hi"
    j = Human("Joel")
    j.say("hello")                  # "Joel: hello"
    # i e j sono istanze del tipo Human, o in altre 
    # parole sono oggetti Human

    # Chiama un metodo della classe
    i.say(i.get_species())          # "Ian: H. sapiens"
    # Cambia l'attributo condiviso
    Human.species = "H. neanderthalensis"
    i.say(i.get_species())          # => "Ian: H. neanderthalensis"
    j.say(j.get_species())          # => "Joel: H. neanderthalensis"

    # Chiama un metodo statico 
    print(Human.grunt())            # => "*grunt*"
    
    # Non è possibile chiamare il metodo statico con l'istanza dell'oggetto
    # poiché i.grunt() metterà automaticamente "self" (l'oggetto i) 
    # come argomento 
    print(i.grunt())                # => TypeError: grunt() takes 0 positional arguments but 1 was given
                                    
    # Aggiorna la property (age) di questa istanza
    i.age = 42
    # Leggi la property
    i.say(i.age)                    # => "Ian: 42"
    j.say(j.age)                   # => "Joel: 0"
    # Cancella la property
    del i.age
    i.age                           # => questo genererà un AttributeError
```


---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
