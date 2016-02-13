# Open data contro le mafie. La mappa interattiva di Confiscati Bene #
(pubblicato su [Startup Calabria](http://www.startupcalabria.com/open-data-contro-le-mafie-quattro-chiacchere-con-confiscati-bene/#more-4075) il *20 Giugno 2015*)

Siamo arrivati all'ultimo appuntamento della rubrica #dataculture prima delle vacanze estive e, come consuetudine, abbiamo deciso di raccontarvi una storia. Parlo al plurale in quanto l'intervista che leggerete è stata scritta a quattro mani, le mie e quelle di [Grazia Pugliese](https://it.linkedin.com/in/graziapugliese), a coronamento della collaborazione iniziata a settembre 2014.
Abbiamo dedicato l'ultimo articolo dell'anno scorso a una storia che arrivava da lontano, da oltreoceano: [come cercare casa sfruttando gli open data](http://www.startupcalabria.com/cercare-casa-con-gli-open-data/). Oggi, invece, torniamo in Italia per parlarvi di un progetto dall'alto valore umano oltre che scientifico: [Confiscati Bene](http://www.confiscatibene.it/it).

*Confiscati Bene è un progetto partecipativo per favorire la trasparenza, il riuso e la valorizzazione dei beni confiscati alle mafie, attraverso la raccolta, l’analisi dei dati e il monitoraggio dei beni stessi.*

Tra i fautori del progetto ci sono tante persone note tra gli attivisti delle varie community che si occupano di open data come [Andrea Nelson Mauro](https://twitter.com/nelsonmau), [Chiara Ciociola](https://twitter.com/chiaracio), [Andrea Borruso](https://twitter.com/aborruso), [Alessio Cimarelli](https://twitter.com/jenkin27) e tanti altri che vi invito a scoprire nella sezione [about di Confiscati Bene](http://www.confiscatibene.it/it/chi-siamo).
L'idea, come ci racconterà Andrea Borruso, con il quale abbiamo fatto una chiacchierata, nasce durante il raduno 2014 di [SOD](http://www.spaghettiopendata.org/) (di cui anche io sono utente, non proprio attivissimo, diciamo in sola lettura). Quest'anno, durante SOD2015, si sono quindi tirate le somme di un progetto che ha avuto un forte riscontro su tutto il territorio nazionale con articoli su testate di quasi tutte le regioni ([qui trovate tutti gli articoli](http://www.confiscatibene.it/it/blog/confiscati-bene-su-19-giornali-del-gruppo-lespresso-inchiesta-di-data-journalism-di-dataninja#.VrNeCkI2fNO)).
Purtroppo, nessuna testata giornalistica calabrese dimostrò interesse a scrivere del progetto e a pubblicare la mappa dei beni confiscati alle mafie in Calabria. Perchè, allora, non diffonderla attraverso il blog di Startup Calabria inserendola nella rubrica #dataculture?
Detto, fatto. C'è voluto solo un tweet per contattare i ragazzi di Confiscati Bene, che sono stati disponibilissimi e felici di raccontare la loro storia.

**Ciao Andrea [Borruso]! È un piacere averti come ospite della nostra rubrica #dataculture. Per chi ancora non ti conoscesse, puoi spiegarci di cosa ti occupi e di come nasce la tua passione per gli open data?**

Sono un geomatico, mi occupo di rilevamento e trattamento informatico dei dati relativi alla Terra e all’ambiente; inoltre, ho una società che costruisce sensori per droni (Panoptes srl).
Per lavoro, ho spesso dovuto cercare dati, mi servivano per le mie analisi. Quando ho scoperto i dati aperti, ho pensato che avrei potuto usare il “mestiere” anche a scopi civici.

**Oggi ci soffermeremo su un progetto di grande successo: ‘Confiscati bene’. In cosa consiste in dettaglio?**

L’obiettivo, alla nascita del progetto, era quello di rendere aperti e riutilizzabili i dati sui beni sequestrati e confiscati alle mafie che pubblicava l’ *”Agenzia nazionale per l'amministrazione e la destinazione dei beni sequestrati e confiscati alla criminalità organizzata”* ([ANBSC](http://www.benisequestraticonfiscati.it/Joomla/)). Si trattava di migliaia di record, di dati sparsi in centinaia di pagine web; ne abbiamo fatto un’estrazione automatica, li abbiamo “puliti” e li abbiamo arricchiti in modo che potessero essere incrociati con altri dati.
Poi abbiamo pensato di raccogliere altri dati a tema pubblicati da altri attori (le PA, le associazioni, ecc.) e abbiamo messo in piedi un vero e proprio catalogo di dati basato su DKAN, lo stesso motore su cui è basata l’ultima versione del portale nazionale sui dati aperti.  

**Tre domande tecniche:**

   **Da Leaflet a TimeMapper c'è l’utilizzo di tanto software open source e collaborativo. Quanto influisce per la riuscita del progetto questa scelta?**

Nel gruppo “tecnico” di Confiscati Bene c’è gente che lavora soprattutto con software open source. Credo che abbia influito soprattutto il fatto che sia software che funziona. Poi c’è anche una questione di “tifo”, ma poi la partita finisce, e la macchina deve continuare a correre.

   **Sul sito c'è una bella e ricca scheda tecnica su DKAN e una spiegazione sull’utilizzo delle API per scaricare i dati. Ci daresti una piccola nota metodologica del processo a cui vengono sottoposti i dati prima di essere caricati sulle mappe?**

I processi di lavorazione dei dati non è complesso: da un lato occorre normalizzarli e pulirli (in questo caso è stato fatto con OpenRefine), anche per sistemare aspetti che possono sembrare secondari ma invece sono cruciali. Ad esempio, i nomi dei luoghi sono scritti tutti in minuscolo o in maiuscolo? Infatti, occorre che siano scritti alla stessa maniera, che siano uniformi. Importante è verificare anche le celle vuote e capire perché ci sono. Occorre costruire poi i metadati per spiegare per ogni colonna qual è il tipo di dato e che informazione contiene. 

   **Come sono stati scelti i software e i temi di layer e icone utilizzate?**

Per la prima versione scegliemmo qualcosa che consentisse presto, durante l’hackathon in cui è nata, di avere un’interfaccia in grado di visualizzare i dati e poter applicare dei filtri di visualizzazione in tempo reale. Simile Exhibit – e quindi soltanto HTML, Javascript e CSS – ci sembrò la scelta giusta.
Per l’attuale versione alcune scelte derivano in modo diretto dall’applicazione di catalogo dati selezionata, che nativamente è basata su PHP e MySQL; ma DKAN può girare anche su altri database server relazionali.
Altre scelte, come quella di usare il rendering cartografico di GeoIQ, nascono per conciliare scelte di rappresentazione e necessità “ecologiche”. Volevamo, infatti, un layer cartografico di base che fosse poco visibile rispetto ai layer sui beni confiscati, ma che contenesse le informazioni di base per leggere bene il territorio. E, inoltre, non volevamo dedicare tempo alla generazione di qualcosa che è già esistente e disponibile su server che non sono andati in affanno nemmeno in momenti di particolare attenzione sul progetto (ad esempio per la pubblicazione dell’indagine del gruppo L’Espresso).

**L’idea è nata durante un raduno della community [Spaghetti open data](http://www.spaghettiopendata.org/) nel 2014. Da chi è formata la community e cosa fate nello specifico?**

Idee ne abbiamo tutti ogni giorno, ma il punto fondamentale è mettersi in gioco e provare a svilupparle. Cercare di capire quale possa essere la strada migliore per far crescere un progetto, al di là delle aspirazioni e ambizioni personali. È nata lì, ma sarebbe potuta nascere in altri contesti: il valore aggiunto è che abbiamo cercato di dare solidità, costruendo un sito e mantenendo una policy inclusiva e di apertura. Perciò la risposta è: la community è formata da tutti, anche da te. Anzi, perché non dai una mano sulla Calabria? Ti va di provare?

**Come mai avete scelto di occuparvi di dati così ‘delicati’?**

Il caso, gli incontri, i luoghi e l’obiettivo. 
Io ho iniziato a occuparmi della cosa grazie a un monitoraggio civico su dei beni confiscati alla Camorra fatto per il progetto OpenPompei. In quell’occasione lavoro con i ragazzi di Monithon, e inizio a imparare qualcosa sul tema dei beni confiscati. 
Le persone incontrate, i luoghi visitati, la maggiore comprensione del contesto, l’hackathon fatto a Bologna e forse il mio essere siciliano, mi hanno fatto appassionare alla cosa e comprendere quanto fosse importante e utile. E ad oggi posso dire che è stato così, per tutte le persone che a vario titolo si sono prese cura del progetto.

**Quanto è stato importante incontrare le persone giuste per avviare un progetto di una tale portata?**

In linea teorica è importante incontrare persone che siano disposte a dare un contributo per far crescere un progetto e che al contempo siano pronte a farsi da parte se il percorso di crescita lo richiede.
Ma Confiscati Bene non sarebbe stato quello che è – con i suoi pregi e i suoi difetti – se durante tutto il suo percorso non avesse “incontrato” tante persone dal grande valore umano e professionale. Sarà qualcosa che racconterò ai nipoti quando saranno più grandi, perché è stato (ed è) un vero privilegio.

**Da quando avete iniziato il progetto che rapporti avete avuto con chi pubblica, o dovrebbe pubblicare, i dati dei beni confiscati e con l'opinione pubblica?**

Ottimi, e li abbiamo costruiti nel tempo. L’Agenzia dei Beni Confiscati ha difficoltà a pubblicare i dati e ci ha chiesto suggerimenti e consigli. Abbiamo cercato di fare la nostra parte ma il contesto è popolato da soggetti che da tempo lavorano sull’argomento e hanno grande esperienza sul dominio. Siamo inclusivi ma cerchiamo anche di farci includere.

**Si può dire che ‘Confiscati bene’ sia un progetto nato dal basso, da comuni cittadini che hanno messo a disposizione le proprie competenze per il bene comune. Secondo te, quanto sono importanti iniziative del genere per colmare i frequenti e spesso penosi vuoti istituzionali?**

Si, e ci sono tanti altri casi così. Mi viene in mente ad esempio [“Cittadini Reattivi”](www.cittadinireattivi.it), un progetto nato per fare trasparenza sui dati relativi all’ambiente e che adesso si sta evolvendo. Non sono importanti le singole iniziative, quanto piuttosto il fatto che i cittadini in modo più o meno professionale cerchino di (pre)occuparsi della cosa pubblica, ognuno come può. Ci lamentiamo sempre dei «penosi vuoti istituzionali» ma quante volte nella quotidianità inciampiamo in «penosi vuoti umani» di gente che tratta la cosa pubblica come se fosse una cosa lontana, di altri, senza valore, una cosa che «chi se frega!»?

**A livello nazionale, esistono altri progetti simili al vostro ma con altre tipologie di dati?**

Sì, alcuni nati prima e alcuni nati dopo. Cittadini Reattivi è uno di questi. C’è poi [Monithon](http://www.monithon.it/), che stimola al monitoraggio sulla spesa dei fondi europei.

**Cosa potrebbe fare un semplice cittadino privo di competenze specifiche ma interessato a contribuire a una maggiore trasparenza dei dati pubblici?**

Partecipare, informarsi, lavorare in gruppo, costruire iniziative sulla trasparenza. Facciamo finta che il cittadino sia il lettore di questo articolo. Potrebbe dire: «Ciao, mi interessa la trasparenza, cosa posso fare?». Ecco, se vuoi, dagli la nostra email.

**Com’è la situazione in Italia in ambito open data e cosa si potrebbe fare per andare verso la giusta direzione?**

È a un punto di stanchezza. Siti e portali nuovi o rifatti non cambiano la sostanza: bisogna pubblicare i dati e pubblicare dati di qualità, evitare che gli Opendata siano solo keyword del marketing (cosa legittima, per carità) ma prima di fare marketing occorre pubblicare buoni dati. Poi puoi andare in giro a dirlo.
Ad esempio: perché i siti dei Comuni pubblicano spesso l’elenco dei parchi in città ma non i dati sulla raccolta differenziata? I primi, sui parchi, li conosciamo. Se conoscessimo i secondi, sulla differenziata, avremmo uno strumento per misurare l’efficienza del sistema, cercare di migliorarlo. Per capire come siamo messi in Italia, basta andare su [http://www.dati.gov.it/](http://www.dati.gov.it/) e cercare “raccolta differenziata”: il risultato è sconsolante.

**Sul portare c'è l'opzione "Partecipa", è possibile, e se sì in che modo, entrare a far parte del team?**

Fai qualcosa per il progetto ed entrerai a far parte del team: cerca nuovi dati, cerca storie di beni confiscati, fai richiesta di accesso ai dati sui beni nel tuo comune, fai crescere la conoscenza e l’attenzione sull’argomento. È questo il modo migliore! 

Ringraziamo ancora una volta **Andrea Borruso** e il resto del team per la loro disponibilità. Siamo, inoltre, orgogliosi di aver contribuito, nel nostro piccolo, a diffondere la mappa dei beni confiscati della nostra Regione. Speriamo di aver stimolato la voglia insita in tutti noi, a contribuire attivamente a rendere accessibili i dati pubblici. 
Se volete saperne di più sui beni confiscati alle mafie relativamente al vostro territorio potete visitare il portale www.confiscatibene.it per consultare la [mappa interattiva](http://viz.confiscatibene.it/cbit/?&ls[0]=regioni&ls[1]=province&ls[2]=comuni&ml=regioni&dl=comuni) e diventare cittadini attivi!
