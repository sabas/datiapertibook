Distribuzione e pacchettizzazione dei dati
==========================================

Seguendo l’evoluzione della produzione del software, abbiamo visto come il concetto di apertura del codice sorgente si sia trasferito nell’ambito della produzione della conoscenza, portando ad avere una sempre maggiore disponibilità di informazioni aperte.

Viene naturale domandarsi come organizzare questa conoscenza per permettere e favorire attività come il riuso, la rielaborazione e la diffusione. Una soluzione può essere trovata nuovamente nell’ambito informatico ed in particolare in come viene prodotto e distribuito il software: nel corso degli anni si è posto l’accento sulla suddivisione dei progetti in componenti riutilizzabili (librerie, codice condiviso) e questo si riflette nella modalità di distribuzione a pacchetti che si vede nelle distribuzioni GNU/Linux come Debian e derivate. Tipicamente installando un software si installa il suo pacchetto; è necessario soddisfare le dipendenze di questo, ovvero scaricare altri pacchetti che contengono codice necessario al funzionamento, ed ogni pacchetto ha una sua versione specifica ed informazioni sulla licenza sotto la quale deve venir utilizzato.

La “pacchettizzazione”[^1] si realizza fornendo un accesso standardizzato e stabile ai dati grezzi tramite interfacce, apportando cambiamenti a queste ultime solo con cambi di versione: facendo questo, ed organizzando questi pacchetti in modo da facilitarne la scoperta e la combinazione, si aiuta lo sviluppo e la crescita della produzione di dati aperti.

I DMS e CKAN
------------

CKAN[^2], sviluppato in seno alla OKFN, viene rilasciato per la prima volta nel Maggio 2006, acquistando progressivamente un ruolo di primo piano nel mercato dei DMS (*Data Management System*, o Data Hub)[^3]. Nel Febbraio 2014 è stata rilasciata la versione 2.2.

Ereditando il nome per analogia dai CMS (*Content Management System*), un DMS deve stimolare la creazione di community intorno ai dati, e facilitare l’aggregazione di questi, permettendo:

-   caricamento ed aggiornamento (ETL, Extract, Transform and Load);

-   archiviazione ed indicizzazione;

-   visualizzazione, analisi ed aggiornamento di dati tabulari;

-   visualizzazione dei dati su grafici o mappe;

-   analisi statistica e machine learning;

-   crowdsourcing;

-   misurazione della qualità e tracciatura della provenienza;

-   attribuzione di un sistema di permessi;

-   ricerca;

-   vendita.

L’istanza principale è situata all’indirizzo <http://datahub.io/> ed esiste una versione italiana all’indirizzo <http://it.ckan.net/>.

CKAN è scritto in Python, si appoggia ad un database PostgreSQL, ad un webserver Apache2 ed usa estensioni in Java per operazioni come la ricerca e indicizzazione (Solr); è possibile scrivere plugin per aggiungere funzionalità.

Dalla versione 1.7 ha il supporto integrato all’RDF: basta richiedere uno specifico formato specificandolo nell’header della richiesta[^4] (come mostrato nel listato sottostante)

```bash
curl -L -H "Accept: application/rdf+xml" http://thedatahub.org/dataset/gold-prices
curl -L http://thedatahub.org/dataset/gold-prices.rdf
```

I file contenenti i dati possono essere caricati in un Filestore (interno a CKAN o nel cloud) al momento della creazione del dataset, ed ad essi sono associati metadati accessibili via API[^5].

Complementare al filestore è il Datastore[^6]: invece di salvare il file intero, esso viene importato in una specie di database dal quale vengono resi accessibili i singoli elementi del file (ad esempio un file CSV nel Filestore viene reso disponibile per il download, mentre nel Datastore possono venir richieste singole righe). Un processo contenuto in una estensione, il Datastorer[^7], permette di aggiungere in fase di caricamento file linkati o caricati sul Filestore.

Altre estensioni permettono di fare l’*harvesting*[^8], ovvero di importare dati da altre sorgenti basate su CKAN, leggendo ad esempio i metadati INSPIRE quando si tratta di dati geospaziali[^9].

Ogni parte del sistema è accessibile tramite una API RESTful (previa autorizzazione) che risponde in JSON; ogni utente ha una propria chiave API con la quale si effettua l’autenticazione.

### Valutazione dei dataset

La piattaforma attribuisce[^10] automaticamente una valutazione al dato secondo lo schema a cinque stelle. Non viene attribuita alcuna stella se la risorsa non è accessibile (la richiesta fallisce), mentre viene attribuita la valutazione secondo il MIME type della risorsa prima tentando di indovinarlo dall’estensione del file, altrimenti leggendo o il content-type dall’head della richiesta HTTP oppure il campo *format* dell’oggetto.

Si attribuisce (e si aggiorna al cambiamento):

-   una stella ai formati testuali (MIME: `text/plain`, `text`, `txt`)

-   due stelle ai formati tabulari propretari di Office (MIME: `xls`, `application/vnd.ms-excel` ed altri)

-   tre stelle a formati open e machine-readable (MIME: `text/csv`, `text/xml`, `xml`, `csv`, `application/json`, `json`)

