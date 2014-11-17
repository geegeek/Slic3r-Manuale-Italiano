% Slic3r: Supporto

Se questo manuale non risponde a qualcuno dei tuoi problemi puoi provare in diversi altri modi:

Canale IRC 
---


Trovi sul server `irc.freenode.net` , la seguenti stande, le quali sono di solito piene di persone che sono in grado di aiutarti in tempo reale:

* `#reprap`: Una comunità molto attiva del progeetto RepRap con molti utenti di Slic3r.

* `#slic3r`: Una chatroom di Slic3r dove gli sviluppatori e gli utenti di Slic3r  possono aiutarsi e dare aiuto.

RepRap.org Forum
----------------

Un mirato [forum di Slic3r](forums.reprap.org/list.php?263) esiste tra i forum di RepRap.

Issue Tracker
-------------

Se un bug riesce ad essere trovato nel software, oppure vuoi mettere in evidenza un altro problema puoi postare sul  [GitHub issue tracker](http://github.com/alexrj/Slic3r/issues).

**Perfavore** assicurati di avere letto le linee guida qui sotto.

GuideLinea per riportare un problema
---------------------------------

Tieni in mente che gli sviluppatori stanno lavorando su una base di volontari, ed il volume delle richieste relative a Slic3r è travolgente, perciò **perfavore** siatene consapevoli e cercate di realizzare il ** report più completo e chiaro possibile** meglio riuscite a fare maggiori saranno le vostre possibilità di avere aiuto ed attenzione.

* C'è un alta probabilità che la problematica, che state riscontrando, è già stata riportata.
  Perfavore controllate la [lista delle problematiche riportate](https://github.com/alexrj/Slic3r/issues)
  prima di creare una nuova segnalazione. Se trovi una segnalazione esistente riportata, sentiti libero di approfondire ed aggiungere maggiori informazioni su quel report.
* Includi il **file STL e config.ini** (si esporta da *File* -> *Export config...*)
  e può essere utilizzato per **riprodurre la problematica**.
* Includi gli **screenshots dell' anteprima del G-code ** dimostrando che la problematica può essere visualizzata nel G-code e non è causata da problemi maccanici o dal firmware.
* Specifica la versionde diSlic3r (o il numero di commit) ed il sistema operativo.
* Assicurati che il file STL sia corretto ( fallimenti dovuti ad un modello corrotto o errato non sono considerati un bug; noi trattiamo solo bug riproducibili con modelli validi nel loro formato).
* Fare un report per ogni segnalazione. Se incontrate multiple, non correlate problematiche, perfavore riportatele separatamente per come sono.

Linee Guida per la richiesta di caratteristiche aggiuntive
----------------------------------

Slic3r è un progetto comunitario, ed ulteriori caratteristiche sono solitamente aggiunte quando c'è un consenso generale su di esse.. Perfavore iniziate a descrivere i vostri *obiettivi* spiegandone un caso concreto. Mostrate il G-code di un caso reale di produzione con l' attuale Slic3r e descrivete cosa vorreste migliorato e perchè. Mettete impegno nella documentazione con immagini, anteprime di screenshot di G-code, ponendo un attento esame nella stesura del testo.

Dopo che vi sarete concentrati sul **perchè** potrete descrivere l' idea sul **come** raggiungere quell' obiettivo. Ma non invertite l' ordine e gli sforzi.
