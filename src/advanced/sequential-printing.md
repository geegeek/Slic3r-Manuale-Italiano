% Stampa Sequenziale

Quando si stampano più oggetti contemporaneamente, può essere utile stampare
ciascuno separatamente. Questo riduce al minimo il fenomeno di oozing e la formazione
di fili tra le stampe. Inoltre, diminuisce il rischio che un problema comprometta
l'intera stampa: se una parte si stacca o fallisce in qualche modo, non verrà
trascinata nelle altre parti durante ogni strato.

![Opzioni di stampa
sequenziale.](images/sequential_printing_options.png "fig:")

Bisogna prestare attenzione affinché l'ugello e l'estrusore non interferiscano
con le parti già stampate. Slic3r dovrebbe avvisare se rileva che l'ugello o
l'estrusore potrebbero collidere con una parte, ma è consigliabile verificare
manualmente che il layout delle parti non causi problemi. I parametri di
`Sgombero dell'estrusore` aiutano Slic3r a rilevare potenziali collisioni:

-   **Raggio** - Lo spazio che deve essere garantito attorno all'estrusore.
    Fai attenzione se l'estrusore non è montato in posizione centrale: utilizza
    il valore massimo sicuro.

-   **Altezza** - La distanza verticale tra la punta dell'ugello e le barre
    dell'asse X, o la parte più bassa che potrebbe interferire con una stampa
    completata.

![Il cilindro di sgombero attorno a un
estrusore.](images/extruder_clearance.jpg "fig:")
