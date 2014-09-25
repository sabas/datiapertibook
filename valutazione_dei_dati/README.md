Valutazione dei dati
====================

Il problema della scala di Tim Berners-Lee, diffusamente usata per vedere “ad occhio” se un dato è buono, è l’essere legata all’ambito nel quale è stata inizialmente proposta, i Linked Data.

Attribuendo i valori più alti a dati che vengono esposti come LOD (RDF, come endpoint SPARQL, eccetera), si sottovalutano insiemi di dati che non ricavano beneficio dall’essere completamente nella nuvola dei dati collegati e non si misura come i dati vengano utilizzati.

Si espongono di seguito approcci alternativi alla valutazione dei dati e si conclude con delle idee di sintesi.

Open Data Engagement: la scala di Davies
----------------------------------------

Nel 2012 ad un workshop sugli Open Government Data (OGD) - i dati aperti prodotti dagli enti pubblici- Tim Davies propone una scala del “coinvolgimento sui dati aperti” (*open data engagement*[^1]) per trovare un parallelo non tecnico alla scala di Berners-Lee.

La premessa considera le informazioni governative come patrimonio pubblico gestito dal governo che fornisce una piattaforma di trasparenza e coinvolgimento del cittadino nelle scelte della cosa pubblica ed asserisce che il governo dovrebbe essere parte attiva nell’assicurarsi che i dati possano essere usati da tutti.

Il coinvolgimento di un ente pubblico nel mettere a disposizione i dati aperti dovrebbe:

##### Esser guidato dalla domanda

La scelta di cosa pubblicare dovrebbe essere legato alla domanda di dati, e bisognerebbe ascoltare in qualche modo le richieste dei cittadini, rispondendo ad esse con dati aperti.

##### Contestualizzare i dati

I metadati associati dovrebbero includere frequenza di aggiornamento, formato e qualità dei dati. Dovrebbe essere fornite spiegazioni su come i dati siano stati creati, un manuale d’uso e link a riutilizzi già esistenti.

##### Supportare la conversazione intorno ai dati

Dovrebbe esser fornita la possibilità di commentare o discutere i dati (sia online che offline), intervenendo nelle discussioni stesse. Il creatore del dato dovrebbe esser facilmente contattabile.

##### Costruire capacità, competenze e reti

Bisogna fornire collegamenti a strumenti per lavorare con i dati, ed informazioni su come usare questi strumenti; bisogna organizzare eventi di formazione su come usare i dati forniti in determinati modi.

##### Collaborare sui dati come risorsa condivisa

Ci devono essere cicli di feedback (le correzioni vanno ascoltate), bisogna collaborare con la comunità sui dataset derivati, fornendo aiuto sulla costruzione di servizi basati sui dati. Bisogna lavorare con altre organizzazioni per connettere le proprie informazioni.

Il coinvolgimento ed il dialogo con la comunità sono elementi importanti per evitare l’effetto “wasted data”[^2]: se non vengono curati dalla comunità, prima o poi finiranno nell’orbita dei big data commerciali, perdendo il potere potenziale di monitoraggio e trasparenza.

Certificati ODI
---------------

L’Open Data Institute[^3] è una società fondata nel 2012 a Londra da Tim Berners-Lee e Nigel Shadbolt come no profit (finanziata principalmente dal governo inglese) per promuovere la cultura dei dati aperti e la creazione da essi di “valore economico, ambientale e sociale” tramite ricerca, comunicazione ed assistenza a startup e progetti legati agli open data. Il 28 Ottobre 2013 sono stati attivati 13 Nodi del network legato all’ODI in giro per il mondo, e l’Italia è rappresentata da uno di essi posto alla Fondazione Bruno Kessler di Trento[^4].

Per aiutare nella valutazione durante il processo di apertura dei dati, o per controllare se un dato pubblicato è conforme alle indicazioni dell’istituto, sono stati ideati i certificati ODI (*ODI Certificates*)[^5].

Un questionario composto da diverse domande (adattate e tradotte rispetto alla giurisdizione nazionale) aiuta a testare i propri dati verso una checklist che chiede informazioni in quattro aree[^6]: pratica, legale, tecnica e sociale.

Il risultato aiuta gli sviluppatori a spiegare cos’è il dato che hanno pubblicato, a migliorarlo e renderlo affidabile con l’aiuto di altri rispettando privacy e diritti di terzi. Ogni risultato si traduce in uno fra quattro certificati:

-   **basico** (o **grezzo**): il livello iniziale richiede che vengano almeno soddisfatti i requisiti della definizione di dato aperto, e bisogna fornire titolo del dato e nome di chi pubblica il dato;

-   **pilota**: mirato ad un rilascio iniziale con successo, bisogna fornire una pagina web che descrive il dataset e permette di essere contattati;

-   **standard**: mirato a dati che vengono pubblicati e tenuti aggiornati con continuità, richiede una API o un aggiornamento regolare;

