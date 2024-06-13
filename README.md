SUPSI 2023-24  
Corso d’interaction design, CV427.01  
Docenti: A. Gysin, G. Profeta  

Elaborato 1: gica.ch

# Titolo progetto
Autore: Davide Torre  
[gica.ch](xxxxxx)


## Introduzione e tema
gica è una piccola media impresa che si occupa di riordini e trasbordi di treni merci. L’azienda si impegna a riorganizzare i vari pesi e la disposizione degli oggetti nei vagoni bloccati sul nostro Territorio, in quanto non possono viaggiare in condizioni precarie o sbilanciate.

Il database mira a raccogliere le informazioni di ogni intervento fatto, come l’archiviazione del numero identificativo del vagone, la sua merce, la data e altre informazioni. Questo sistema testimonia il proprio operato e documenta gli interventi completati, migliorando la gestione e la tracciabilità dei vagoni.



## Riferimenti progettuali
Nel progettare questo sistema, ho preso in considerazione i dati necessari all’azienda, focalizzandomi su ciò che è utile o superfluo per l’ente. Ho effettuato un’analisi attenta delle mansioni e delle operazioni della ditta per garantire che il sistema rispondesse alle reali esigenze operative.

## Design dell’interfraccia e modalià di interazione
L’interfaccia del database è stata progettata per essere intuitiva e di facile utilizzo, consentendo agli utenti di accedere e visualizzare le informazioni sui vagoni in modo rapido ed efficiente. Il design minimalista e il layout a griglia permettono di visualizzare chiaramente un gran numero di record senza sovraccaricare l’utente con dettagli superflui.

Gli utenti possono interagire con l’interfaccia tramite clic e mouseover. Ogni sezione dell’interfaccia offre funzionalità specifiche per il filtraggio e l’ordinamento dei dati:

	>	Home: Visualizza una panoramica generale dei dati.
	>	Data: Permette di ordinare e filtrare i dati in base alla data degli interventi.
	>	Provenienza: Consente di visualizzare i dati in base alla provenienza delle merci.
	>	Merce: Mostra le informazioni organizzate per tipo di merce.
	>	Metadati: Fornisce dettagli aggiuntivi sui dati raccolti e archiviati.

Ogni foto rappresenta un vagone, creando così una sorta di catena visiva. Le fotografie dei vagoni sono utilizzate per permettetere agli utenti di identificare facilmente le varie presenze e navigare nei dati a colpo d’occhio. Questo approccio visivo rende il sistema più intuitivo e facilita la comprensione delle informazioni presentate.


## Tecnologia usata

// Esempio di caricamento dei dati da un file JSON e filtraggio dei dati
document.addEventListener('DOMContentLoaded', function() {
    fetch("./assets/data.json")
        .then(response => response.json())
        .then(json => {
            data = json;
            displayData(data);
        });
});
-------------
// Funzione per visualizzare i dati
function displayData(data) {
    const output = data.map(item => `
        <div class='item'>
            <img src='./assets/immagini/${item.file}.jpg'>
            <div class="image-info">
                <div class='data'>${item.data}</div>
                <div class='provenienza'>${item.provenienza}</div>
                <div class='vagone'>${item.vagone}</div>
                <div class='merce'>${item.merce}</div>
                <div class='prestazione'>${item.prestazione}</div>
            </div>
        </div>
    `).join('');
    document.querySelector('main').innerHTML = output;
}
-------------
// Funzione per ordinare i dati per data
function sortByDate(data) {
    return data.sort((a, b) => new Date(a.data) - new Date(b.data));
}



## Target e contesto d’uso
Il progetto è destinato ai responsabili della gestione dei riordini e dei trasbordi di vagoni merci. Questi utenti necessitano di un sistema efficiente e intuitivo per raccogliere e analizzare dati sugli interventi effettuati sui vagoni. Il sistema consente loro di prendere decisioni basate sui dati raccolti, migliorando la gestione operativa e strategica.

Contesto d’uso

Il sistema è progettato per essere utilizzato in ambienti operativi dove è fondamentale avere accesso rapido e preciso alle informazioni sui vagoni. Il target principale include:

	>	Amministratori: Possono analizzare i dati raccolti per identificare tendenze e ottimizzare le risorse, decidendo dove investire nuovi mezzi e materiali. 
	>	Clienti: Il sistema può essere condiviso con i clienti per dimostrare la trasparenza, l’efficacia operativa e la presenza dell’azienda sul territorio come anche l'esperienza accumulata. 


Utilizzo in contesti operativi

Il sistema consente di identificare rapidamente quali merci sono più presenti e quali interventi sono stati effettuati. Questo facilita la gestione operativa, consentendo di:

	>	Ottimizzare le risorse: Identificare dove investire in nuovi mezzi e risorse basandosi sulla quantità e il tipo di lavori svolti.
	>	Evitare sprechi: Riconoscere aree con bassa quantità di lavori e ridurre gli investimenti in risorse non necessarie.
	>	Analizzare le performance: Monitorare le prestazioni dei riordini e dei trasbordi, migliorando continuamente i processi aziendali.


