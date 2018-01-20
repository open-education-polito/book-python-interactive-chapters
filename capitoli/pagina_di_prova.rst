=======================
Istruzioni Condizionali
=======================

.. Here is were you specify the content and order of your new book.

.. Each section heading (e.g. "SECTION 1: A Random Section") will be
   a heading in the table of contents. Source files that should be
   generated and included in that section should be placed on individual
   lines, with one line separating the first source filename and the
   :maxdepth: line.

.. Sources can also be included from subfolders of this directory.
   (e.g. "DataStructures/queues.rst").

SEZIONE 1: Introduzione
:::::::::::::::::::::::

A volte, nella scrittura di un programma, ci si accorge che se i
contenuti delle scatole hanno certi valori si devono fare certe cose,
altrimenti se ne debbono fare altre. Vediamo un esempio.
Supponiamo di voler mandare un messaggio gentile a chi usa il nostro
programma. Nello scrivere il programma ci accorgiamo che il messaggio
è diverso a seconda che il nostro interlocutore sia una femmina oppure
un maschio. Allora gli chiediamo se è femmina o maschio e poi
scriviamo un messaggio se è una femmina, un messaggio diverso se è un
maschio.

Sezione 2: IF
:::::::::::::

L'istruzione che ci permette di scegliere cosa fare si chiama if , che in
inglese significa SE.
Questo è il codice del programma che descrive l'esempio appena fatto
(provalo subito con l'interprete di Python) :

.. activecode:: esempioIf 
   :coach:
   :caption: Esempio di uso If 

   nome = raw_input("Scrivi il tuo nome ")
   utente = raw_input("Sei femmina? ")
   if utente == "si":
     print "Cara ", nome, ", sei bravissima!"
   if utente == "no":
     print "Caro ", nome, ", sei bravissimo!"

Vediamo altri esempi concreti per capire bene il significato di “scelta”:

* A casa:

  SE suonano alla porta vado ad aprire.
  In questo caso l'azione di andare ad aprire viene eseguita solo se si
  verifica una precisa condizione: SE suonano alla porta.
  Una mia azione (andare ad aprire la porta) avviene solo se la condizione
  (SE suonano) si verifica.

* A scuola:

  SE domani c'è ginnastica devo portare le scarpe da ginnastica
  SE hai fatto i compiti puoi andare a giocare
  SE i lati e gli angoli di un poligono sono tutti uguali il
  poligono è regolare
  Prova ad analizzare gli esempi indicando per ognuno la condizione
  iniziale e l'azione conseguente nella tabella seguente e compila la
  tabella. Ovviamente puoi aggiungere tutti quelli che ti vengono in
  mente.

+------------+------------+
| Condizione | Azione     |
+============+============+
| Ginnastica | Scarpe     |
+------------+------------+
| Compiti?   | Gioco      |
+------------+------------+


.. parsonsprob:: question1_100_4

   Construct a block of code that correctly implements the accumulator pattern.
   -----
   voto = input("che voto hai preso? ")
   if voto >= 6 :
     print "promosso"
     print "bravo!"
   else:
     print "bocciato"
     print "devi studiare di piu'!"

Multiple Choice
---------------

.. mchoice:: question1_2
    :multiple_answers:
    :correct: a,c
    :answer_a: condizione 
    :answer_b: ciclo 
    :answer_c: valutare una possibilità 
    :answer_d: aprire un file 
    :feedback_a: Red is a definitely on of the colors.
    :feedback_b: Yes, yellow is correct.
    :feedback_c: Remember the acronym...ROY G BIV.  B stands for blue.
    :feedback_d: Yes, green is one of the colors.

    A cosa serve l'if? 

