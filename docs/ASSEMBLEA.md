---
mustache: dati.yaml
---

# {{titolo}}

## 1. Dati della riunione

L'anno **{{data-anno}}**, il giorno **{{data-giorno}}** del mese di **{{data-mese}}**, alle ore **{{ora_inizio}}**, presso **{{luogo}}**, si è riunita in **{{convocazione}}** l'**{{tipo_riunione}}** dell'associazione **{{associazione}}**.

La riunione è stata regolarmente convocata nei modi e nei termini previsti dallo statuto vigente.

## 2. Partecipanti e verifica del quorum

**Risultano presenti:**

{{presenti}}

**Risultano assenti:**

{{assenti}}

**Verifica del quorum:**

| | |
|---|---|
| Soci totali aventi diritto di voto | **{{n_soci_totale}}** |
| Presenti in assemblea | **{{n_presenti}}** |
| Deleghe ricevute | **{{n_deleghe}}** |
| Totale aventi diritto al voto presenti o rappresentati | **{{n_aventi_diritto_voto}}** |
| Quorum richiesto | **{{quorum_richiesto}}** |

Il quorum è raggiunto. L'assemblea è **validamente costituita**.

## 3. Costituzione dell'assemblea

Il socio **{{presidente_assemblea}}** propone di assumere la presidenza dei lavori assembleari. Non essendovi opposizioni, assume la presidenza dell'assemblea.

Il Presidente invita il socio **{{segretario_assemblea}}** a svolgere le funzioni di segretario verbalizzante, il quale accetta.

## 4. Ordine del giorno

Il Presidente dichiara aperta la seduta e pone in discussione il seguente ordine del giorno:

{{ordine_del_giorno}}

## 5. Svolgimento della riunione

### 5.1 Presa d'atto della cessazione del Consiglio Direttivo in carica

Il Presidente informa l'assemblea che in data **{{data_dimissioni}}** i membri del Consiglio Direttivo in carica hanno rassegnato le proprie **{{motivo_cessazione}}**. I membri uscenti sono:

{{vecchio_consiglio}}

L'assemblea **prende atto all'unanimità** della cessazione del Consiglio Direttivo e ringrazia i membri uscenti per l'attività svolta nel periodo del mandato.

### 5.2 Elezione del nuovo Consiglio Direttivo

Il Presidente apre la procedura per l'elezione del nuovo Consiglio Direttivo e invita i soci a presentare le proprie candidature.

Vengono presentate le seguenti candidature:

{{candidati_consiglio}}

Non essendovi ulteriori candidature, si procede alla votazione con **voto palese**.

L'assemblea approva **all'unanimità** la seguente composizione del nuovo Consiglio Direttivo:

{{nuovo_consiglio_eletto}}

### 5.3 Attribuzione delle cariche interne al nuovo Consiglio Direttivo

Il Presidente invita il nuovo Consiglio Direttivo a procedere all'attribuzione delle cariche interne.

Il nuovo Consiglio Direttivo delibera, all'unanimità, la seguente attribuzione delle cariche:

- **Presidente:** {{nuovo_presidente}}
- **Segretario:** {{nuovo_segretario}}
- **Tesoriere:** {{nuovo_tesoriere}}

Il neo-eletto Presidente **{{nuovo_presidente}}** ringrazia e assume la conduzione dei lavori assembleari per i punti successivi.

### 5.4 Modifica della denominazione sociale

Il Presidente illustra la proposta di modifica della denominazione dell'associazione dall'attuale **"{{vecchia_denominazione}}"** alla nuova denominazione **"{{nuova_denominazione}}"**, e ne spiega le motivazioni.

Dopo breve discussione, si procede alla votazione con **voto palese**.

L'assemblea approva **all'unanimità** la modifica della denominazione sociale in **"{{nuova_denominazione}}"**, con efficacia **{{data_efficacia}}**.

### 5.5 Approvazione del nuovo statuto sociale

Il Presidente illustra all'assemblea il testo del nuovo statuto sociale ({{riferimento_statuto}}), dando lettura degli articoli e illustrando le modifiche rispetto al testo vigente.

Non essendovi osservazioni, si procede alla votazione con **voto palese**.

L'assemblea approva **all'unanimità** il nuovo statuto sociale così come proposto, riportato integralmente nell'{{riferimento_statuto}}, con efficacia **{{data_efficacia}}**.

### 5.6 Varie ed eventuali

Nessuno dei presenti chiede la parola per varie ed eventuali.

## 6. Chiusura

Non essendovi altri argomenti da trattare, il Presidente dichiara chiusa la seduta alle ore **{{ora_fine}}**.

Letto, approvato e sottoscritto.

{{luogo}}, lì {{data}}

_________________________          _________________________

Il Presidente dell'Assemblea        Il Segretario Verbalizzante
