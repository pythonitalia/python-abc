
# Ambiente di sviluppo

## L'editor di testo

Il fondamentale, e più usato, strumento di ogni programmatore è l'_editor di testo_, un programma in grado di creare e modificare file,  testuali appunto, contenenti il codice sorgente dei programmi.
Un file testuale è un file che contiente solo ed esclusivamente byte che verranno interpretati come caratteri di testo. 

Un editori di testo non è un [IDE](#IDE), inizia a programmare con un semplice editor di testo e passa ad un [IDE](#IDE) solo quando avrai più esperienza.

**Nota**: Un _editor di testo_ non è un programma per il _word processing_, programmi come _MS-Word_ non scrivono file testuali ma file con un formato proprietario contenenti i dati relativi alla formattazione del testo (font, dimensioni, colori, ...). Un file di testo contenente una "a" avrà una lunghezza di 1 byte, l'equivalente testo in un file di _MS-Word_ genererà un file intorno ai 9.000 byte.

### Funzionalità

Naturalmente qualunque editor di testo in grado semplicemente di creare, aprire e modificare un file di testo ti permetterà di scrivere il tuo codice.
Ci sono poi altre caratteristiche che ti renderanno la vita più semplice nelle ore che passerai a scrivere.

* Funzioni di ricerca e sostituzione 
* Funzioni per tagliare, copiare e incollare
vRappresentazione a colori ([syntax highlighting](https://it.wikipedia.org/wiki/Syntax_highlighting)) del codice
* Possibilità di aggiungere funzionalità dell'editor tramite _plugin_ 
* Personalizzazione (dimensione del carattere, combinazioni di colori, ecc)

**Nota**: oggi è quasi obbligatorio che un editor di testo supporti la  [codifica UTF-8](https://it.wikipedia.org/wiki/UTF-8).


### Linea di comando

Se si programma per lavoro prima o poi Linux si dovrà utilizzare, per questo è fondamentale conoscere i suoi editor testuali da linea di comando: `vim` e `nano`.

Entrambi, funzionando in modalità testuale (non grafica) e possono sembrare un po' ostici. Tutti i comandi (esci, salva, cerca, ...) vengono attivati tramite combinazioni di tasti, il mouse, se siete fortunati, può essere utilizzato per selezionare un testo e copiarlo.

Tra i due `nano` è probabilmente il più semplice, si scrive direttamente sul "foglio" e in una barra vengono indicati i comandi principali, con `^` che indica il tasto `ctrl` (`ctrl+x` esce, `ctrl+o` salva, `ctrl+w` cerca).


### I più diffusi editor di testo (ambiente grafico) 

* [Sublime Text](https://www.sublimetext.com/)
* [Atom](https://atom.io)
* [Visual Studio Code](https://code.visualstudio.com)

## IDE

Il processo di creazione del programma parte dalla scrittura del codice ma continua poi nelle fasi, ad esempio, di compilazione e [debug](https://it.wikipedia.org/wiki/Debugging). A seconda del linguaggio utilizzato, queste fasi vengono eseguite dal programmatore con vari singoli strumenti a sua disposizione.

Un IDE (Integrated Development Environment), conosciuto anche come _ambiente di sviluppo integrato_, è un unico programma dal quale è possibile gestire tutte le fasi dello sviluppo di un software. Un IDE permette da un unica interfaccia di scrivere, controllare, compilare, eseguire, testare e distribuire un programma.

* [PyCharm](https://www.jetbrains.com/pycharm/)
* [PyDev (Eclipse for Python)](http://www.pydev.org/)
* [WingIDE](https://wingware.com/)
* [Komodo IDE](https://www.activestate.com/komodo-ide)
