% Velocità

Una volta che la stampante produce stampe di buona qualità in modo affidabile, potrebbe essere utile aumentare la velocità. Questo offre diversi vantaggi, il più ovvio è la riduzione del tempo di stampa. Inoltre, tempi di stampa più rapidi possono consentire di utilizzare più layer, ovvero un'altezza di layer inferiore, migliorando così la qualità percepita della stampa. Un ulteriore beneficio è che un movimento di viaggio più veloce, tra un'estrusione e l'altra, può ridurre gli effetti dell'oozing.

Il miglior approccio è incrementare i vari parametri di velocità a piccoli passi e osservare l'effetto di ogni cambiamento sulla qualità di stampa. La velocità di viaggio è un buon punto di partenza e non è irrealistico raggiungere velocità fino a 250mm/s (se la tua stampante è in grado di gestirle). In modalità semplice, è possibile regolare la velocità di perimetri e riempimenti, con la regola generale di impostare il perimetro leggermente più lento rispetto al riempimento per ridurre le imperfezioni sulla superficie (il riempimento può essere più veloce perché piccoli spazi vuoti non influenzano tanto).

La modalità esperto offre più parametri per ottimizzare le velocità di stampa. È possibile differenziare tra perimetri esterni, piccoli dettagli e altri perimetri, posizioni del riempimento, ponti e gap, oltre alla possibilità di rallentare per il primo layer.

![Opzioni avanzate di velocità in modalità esperto.](images/speed_advanced_settings.png "fig:")

Quando indicato, un valore può essere espresso in percentuale, in relazione al valore precedente, ad esempio il 50% di riempimento solido sarà la metà del valore definito per il riempimento.

Ecco alcune linee guida generali per ogni opzione:

-   **Perimetri** - In modalità esperto, questo parametro può essere leggermente aumentato poiché l'opzione `Perimetri esterni` può essere usata per garantire superfici esterne senza imperfezioni.

-   **Piccoli perimetri** - Pensato per fori, isole e dettagli fini, una velocità più lenta è consigliata.

-   **Perimetri esterni** - Un valore leggermente più lento può garantire superfici più pulite.

-   **Riempimento** - Il più veloce possibile senza compromettere l'integrità della struttura di riempimento. Estrusioni troppo rapide possono rompersi e creare punti deboli.

-   **Riempimento solido** - Il fondo del modello e eventuali layer solidi aggiuntivi sono di solito leggermente più lenti del riempimento ma più veloci dei perimetri.

-   **Riempimento solido superiore** - Consenti il tempo necessario affinché l'estrusione copra uniformemente i layer superiori precedenti, producendo una superficie superiore pulita. Gli ultimi layer dovrebbero aver coperto bene la struttura di riempimento, preparando la base per una finitura ordinata.

-   **Materiale di supporto** - Generalmente le strutture di supporto possono essere realizzate rapidamente, purché la base sia adeguatamente supportata.

-   **Ponti** - L'estrusione su distanze dipende dal materiale e dal raffreddamento. Procedere troppo lentamente provoca cedimenti, mentre procedere troppo velocemente porta a rotture. La sperimentazione è essenziale, ma in genere i ponti sono più lenti dei perimetri.

-   **Riempimento dei gap** - Riempire piccoli gap porta l'estrusore a oscillare rapidamente, e le vibrazioni risultanti potrebbero influire negativamente sulla stampante. Un valore più basso può prevenire questo problema. Un'impostazione pari a zero disabilita completamente il riempimento dei gap.

-   **Viaggio** - Il più veloce possibile per minimizzare l'oozing.

-   **Velocità del primo layer** - Come menzionato nella sezione dedicata al primo layer, è importante che il primo layer sia posato correttamente, e un ritmo più lento aiuta enormemente. Impostare un valore del 50%, o anche inferiore, può fare la differenza.

`Controllo dell'accelerazione` è un'impostazione avanzata che consente di configurare l'accelerazione per perimetri, riempimenti, ponti e un'impostazione predefinita generale. La scelta dei valori dipende dalle capacità della macchina. Le impostazioni nel firmware possono essere un buon punto di partenza.

Considera eventuali restrizioni imposte dal firmware, poiché molti prevedono impostazioni per la velocità massima sicura di ciascun asse.
