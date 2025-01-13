% Estrusori Multipli

Una stampante con più di un estrusore può essere utilizzata in modi diversi: l'estrusore aggiuntivo può stampare un colore o un materiale diverso; oppure può essere assegnato a stampare caratteristiche specifiche, come il riempimento, i supporti o i perimetri.

La stampa multi-materiale richiede un oggetto adeguatamente progettato, solitamente scritto in formato AMF, che supporta materiali multipli (vedi Formati Modello in §). Di seguito vengono fornite istruzioni su come creare un file di questo tipo.

## Configurazione degli Estrusori

Nella scheda `Impostazioni Stampante` è presente l'opzione `Estrusori`, sotto `Capacità`, che consente di definire il numero di estrusori. Incrementando questo valore, verrà aggiunta dinamicamente una definizione per un altro estrusore nel pannello a sinistra.

![Opzioni per estrusori multipli - Scheda Impostazioni Stampante (Generale). Due estrusori sono definiti nel pannello a sinistra.](images/multipleextruders/printer_settings_general_multiple_extruder_options.png "fig:")

Ogni estrusore può essere configurato come di consueto, ma ci sono impostazioni aggiuntive specifiche per le configurazioni con estrusori multipli.

![Opzioni per estrusori multipli - Scheda Impostazioni Stampante (Estrusore).](images/multipleextruders/printer_settings_extruder_multiple_extruder_options.png "fig:")

-   **Offset dell'Estrusore**: deve essere utilizzato se il firmware non gestisce lo spostamento di ciascun ugello aggiuntivo. La documentazione del firmware dovrebbe indicare se questo è il caso. Ogni estrusore aggiuntivo riceve un offset rispetto al primo. Se il firmware gestisce questa funzione, tutti gli offset possono rimanere su 0,0.

-   **Retrattazione per Estrusori Secondari**: Poiché l'estrusore secondario sarà inattivo mentre il primo lavora, è importante che il materiale venga sufficientemente ritratto per evitare l'oozing. Come per le impostazioni di retrazione standard (vedi p.), l'opzione `Lunghezza` viene misurata dal filamento grezzo che entra nell'estrusore.

## Assegnazione dei Filamenti

Se è stato selezionato un profilo di stampante con estrusori multipli, nella scheda `Plater` è possibile selezionare un filamento diverso per ciascun estrusore.

![Plater con opzioni di filamento multiplo.](images/multipleextruders/plater_multi_filament.png "fig:")

## Assegnazione degli Estrusori per Oggetti Monomateriale

Per stampe a materiale singolo, in cui l'estrusore secondario è destinato a un'estrusione specifica, la sezione `Estrusori Multipli` della scheda `Impostazioni di Stampa` consente di assegnare un estrusore a ciascun tipo di estrusione.

![Opzioni per estrusori multipli - Scheda Impostazioni di Stampa.](images/multipleextruders/print_settings_multiple_extruder_options.png "fig:")

## Configurazione dei Cambi di Strumento

La sezione `G-code Personalizzato` nella scheda `Impostazioni Stampante` include un'opzione per inserire codice G tra i cambi di strumento. Come per tutte le sezioni di codice G personalizzato, è possibile utilizzare variabili segnaposto per fare riferimento alle impostazioni di Slic3r. Tra queste ci sono le variabili `[previous_extruder]` e `[next_extruder]`.

![Opzioni per estrusori multipli - G-code per cambio di strumento.](images/multipleextruders/printer_settings_custom_gcode.png "fig:")

## Stampa di Oggetti Multi-materiale

Se esiste già un file AMF multi-materiale (ad esempio creato da un programma CAD in grado di esportare tale formato), questo può essere caricato in Slic3r come di consueto. L'assegnazione tra materiali dell'oggetto ed estrusori è sequenziale, cioè il primo materiale è assegnato al primo estrusore, e così via.

## Generazione di File AMF Multi-materiale

Slic3r offre la possibilità di combinare più file STL in un file AMF multi-materiale.

-   Dividi il design originale in parti separate nel programma CAD ed esporta ogni parte come STL.

-   In Slic3r, seleziona `Combina file STL multi-materiale...` dal menu `File`.

-   Quando appare la finestra di dialogo per i file, scegli il primo STL, che sarà assegnato al primo materiale (e quindi al primo estrusore). Clicca su `Apri` per selezionare il prossimo STL, e così via, fino a che ogni STL è assegnato a un materiale. Per indicare che non ci sono altri file STL, scegli `Annulla`.

-   La finestra di dialogo successiva richiede la posizione e il nome del file AMF.

Una volta generato, il file può essere caricato e stampato come descritto sopra.
