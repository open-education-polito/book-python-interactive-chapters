=============================
Quinto passo: primi programmi
=============================

.. role:: boltred

.. role:: blue

.. role:: red

.. role:: boltblue

.. role:: green

**Vediamo come fare a passare da una scatola all’altra.**

Istruzione di copia
===================

Cosa succede quando diamo al computer un'istruzione come: 
pippo = pluto
Il computer fa le seguenti operazioni: 

1. mette a disposizione la scatola di nome pippo

2. apre la scatola di nome pluto 

3. legge il contenuto (vi ricordate il foglietto nella scatola?) di pluto lo ricopia 

4. lo ricopia su un altro foglietto che  mette nella scatola pippo.

Al termine di queste operazioni le due scatole pippo e pluto contengono lo stesso numero 15. 
:blue:`Ecco come si presentano le scatole prima e dopo dell’esecuzione dell’istruzione:`

.. image:: images/pipponuovo.png
   :align: center
   :width: 250pt

:blue:`Osserva`: il contenuto di pluto (la scatola che si trova a destra del segno =) viene trasferito in pippo e non viceversa e che pluto non perde il suo contenuto. Perché?
:blue:`PERCHE’ E’ UNA COPIATURA` e non un trasferimento.

E se invece nella scatola pippo ci fosse stato un fogliettino 
con scritto 5?
Il risultato dopo l’istruzione sarebbe stato lo stesso. 
Cosa succede invece se scriviamo: 

pluto = pippo,
*quando* 
pippo = 5 e pluto = 15? 

Le due scatole conterranno il numero 5. 

Vediamo come scrivere i programmi corrispondenti a queste due istruzioni: 

**Programma 1 pippo = pluto**
::

	pippo = 5
	pluto = 15
	print ("pippo = ", pippo)
	print ("pluto = ", pluto)
	pippo = pluto
	print ("Dopo l'esecuzione dell'istruzione pippo = ", pippo) 
	print ("Dopo l'esecuzione dell'istruzione pluto = ", pluto)
	
	# Risultato Atteso:
	# pippo = 5
	# pluto = 15
	# Dopo l’esecuzione dell’istruzione pippo = 15 
	# Dopo l’esecuzione dell’istruzione pluto = 15 
                

**Programma 2 pluto = pippo**

.. activecode:: Copiatura
   :coach:
   :caption: Come copiare
   
   pippo = 5
   pluto = 15
   print ("pippo = ", pippo)
   print ("pluto = ", pluto)
   pluto = pippo
   print ("pluto = ", pluto) 
   print ("pippo = ", pippo)

Incremento
==========

Prova a immaginare cosa fa il computer per eseguire la seguente istruzione:

**pippo = pluto + 3**

Il computer farà così: 

    - Metterà a disposizione una scatola di nome pippo
    - Cercherà pluto e ne leggerà il contenuto.
    - Aggiungerà 3 al contenuto di pluto e metterà in pippo il risultato dell’operazione a destra dell’uguale. 
      
A questo punto, che cosa conterrà pippo e che cosa conterrà pluto? 
**pippo conterrà il numero 18 e pluto conterrà sempre il numero 15.** 
In pratica il computer inizia a lavorare sull’operazione a destra dell’uguale e il risultato viene messo nella scatola a sinistra.
Osserva ancora che il nome della scatola a destra dell’uguale indica il suo contenuto, mentre il nome della scatola a sinistra precisa la scatola
che conterrà il risultato.

.. image:: images/pippot.png
   :align: center
   :width: 200pt
 
Lo scambio
==========
 
Un po’ più complicata è l’operazione di scambio del contenuto di due scatole. 
Ad esempio se minnie = 10 e mickey = 12 come posso scambiare il contenuto di minnie e mickey, cioè inserire 12 in minnie e 10 in mickey?
E’come scambiare il contenuto di due bicchieri uno pieno di Coca Cola e l’altro pieno di aranciata. In quel caso occorre un terzo bicchiere. 
Nel nostro caso serve una **terza scatola!**
Esatto. Una scatola che possiamo chiamare, ad esempio, park, 
nella quale riponiamo il contenuto di una delle due scatole. Cosa fa il computer?  
    
    1. Apre le due scatole già disponibili di nome minnie e di nome mickey. 
    2. Mette a disposizione una scatola di nome park e ci inserisce il contenuto di minnie. 
    3. Legge il contenuto di mickey e lo mette in minnie. 
    4. Legge il contenuto di park (che era quello di minnie) e lo mette in mickey. 

+-------------------------------------------------------------+
| :blue:`minnie = 10;    mickey = 12`                         |
+-------------------------------+-----------------------------+
| :blue:`park = minnie`         | :boltblue:`park = .......`  |
|                               |                             |
|                               | :boltblue:`minnie = ......` |
+-------------------------------+-----------------------------+
| :blue:`minnie = mickey`       | :boltblue:`minnie = .......`|
|                               |                             |
|                               | :boltblue:`mickey = ......` |
+-------------------------------+-----------------------------+
| :blue:`mickey = park`         | :boltblue:`park = .......`  |
|                               |                             |
|                               | :boltblue:`minnie = ......` |
+-------------------------------+-----------------------------+

