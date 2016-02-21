# Crea e condividi le tue mappe con TileMill #
(Pubblicato su [Startup Calabria](http://www.startupcalabria.com/crea-e-condividi-le-tue-mappe-con-tilemill/) il *20 Dicembre 2014*)

Ultimo appuntamento del 2014 con #DataCulture! Nella prima edizione abbiamo parlato di [come si diventa un OpenstreetMapper](http://www.startupcalabria.com/4-passi-per-diventare-un-openstreetmapper/), [la scorsa puntata era dedicata ad Osmose](http://www.startupcalabria.com/mappe-di-qualita-con-osmose/) un tool per correggere le mappe, oggi finalmente si parlerà di come riutilizzare i dati e costruire le nostre mappe.

Oggi creeremo una **mappa interattiva dei dati ISTAT sulla produzione di rifiuti e il riciclaggio nelle città copoluogo di provincia**.

Il tool che useremo oggi è [TileMill](https://www.mapbox.com/tilemill/), un'**applicazione open source** rilasciata da [Mapbox](https://www.mapbox.com/), una delle società che fanno business sui dati OSM e principale concorrente di Google.

Mapbox è un servizio freemium che permette di personalizzare le mappe che poi andranno sui nostri portali o verranno condivise sui social network, [con dei piani basati su memoria utlizzata e view](https://www.mapbox.com/pricing/). Per prima cosa, per rendere più semplice il tutorial, ho aperto un account free sul sito così da poter condividere nel modo più semplice possibile la mappa creata.

Una volta entrati nell'account vediamo che c'è un editor on-line per i progetti che non è ciò che useremo oggi. Passiamo, quindi, al core dell'articolo e scarichiamo **TileMill** (oggi si lavora off-line!), è **free platform** quindi scaricate la versione che vi serve (io lavoro su Ubuntu 32-bit) e seguite il [wiki di installazione](https://www.mapbox.com/tilemill/docs/linux-install/), è tutto molto semplice.

Installato, apriamo e ci appare la schermata con i progetti, ne esistono alcuni di default, come potete vedere nella mia c'è un *"Primo Test"* che si riferisce a un [tutorial ufficiale](https://www.mapbox.com/tilemill/docs/crashcourse/point-data/), e quello di questo tutorial.

![tilemill1](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-1.png)

Click su *"New Project"* e partiamo compilando la form di creazione. Per ora lasciate la spunta su *"Default data"*, così da avere la base di Mapbox, e poi *"Add"*.
Nell'immagine seguente potete vedere come si presenta l'editor, con le varie aree e menù che ho indicato in rosso.

![tilemill2](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-2.png)

Per prima cosa dovremmo caricare i layer geografici, in formato shapefile, ma come ottenerli?

Ci sono molti modi e servizi per farlo, nel nostro caso vogliamo una mappa con i capoluoghi di provincia, quindi andiamo sulla pagina dei [geodati ISTAT](http://www.istat.it/it/archivio/104317) e scarichiamo i confini delle provincie italiane, poi dal menù dei Layers, *"Add Layers"*.
Come vediamo dalla finestra ci sono diversi modi per caricarli, noi usiamo un file, ma si possono usare anche i database, infatti è proprio questa la potenza di TileMill rispetto all'editor on-line, andiamo su *"Browse"*.

![tilemill3](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-3.png)

Vediamo che si possono caricare anche degli shapefile default di Mapbox, alcuni sono molto precisi a livello mondiale, soprattutto per quanto riguarda la geografia, ma quando andiamo più nel particolare l'Europa non è ben rappresentata, comunque non è ciò che ci serve oggi, quindi andiamo nella cartella con i nostri limiti provinciali e carichiamo, poi *"Save & Style"*, infine zoom sull'Italia.

![tilemill5](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-5.png)

A me sinceramente in verdino di default non piace proprio per niente, inoltre non è funzionale al progetto finale, così dall'area del codice possiamo andare a modificare il colore delle aree e delle linee del nostro livello, ricordiamoci di salvare alla fine di ogni operazione per vedere le modifiche apportate. (Per rendere più chiara l'operazione lascerò sempre il default commentato in questo tutorial).

![tilemill6](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-6.png)

Fatto ciò ci servono le coordinate dei capoluoghi di provincia, questi li ho prelevati da [GFOSS](http://geodati.gfoss.it/wiki/index.php/Categoria:Capoluoghi_di_provincia), da [I.Stat il datawarehouse dell'ISTAT](http://dati.istat.it/) ho prelevato i dati con i Kg di rifiuti prodotti pro-capite nei capoluoghi e la percentuale di riciclaggio, avendo tutti questi dati ho creato un .csv, ora possiamo caricarlo come layer con lo stesso procedimento precedente, il risultato lo vedete di seguito.

![tilemill7](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-7.png)

Ora che abbiamo tutti i dati che ci occorrono dobbiamo lavorare un pò sulla mappa per personalizzarla come più ci piace/serve, per il nostro progetto.

L'idea è di avere una dimensione del pallino che indica la città più grande/piccolo a seconda della quantità di rifiuti pro-capite prodotta, e un semaforo rosso, giallo, verde, secondo la percentuale di riciclaggio (I dati per Cosenza sono assenti quindi la colorerò in bianco).

Per modificare il colore dobbiamo agire su **marker-fill** e **marker-line-color**, mentre per le dimensioni su **marker-width** come vedremo nell'immagine successiva.

![tilemill8](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-8.png)

Fatto questo io voglio personalizzare ancora la mappa, non mi interessa vedere il puntino, ma voglio il nome del capoluogo. Quindi diciamo a TileMill dove sta il testo che che cerchiamo con **text-name: [Capoluogo];** e il font da utilizzare **text-face-name: 'Ubuntu Regular';** infine sostituiamo **marker-fill** e **marker-width** con **text-fill** e **text-size**, possiamo cancellare tranquillamente le righe riguardanti **marker-line-color**, salviamo e godiamoci il risultato.

![tilemill9](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-9.png)

Ora nonostante i suoi difetti è molto più leggibile, ma non ancora completa, andiamo nel menù dell'interattività (quello con la manina), troviamo quattro menù, noi ci concentreremo su *"Legend"* per inserire una legenda alla mappa, e *"Teaser"* per renderla interattiva.
Per la legenda gran parte del [codice è standard quindi possiamo tranquillamente copiarlo e incollarlo dal tutorial ufficiale di TileMill](https://www.mapbox.com/tilemill/docs/guides/advanced-legends/), io ho scelto una legenda con gradazione di colori orizzontale, l'unica particolarità è l'inserimento del logo di [Startup Calabria](http://www.startupcalabria.com/) in alto e i link in basso, allego comunque il codice da copiare e incollare nel box.
```
 <div style="text-align:center;">
<div class='my-legend'>
<img src="http://www.startupcalabria.com/wp-content/uploads/2013/10/sclogo.png">
<div style="text-align:left;">
<div style="font:bold 10pt Ubuntu Regular;">Kg di rifiuti pro-capite nei capoluoghi di provincia nel 2012.</div>
<div style="font:italic 8pt Ubuntu Regular;">La circonferenza indica la quantità, il colore la percentuale di riciclaggio.</div>
<div class='legend-scale'>
  <ul class='legend-labels'>
    <li><span style='background:#FF0000;'></span>0 – 33%</li>
    <li><span style='background:#FFFF00;'></span>33 – 66%</li>
    <li><span style='background:#1F3;'></span>+ 66%</li>
  </ul>
</div>
<div class='legend-source'>Dati: <a href="http://dati.istat.it/">ISTAT</a>
Geodati: <a href="http://www.istat.it/it/strumenti/cartografia">ISTAT</a> e <a href="http://geodati.gfoss.it/wiki/index.php/Pagina_principale">GFOSS</a> </div>
</div>

<style type='text/css'>
  .my-legend .legend-title {
    text-align: center;
    margin-bottom: 8px;
    font-weight: bold;
    font-size: 90%;
    }
  .my-legend .legend-scale ul {
    margin: 0;
    padding: 0;
    float: center;
    list-style: none;
    }
  .my-legend .legend-scale ul li {
    display: block;
    float: left;
    width: 50px;
    margin-bottom: 6px;
    text-align: center;
    font-size: 80%;
    list-style: none;
    }
  .my-legend ul.legend-labels li span {
    display: block;
    float: center;
    height: 15px;
    width: 50px;
    }
  .my-legend .legend-source {
    font-size: 70%;
    color: #999;
    clear: both;
    }
  .my-legend a {
    color: #777;
    }
</style> 
```

![tilemill10](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-10.png)

Passiamo ora al menù **"Teaser"**, per prima cosa dal menù a tendina in basso bisogna scegliere su qual layer lavorare, noi lavoriamo su *capprov* dove abbiamo i dati ISTAT, se vedete in basso ci indica le colonne presenti nel file .csv, noi ora nel box scriveremo quello che vogliamo vedere nel popup interattivo che comparirà in alto a destra sulla mappa quando passeremo col mouse sul nome delle città, il codice è il seguente:
```
{{{Capoluogo}}} : {{{Rifiuti}}} Kg di rifiuti pro-capite, di cui viene differenziato il {{{PercDiff}}}% 
```
e il risultato nell'immagine successiva.
 
![tilemill11](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-11.png)

Ora abbiamo finito con l'editor, ma la mappa va pubblicata, quindi andiamo su export, e scegliamo il formato MBTiles (si può anche fare upload direttamente ma io preferisco così per avere il file anche in locale). TileMill ha creato una cartella dove mette i file, su Ubuntu è in */home/user/Documents/MapBox/export*.

Prima di esportare selezioniamo i criteri della mappa: lo zoom, la centralità… come indicato dal menù sulla destra.

![tilemill12](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-12.png)

Torniamo sul nostro account Mapbox che abbiamo creato all'inizio del tutorial, e andiamo sul menù Data per caricare il file, durante il caricamento Mapbox ci dice quanti MB abbiamo ancora a disposizione dei 100MB free del nostro account, questa mappa pesa circa 1.5MB.

![tilemill13](https://github.com/nickprock/dataculture_osm/blob/master/img/TileMill-13.png)

Click sul nome del file e si apre un menù. In caso volessimo aggiornare la mappa possiamo farla da TileMill e poi ricaricarla usando **"Update"**, inoltre possiamo scegliere se avere una preview o usarlo come layer per un progetto. Scegliamo quest'ultima opzione e si apre la mappa, come in TileMill scegliamo le opzioni *"Nome"* e *"Descrizione"* dal menù **"Settings"** e da **"Advanced"** spuntiamo **"Save Positions"** e scegliamo il livello di zoom prima di salvare.

Ora abbiamo il nostro progetto; non ci resta che fare click su **"Share"** e abbiamo tutte le opzioni di condivisione sui social e il codice per embeddare la mappa sul vostro sito.