-   quattro stelle ai formati con MIME `rdf` o `application/rdf+xml`

DataProtocols
-------------

I servizi basati sui dati a volte non riescono a comunicare fra loro perché mancano degli standard che descrivano l’interazione fra cataloghi di dati e la struttura dei dati pubblicati. Una iniziativa che prende le mosse da membri della OKFN, di ScraperWiki e di altri progetti legati al mondo dell’open data, chiamata DataProtocols[^11], mira a specificare alcune proposte che possano migliorare la vita della comunità, non come standard in senso stretto, ma come best practice che si suggerisce di seguire quando si producono dataset.

### (Tabular) Data Package

Un Data Package[^12] è costituito da un descrittore in formato JSON (che deve esser chiamato `datapackage.json`) nella directory radice e da zero o più file contenenti dati che possono essere resi disponibili nella directory radice, in sottodirectory oppure come servizio remoto (URL); I dati possono essere anche inseriti inline all’interno del descrittore.

Il descrittore ha una serie di campi obbligatori e/o suggeriti:

-   `name` [obbligatorio]: il nome del pacchetto dovrebbe essere stabile ed essere usabile negli URL (solo caratteri alfanumerici più punto, trattino e underscore);

-   `resources` [suggerito]: un array di oggetti che descrivono le risorse;

-   `license` [suggerito]: identificatore della licenza secondo la specifica dell’Open Definition[^13], nel caso ci siano più licenze diventa

-   `licenses`: array di oggetti ciascuno contenente in `type` l’identificatore ed in `url` il link al testo della licenza;

-   `datapackage_version` [suggerito]: la versione della specifica Data Package usata secondo lo standard del Semantic Versioning[^14];

-   altri dati raccomandati includono il titolo (`title`), la descrizione (`description`), il versionamento del pacchetto (`version`);

-   dati opzionali includono i manutentori (`mantainers`), i contributori (`contributors`) e le dipendenze rispetto altri pacchetti (`dataDependencies`).

Per quanto riguarda le risorse nel descrittore:

-   Deve essere presente uno o più fra `url` (link a risorsa), `path` (link relativo a risorsa nel pacchetto), `data` (contenente i dati inline).

-   Ci sono campi opzionali come il formato della risorsa (`format`), la codifica (`encoding`, di default utf-8) e nel caso di dati tabulari, lo schema (conforme alla specifica JSON Table Schema[^15]).

-   Per i dati inline, se il formato non è esplicitato, il campo `data` viene inteso come JSON, per usare altri tipi di dato, il requisito è che sia presente il campo `format` o `mediatype` e che il campo `data` sia una stringa.

Per la specifica Tabular Data Package[^16] si pongono una serie di restrizioni alla specifica del data package:

-   deve possedere il descrittore;

-   ogni risorsa deve essere descritta e contenere lo schema;

-   ci deve essere almeno un file di dati e tutti devono essere in CSV;

-   nel caso si vogliano usare CSV non in formato standard, bisogna includere il campo `dialect`, composto secondo il CSV Dialect Description Format[^17].

### Linear TSV[^18]

Candidato a sostituire i CSV, criticati come ambigui, propone un formato lineare simile al formato di serializzazione nativo dei database:

-   i record sono separati dal simbolo di nuova linea (`0x0a`);

-   i campi dei record da un tab (`0x09`);

-   il carriage-return (`0x0d`) è utilizzabile ma sconsigliato;

-   se bisogna inserire i simboli riservati, bisogna usare sequenze di escape (`\n`, `\t`, `\r`, `\\`);

-   se un campo non ha valore, va inserita la sequenza `\N` (con la N maiuscola, corrisponde al `NULL` dei database; bytes `0x5c` e `0x4e`);

-   la riga di intestazione è lasciata fuori, va implementata con le altre specifiche come la Data Package.
****

[^1]: <http://events.ccc.de/congress/2009/Fahrplan/events/3647.en.html>

[^2]: <http://ckan.org/>

[^3]: <http://blog.scraperwiki.com/2012/03/09/from-cms-to-dms-c-is-for-content-d-is-for-data/>

[^4]: <http://docs.ckan.org/en/latest/linked-data-and-rdf.html>

[^5]: <http://docs.ckan.org/en/latest/filestore.html>

[^6]: <http://docs.ckan.org/en/latest/datastore.html>

[^7]: <https://github.com/okfn/ckanext-datastorer>

[^8]: <http://docs.ckan.org/en/latest/harvesting.html>

[^9]: <https://github.com/okfn/ckanext-spatial>

[^10]: <https://github.com/okfn/ckan/wiki/Data-quality>

[^11]: <http://dataprotocols.org/>

[^12]: <http://dataprotocols.org/data-packages/>

[^13]: <http://licenses.opendefinition.org/>

[^14]: <http://semver.org/>

[^15]: <http://dataprotocols.org/json-table-schema/>

[^16]: <http://dataprotocols.org/tabular-data-package/>

[^17]: <http://dataprotocols.org/csv-dialect/>

[^18]: <http://dataprotocols.org/linear-tsv/>