:blue:`Prima di proseguire...esercitiamoci un po’`
==================================================

|
| **Esercizio n. 1** 
|
|	Se click1 = 24 e slam1 = 32 come faccio per copiare il contenuto di click1 in slam1? E quando l’ho copiato come faccio per rimettere elle due scatole il contenuto originale?
|       Prova a illustrare i vari passaggi attraverso i quali il calcolatore copia il contenuto di una scatola in un'altra. 
|

|
| **Esercizio n. 2** 
|
|	Scrivi un programma per scambiare il contenuto delle due scatole seguenti:
|       pluto = “America” 
|       pippo = “Asia”
|

|
| **Esercizio n. 3** 
|
|	La scatola star contiene il numero 8. 
|       Come posso ordinare al computer di svuotarla e di mettere 15 al posto di 8?
|

|
| **Esercizio n. 4**
|
|	La scatola blam contiene il numero 2. 
|       Scrivi il programma che calcola il cubo del contenuto e lo mette nella scatola blam3. 
|

Input
=====

Finora abbiamo visto come inserire un numero o una stringa in una scatola, cioè un dato in una variabile utilizzando le istruzioni di assegnazione
del tipo:
scatola1 = 37.5 oppure scatola1 = "Viva la Juve" 
Oltre a questo, esiste un altro modo, molto importante, per introdurre un numero o una stringa in una scatola, rappresentato dall’istruzione input. 

:boltblue:`INPUT`, che significa letteralmente “ingresso”, si usa nel modo seguente: 

:blue:`scatola` = :green:`input`:red:`(prompt)`

Dove:

:blue:`scatola` è il nome della scatola nella quale inserirò un nuovo dato;

:green:`Input` è il comando che diamo al computer e che serve a inserire un dato qualunque  nella scatola. Quel dato è indicato dall’utilizzatore del programma attraverso la tastiera;

:red:`Prompt` è un messaggio che diamo all'utilizzatore perché sappia quale dato deve inserire da tastiera 

Ad esempio con:

**pluto = input ("Quanti anni hai?")** 
Chiediamo all'utilizzatore di indicare i propri anni, il computer leggerà il numero e lo inserirà nella
scatola di nome pippo. Quando il computer legge la parola input, si ferma e attende che l'operatore inserisca un numero dalla tastiera. 
Per far capire al computer quando il numero e’ finito, l’operatore preme il tasto Invio (o Enter). A questo punto il programma riprende e input interpreta ciò che l'operatore ha inserito come una stringa di caratteri e lo mette nella scatola indicata. 
Il programma prosegue poi con le istruzioni successive. 
La funzione INPUT è molto utile nella costruzione dei programmi, perché ci permette di trasmettere dei dati al calcolatore durante L’esecuzione
del programma. 

Finora abbiamo sempre inserito tutti i dati prima dell'esecuzione di un programma e poi abbiamo eseguito il programma stesso; con input, invece,
i dati possono essere inseriti durante l'esecuzione. Vediamo in dettaglio cosa succede nel programma seguente quando usiamo la “funzione” input: 

**anni = int (input ("Quanti anni hai? "))** 

**print ("Tu hai ", anni, " anni")**

+-----------------------------------------+----------------------------------------+
| anni = int (input ("Quanti anni hai? ") | 1) Il computer mette a disposizione la |
|                                         | scatola chiamata "anni", se questa     |
|                                         | scatola è stata gia utilizzata;        |
|                                         | oppure una scatola nuova alla quale da |
|                                         | il nome "anni"                         |
|                                         |                                        |
|                                         | 2) si ferma nell'attesa che venga      |
|                                         | inserito un dato dalla tastiera        |
|                                         |                                        |
|                                         | 3) inserisce i dato nella scatola      | 
|                                         | indicata                               |
+-----------------------------------------+----------------------------------------+                                       
| print ("Tu hai ", anni, " anni")        | Stampa prima la stringa “Tu hai  ”     |                                  
|                                         | poi il contenuto della scatola anni    | 
|                                         | e infine la stringa “anni"             |
+-----------------------------------------+----------------------------------------+                                         
                                       
Utilizzando Python, prova ad eseguire il programma. 

Hai notato che prima del comando “input” abbiamo aggiunto “int”?
E’ necessario dire all’interprete quando vogliamo inserire un numero e specificare bene il tipo di numero perché altrimenti l’interprete pensa che sia un qualunque carattere di una stringa.
Quando vogliamo :boltred:`inserire un numero intero` scriveremo: 

::

	int (input()) 

Quando vogliamo :boltblue:`inserire un numero con la virgola` scriveremo: 

::

	float (input())

