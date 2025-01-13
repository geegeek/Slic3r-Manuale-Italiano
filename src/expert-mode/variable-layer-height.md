% Altezza Layer Variabile

Slic3r consente di regolare l'altezza dei layer in punti arbitrari lungo l'asse Z. Ciò significa che alcune parti del modello possono essere stampate con un'altezza di layer grossolana, ad esempio le sezioni verticali, mentre altre parti possono essere stampate con un'altezza di layer più fine, come i gradienti inclinati dove la stratificazione appare più evidente.

Il modello nella figura seguente offre un esempio rudimentale di utilizzo dell'altezza dei layer variabile per migliorare la qualità della stampa. Le pareti della struttura non necessitano di un'alta definizione per una qualità accettabile, ma il tetto inclinato mostra artefatti dei layer, poiché l'altezza di 0.4mm è troppo grossolana, in particolare per la parte superiore, che risulta appiattita.

![Esempio di modello evidenziando l'uso dell'altezza layer variabile.](images/variable_layer_height/example_model.png "fig:")

![Esempio con altezza layer normale.](images/variable_layer_height/example_gcode_normal_layer_heights.png "fig:")

Le opzioni per l'altezza dei layer variabile sono accessibili facendo doppio clic sul nome di una parte nella finestra Plater. Questo farà comparire una finestra pop-up con due schede. La prima fornisce alcune informazioni sul modello, come mostrato in figura.

![Opzioni altezza layer variabile - Info.](images/variable_layer_height/variable_layer_height_options_tab_1.png "fig:")

È utile notare l'altezza del modello, poiché sarà importante per calcolare l'altezza Z massima.

La seconda scheda presenta una tabella in cui ogni riga definisce un'altezza di layer per un determinato intervallo lungo l'asse Z, espresso in millimetri. In questo esempio, le pareti del modello sono stampate a 0.4mm, le parti più ripide del tetto a 0.2mm e le meno ripide a 0.15mm. Nota che ogni intervallo si divide esattamente per l'altezza di layer indicata, evitando "gap" tra le sezioni.

![Opzioni altezza layer variabile - Layer.](images/variable_layer_height/variable_layer_height_options_tab_2.png "fig:")

Il G-Code risultante mostra una definizione più alta, che dovrebbe portare a una stampa di qualità superiore.

![Esempio con altezza layer variabile.](images/variable_layer_height/example_gcode_variable_layer_heights.png "fig:")

La figura seguente mostra il modello stampato. La stampa a sinistra ha un'altezza layer costante di 0.4mm, mentre quella a destra utilizza un'altezza layer variabile.

![Esempio di stampa con altezza layer variabile.](images/variable_layer_height/example_print.jpg "fig:")

Una caratteristica aggiuntiva dell'opzione di altezza layer variabile è che, inserendo uno zero per un intervallo, quella parte del modello non verrà stampata. La figura seguente mostra il G-Code dove i layer tra 0 e 4mm sono saltati. Questo è un modo utile per dividere un modello alto in più sezioni più corte, che possono essere stampate singolarmente e assemblate successivamente.

![Esempio con layer saltati.](images/variable_layer_height/example_gcode_skipped_layers.png "fig:")
