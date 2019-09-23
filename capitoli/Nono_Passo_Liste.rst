====================
Nono passo: le Liste
====================

.. role:: red

.. role:: boltred

.. role:: blue

.. role:: boltblue

:red:`In questo step impareremo:`

- cos'è una lista
- quando è utile utilizzare le liste
- a creare liste annidate
- ad attraversare una lista utilizzando il ciclo "for"

Cos’è una lista? È come quella che si fa quando bisogna fare la spesa? O come quando si fa l’elenco degli amici da invitare alla festa per il compleanno? Esatto!

:blue:`Una lista è un insieme ordinato di valori di qualunque tipo`, proprio come la lista della spesa.
 
Vediamo qualche esempio:

**lista di tutti numeri interi**
::

	[3, 6, 9, 12, 15]

----

**lista di tutte stringhe**
::

	["Luigi","Mario","Nicola","Giuseppina"]

----

**lista mista: 3 stringhe, 3 numeri interi, 1 stringa, 2 numeri decimali**
::

	["pane","latte","zucchero",1,15,230,"bicchieri",1.5,2.5]

----

I valori della lista sono chiamati “elementi” .
Le parentesi quadrate [ ] iniziano e finiscono la lista e la virgola (“,”) separa un elemento della lista dall'altro.
Come abbiamo visto in uno degli esempi precedenti, non è obbligatorio che gli elementi di una lista siano tutti dello stesso tipo, tutti numeri o tutte stringhe. Una lista può essere non omogenea.

Esiste poi una lista speciale chiamata “lista vuota” e si indica con [ ].

La lista vuota non contiene alcun elemento.

Ad esempio:
::

	["pane","latte","zucchero",1,15,230,"bicchieri",1.5,2.5]
	[1,"due",3.0]
	[]
	["tabellina del cinque",5,10,15,20,25]

----

**Ovviamente, alle liste dobbiamo dare un nome:**
::

	spesa = ["pane","latte","zucchero",1,15,230,"bicchieri",1.5,2.5]
	vocabolario = ["bicicletta","casa","scuola"]
	datiDiBuffon = ["Buffon", "Gianluigi", 1978]
	listaVuota = []

----

Prova a visualizzare sul video il contenuto delle liste precedenti.

.. activecode:: Prova


----

:blue:`Le liste sono un tipo di variabile: variabili "composte".`

Le variabili ordinarie immagazzinano un singolo valore.
Le liste sono variabili che possono contenere più di un valore. Possiamo pensarle come armadi composti da una serie di cassetti scatole.

Vediamo ora come si fa ad accedere ai singoli elementi di una lista.
Prova a scrivere il seguente programma e analizza attentamente il risultato: 

::

	Squadre = ["Juventus", "Inter", "Milan", "Roma"] i = 0
	while i < 4: 
		print (Squadre [i])
		i = i + 1

Questo programma assegna alla lista squadre alcuni valori e con il ciclo WHILE “attraversa” la lista e ne visualizza un elemento alla volta.

Per farlo usa un indice (nel nostro caso “i”). Squadre[i] individua l'elemento i della lista squadre.

:blue:`Quindi è possibile accedere separatamente a ciascun elemento della lista.`

Ricordi che abbiamo parlato di insieme ordinato di valori?

:blue:`Gli elementi di una lista sono valori numerati e identificati da un indice.`

Un indice identifica un particolare elemento di un insieme ordinato che nel nostro caso è l'insieme degli elementi della lista.

La numerazione degli elementi della lista inizia da 0.
::

	Squadre [0] = è la stringa "Juventus"
	Squadre [1] = è la stringa "Inter"
	Squadre [2] = è la stringa "Milan"
	Squadre [3] = è la stringa "Roma"

Appare chiaro da questi esempi che l'elemento [0] è il primo e l'elemento [2] è il terzo.

**Nota bene:** Fai attenzione al fatto che gli indici di una lista, cosi come gli indici di una stringa, iniziano sempre da zero; può sembrarti strano, ma i calcolatori preferiscono iniziare a contare da zero.

Quindi per accedere al primo elemento di una lista dobbiamo scrivere [0] e non [1]. 

Esercitati a selezionare gli elementi di tutte le liste che abbiamo usato come esempio e prova a scrivere un ciclo while per attraversarle e visualizzare gli elementi su video, come nell'esempio seguente, con la lista: [3,6,9,12,15]

