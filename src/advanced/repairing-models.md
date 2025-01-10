% Riparazione dei Modelli

Se la mesh 3D descritta nel modello contiene buchi o i bordi non sono
allineati (condizione nota come non-manifold), Slic3r potrebbe avere
problemi nell'elaborazione. Slic3r cercherà di risolvere eventuali problemi, ma alcuni
potrebbero essere fuori dalla sua portata. Se l'applicazione segnala che un modello
non può essere tagliato correttamente, esistono diverse opzioni disponibili, descritte
qui di seguito, tutte gratuite al momento della stesura.

#### Netfabb Studio

Netfabb offre una gamma di applicazioni per la modellazione 3D, incluso
un versione base gratuita[^1]. Questa versione include un modulo di riparazione
delle mesh che può aiutare a eliminare vari problemi. Istruzioni aggiornate sono
disponibili sul wiki di Netfabb[^2], di seguito un rapido riepilogo dei passaggi.

![Netfabb Studio: Riparazione
della parte.](images/repair/netfabb_studio_part_repair.png "fig:")

-   Avvia Netfabb Studio e carica il file STL problematico, utilizzando
    il menu `File` o trascinandolo nell'area di lavoro. Se Netfabb rileva un
    problema, mostrerà un'icona di avviso rosso nell'angolo in basso a destra.

-   Per avviare gli script di riparazione, seleziona la parte e clicca
    sull'icona di pronto soccorso nella barra degli strumenti (la croce rossa),
    oppure seleziona `Extras->Repair Part` dal menu contestuale. Si aprirà
    la scheda di riparazione della parte che mostrerà lo stato del modello.

-   Le schede `Actions` e `Repair scripts` offrono diversi script di riparazione
    che possono essere applicati manualmente. Tuttavia, per questo riepilogo,
    selezionare lo script di riparazione automatica risolverà la maggior parte
    dei problemi.

-   Il pulsante di riparazione automatica presenta due opzioni: Default e
    Simple. Scegliendo Default si copriranno la maggior parte dei casi.
    Seleziona `execute` per eseguire gli script.

-   Una volta completata la riparazione, i risultati devono essere applicati
    selezionando `Apply repair`, scegliendo se sovrascrivere la parte esistente
    o meno.

-   La parte può essere quindi esportata selezionando `Export part->As STL`
    dal menu contestuale.

-   Se Netfabb rileva ancora errori nella parte esportata, offrirà l'opzione
    di applicare ulteriori riparazioni prima dell'esportazione.

![Netfabb Studio: Esportazione
della parte.](images/repair/netfabb_studio_export_part.png "fig:")

#### Servizio Cloud di Netfabb

Netfabb ospita anche un servizio web in cui è possibile caricare un
file STL per analizzarlo e ripararlo[^3].

![Servizi Cloud
Netfabb.](images/repair/netfabb_cloud_services.png "fig:")

-   Vai a http://cloud.netfabb.com

-   Scegli il file STL da caricare utilizzando il pulsante fornito.

-   Inserisci un indirizzo email per essere informato quando il servizio
    avrà terminato.

-   Scegli se utilizzare misure metriche o imperiali.

-   Leggi e accetta i termini di servizio, quindi clicca su
    `Upload to Cloud`.

-   Una volta che il servizio ha analizzato e riparato il file, riceverai un'email
    con il link per scaricare il file riparato.

#### FreeCAD

FreeCAD[^4] è un programma CAD completo e gratuito che include un modulo
per le mesh, utile per riparare modelli degenerati. Di seguito i passaggi
per analizzare e riparare un modello problematico.

![FreeCAD Riparazione
della parte.](images/repair/freecad_part_repair.png "fig:")

-   Avvia FreeCAD e dalla schermata iniziale scegli
    `Working with Meshes`.

-   Carica il modello trascinandolo nell'area di lavoro o utilizzando
    il menu `File`. Un piccolo messaggio nell'angolo in basso a sinistra indicherà
    se il modello presenta problemi.

-   Dal menu, seleziona `Meshes->Analyze->Evaluate & Repair mesh` per
    aprire la finestra di dialogo con le opzioni di riparazione.

-   Nella finestra di dialogo seleziona la mesh caricata, quindi esegui
    ogni analisi cliccando sul pulsante `Analyze` per ciascun tipo di problema,
    oppure seleziona `Repetitive Repair` in basso per eseguire tutti i controlli.
    Se viene rilevato un problema corrispondente, il pulsante `Repair` diventa
    disponibile.

-   Per ogni riparazione desiderata, premi il pulsante `Repair`.

-   È importante rivedere l'effetto dello script di riparazione sul modello.
    Potrebbe accadere che lo script danneggi il file anziché ripararlo, ad esempio
    rimuovendo triangoli importanti.

-   Esporta il modello riparato tramite l'opzione di menu `Export` o il menu contestuale.

[^1]: http://www.netfabb.com/basic.php

[^2]: http://wiki.netfabb.com/Part\_Repair

[^3]: http://cloud.netfabb.com/

[^4]: <http://sourceforge.net/projects/free-cad>
