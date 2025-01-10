% Script di Post-Processing

Ci possono essere situazioni in cui il G-Code generato da Slic3r deve essere modificato
o ritoccato dopo la sua creazione. Per questa ragione, esiste la possibilità di eseguire
script arbitrari come parte delle fasi finali del processo di slicing.

Esempi di script possono essere trovati nel [repository GitHub](https://github.com/alexrj/Slic3r/tree/master/utils/post-processing)
o nel [forum RepRap](http://forums.reprap.org/list.php?263).

**Nota:** gli script di post-processing possono essere scritti in **qualsiasi linguaggio**
(Perl, Python, Ruby, Bash, ecc.). Devono essere semplicemente eseguibili e accettare
il percorso del file G-code come unico argomento.

Nella sezione `Opzioni di Output` della scheda `Impostazioni di Stampa` si trova
l'opzione `Script di Post-Processing`. È possibile aggiungere il percorso assoluto
di ogni script, separati da punti e virgola. Ogni script deve essere riconosciuto
dal sistema host ed essere eseguibile.

![Opzione script di post-processing.](images/post_processing_scripts/post_processing_scripts_options.png "fig:")

Ogni script riceverà come argomento il percorso assoluto del file G-code generato
da Slic3r. Lo script dovrà modificarlo direttamente; in alternativa, può
produrre il nuovo G-code in un file temporaneo e poi sovrascrivere quello originale.

Tutte le opzioni di configurazione di Slic3r sono messe a disposizione
degli script attraverso variabili d'ambiente. Queste iniziano tutte con
`SLIC3R_`, ad esempio `SLIC3R_LAYER_HEIGHT`. Il seguente script non modificherà
il G-code e scriverà semplicemente tutte le opzioni di Slic3r nell'output standard:

```
#!/bin/sh
echo "Post-processing G-code file: $*"
env | grep ^SLIC3R
```

Per motivi di sicurezza, non è possibile fornire argomenti agli script. Tuttavia,
è possibile scrivere uno script wrapper.

### Esempio in Perl

La modalità in-place di Perl (`perl -i`) rende facile modificare il contenuto del
file G-code, senza doverlo copiare, modificare e poi sostituire l'originale. Il
seguente esempio semplicemente stamperà il contenuto sull'output standard:

```
#!/usr/bin/perl -i
use strict;
use warnings;

while (<>) {
     # modifica $_ qui prima di stamparlo
     print;
}
```

Se si verifica un errore *can't do inplace edit without backup* durante la specifica
dello script di post-processing, prova ad aggiungere `$^I = '.bak';` prima del ciclo `while`. 
Questo creerà un file di backup del file G-code generato. Windows non consente che due script
creino e/o accedano a un unico file contemporaneamente, quindi è necessario un backup.