:blue:`1. Innanzitutto dobbiamo dare un nome alla lista:`
::

	tabellina = [3,6,9,12,15]

:blue:`2. Quindi selezionare gli elementi:`
::

	print (tabellina [0])
	
	# Risultato Atteso: 3

.. Esercizio da modificare.

:blue:`3. Ora scriviamo il ciclo per attraversare la lista:`
::

	i = 0
	while i < 5: 
		print (tabellina [i])
		i = i + 1

.. activecode:: Ciclo


----

------
Indici
------

Si accede agli elementi di una lista nel modo già visto per accedere ai caratteri di una stringa. 
::

	print (tabellina [1]) #Visualizza il secondo elemento della lista: tabellina
 
Una qualsiasi espressione che produca un intero può essere un indice. Ad esempio: *tabellina[5-1]* visualizza: *15*
 
Prova a usare un numero decimale come indice e analizza il messaggio di errore che compare:

:boltred:`TypeError: sequence index must be integer`

Prova a leggere o a modificare un elemento che non esiste. Ad esempio:
::

	tabellina[7] = 2

L'interprete cerca di assegnare a *tabellina [7]* il valore *2*. 

Anche qui analizza attentamente il messaggio di errore: 

:boltred:`IndexError: list assignment index out of range`

Cosa succede se l'indice ha valore negativo? Esempio: :blue:`tabellina [-2]`

:blue:`Se un indice ha valore negativo il conteggio parte dalla fine della lista.
Per verificarlo prova a scrivere: tabellina[-3]
Questo metodo di usare l’indice negativo si rivela molto comodo quando non si conosce la lunghezza della lista. Sappiamo che se scriviamo [-1] accederemo all’ultimo elemento, [-2] al penultimo e così via.`

Infine, come abbiamo visto all’inizio, una variabile di ciclo può essere usata 
come indice di lista. Esempio:
::

	amici = ["Gianni", "Luigi", "Carlo"] 
        i= 0
	while i < 3: 
		print (amici [i])
		i = i + 1

--------------
Lista speciale
--------------

È la lista composta da tutti numeri interi, talmente comune che Python fornisce un modo speciale per crearla. La funzione list(range) è lo strumento usato per crearla. Infatti, scrivere *[0,1,2,3,4]* è equivalente a scrivere *list(range(5))*.

Cioè, la funzione *list(range)* crea una lista che parte da 0 e arriva fino al numero indicato dall'indice.

*list(range (10))* è equivalente a *[0,1,2,3,4,5,6,7,8,9]*

Con list(range) si può scrivere: *list(range (1,5))* che è equivalente a *[1,2,3,4]*

La funzione *list(range)* in questo caso legge dalla lista di interi gli elementi che partono dal primo indice incluso e arrivano all'ultimo indice escluso.

**Nota Bene:** La funzione *list(range)* ha sempre le parentesi tonde.

Con *list(range)* possiamo scrivere anche espressioni del tipo: *list(range (1,10,2))* che è equivalente a *[1,3,5,7,9]*.
 
Il terzo indice si chiama "passo" e indica con quale intervallo leggere i numeri dalla lista di interi partendo da 1 e arrivando a 10 escluso. In questo caso legge il primo, il terzo, il quinto e cosi via fino a 10-1, ottenendo una lista di numeri dispari.

:blue:`Che lista ottieni con questa funzione? list(range(2,10,2))`

:boltblue:`3 - Lunghezza di una lista`

La funzione *len* applicata ad una lista produce il numero di elementi di una lista, come nelle stringhe.
::

	allievi = ["Luigi","Marco","Filippo","Paola","Gabriella","Silvia"]
	i= 0
	while i < len(allievi): 
		print (allievi[i])
		i= i + 1
	
	# Risultato Atteso: Luigi Marco Filippo Paola Gabriella

:boltblue:`4 - Operazioni sulle liste`

Come per le stringhe, l'operatore + concatena le liste:

.. activecode:: Esempio

	allievi3A = ["Luigi","Marco","Filippo","Paola","Gabriella","Silvia"]
	allievi4E = ["Gabriele","Alessandro","Anna","Michela","Antonio"]
	allievi = allievi3A + allievi4E
	print (allievi)

L'operatore * ripete una lista un dato numero di volte. 

Se *numeri* é la lista *[3,6,9,12,15]*, numeri* 3 é la lista
*[3, 6, 9, 12, 15, 3, 6, 9, 12, 15, 3, 6, 9, 12, 15,]*.
::

	print(allievi4E * 2)