-   **esperto**: assegnato a dati che sono di riferimento per altri dataset e che siano aggiornati quasi in tempo reale rispetto alle modifiche.

Open Data Census
----------------

L’Open Data Census è una iniziativa di monitoraggio civico del patrimonio informativo che dovrebbe essere liberamente disponibile a tutti, stando a diverse interpretazioni tra cui la più importante è l’Open Data Charter promossa dal G8 nel 2013.

Proposto al meeting dell’Aprile 2012[^7] dell’Open Government Partnership[^8], si è evoluto in un grande progetto di valutazione e controllo che viene istanziato nell’Open Data Index[^9] nei giorni precedenti la riunione annuale dell’OGP: l’edizione 2013 è stata rilasciata il 28 Ottobre.

### Open Data Charter

Il meeting del G8 sotto la presidenza britannica tenutosi il 17 e 18 Giugno 2013 ha approvato l’Open Data Charter[^10], un documento condiviso che dichiara l’importanza del rilascio di dati aperti ed il loro valore, individuando dei principi che devono esser la base dell’azione dei governi sul tema:

-   Open Data by Default: le informazioni del Settore Pubblico sono da intendersi pubblicate come dati aperti (a meno di particolari tipologie);

-   Qualità e quantità: i dati devono esser rilasciati alla massima qualità, nel minor tempo possibile, scritti e descritti chiaramente;

-   Usabili da tutti: devono esser rilasciati più dati possibile ed in formato aperto;

-   Rilascio dei dati per migliorare la gestione: condividere in trasparenza dati e processi di creazione e consumo;

-   Rilascio dei dati per favorire l’Innovazione: lavorare ad incrementare l’informazione e la cultura dei dati aperti ed impegnarsi a fornire dati processabili automaticamente per dare potere agli innovatori.

Vengono individuate nell’appendice tecnica quattordici categorie di dati considerate ad alto valore aggiunto:

-   Aziende: registro delle imprese;

-   Crimine e giustizia: statistiche;

-   Osservazione della Terra: dati meteorologici, climatici e sul settore primario;

-   Educazione: elenco e performance delle scuole;

-   Energia ed Ambiente: livelli di inquinamento, consumi;

-   Finanza e contratti: bilanci, spese e contratti sia nazionali sia locali, previsionali e consolidati;

-   Dati geospaziali: topografia, CAP, mappe nazionali e locali;

-   Sviluppo globale: statistiche su aiuti umanitari;

-   Responsabilità di governo e democrazia: contatti, risultati elettorali, atti legislativi, salari;

-   Salute: performance e prescrizioni;

-   Scienza e Ricerca: genetica, attività, risultati sperimentali;

-   Statistiche: su scala nazionale, censimento, infrastrutture;

-   Mobilità sociale e benessere: dati residenziali, assicurazioni e disoccupazione;

-   Trasporti ed infrastrutture: orari del trasporto pubblico, access point, banda larga.

### Census nazionale e locale

Il monitoraggio dell’Open Data Census è iniziato su scala nazionale: quale nazioni soddisfano maggiormente i requisiti dell’Open Data Charter? Con che qualità?

La piattaforma del census propone di effettuare un monitoraggio a cui possono partecipare tutti in fase di compilazione (inviando una *Submission* contenente luogo -fra quelli impostati nell’istanza del census-, dato esaminato, anno preso in considerazione e risposte all’insieme di domande -che può essere configurato a seconda del census-); le schede ricevute vengono revisionate da una serie di revisori autorizzati e diventano *Entry* del census.

Considerando il census nazionale[^11], si nota che l’insieme dei dati corrisponda con la Carta del G8 ed attualmente l’Italia ha ottenuto 515 punti mentre la Gran Bretagna, prima classificata, ha 940 punti: pesa la mancanza come dato libero dei codici d’avviamento postale.

Le domande a cui si deve rispondere sono:

-   Esiste il dato?

-   È in forma digitale?

-   È pubblicamente disponibile?

-   È disponibile gratuitamente?

-   È disponibile online?

-   È leggibile automaticamente?

-   È scaricabile nella sua interezza?

-   Ha una licenza aperta?

-   È aggiornato puntualmente?

A Febbraio 2014 arriva la versione locale (e localizzata) per l’Italia: partendo dai capoluoghi di regione si è progressivamente aperto ad altre città, estendendo l’insieme di dati per considerarne altri importanti a livello locale (anche se le domande poste per ogni dato sono le medesime della versione nazionale).

Open Government Data
--------------------

Per Open Government si intende un insieme di idee per le quali l’amministrazione pubblica debba essere aperta ai cittadini in settori che comprendono la comunicazione istituzionale, il dibattito pubblico (partecipazione civica), la trasparenza dell’attività.

Nel 2007 un meeting organizzato[^12] da Tim O’ Reilly tra interessati all’argomento ha prodotto un elenco di 8 principi che i dati prodotti da una amministrazione pubblica devono rispettare per esser conformi ai criteri delle politiche di open government:

