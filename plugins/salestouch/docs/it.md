# SalesTouch

[English](../README.md) · [Français](fr.md) · [Deutsch](de.md) · [Español](es.md) · [Português](pt.md) · [Italiano](it.md)

**Prospezione LinkedIn per agenti IA.** SalesTouch è un MCP LinkedIn che collega Claude alla ricerca di potenziali clienti, alle conversazioni, ai messaggi, alle pubblicazioni, ai follow-up e alle code. SalesTouch non è affiliato a LinkedIn né approvato da LinkedIn.

## Requisiti

Uno spazio SalesTouch con un piano attivo e un account LinkedIn collegato. Le funzioni Sales Navigator richiedono i relativi permessi. I risultati dipendono dalle autorizzazioni, dai dati disponibili e dai limiti della piattaforma.

## Installare in Claude Code

Esegui in Claude Code:

```text
/plugin marketplace add antoineDsh/SalesTouch
/plugin install salestouch@salestouch
```

Riavvia Claude Code, esegui `/mcp`, scegli SalesTouch e autorizza il collegamento nel browser. Non inserire password LinkedIn, cookie o chiavi API nella conversazione o nella configurazione del plugin.

## Installare in Claude Desktop o Cowork

Apri **Customize → Plugins**. In **Personal plugins**, seleziona **+ → Add marketplace**, scegli l’opzione repository e inserisci `antoineDsh/SalesTouch`. Installa e attiva `salestouch`, quindi autorizza il connettore SalesTouch. Le opzioni disponibili dipendono dal piano Claude e dalle impostazioni dell’organizzazione.

## Cursor

Clona questo repository pubblico in `~/.cursor/plugins/local/salestouch` e ricarica Cursor. Apri **Settings → Tools & MCPs**, trova `salestouch`, fai clic su **Connect** e autorizza SalesTouch nel browser. La tua organizzazione può limitare i plugin locali. L’inserimento nel marketplace è soggetto alla revisione di Cursor.

Puoi anche aggiungere la [configurazione MCP](../../../README.md#cursor) in `.cursor/mcp.json` per il progetto oppure in `~/.cursor/mcp.json` per il tuo profilo. Completa rapidamente l’autorizzazione: Cursor può smettere di attendere dopo 30 secondi. In tal caso, fai nuovamente clic su **Connect**. Inizia con il prompt di verifica degli account riportato sotto. Mantieni attive le approvazioni degli strumenti e controlla destinatari e contenuti prima di autorizzare azioni esterne.

L’installazione del plugin MIT è gratuita. Il servizio SalesTouch ospitato richiede un abbonamento separato. Non inserire credenziali LinkedIn nella configurazione MCP.

## Tre prompt per iniziare

1. «Elenca i miei account LinkedIn collegati con SalesTouch.»
2. «Cerca informazioni su questo profilo LinkedIn e sui suoi post recenti. Prepara una presentazione pertinente senza inviarla: [URL del profilo].»
3. «Leggi questa conversazione LinkedIn, riassumi le esigenze del potenziale cliente e prepara una risposta senza inviarla: [ID conversazione o URL del profilo].»

Sostituisci i valori tra parentesi con i tuoi destinatari. Puoi anche estrarre risultati di ricerca o persone che hanno interagito con un post, sfogliare i risultati salvati e scaricare esportazioni. Controlla destinatario, contenuto e orario prima di approvare un’azione. In attesa non significa consegnato. Controlla la coda prima di ripetere un’operazione di scrittura.

## Collegamento e assistenza

L’endpoint MCP remoto è `https://www.salestouch.io/api/mcp`, con Streamable HTTP e OAuth. Se l’autorizzazione fallisce, ricollega il connettore, verifica lo spazio e il collegamento LinkedIn, quindi ripeti il prompt degli account. Condividi con l’assistenza solo un codice di errore e i passaggi per riprodurlo, senza credenziali, token o messaggi privati.

[Configurazione](../SETUP.md) · [Assistenza](https://www.salestouch.io/support) · [Sicurezza](../SECURITY.md) · [Documentazione](https://www.salestouch.io/docs) · [Privacy](https://www.salestouch.io/privacy) · [Condizioni](https://www.salestouch.io/terms) · [support@salestouch.io](mailto:support@salestouch.io)

I file del plugin sono distribuiti con [licenza MIT](../LICENSE). Il backend ospitato è proprietario.

## Versione 0.9.3

Installa SalesTouch localmente in Cursor, collegalo tramite OAuth e inizia verificando gli account. Il pacchetto Cursor include ora il logo e istruzioni più chiare.

## Versione 0.9.2

Collegamento a Claude Code corretto: vengono richieste solo le autorizzazioni necessarie al MCP.

## Versione 0.9.1

Installazione aggiornata in sei lingue; configurazione e assistenza incluse nel pacchetto; analytics tecnici MCP senza obiettivi delle conversazioni o contenuti delle chiamate. [Cronologia](../CHANGELOG.md).