produce: 

Gabriele Alessandro Anna Michela Antonio Gabriele Alessandro Anna Michela Antonio

----------------
Sezione di lista
----------------

Una sezione di lista è l'analogo di una sezione di stringa e ha la stessa logica di funzionamento. Infatti, come per le stringhe, si adotta l'operatore porzione:

Se *amici* é la lista *[“Gianni”,”Luigi”,”Carlo”]*
::

	print (amici [0:3])
	
	# Risultato Atteso: "Gianni" "Luigi" "Carlo"

::

	print (amici [1:3])
	
	# Risultato Atteso: "Luigi" "Carlo"

Se
::

	allievi4E = ["Gabriele","Alessandro","Anna","Michela","Antonio"]
	
        print (allievi4E [1:3])

	# Risultato Atteso: "Alessandro", "Anna"

**Ricordati: il primo indice incluso, il secondo indice escluso. Con questo operatore possiamo eliminare uno o più elementi di una lista assegnando alla corrispondente sezione una stringa vuota.**

::

	allievi4E = ["Gabriele","Alessandro","Anna","Michela","Antonio"]
	allievi4E [1:3] = []
	print (allievi4E)
	
	# Risultato Atteso: Gabriele Michela Antonio

Ma non è così pratico ed è facile sbagliare. Con la funzione del è molto più facile cancellare un elemento da una lista.
::

	Squadre = ["Juventus", "Inter", "Milan", "Roma"]
	del Squadre [1]
	print (Squadre)
	
	# Risultato Atteso: Juventus Milan Roma

Analogamente possiamo inserire uno o più elementi in una lista inserendoli in una sezione vuota nella posizione desiderata.
::

	allievi4E = ["Gabriele","Alessandro","Anna","Michela","Antonio"]
	print (allievi4E [2:2])
	allievi4E [2:2] = ["Sandra", "Andrea"]
	print (allievi4E)
	
	# Risultato Atteso: Gabriele Alessandro Sandra Andrea Anna Michela Antonio

**Cosa ottengo se scrivo quanto segue?**
::

	allievi4E = ["Gabriele","Alessandro","Anna","Michela","Antonio"]
	print (allievi4E [:4])
	print (allievi4E [3:])
	print (allievi4E [:]) 

Se non viene specificato il primo indice la porzione parte dall'inizio della stringa. Senza il secondo indice la porzione finisce con il termine della stringa.
Se mancano entrambi gli indici si intende tutta la lista.

--------------
Liste annidate
--------------

Un elemento di una lista può essere a sua volta una lista.
::

	tabellina = [3,6,9,12,15,[10,20,30]]
	print (tabellina [5])
	[10 20 30]

Il sesto elemento della lista tabellina è a sua volta una lista.

Nell'esempio seguente la lista allievi_4E è diventata una lista di liste:
::

	allievi4E = [["Bianchi","Gabriele"],["Verdi","Alessandro"],["Rossi","Anna"],["Neri","Michela"],["Viola","Antonio"]]
	print (allievi4E[2])
	
	# Risultato Atteso: Rossi Anna

:blue:`Cosa ottengo se scrivo print (allievi4E[2][0])?`

Ottengo il risultato *[Rossi]*.

Posso estrarre un elemento da una lista annidata con due metodi differenti.

Il primo è il seguente:
::

	allievo = allievi4E [2]
	print (allievo [0])
	
	# Risultato Atteso: Rossi

Creo una lista che si chiama allievo e prendo il primo elemento di quella nuova lista.

Il secondo mi permette di scrivere direttamente: allievi4E [2][0]

Questa espressione deve essere letta da sinistra verso destra: trova il terzo elemento [2] della lista allievi4E ed essendo questo elemento a sua volta una lista, ne estrae il primo elemento [0]. 

Ancora una domanda difficile. Qual è la lunghezza della lista seguente?
::

	allievi4E = [["Bianchi","Gabriele"],["Verdi","Alessandro"],["Rossi","Anna"],["Neri","Michela"],["Viola","Antonio"]]

:boltblue:`Il ciclo FOR (ancora più semplice attraversare una lista)`

Riprendiamo l’esempio:
::

	allievi = ["Luigi","Marco","Filippo","Paola","Gabriella","Silvia"]
	i= 0
	while i < len(allievi): 
		print (allievi[i])
		i=i+ 1
	
	# Risultato Atteso: Luigi Marco Filippo Paola Gabriella Silvia

