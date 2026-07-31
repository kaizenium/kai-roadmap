# Roadmap di Kai

Questo documento tiene traccia dell'ordine di sviluppo del linguaggio Kai e del suo ecosistema. Le fasi sono ordinate per dipendenza e non per data - ogni fase necessita del risultato principale della precedente. Questo è un livello di impegno realistico per un progetto che si trova attualmente nella fase di specifica.
 
## Legenda degli Stati
 
| Etichetta | Significato |
|---|---|
| COMPLETATO | Completato |
| IN CORSO | In lavorazione attiva |
| PIANIFICATO | Programmato, non ancora iniziato |
| IDEA | In fase di valutazione, non definitivo |
 
---
 
## Fase 0 — Design del Linguaggio
 
**Obiettivo:** Definire sintassi e semantica sulla carta.
 
| Stato | Voce |
|---|---|
| COMPLETATO | Definire la filosofia e i domini target |
| IN CORSO | Specifica del linguaggio v0.1 ([about-kai](https://github.com/kaizenium/about-kai)) |
| PIANIFICATO | Espandere gli esempi di sintassi (casi limite: vincoli generici, regole di overloading degli operatori, dettagli del sistema di macro) |
| PIANIFICATO | Raccogliere feedback della community sulla specifica |
 
## Fase 1 — Lexer e Parser
 
**Obiettivo:** Un front end minimale in grado di trasformare il codice sorgente Kai in un AST.
 
| Stato | Voce |
|---|---|
| PIANIFICATO | Lexer: definizioni dei token, gestione dei letterali string/char/numerici |
| PIANIFICATO | Parser: grammatica di espressioni/istruzioni, regole di precedenza |
| PIANIFICATO | Definizioni dell'AST |
| PIANIFICATO | Messaggi di errore del parser (con info riga/colonna) |
 
## Fase 2 — Analisi Semantica
 
**Obiettivo:** Type checking funzionante e validazione di base.
 
| Stato | Voce |
|---|---|
| PIANIFICATO | Tabella dei simboli e risoluzione degli scope |
| PIANIFICATO | Type checking (`i8`-`i64`, `u8`-`u64`, `f32`/`f64`, `bool`, `char`, `str`) |
| PIANIFICATO | Risoluzione di campi e metodi di struct/class |
| PIANIFICATO | Applicazione delle regole di visibilità (`public`/`private`/`protected`) |
| PIANIFICATO | Risoluzione dei tipi generici (`Vector<T>`) |
 
## Fase 3 — Generazione del Codice
 
**Obiettivo:** Trasformare un AST validato in Assembly x86-64 funzionante.
 
| Stato | Voce |
|---|---|
| PIANIFICATO | Codegen per espressioni di base e flusso di controllo (`if`/`for`/`while`/`switch`) |
| PIANIFICATO | Convenzione di chiamata delle funzioni, gestione dello stack frame |
| PIANIFICATO | Layout di memoria di struct/class |
| PIANIFICATO | Integrazione dei blocchi assembly inline (`asm {}`) |
| PIANIFICATO | Combinare l'output NASM/GAS tramite il linker |
| PIANIFICATO | Traguardo: eseguire "Hello World" (Linux x86-64) |
 
## Fase 4 — Maturità del Compilatore
 
**Obiettivo:** Rendere possibile scrivere programmi reali.
 
| Stato | Voce |
|---|---|
| PIANIFICATO | Codegen per puntatori/riferimenti sotto gestione manuale della memoria |
| PIANIFICATO | Ordine di chiamata costruttore/distruttore, ereditarietà e dispatch virtuale |
| PIANIFICATO | Valutazione constexpr |
| PIANIFICATO | Implementazione del sistema di macro |
| PIANIFICATO | Migliorare i messaggi di errore e warning del compilatore |
| IDEA | Passaggi di ottimizzazione di base (eliminazione del codice morto, constant folding) |
 
## Fase 5 — Ecosistema degli Strumenti
 
**Obiettivo:** Rendere il linguaggio utilizzabile quotidianamente.
 
| Stato | Voce |
|---|---|
| PIANIFICATO | CLI [kai](https://github.com/kaizenium/kai): `build`/`run`/`clean`/`add`/`remove`/`update` |
| PIANIFICATO | [kai-syntax](https://github.com/kaizenium/kai-syntax): syntax highlighting per editor (VSCode, Vim) |
| PIANIFICATO | [kaifmt](https://github.com/kaizenium/kaifmt): formattatore di codice |
| PIANIFICATO | [kaistd](https://github.com/kaizenium/kaistd): libreria standard minimale (I/O, stringhe, collezioni) |
| IDEA | [kaitest](https://github.com/kaizenium/kaitest): strumento di test |
| IDEA | [kaibench](https://github.com/kaizenium/kaibench): strumento di benchmark |
 
## Fase 6 — Espansione della Piattaforma
 
**Obiettivo:** Andare oltre Linux x86-64.
 
| Stato | Voce |
|---|---|
| IDEA | Cross compile: `--target windows-x86_64` |
| IDEA | Cross compile: `--target linux-arm64` |
| IDEA | Cross compile: `--target riscv64` |
| IDEA | Supporto macOS |
 
## Fase 7 — Developer Experience
 
**Obiettivo:** Supporto a livello IDE e documentazione.
 
| Stato | Voce |
|---|---|
| IDEA | [kailsp](https://github.com/kaizenium/kailsp): Language Server (autocompletamento, vai alla definizione, diagnostica) |
| IDEA | [kaidoc](https://github.com/kaizenium/kaidoc): generatore di documentazione |
| IDEA | Ecosistema di pacchetti (repository community `shared/`) |
 
## Fase 8 — Self-Host
 
**Obiettivo:** Il compilatore Kai è scritto in Kai.
 
| Stato | Voce |
|---|---|
| IDEA | [kai-bootstrap](https://github.com/kaizenium/kai-bootstrap): compilatore bootstrap |
| IDEA | Portare il compilatore esistente in Kai |
| IDEA | Definire un'ABI stabile |
 
---
 
## A Che Punto Siamo?
 
Il progetto è in **Fase 0** - la specifica del linguaggio è in fase di lavorazione attiva. Il passaggio alla Fase 1 (Lexer e Parser) inizierà una volta che la specifica si sarà stabilizzata abbastanza da poterci costruire sopra.
 
## Vuoi Contribuire?
 
In questa fase, il contributo più prezioso è la discussione e il feedback sulla specifica [about-kai](https://github.com/kaizenium/about-kai). Una call separata per i contributi di codice verrà lanciata una volta iniziata la Fase 1.
