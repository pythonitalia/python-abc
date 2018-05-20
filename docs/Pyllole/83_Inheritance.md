


# Ereditarietà  (Inheritance)

L'ereditarietà consente di definire nuove classi figlio che ereditano metodi e variabili dalla loro classe genitore.

Usando la classe `Human` definita sopra come classe base o genitore, possiamo definire una classe figlia, `Superhero`, che erediterà le variabili di classe come `species`, `name` e `age`, così come i metodi, come `sing` e `grunt`, dalla classe `Human`, ma potrà anche avere le sue proprietà uniche.

Per importare le funzioni da altri file usa il seguente formato from "nomefile-senza-estensione" import "funzione-o-classe"

```python
>>> from human import Human
```

Specificare le classi genitore come parametri della definizione della classe

```python
class Superhero(Human):
    # Se la classe figlio deve ereditare tutte le definizioni del 
    # genitore  senza alcuna modifica, puoi semplicemente usare 
    # la parola chiave "pass" (e nient'altro)
    # Le classi figlio possono sovrascrivere gli attributi dei loro genitori
    species = 'Superhuman'

    # Le classi figlie ereditano automaticamente il costruttore della classe 
    # genitore, inclusi i suoi argomenti, ma possono anche definire ulteriori 
    # argomenti o definizioni e sovrascrivere i suoi metodi (compreso  il 
    # costruttore della classe).
    # Questo costruttore eredita l'argomento "nome" dalla classe "Human" e 
    # aggiunge gli argomenti "superpowers" e "movie":
    def __init__(self, name, movie=False,
         superpowers=["super strength", "bulletproofing"]):

    # aggiungi ulteriori attributi della classe
    self.fictional = True
    self.movie = movie
    self.superpowers = superpowers

    # La funzione "super" ti consente di accedere ai metodi della classe 
    # genitore che sono stati sovrascritti dalla classe figlia,  
    # in questo caso il metodo __init__.
    # Il seguente codice esegue il costruttore della classe genitore:
    super().__init__(name)

    # Sovrascrivere il metodo "sing"
    def sing(self):
        return 'Dun, dun, DUN!'

    # Aggiungi un ulteriore metodo dell'istanza
    def boast(self):
        for power in self.superpowers:
            print("I wield the power of {pow}!".format(pow=power))
```

Proviamo la classe `Superhero`:

```python
if __name__ == '__main__':
    sup = Superhero(name="Tick")

# Controllo del tipo di istanza
if isinstance(sup, Human):
    print('I am human')
if type(sup) is Superhero:
    print('I am a superhero')

# Ottieni il "Method Resolution search Order" usato sia da getattr () 
# che da super (). Questo attributo è dinamico e può essere aggiornato
print(Superhero.__mro__)    # => (<class '__main__.Superhero'>,
                            # => <class 'human.Human'>, <class 'object'>)

# Esegui il metodo principale ma utilizza il proprio attributo di classe
print(sup.get_species())    # => Superhuman

# Esegui un metodo che è stato sovrascritto
print(sup.sing())           # => Dun, dun, DUN!

# Esegui un metodo di Human
sup.say('Spoon')            # => Tick: Spoon

# Esegui un metodo che esiste solo in Superhero
sup.boast()                 # => I wield the power of super strength!
                                # => I wield the power of bulletproofing!

# Attributo di classe ereditato
sup.age = 31
print(sup.age)              # => 31

# Attributo che esiste solo in Superhero
print('Am I Oscar eligible? ' + str(sup.movie))
```


---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
