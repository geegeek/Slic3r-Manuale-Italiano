% Combattere l'Oozing

A meno che il materiale estruso non abbia una viscosità molto alta, tenderà a fuoriuscire dall'ugello tra le estrusioni. Slic3r offre diverse impostazioni che possono aiutare a risolvere questo problema.

Le impostazioni di retrazione, nella scheda `Stampante`, indicano alla stampante di tirare indietro il filamento tra i movimenti di estrusione. Questo allevia la pressione nell'ugello, riducendo così l'oozing. Dopo il movimento successivo, la retrazione viene annullata per preparare l'estrusore alla prossima estrusione.

![Impostazioni di retrazione.](images/retraction_settings.png "fig:")

-   **Lunghezza** - Il numero di millimetri di filamento da retrarre. Nota che la misura viene presa dal filamento grezzo che entra nell'estrusore. Si consiglia un valore tra 1 e 2 mm. Gli estrusori Bowden potrebbero necessitare di 4 o 5 mm a causa dell'isteresi introdotta dal tubo.

-   **Sollevamento Z** - Solleva l'intero estrusore sull'asse Z di un determinato numero di millimetri durante ogni spostamento. Questo può essere utile per evitare che l'ugello tocchi il filamento già posato, ma di solito non è necessario e rallenta la stampa. Un valore di 0,1 mm è solitamente sufficiente.

-   **Velocità** - La velocità con cui il motore dell'estrusore ritrae il filamento. Questo valore dovrebbe essere il più veloce possibile senza che il motore perda passi. Vale la pena sperimentare per trovare la velocità di retrazione ottimale.

-   **Lunghezza extra al riavvio** - Aggiunge una lunghezza extra di filamento dopo la retrazione compensata dal movimento. Questa impostazione è raramente usata, ma può essere utile aggiungere una piccola quantità di materiale se la stampa mostra segni di carenza di materiale dopo i movimenti.

-   **Spostamento minimo dopo retrazione** - Eseguire una retrazione dopo movimenti molto brevi è di solito inutile poiché l'oozing è insignificante e rallenta i tempi di stampa. Imposta la distanza minima in millimetri che l'ugello deve percorrere prima di considerare una retrazione. Se la stampante gestisce bene l'oozing, questo valore può essere aumentato a 5 o 6 mm.

-   **Retrarre al cambio di layer** - Il movimento lungo l'asse Z deve essere considerato per evitare la formazione di blob. Si consiglia di lasciare attiva questa impostazione.

-   **Pulire prima della retrazione** - Sposta l'ugello durante la retrazione per ridurre le possibilità di formazione di blob.

Inoltre, nella scheda `Stampa` ci sono impostazioni aggiuntive per controllare l'oozing:

-   **Retrarre solo quando si attraversano i perimetri** (Riempimento) - Indica a Slic3r di retrarre solo se l'ugello attraverserà i bordi dell'isola corrente in estrusione. Piccole quantità di oozing all'interno delle pareti possono essere tollerate.

-   **Evitare di attraversare i perimetri** (Layer e perimetri - Avanzato) - Forza l'ugello a seguire i perimetri il più possibile per minimizzare il numero di volte in cui li attraversa, muovendosi tra e dentro le isole. Questo ha un impatto negativo sui tempi di generazione del G-code e di stampa.

-   **Punti di partenza casuali** (Layer e perimetri - Gusci verticali) - Quando l'estrusore si sposta all'inizio di un nuovo layer, l'oozing può causare blob. Se lo stesso punto di partenza viene usato per ogni layer, si può formare una cucitura lungo l'oggetto. Questa impostazione sposta il punto di partenza in una posizione diversa per ogni layer.

Vedi anche la sezione **Stampa Sequenziale** per un'altra tecnica utile a minimizzare la formazione di fili tra gli oggetti.
