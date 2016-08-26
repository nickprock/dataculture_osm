#uMap: crea e condividi le tue mappe open in 10 minuti#
##Mappe da CSV##
(pubblicato su [Startup Calabria](http://www.startupcalabria.com) il *31 ottobre 2015*)

**uMap** è un software open source con licenza [WTFPL](https://it.wikipedia.org/wiki/WTFPL) che consente di creare mappe che fanno uso dei layer di openstreetmap come sfondo.
La creazione e soprattutto la condivisione delle mappe è semplicissima, sul sito garantiscono "in un minuto" anche per chi non è avvezzo ai sistemi **GIS** o alla programmazione in generale.
Una volta effettuata la registrazione/accesso sul portale ci si presenta questa schermata.

![umap01](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap01.png)

Se scrolliamo in basso possiamo vedere le mappe nel mondo e le ultime generate, così possiamo prendere spunto. Noi però andiamo su 'crea mappa' e vediamo come è fatta la schermata di creazione.

![umap02](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap02.png)

Approfondiamo il menù delle impostazioni (il più importante) e troviamo:

![umap03](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap03.png)

  - **Modifica Nome e Descrizione della mappa**.
  - **Opzioni interfaccia utente**. Io di solito lo lascio di default.
  - **Proprietà preimpostate**. Permette di impostare le proprietà dei PIN: il colore, la forma, l'icona. Per le icone ci sono già tanti simboli ma nulla ci vieta di caricarne di nuovi.
  - **Default popup options**. Permette di modificare lo stile dei popup e il contenuto che visualizzaremo all'interno; una volta modificato possiamo testarlo uscendo dalla modalità di modifica.
  - **Sfondo personalizzato**. Cambia il layer di sfondo della mappa.
  - **Slideshow**. Io di solito lo lascio di default.
  - **Ringraziamenti**. Per inserire i credits e la licenza. Ricordatevi di inserire la licenza [ODbl](https://it.wikipedia.org/wiki/Open_Database_License) che è quella dei dati di OpenStreetMap.

Visto questo, passiamo al menù di caricamento dati. Qui possiamo caricare diversi tipi di dataset. In questo articolo vedremo come lavorare con i dati che stanno in un .csv.

![umap04](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap04.png)

Qualche mese fa ho letto sul ["Corriere della Calabria"](http://www.corrieredellacalabria.it/) degli articoli molto interessanti sui beni archeologici agonizzanti della nostra Regione, così mi sono armato di pazienza e ho creato un file .csv per ogni luogo citato nell'articolo con i seguenti dati:

  - il nome;
  - il nome dell'attuale comune dove si trova il bene archeologico;
  - una breve descrizione;
  - la pagina Wikipedia (se esiste, o comunque una sorgente);
  - latitudine e longitudine.

Per prima cosa, non avendo la posizione precisissima del luogo e parlando di archeologia, ho optato per un layer che ricorda le vecchie mappe: il suo nome è **Watercolor** e lo trovate nel menù che si vede nella seconda figura.
Successivamente, ho caricato il file dall'apposito menù e scelto l'estensione (come potete vedere uMap ne supporta tante).
Dal menù Proprietà preimpostate scelgo il colore del PIN e l'icona. Ho scelto la classica icona per musei e beni culturali.

![umap05](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap05.png)

Nel menù per l'impostazione del popup scelgo la forma tabellare, così verranno visualizzate tutte le informazioni contenute nel .csv.
Alla fine, andiamo ad impostare licenza e credits. Come già detto, la licenza è ODbl, mentre nei credits ho incluso le informazioni riguardanti l'articolo da cui ho preso i dati.

![umap06](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap06.png)

Nell'immagine successiva si può vedere il risultato del nostro lavoro fatto in 10 minuti.

![umap07](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap07.png)

Andando su condividi abbiamo sia il [link della mappa](http://umap.openstreetmap.fr/en/map/beni-archeologici-agonizzanti_27736#9/38.8900/16.4053) che il codice per inserire l'iframe nei nostri siti e blog, oppure possiamo scaricare i dati della mappa in modo molto veloce.

##Mappe con Overpass-Turbo e uMap##
(pubblicato su [Startup Calabria](http://www.startupcalabria.com) il *28 Novembre 2015*)

Per creare questa tipologia di mappa utilizzeremo [Overpass-Turbo](http://overpass-turbo.eu/), un'interfaccia web per utilizzare ed esportare i risultati delle query overpass. Queste query (di sola lettura) sfruttano le API di OpenStreetMap selezionando parte del suo immenso database per restituirci dei risultati che possono essere esportati per creare altri progetti e servizi ([per saperne di più vi rimando alla pagina wiki](wiki.openstreetmap.org/wiki/Overpass_turbo)).

![umap08](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap08.png)

Per prima cosa dobbiamo sapere cosa vogliamo cercare (nel nostro caso utilizzerò un mio vecchio progetto) Andiamo su OpenStreetMap e inseriamo una keyword, ad esempio, se vogliamo creare una mappa di tutte le farmacie calabresi nel motore di ricerca inseriamo 'Farmacia'.

![umap09](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap09.png)

OpenStreetMap ci restituisce una serie di risultati, ne prendiamo uno a caso e controlliamo i tag.

![umap10](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap10.png)

Vediamo che il tag per le farmacie e parafarmacie è "amenity"="pharmacy", ma cosa distingue farmacie e parafarmacie? Un altro [tag, dispensing](http://wiki.openstreetmap.org/wiki/Tag:amenity%3Dpharmacy), questo indica se hanno farmaci con ricetta medica o no, quindi a noi servono quelle "dispensing"="yes".
Torniamo su Overpass e cerchiamo wizard sulla barra degli strumenti.

![umap11](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap11.png)

Il wizard è il modo più semplice di costruire query overpass, inseriamo ciò che ci serve, quindi: **"amenity"="pharmacy" and "dispensing"="yes" in Calabria** e Overpass-Turbo ci scriverà la query nel suo editor. Non ci resta che cliccare su **Esegui** e attendere i risultati.

![umap12](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap12.png)

![umap13](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap13.png)

Una volta ottenuti i risulati andiamo su **Esporta** e scegliamo **"dati grezzi direttamente da Overpass API"**. Si apre un'altra pagina con il file. A noi serve solo l'indirizzo di questa pagina, quindi, lo copiamo.
Apriamo uMap col nostro account e creiamo una nuova mappa.
Andiamo ad importare i dati incollando l'indirizzo del JSON di Overpass-Turbo in **"Aggiungi un URL qui"**, poi scegliamo tra i formati **osm**. Dovrebbero apparire tutti i pin sulla mappa.

![umap14](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap14.png)

Personalizzate il tutto (colori, icone, layer,…) come preferite.
Una volta finita la personalizzazione andate sul menù che vi indica i livelli, e click su **"Edit"** (la matita), si aprirà un nuovo menù sulla destra, da qui scegliete **"type of layer"** cluster per raggruppare i pin man mano che ci si allontana con lo zoom.

![umap15](https://github.com/nickprock/dataculture_osm/blob/master/img/uMap15.png)

Ora la nostra mappa è completa e possiamo condividerla.
