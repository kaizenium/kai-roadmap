# Kai Roadmap

Dieses Dokument verfolgt die Entwicklungsreihenfolge der Sprache Kai und ihres Ökosystems. Die Phasen sind nicht nach Datum, sondern nach Abhängigkeiten geordnet - jede Phase benötigt das Kernergebnis der vorherigen. Dies ist ein realistisches Maß an Verbindlichkeit für ein Projekt, das sich derzeit noch in der Spezifikationsphase befindet.
 
## Status-Legende
 
| Label | Bedeutung |
|---|---|
| ABGESCHLOSSEN | Abgeschlossen |
| IN BEARBEITUNG | Wird aktiv bearbeitet |
| GEPLANT | Geplant, noch nicht begonnen |
| IDEE | Wird in Erwägung gezogen, noch nicht final |
 
---
 
## Phase 0 — Sprachdesign
 
**Ziel:** Syntax und Semantik auf dem Papier festlegen.
 
| Status | Punkt |
|---|---|
| ABGESCHLOSSEN | Philosophie und Zielbereiche definieren |
| IN BEARBEITUNG | v0.1-Sprachspezifikation ([about-kai](https://github.com/kaizenium/about-kai)) |
| GEPLANT | Syntaxbeispiele erweitern (Grenzfälle: generische Constraints, Regeln für Operatorüberladung, Details des Makrosystems) |
| GEPLANT | Community-Feedback zur Spezifikation einholen |
 
## Phase 1 — Lexer und Parser
 
**Ziel:** Ein minimales Frontend, das Kai-Quellcode in einen AST umwandeln kann.
 
| Status | Punkt |
|---|---|
| GEPLANT | Lexer: Token-Definitionen, Verarbeitung von String-/Char-/numerischen Literalen |
| GEPLANT | Parser: Ausdrucks-/Anweisungsgrammatik, Prioritätsregeln |
| GEPLANT | AST-Definitionen |
| GEPLANT | Parser-Fehlermeldungen (mit Zeilen-/Spalteninformation) |
 
## Phase 2 — Semantische Analyse
 
**Ziel:** Funktionierende Typprüfung und grundlegende Validierung.
 
| Status | Punkt |
|---|---|
| GEPLANT | Symboltabelle und Scope-Auflösung |
| GEPLANT | Typprüfung (`i8`-`i64`, `u8`-`u64`, `f32`/`f64`, `bool`, `char`, `str`) |
| GEPLANT | Auflösung von Struct-/Class-Feldern und -Methoden |
| GEPLANT | Sichtbarkeitsregeln durchsetzen (`public`/`private`/`protected`) |
| GEPLANT | Auflösung generischer Typen (`Vector<T>`) |
 
## Phase 3 — Codegenerierung
 
**Ziel:** Einen validierten AST in funktionierendes x86-64-Assembly umwandeln.
 
| Status | Punkt |
|---|---|
| GEPLANT | Codegenerierung für grundlegende Ausdrücke und Kontrollfluss (`if`/`for`/`while`/`switch`) |
| GEPLANT | Funktionsaufrufkonvention, Stack-Frame-Verwaltung |
| GEPLANT | Speicherlayout von Struct/Class |
| GEPLANT | Integration von Inline-Assembly-Blöcken (`asm {}`) |
| GEPLANT | NASM/GAS-Ausgabe über den Linker zusammenführen |
| GEPLANT | Meilenstein: "Hello World" ausführen (Linux x86-64) |
 
## Phase 4 — Compiler-Reife
 
**Ziel:** Reale Programme werden schreibbar.
 
| Status | Punkt |
|---|---|
| GEPLANT | Codegenerierung für Pointer/Referenzen unter manueller Speicherverwaltung |
| GEPLANT | Aufrufreihenfolge von Konstruktor/Destruktor, Vererbung und virtuelles Dispatching |
| GEPLANT | constexpr-Auswertung |
| GEPLANT | Implementierung des Makrosystems |
| GEPLANT | Compiler-Fehler- und Warnmeldungen verbessern |
| IDEE | Grundlegende Optimierungsdurchläufe (Dead-Code-Eliminierung, Constant Folding) |
 
## Phase 5 — Tooling-Ökosystem
 
**Ziel:** Die Sprache für den täglichen Gebrauch nutzbar machen.
 
| Status | Punkt |
|---|---|
| GEPLANT | [kai](https://github.com/kaizenium/kai) CLI: `build`/`run`/`clean`/`add`/`remove`/`update` |
| GEPLANT | [kai-syntax](https://github.com/kaizenium/kai-syntax): Syntaxhervorhebung für Editoren (VSCode, Vim) |
| GEPLANT | [kaifmt](https://github.com/kaizenium/kaifmt): Code-Formatierer |
| GEPLANT | [kaistd](https://github.com/kaizenium/kaistd): minimale Standardbibliothek (I/O, Strings, Collections) |
| IDEE | [kaitest](https://github.com/kaizenium/kaitest): Test-Tool |
| IDEE | [kaibench](https://github.com/kaizenium/kaibench): Benchmark-Tool |
 
## Phase 6 — Plattformerweiterung
 
**Ziel:** Über Linux x86-64 hinausgehen.
 
| Status | Punkt |
|---|---|
| IDEE | Cross-Compile: `--target windows-x86_64` |
| IDEE | Cross-Compile: `--target linux-arm64` |
| IDEE | Cross-Compile: `--target riscv64` |
| IDEE | macOS-Unterstützung |
 
## Phase 7 — Entwicklererfahrung
 
**Ziel:** Unterstützung auf IDE-Niveau und Dokumentation.
 
| Status | Punkt |
|---|---|
| IDEE | [kailsp](https://github.com/kaizenium/kailsp): Language Server (Autovervollständigung, Sprung zur Definition, Diagnostik) |
| IDEE | [kaidoc](https://github.com/kaizenium/kaidoc): Dokumentationsgenerator |
| IDEE | Paket-Ökosystem (`shared/`-Community-Repository) |
 
## Phase 8 — Self-Hosting
 
**Ziel:** Der Kai-Compiler wird in Kai geschrieben.
 
| Status | Punkt |
|---|---|
| IDEE | [kai-bootstrap](https://github.com/kaizenium/kai-bootstrap): Bootstrap-Compiler |
| IDEE | Bestehenden Compiler nach Kai portieren |
| IDEE | Eine stabile ABI definieren |
 
---
 
## Wo stehen wir aktuell?
 
Das Projekt befindet sich in **Phase 0** - die Sprachspezifikation wird aktiv bearbeitet. Der Übergang zu Phase 1 (Lexer und Parser) beginnt, sobald die Spezifikation stabil genug ist, um darauf aufzubauen.
 
## Mitwirken?
 
In diesem Stadium ist der wertvollste Beitrag die Diskussion und das Feedback zur [about-kai](https://github.com/kaizenium/about-kai)-Spezifikation. Ein gesonderter Aufruf zu Code-Beiträgen erfolgt, sobald Phase 1 beginnt.