-   completi: i dati pubblici devono essere completi (e rilasciati anche in blocco) a meno di problemi di privacy e sicurezza;

-   primari: i dati sono resi disponibili senza nessun tipo di aggregazione;

-   puntuali: il rilascio deve essere fatto il prima possibile per preservarne in valore;

-   accessibili: il rilascio deve essere in formato standard e senza filtri (form di richiesta);

-   processabili da macchine: la struttura deve consentire di lavorarci con strumenti automatici;

-   non discriminatori: non deve esser richiesta la registrazione per accedervi;

-   in formato non proprietario: ovvero in un formato su cui nessuna entità ha controllo esclusivo;

-   liberi da limitazioni: non devono esser soggetti a copyright, brevetti e marchi (precisando quali dati sono liberi e quali no).

-   In aggiunta la rispondenza ai principi deve essere controllabile (ci deve essere il modo di contattare una persona responsabile).

Criteri analoghi appaiono nelle linee guida della Sunlight Foundation[^13], nei criteri della Casa Bianca[^14], nel modello di implementazione della Città di Vienna[^15] ed altri[^16].

Considerazioni
--------------

Ci sono diversi metodi di valutazione del mondo dei dati aperti: abbiamo visto metodi basati su criteri formali (la scala Berners-Lee), sull’iterazione fra produttore e consumatore (la scala Davies), sulla criticità del dato (Open Data Census), sulla trasparenza (Open Government Data).

Altri metodi tendono a elencare criteri da verificare per stabilire la validità di un dato: sono diverse le checklist che permettono di stabilire se un dato soddisfa i requisiti, specie all’interno del mondo dell’Open Government[^17].

Si propongono due possibili approcci che possono costituire percorsi di accesso alla valutazione di un dato:

-   Sintetizzare le diverse classificazioni cogliendone i punti di interesse generale (non scendendo pertanto nel dettaglio del singolo criterio, poiché in diversi casi non potrebbe essere applicabile): un possibile metodo potrebbe derivare dalla classificazione usata per le strutture ricettive (classificazione “a stelle”)[^18], nella quale le stelle assegnate ad una struttura ricettiva vengono derivate dividendo in 6 classi un punteggio calcolato sulla presenza o meno di un determinato livello di servizio.

-   Stabilire un percorso di orientamento nella scelta del metodo di classificazione o valutazione da utilizzare, che porta a selezionarne uno tra quelli già esistenti.

![Più che proporre ulteriori procedure, bisognerebbe riutilizzare o migliorare l’esistente. Fonte <http://xkcd.com/927/>](../img/standards.png)
****

[^1]: Sito <http://www.opendataimpacts.net/engagement/>, Report originale <http://www.w3.org/2012/06/pmod/pmod2012_submission_5.pdf>

[^2]: Si vedano le riflessioni di Chris Taggart (<http://www.slideshare.net/countculture/ogd-camp-2011/1>) e Maurizio Napolitano (<http://www.chefuturo.it/2012/12/wasted-datafood/>) in proposito.

[^3]: <http://theodi.org/>

[^4]: <http://www.fbk.eu/it/news/fbk-nodo-italiano-dellopen-data-institute>, Sito <http://theodi.org/nodes/trento>

[^5]: <https://certificates.theodi.org/>, applicazione open source sviluppata su Github [https://github.com/theodi/open-data-certificate ](https://github.com/theodi/open-data-certificate )

[^6]: Informazioni generali <https://certificates.theodi.org/overview>, Il file xml della versione italiana completa <https://github.com/theodi/open-data-certificate/blob/master/prototype/translations/certificate.it.xml>

[^7]: <http://blog.okfn.org/2012/04/17/launching-the-open-data-census-2012/>

[^8]: <http://www.opengovpartnership.org/>

[^9]: <https://index.okfn.org/>

[^10]: <http://www.agid.gov.it/sites/default/files/documentazione/open_data_charter.pdf>

[^11]: <http://national.census.okfn.org/>

[^12]: <https://public.resource.org/open_government_meeting.html>

[^13]: <http://sunlightfoundation.com/opendataguidelines/>

[^14]: <http://www.whitehouse.gov/open/documents/evaluation>

[^15]: <http://www.kdz.eu/en/open-government-implementation-model>

[^16]: <http://opengovdata.org/> presenta una versione annotata dei principi con indicazione di alcune corrispondenze

[^17]: Vedasi ad esempio il documento sull’implementazione dell’Open Government a Vienna, la checklist di Opquast <https://checklists.opquast.com/en/opendata>, la checklist del consumatore di dati dell’ODI <http://theodi.org/guides/the-open-data-consumers-checklist>, la checklist contenuta nelle “Linee guida valorizzazione patrimonio informativo pubblico” dell’Agenzia per l’Italia Digitale.

[^18]: Riformata con il Decreto della Presidenza del Consiglio dei Ministri del 21 Ottobre 2008
