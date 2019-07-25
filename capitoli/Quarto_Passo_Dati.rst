=================================
Quarto passo: dati e tipi di dati
=================================

.. role:: red

.. role:: boltred

.. role:: blue

.. role:: boltblue

.. role:: boltgreen

| Fino ad ora abbiamo lavorato quasi sempre su **numeri**.

Abbiamo visto, ad esempio, che una scatola può contenere numeri interi come 27, 251, 1100050, oppure numeri decimali, ossia numeri con virgola che Python vuole che siano scritti con il simbolo “**.**”, come :

| 27.35
| 251.5
| 3.1415

In questa sezione inizieremo a parlare anche di **caratteri e stringhe.**

**Esistono infatti diversi tipi di dati:**

- **i numeri**

- **i caratteri**

- **le stringhe**

Dei numeri abbiamo già parlato nel capitolo precedente, mentre **un carattere è un simbolo** come, ad esempio, la lettera “a” minuscola, la “Q” maiuscola, la cifra “7”, il simbolo “+”, e qualunque altro simbolo che compaia sulla tastiera del tuo PC.

**Una stringa è un qualsiasi messaggio, quindi una serie di caratteri, numeri, lettere o altri simboli** presenti sulla tastiera, compresi tra virgolette, che il computer può stampare tali e quali sul video.
In Python le stringhe possono presentarsi in diversi modi:

- tra virgolette semplici: 'ciao'

- tra virgolette doppie: "ciao"

- tra virgolette doppie ripetute tre volte: """ciao"""

Ecco alcuni esempi di stringhe composte da:

+-------------------------+--------------------------+
|Una serie di lettere     | :boltred:`“ciao”`	     |
+-------------------------+--------------------------+
|Una serie di lettere che | :boltred:`"viva la Juve”`|
|formano un messaggio     |             	     |
+-------------------------+--------------------------+
|Una serie di simboli     | :boltred:`“#@&%”`        |
+-------------------------+--------------------------+
|Anche i numeri tra       | :boltred:`“8-5=3”`       |
|virgolette vengono letti |                          |
|come simboli e stampati  |              	     |
|tali e quali             |              	     |
+-------------------------+--------------------------+

| Prova a eseguire il programma;
| Il calcolatore visualizzerà tutti i caratteri compresi tra le virgolette: :red:`Ciao`

.. activecode:: esempio_print1
   :nocanvas:
   :language: python
   
   print("ciao")

| Ora prova a eseguire questo; 
| Anche in questo caso il calcolatore visualizzerà tutti i caratteri racchiusi tra virgolette: :blue:`Viva la Juve`

.. activecode:: esempio_print2
   :nocanvas:
   :language: python
   
   print("Viva la Juve")

Se scriviamo l’istruzione:

::

	 print ("8+4")
  
| il calcolatore visualizzerà: 8+4 senza fare nessun calcolo. Perché?
| Perché hai dato al computer il seguente ordine: *visualizza la stringa costituita da tre caratteri: 8 + 4*.

I numeri 8 e 4 sembrano effettivamente dei numeri ma essendo chiusi tra virgolette vengono interpretati come i caratteri di un messaggio qualunque e quindi come…”una stringa”!
 
Se poi scrivi l’istruzione: print (“8+4=13”) il calcolatore scriverà: 8+4=13 senza accorgersi dell’errore di calcolo, perché l’ordine che gli hai dato è solo quello di scrivere la stringa composta dai caratteri: 8+4=13

*Ovviamente possiamo mettere la stringa in una scatola, come abbiamo fatto con i numeri, usando l'istruzione di assegnazione.*

Ad esempio:

::

	SCATOLA1 = "scuola elementare"
	print (SCATOLA1)

Il risultato sarà: :boltred:`scuola elementare`

.. activecode:: esempio_scatola1
   :nocanvas:
   :language: python
   
   SCATOLA1= "scuola elementare"
   print (SCATOLA1)

Prova ad eseguire i seguenti comandi facendo copia e incolla:

::

	print ("MATEMATICA")
	print ("Via Roma 100")
	print ("Area")
	print ("++++****++++")

I risultati saranno rispettivamente:

| MATEMATICA
| Via Roma 100
| Area
| ++++****++++

Esaminiamo ora le due istruzioni:

::

	print ("8+4")

Il calcolatore visualizzerà: :boltred:`8+4`

In questo caso ci sono le virgolette e il calcolatore riceve l’istruzione di visualizzare i caratteri contenuti tra le “ ” .

.. activecode:: esempio_print3
   :nocanvas:
   :language: python
   
   print ("8+4")