Questo ciclo può essere scritto anche in questo modo:
::

	allievi = ["Luigi","Marco","Filippo","Paola","Gabriella","Silvia"]
	for allievo in allievi: 
		print ("Ora stampo l'allievo: ", allievo)

Possiamo leggere quasi letteralmente: “Fai quello che segue per ciascun allievo nella lista allievi, lavorando la prima volta sul primo elemento, la seconda sul secondo, e cosi via.

Stesso risultato, ma il programma è più breve. In termini generali devo scrivere:

:blue:`for <nome di variabile> in <nome di lista> :`

**L’istruzione for significa: per ciascuna variabile della lista fai tutto quello che segue.**

**In modo più formale la lista viene analizzata dal primo elemento sino all'ultimo. La prima volta:**

1. alla variabile allievo assegna il valore allievi[0]
2. esegue i comandi che seguono i due punti
3. ritorna all’istruzione for

e prosegue fin quando trova un elemento nella lista.

Negli esempi che seguono cerchiamo di capire a cosa può servire il ciclo :blue:`for`.

**Stampiamo il quadrato dei primi 11 numeri interi**
::

	for numero in list(range(11)):
		print ("il quadrato di ", numero, " è ", numero * numero)
	
	# Risultato Atteso:
		# il quadrato di 0 è  0
		# il quadrato di 1 e` 1
		# il quadrato di 2 e` 4
		# il quadrato di 3 e` 9
		# il quadrato di 4 e` 16                                      
		# il quadrato di 5 e` 25
		# il quadrato di 6 e` 36
		# il quadrato di 7 e` 49
		# il quadrato di 8 e` 64
		# il quadrato di 9 e` 81
		# il quadrato di 10 e` 100

Ti ricordi come si fa a modificare il programma per ottenere un elenco in colonna?

Misuriamo ora la lunghezza di alcune parole:
::

	vocabolario = ['alba','banana','carro','dodici','giacca','finestra']
	for parola in vocabolario:
		print (parola, len(parola))
	# Risultato Atteso:
		# alba 4
		# banana 6
		# carro 5
		# dodici 6
		# giacca 6
		# finestra 8

:blue:`Per uscire immediatamente da un ciclo for o while devi usare l’istruzione break.`

Vediamo un esempio semplice: un programma che stampa tutti i numeri positivi fino a 100 ma se viene inserito 0 si interrompe. 
::

	i= 1
	while i < 100 : 
        	i = int(input('Inserisci un numero: '))
        	if i == 0:
			break
		print ('Il numero è: ', i)
	print ('Finito')

Ricordati che se il ciclo avesse un else questo non verrebbe mai eseguito.

--------------------
Esercitiamoci un po'
--------------------

1. Scrivi un programma che analizzi le seguenti stringhe e per ognuna stampi le lettere una ad una: banana, cipolla, bambino, finestra, girotondo.

2. Scrivi un programma che sommi tutti gli elementi di una lista data di numeri.

3. Scrivi un programma che stampi la “successione di Fibonacci”. La somma di due elementi definisce l'elemento successivo (1,2,3,5,8,13...).

4. Scrivi un programma per trovare i numeri primi in una lista di numeri che va da 2 a 20.

5. Scrivi un programma che conta il numero di volte in cui la lettera 'a' compare in una stringa, usando un contatore.

6. Scrivi un programma che operi su una lista di numeri e conti il numero di volte in cui un valore cade in un determinato intervallo.

.. activecode:: Esercizi

----

Nel programma seguente  ci sono alcuni errori, trovali e correggili:

.. activecode:: Esercizio7

	def interrogazione (domanda,rispostaEsatta):
		rispostaAllievo = input (domanda)
		if rispostaEsatta = rispostaAllievo:
			print ("La risposta e' esatta")
		else:
			print ("Risposta errata")
			print ("La risposta esatta e' ", rispostaEsatta)
	domanda1 = "In che anno è caduto l'impero romano d'occidente? " rispostaEsatta1 = "476"
	interrogazione (domanda1, rispostaEsatta1)
	domanda2 = "Chi e' stato il primo presidente degli Stati Uniti? " rispostaEsatta2 = "Washington" 
	interrogazione (domanda2, rispostaEsatta2)
	domanda3 = "In che anno è terminata la prima guerra mondiale? " rispostaEsatta3 = "1918"
	interrogazione (domanda3, rispostaEsatta3)

