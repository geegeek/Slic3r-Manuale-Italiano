% Ottimizzazione del Riempimento

Slic3r offre diverse impostazioni avanzate per il riempimento che possono aiutare a migliorare la qualità delle estrusioni.

![Impostazioni avanzate del riempimento.](images/infill_advanced_settings.png "fig:")

-   **Riempire ogni n layer** - Produce un riempimento verticale sparso saltando un numero specifico di layer. Questo può essere utile per ridurre i tempi di stampa quando il riempimento mancante è accettabile.

-   **Riempire solo dove necessario** - Slic3r analizzerà il modello e determinerà dove è richiesto il riempimento per supportare soffitti interni e sporgenze. Utile per ridurre tempo e materiali.

-   **Riempimento solido ogni n layer** - Forza un pattern di riempimento solido sui layer specificati. Impostare a zero per disabilitare questa opzione.

-   **Angolo di riempimento** - Di default, il pattern di riempimento è orientato a 45° rispetto al modello per garantire la migliore adesione alle strutture delle pareti. Le estrusioni di riempimento che corrono adiacenti ai perimetri possono delaminarsi sotto stress. Alcuni modelli potrebbero beneficiare della rotazione dell'angolo di riempimento per ottimizzare la direzione dell'estrusione.

-   **Area soglia per riempimento solido** - Piccole aree all'interno del modello sono generalmente meglio riempite completamente per garantire integrità strutturale. Tuttavia, ciò richiederà più tempo e materiale e potrebbe rendere alcune parti inutilmente solide. Regola questa opzione per bilanciare queste esigenze.

-   **Retrarre solo attraversando i perimetri** - La retrazione, per prevenire l'oozing, non è necessaria se l'estrusore rimane entro i confini del modello. Tuttavia, se il materiale di stampa tende a oozing eccessivo, non retrarre potrebbe causare una perdita di materiale sufficiente a compromettere la qualità dell'estrusione successiva. La maggior parte delle stampanti e dei materiali moderni non soffre di problemi di oozing così estremi.

-   **Riempimento prima dei perimetri** - Inverte l'ordine di stampa del layer. Solitamente, il perimetro viene posato inizialmente, seguito dal riempimento, e questo è preferibile poiché il perimetro funge da parete contenitiva per il riempimento.