Scrivendo invece:

::

	print (8+4)

il calcolatore visualizzerà: :boltred:`12`

.. activecode:: esempio_print4
   :nocanvas:
   :language: python
   
   print ("8+4")
   print (8+4)

Visto che non ci sono le virgolette il calcolatore interpreta 8+4 come un’espressione aritmetica e la esegue visualizzandone il risultato.

Proviamo ora a collegare le due istruzioni e scriviamo: 

::

	print ("8+4  =",  8+4)

Il calcolatore prima visualizzerà la stringa ”8+4 =“ e poi il risultato dell’operazione 8+4.

| Quale sarà il risultato?  
| Il messaggio: :boltblue:`8+4 = 12`

.. activecode:: esempio_print5
   :nocanvas:
   :language: python
   
   print ("8+4 =", 8+4)

Facciamo ancora due esempi :

::

	print  ("3+5 =", 3+5)

Avrà come risultato: :boltred:`3+5=  8`

::

	print  ("4*4 =",  4*4)

Avrà come risultato:  :boltblue:`4*4=  16`

+-----------------------------------------+-------------------------------------+
|Sono stringhe                            |Sono numeri                          |
+=========================================+=====================================+
| :boltred:`"3+5="`, :boltblue:`"4*4="`   | :boltred:`3+5`, :boltblue:`4*4`     |
+-----------------------------------------+-------------------------------------+

Il primo è gia scritto, prova a scrivere il secondo:

.. activecode:: esempio_print6
   :nocanvas:
   :language: python
   
   print ("3+5 =", 3+5)

Nell’esempio successivo cambia solo l’ordine con cui devono essere eseguiti gli ordini, in questo caso prima l’operazione su numeri e poi la stringa:

::

	print (100-10, " = 100 - 10")

Il risultato sarà: :boltgreen:`90 = 100-10`

.. activecode:: esempio_print7
   :nocanvas:
   :language: python
   
   print (100-10, " = 100 - 10")

Facciamo due  esempi simili utilizzando le variabili:

::

	scatola2 = 14+8
	print ("14+8 = ", scatola2)

Il risultato sarà: :boltred:`14+8 = 22`

::

	scatola3 = 5*3
	print ("5*3 =  ", scatola3)

Il risultato sarà: :boltred:`5*3= 15`

.. activecode:: esempio_scatola2
   :nocanvas:
   :language: python
   
   scatola2 = 14+8
   print ("14+8 = ", scatola2)

------------

:boltblue:`ATTENZIONE:`

1. La parte a sinistra dell’uguale è una stringa anche se nel messaggio in uscita sembrano tutti numeri. E pertanto 14,  8,  5,  3  non sono numeri ma caratteri.

2. Hai notato che è stata utilizzata una virgola per separare le due parti del messaggio print (“5*3= ”, scatola3) ? Sai perché?

Perché l’'istruzione print() dice a Python: "devi visualizzare le seguenti cose".
Se vuoi fare visualizzare più oggetti sulla stessa riga devi separarli con una virgola.

Nel tuo caso hai detto a Python: visualizzami la stringa "5*3= " così com'è e subito dopo hai aggiunto: visualizzami il risultato della moltiplicazione tra i numeri 5 e 3.

------------

:blue:`Prova a rispondere ai seguenti quesiti:`

1. In quale di questi due comandi i numeri sono numeri e non simboli?

::

	print ("6 + 3")
	print (6+3) 

2. Quale sarà il risultato dei due comandi?

3. Quale sarà il risultato del comando?

::

	print ("9 * 5 = ", 9 * 5)

4. Quale risultato darà l'istruzione seguente? 

