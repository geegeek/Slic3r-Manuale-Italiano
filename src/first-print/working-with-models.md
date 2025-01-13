% Lavorare con i Modelli

Un altro passaggio si trova tra questo momento e la prima stampa: è necessario trovare un modello e poi tagliarlo.

## Formati dei Modelli

Slic3r accetta i seguenti tipi di file.

- **File STereoLithography (STL)**: I file STL possono provenire da una vasta gamma di fonti e sono ormai uno standard de facto nella stampa 3D. I file descrivono semplicemente la geometria superficiale di un oggetto 3D senza informazioni aggiuntive (come colore o materiale), e è questa semplicità che probabilmente ha reso il formato onnipresente.

- **File Wavefront OBJ**: I file OBJ sono un formato aperto originariamente utilizzato in un'applicazione di animazione di Wavefront Technologies, ma sono stati successivamente adottati dalla comunità più ampia di modellazione 3D. È simile al formato STL.

- **Formato di File per la Produzione Additiva (AMF)**: AMF è stato sviluppato in risposta alla natura limitata del formato STL. Oltre a descrivere la geometria del modello 3D, può anche descrivere colori e materiali, nonché attributi più complessi, come miscele di gradienti e disposizioni di oggetti multipli (costellazioni). Sebbene il formato sia considerato uno standard, deve ancora essere ampiamente adottato nella comunità dei maker 3D.

## Trovare Modelli

I file dei modelli 3D possono provenire da un repository online, come Thingiverse[^1] o GrabCAD[^2], oppure essere creati con un programma CAD, come FreeCAD[^3], Sketchup[^4] o OpenSCAD[^5], oppure con uno strumento CAD online come Shapesmith[^6].

Potresti voler visualizzare i file prima di tagliarli e ci sono molte applicazioni gratuite disponibili, una delle quali è Meshlab[^7] - uno strumento completo per visualizzare e lavorare con file 3D.

![Strumento CAD online Shapesmith.](images/working-with-models/shapesmith.png "fig:")

## Lavorare con il Plater

Slic3r dispone di uno strumento, chiamato Plater, che permette di caricare e organizzare uno o più modelli prima di essere tagliati.

![Plater](images/working-with-models/plater.png "fig:")

Una volta acquisito un modello, trascinalo nella finestra del Plater (o utilizza il pulsante Aggiungi sotto l'elenco dei file) per caricarlo in Slic3r. Nella figura seguente, il tradizionale RepRap Minimug[^8] è caricato ed è visto dall'alto. L'anello attorno al modello è uno skirt - un singolo perimetro, a diversi millimetri di distanza dal modello, che viene estruso per primo. Questo è utile per assicurarsi che la plastica fluisca senza problemi dall'ugello quando la stampa del modello inizia.

![Modello Minimug.](images/working-with-models/minimug_model.png "fig:")

![File STL caricato.](images/working-with-models/plater_model_loaded.png "fig:")

Il modello può essere riposizionato trascinando la sua rappresentazione sul lato sinistro dello schermo all'interno del piano di stampa. Nota che le dimensioni del piano di stampa devono corrispondere a quelle della tua stampante, come specificato durante la configurazione iniziale.

Sul lato destro si trova l'elenco dei file attualmente caricati. I pulsanti nella parte superiore dell'elenco dei file permettono di organizzare i modelli.

- **Più/Meno** - Regola quante copie devono essere stampate.
- **45°/Ruota** - Ruota il modello selezionato attorno all'asse Z, in incrementi di 45° in senso orario o antiorario, o di un determinato angolo.
- **Scala** - Aumenta o diminuisci le dimensioni del modello stampato.
- **Dividi** - Divide un modello composto da più parti nelle sue componenti, permettendo di organizzare ciascuna singolarmente.

I pulsanti nella parte inferiore dell'elenco dei file permettono di aggiungere, rimuovere, auto-organizzare o esportare i modelli.

- **Aggiungi** - Apre una finestra di dialogo per aggiungere un modello al plater, come alternativa al trascinamento diretto del file.
- **Elimina/Elimina Tutti** - Rimuove uno o tutti i modelli dal plater.
- **Autoarrangia** - Tenta di organizzare i modelli per ottenere il layout ottimale.
- **Esporta G-code** - Avvia il taglio del modello e produce un file G-Code.
- **Esporta STL** - Salva l'attuale set di modelli come un unico file STL.

## Pulizia dei File STL

Se la mesh 3D descritta nel modello contiene buchi o bordi non allineati (condizione nota come non-manifold), Slic3r potrebbe avere problemi a lavorarci. Slic3r tenterà di risolvere eventuali problemi che può, ma alcuni problemi potrebbero essere fuori dalla sua portata. Se l'applicazione segnala che un modello non può essere tagliato correttamente, ci sono diverse opzioni disponibili: vedi il capitolo sulla **Riparazione dei Modelli**.

[^1]: <http://www.thingiverse.com>
[^2]: <http://grabcad.com>
[^3]: <http://sourceforge.net/projects/free-cad>
[^4]: <http://www.sketchup.com>
[^5]: <http://www.openscad.org>
[^6]: <http://shapesmith.net>
[^7]: <http://www.meshlab.org>
[^8]: <http://www.thingiverse.com/thing:18357>
