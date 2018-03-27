# Ereditarietà multipla

È possibile ereditare metodi e proprietà da più di un genitore.

Creaimo una nuova classe `Bat`:

```python
# bat.py
class Bat:

species = 'Baty'

def __init__(self, can_fly=True):
    self.fly = can_fly

# Questa classe ha anche un metodo "say"
def say(self, msg):
    msg = '... ... ...'
    return msg

# E anche un suo metodo personale
def sonar(self):
    return '))) ... ((('

if __name__ == '__main__':
    b = Bat()
    print(b.say('hello'))
    print(b.fly)
```

Definiamo una classe che erediti da `Superhero` e `Bat` e proviamola

```python
# superhero.py
from superhero import Superhero
from bat import Bat

# Definisci Batman come classe figlia che eredita sia
# da Superhero che da Bat
class Batman(Superhero, Bat):

    def __init__(self, *args, **kwargs):
    # In genere per ereditare gli attributi devi chiamare super:
    # super(Batman, self).__init__(*args, **kwargs)
    # Ma qui abbiamo a che fare con l'ereditarietà multipla, 
    # e super() funziona solo con la successiva classe 
    # nell'elenco MRO.
    # Quindi, invece, chiamiamo esplicitamente __init__ per 
    # tutti gli antenati. L'uso di *args e **kwargs consente 
    # di passare in modo pulito gli argomenti, con ciascun 
    # genitore che "sbuccia un livello della cipolla".
        Superhero.__init__(self, 'anonymous', movie=True, 
                           superpowers=['Wealthy'], *args, **kwargs)
        Bat.__init__(self, *args, can_fly=False, **kwargs)
        # sovrascrivere il valore per l'attributo name
        self.name = 'Sad Affleck'

    def sing(self):
        return 'nan nan nan nan nan batman!'

if __name__ == '__main__':
    sup = Batman()

    # Ottieni il "Method Resolution search Order" 
    # utilizzato da getattr() e super().
    # Questo attributo è dinamico e può essere aggiornato
    print(Batman.__mro__)       # => (<class '__main__.Batman'>, 
                                # => <class 'superhero.Superhero'>, 
                                # => <class 'human.Human'>, 
                                # => <class 'bat.Bat'>, <class 'object'>)

    # Esegui il metodo del genitore ma utilizza il proprio 
    # attributo di classe
    print(sup.get_species())    # => Superhuman

    # Esegui un metodo che è stato sovrascritto
    print(sup.sing())           # => nan nan nan nan nan batman!

    # Esegui un metodo da Human, perché l'ordine di 
    # ereditarietà è importante 
    sup.say('I agree')          # => Sad Affleck: I agree

    # Esegui un metodo che esiste solo nel 2o antenato
    print(sup.sonar())          # => ))) ... (((

    # Attributo di classe ereditato
    sup.age = 100
    print(sup.age)              # => 100

    # Attributo ereditato dal secondo antenato il cui valore 
    # predefinito è stato ignorato.
    print('Can I fly? ' + str(sup.fly)) # => Can I fly? False
```





---

_This content is a derivative of ["Learn X in Y minutes"](https://github.com/adambard/learnxinyminutes-docs) by [adambard](https://github.com/adambard), used under a CC BY-SA 3.0 license._
