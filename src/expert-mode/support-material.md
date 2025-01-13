% Materiale di Supporto

In generale, la maggior parte dei modelli 3D può essere stampata con parti sporgenti fino a un certo angolo. L'angolo è determinato da diversi fattori, in particolare l'altezza del layer e la larghezza dell'estrusione, ed è solitamente intorno ai 45°. Per modelli con sporgenze più ampie, potrebbe essere necessario stampare una struttura di supporto sotto di esse. Questo comporta un maggiore utilizzo di materiale, tempi di stampa più lunghi e un'operazione di pulizia post-stampa.

![Opzioni per le strutture di supporto.](images/support/advanced_support.png "fig:")

Per iniziare, attiva l'opzione per il materiale di supporto selezionando la casella `Genera materiale di supporto`. Impostare un valore pari a zero nel parametro `Soglia per le sporgenze` indica a Slic3r di rilevare automaticamente le aree in cui fornire supporto; in alternativa, verrà utilizzato il valore di angolo specificato. La generazione del supporto è un argomento relativamente complesso e ci sono diversi aspetti che determinano il supporto ottimale. È fortemente consigliato impostare la soglia a zero e lasciare che Slic3r determini il supporto necessario.

Modelli piccoli, o quelli con una base ridotta, possono talvolta rompersi o staccarsi dal piano di stampa. L'opzione `Forza supporto` consente di stampare strutture di supporto per un numero specifico di layer, indipendentemente dal valore della soglia di angolo.

Per dimostrare i pattern di riempimento, il modello di una minimug è stato inclinato di 45° lungo l'asse X, come mostrato in figura.

![Modello minimug inclinato di 45°.](images/support/support_minimug_45deg.png "fig:")

Come per il riempimento, ci sono diversi pattern disponibili per le strutture di supporto.

- **Rectilinear**  
  ![Pattern di supporto: Rectilinear](images/support/support_pattern_rectlinear.png "fig:")

- **Rectilinear Grid**  
  ![Pattern di supporto: Rectilinear Grid](images/support/support_pattern_rectlinear_grid.png "fig:")

- **Honeycomb**  
  ![Pattern di supporto: Honeycomb](images/support/support_pattern_honeycomb.png "fig:")

`Distanza del Pattern` determina la distanza tra le linee del supporto ed è simile alla densità del riempimento, ma viene definita solo in mm. Quando si modifica questo attributo, è importante considerare la larghezza dell'estrusione del supporto e la quantità di materiale di supporto che aderirà all'oggetto.

È importante scegliere un pattern di supporto che si adatti al modello, in modo che il materiale di supporto si attacchi perpendicolarmente alla parete dell'oggetto, piuttosto che parallelamente, rendendo più facile la rimozione. Se la struttura di supporto corre lungo la lunghezza di una parete, l'opzione `Angolo del Pattern` consente di ruotare la direzione delle linee di supporto.

![Esempio di angolo del pattern ruotato di 45°.](images/support/support_pattern_rectlinear_rotated.png "fig:")