Quindi per lavorare con le variabili numeriche (cioè le variabili di tipo numero) davanti al comando input si deve sempre aggiungere int o float. 

Prova a descrivere la sequenza di operazioni fatte dal calcolatore per eseguire il programma seguente :
Programma 3  “Stampa il triplo di un numero”
numero = int (input ("Introduci un numero "))
numero = numero * 3
print ("Il triplo del numero introdotto è : ", numero)
Prova ora ad inserire dei caratteri che non rappresentino un numero e osserva quale sarà il nuovo risultato. Sfortunatamente se i caratteri inseriti dall'operatore non rappresentano un numero, il programma stampa un messaggio d'errore e si blocca perché int(input()) e float(input()) funzionano soltanto con i numeri. 

**Come facciamo a far in modo che l’interprete accetti qualunque carattere immesso dall'utilizzatore?**
**Usiamo semplicemente il comando “input” senza specificare nulla.** 

**Il programma seguente:** 

::	

      	s = input ("Come ti chiami? ")
        print ("Ciao PAOLA", s)                       
	 
	# soluzione
 	# Ciao Paola
	# Ciao Alda
	# Ciao Marco 

Esercitati con gli esempi seguenti:

::

	print ("Alt! ")
	s = input ("Chi va la'? ")
	print ("Passa pure ", s)
	num = int (input ("Scrivi un numero "))
	print ("num = ", num)
	print ("num * 2 = ", num * 2)

        
Esercitiamoci un po’ 
====================

Ci sono più soluzioni possibili per ognuno degli esercizi proposti; sta a te trovarle e, soprattutto, provarle. 

1. Scrivi un programma che chiede un numero e ne calcola il quadrato e il cubo e li visualizza sullo schermo. 
    
2. Scrivi un programma che aggiunge 7 a qualunque numero inserito e visualizza il risultato sullo schermo. 
    
3. Scrivi un programma che chiede due numeri, li somma e visualizza il risultato. 
   
4. Scrivi il programma per calcolare l’area di qualunque rettangolo chiedendo all’utilizzatore la base e l’altezza. 
   
5. Scrivi il programma che chieda tre numeri e ne visualizzi sia la somma sia il prodotto. 
   
6. Scrivi il programma che calcola la metà e il doppio di qualunque numero inserito dall’utente, poi visualizza i risultati. 
    
7. Scrivi il programma che chiede la misura del lato di un quadrato e ne calcola l’area, poi visualizza il risultato. 
   
8. Scrivi il programma che calcola il perimetro del cortile della scuola che è un rettangolo i cui lati misurano rispettivamente 45 m e 65 m
   visualizza il risultato. Quindi calcola il perimetro di ogni rettangolo per il quale l’operatore inserisca la misura della base e
   dell’altezza. 
   
9. Scrivi un programma che chiede tre numeri, ne calcola la somma, la somma dei quadrati e il quadrato della somma. Infine, visualizza i
   risultati. 

.. activecode:: Esercizi_5_1
   :coach:
   :caption: Esercizi

   # Prova i tuoi esercizi

**ESERCIZI CON VALUTAZIONE**

Concediamoci un momento di pausa per giocare un po’.
Prima di proseguire il nostro percorso di studio, facciamo 
un breve gioco. Giochiamo a:

:boltred:`CACCIA ALL’ERRORE!`

Regole del gioco: 
In ogni programma è inserito un errore. 
Leggi attentamente ciascun programma, prova a digitarlo utilizzando Python, scopri e correggi l’errore. 
Per ogni esercizio assegnati un punto se riesci a trovare l’errore e un altro punto se riesci a correggerlo.

------------------------------

::

         # Es. 1: 
         # stampa il nome del tuo cantante preferito.
         
         cantante = input ("Scrivi il nome del cantante preferito: ")
         print ("Il mio cantante preferito e' ", cantant)


------------------------------

::

       # Es. 2  	
       # Input di numeri e stringhe

       primoNumero = int(input ("Scrivi il primo numero:  "))
       secondoNumero = int(input ("Scrivi il secondo numero: "))
       nome = input ("Scrivi il tuo nome:  ")
       cognome = input ("Scrivi il tuo cognome:  ")
       Print (nome, cognome, primoNuumero, "per", secondoNumero, "uguale", primoNumero*secondoNumero)
	

------------------------------

::

        # Es. 3: domanda di filosofia

	printt (" Sai in quale anno e' nato Socrate")
	sino = input ("si o no")
	print ("Ma certo, nell'anno 469 prima di Cristo")
	

------------------------------

::

        # Es. 4: divisione con resto

	primo = float (input ("Inserisci il primo numero"))
	secondo = float (input ("Inserisci il secondo numero"))
	print (primo, "diviso", secondo,"si ottiene", primo/secondo)
	print "il resto della divisione e' ", primo % secondo
	
.. activecode:: Esercizi_5_2
   :coach:
   :caption: Esercizi

   # Caccia all'errore: correggi gli esempi 