::

	print ("Auguri a " + "tutti”)

------------

:boltblue:`Dati e tipi di dati (operazioni sulle stringhe)`

Numeri interi e decimali possono essere utilizzati per operazioni matematiche, le stringhe no, anche se il loro contenuto sembra un numero.

| Scrivere: "ciao"/12  *oppure*   "18"+5
| :red:`e' sbagliato e genera un SYNTAX ERROR`

.. da e' a ERROR rosso

Tuttavia gli operatori  +  e  * , e soltanto questi,  possono essere utilizzati anche con le stringhe ma in questo caso hanno un significato diverso da quello della somma e del prodotto aritmetico.

*Se ad una stringa viene sommata un'altra stringa l'effetto che si ottiene e' il :boltred:`concatenamento`, cioè la seconda stringa si aggiunge al fondo della prima.*

Ad esempio:

::

	print("casa"+" dolce "+"casa")

genera a video: :boltred:`casa dolce casa`

.. activecode:: esempio_print8
   :nocanvas:
   :language: python
   
   print("casa"+" dolce "+"casa")

Gli spazi prima e dopo la parola “dolce” fanno parte della stringa e sono necessari, altrimenti a video le stringhe concatenate sarebbero attaccate come un'unica parola, come succede scrivendo:  print(“casa”+”dolce”+”casa”).

*Se invece vogliamo ripetere tante volte la stessa stringa (questo effetto si chiama :boltblue:`ripetizione`) possiamo moltiplicarla per un numero intero usando l'operatore :boltblue:`*`.*

| "ciao" * 3	*diventa*     ciaociaociao
| "ciao " * 3   *diventa*     ciao ciao ciao
| "Ha, " * 5    *diventa*     Ha, Ha, Ha, Ha, Ha,

Nota bene: se non si mette lo spazio fra la scritta e le virgolette, il risultato verra tutto attaccato, come nel primo esempio: ciaociaociao.

Prova a cambiare l'esempio sottostante.

.. activecode:: esempio_print9
   :nocanvas:
   :language: python
   
   print("ciao"*3)

Possiamo anche mettere una stringa in una scatola, ossia assegnare una stringa ad una variabile e poi applicare le operazioni possibili sulle stringhe.

Ad esempio:

::

	SCATOLA1 = "casa "
	SCATOLA2= "dolce casa"
	print (SCATOLA1 + SCATOLA2)

:blue:`*casa dolce casa*`

.. activecode:: esempio_scatola3
   :nocanvas:
   :language: python
   
   SCATOLA1 = "casa "
   SCATOLA2= "dolce casa"
   print (SCATOLA1 + SCATOLA2)

Le operazioni possono anche essere combinate tra loro nella stessa istruzione.

Ad esempio:

print ("ciao " + (" ciao " * 3))

| darà come risultato: *ciao ciao ciao ciao*
| Questo risultato si può ottenere in altri modi,

ad esempio:

| print ("ciao " * 4)
| print ("ciao "+" ciao "+" ciao  "+" ciao ")

------------

:blue:`Esercitiamoci un po’`
::::::::::::::::::::::::::::

1. Scrivi le istruzioni necessarie per far comparire sul video la scritta:

 Cinque per tre e' uguale a 15.
 (Puoi ottenere questo risultato con o senza scatole, ossia le variabili. Trova le varie soluzioni).

|

2. Scrivi tutte le sequenze di istruzioni possibili per visualizzare il messaggio “Buon Compleanno” cinque volte.
       
|

3. Scrivi la sequenza di istruzioni per visualizzare il tuo nome e cognome in due stringhe separate.

|

4. Scrivi la sequenza di istruzioni per ottenere il messaggio seguente utilizzando le variabili: l'area del rettangolo e' uguale a 50.

|

5. Scrivi la sequenza di istruzioni per ottenere il perimetro e l'area di un rettangolo che abbia i lati di cm 9 e cm 5.

|

6. Scrivi le istruzioni per un programma che concateni due variabili stringa (attenti agli spazi) e moltiplichi due variabili numeriche (intere). Infine visualizza il risultato sullo schermo.

|

7. Prova a verificare il programma:

::

	print ('O   O')
	print ('---') 

e poi scrivine uno tu, inventando un nuovo disegno.

8. Trova l’errore:

::

	print (ciao+4)
	print ("ciao”+4)
       
9. Trova l’errore:

::

	scatola = "che bello il telefonino"
	print (scatola)
	farfalla = "cane"
	print ("è bello il mio", farfalla, "Joe!")
        
10. Trova l’errore:

::

	scatola = "viva il calcio balilla"*3
	print (scatola)
	farfalla = "cane"/5
	print ("è bello il mio", farfalla, "Joe!")

.. activecode:: esercizi1
   :nocanvas:
   :language: python

------------

:boltblue:`Adesso prova a scrivere tre semplici programmi:`

1. Scrivi le istruzioni per visualizzare cinque volte il messaggio “Ho conosciuto una principessa”.

2. Scrivi le istruzioni per ottenere che nella scatola1 ci sia 30, nella scatola2 ci sia anni e che il computer stampi: ’ domani compirai 30 anni’ .

3. Utilizzando le variabili, scrivi la sequenza di istruzioni per ottenere il messaggio seguente: l'area del rettangolo e' uguale a 20 cm e l’area del triangolo rettangolo è uguale a 20 cm.

.. activecode:: esercizi2
   :nocanvas:
   :language: python
