# Feuille de Route de Kai

Ce document suit l'ordre de développement du langage Kai et de son écosystème. Les phases sont classées par dépendance plutôt que par date - chaque phase nécessite le résultat principal de la précédente. Il s'agit d'un niveau d'engagement réaliste pour un projet actuellement au stade de la spécification.
 
## Légende des Statuts
 
| Étiquette | Signification |
|---|---|
| TERMINÉ | Terminé |
| EN COURS | En cours de développement actif |
| PRÉVU | Planifié, pas encore commencé |
| IDÉE | À l'étude, non finalisé |
 
---
 
## Phase 0 — Conception du Langage
 
**Objectif :** Fixer la syntaxe et la sémantique sur le papier.
 
| Statut | Élément |
|---|---|
| TERMINÉ | Définir la philosophie et les domaines cibles |
| EN COURS | Spécification du langage v0.1 ([about-kai](https://github.com/kaizenium/about-kai)) |
| PRÉVU | Étendre les exemples de syntaxe (cas limites : contraintes génériques, règles de surcharge d'opérateurs, détails du système de macros) |
| PRÉVU | Recueillir les retours de la communauté sur la spécification |
 
## Phase 1 — Lexer et Parser
 
**Objectif :** Un front-end minimal capable de transformer le code source Kai en AST.
 
| Statut | Élément |
|---|---|
| PRÉVU | Lexer : définitions des tokens, gestion des littéraux string/char/numériques |
| PRÉVU | Parser : grammaire des expressions/instructions, règles de priorité |
| PRÉVU | Définitions de l'AST |
| PRÉVU | Messages d'erreur du parser (avec info ligne/colonne) |
 
## Phase 2 — Analyse Sémantique
 
**Objectif :** Vérification de type fonctionnelle et validation de base.
 
| Statut | Élément |
|---|---|
| PRÉVU | Table des symboles et résolution de portée |
| PRÉVU | Vérification de type (`i8`-`i64`, `u8`-`u64`, `f32`/`f64`, `bool`, `char`, `str`) |
| PRÉVU | Résolution des champs et méthodes struct/class |
| PRÉVU | Application des règles de visibilité (`public`/`private`/`protected`) |
| PRÉVU | Résolution des types génériques (`Vector<T>`) |
 
## Phase 3 — Génération de Code
 
**Objectif :** Transformer un AST validé en Assembly x86-64 fonctionnel.
 
| Statut | Élément |
|---|---|
| PRÉVU | Génération de code pour les expressions de base et le flux de contrôle (`if`/`for`/`while`/`switch`) |
| PRÉVU | Convention d'appel de fonction, gestion des stack frames |
| PRÉVU | Disposition mémoire des struct/class |
| PRÉVU | Intégration des blocs d'assembleur en ligne (`asm {}`) |
| PRÉVU | Combiner la sortie NASM/GAS via le linker |
| PRÉVU | Jalon : exécuter "Hello World" (Linux x86-64) |
 
## Phase 4 — Maturité du Compilateur
 
**Objectif :** Permettre l'écriture de véritables programmes.
 
| Statut | Élément |
|---|---|
| PRÉVU | Génération de code pour pointeurs/références sous gestion manuelle de la mémoire |
| PRÉVU | Ordre d'appel constructeur/destructeur, héritage et dispatch virtuel |
| PRÉVU | Évaluation constexpr |
| PRÉVU | Implémentation du système de macros |
| PRÉVU | Améliorer les messages d'erreur et d'avertissement du compilateur |
| IDÉE | Passes d'optimisation de base (élimination de code mort, constant folding) |
 
## Phase 5 — Écosystème d'Outils
 
**Objectif :** Rendre le langage utilisable au quotidien.
 
| Statut | Élément |
|---|---|
| PRÉVU | CLI [kai](https://github.com/kaizenium/kai) : `build`/`run`/`clean`/`add`/`remove`/`update` |
| PRÉVU | [kai-syntax](https://github.com/kaizenium/kai-syntax) : coloration syntaxique pour éditeurs (VSCode, Vim) |
| PRÉVU | [kaifmt](https://github.com/kaizenium/kaifmt) : formateur de code |
| PRÉVU | [kaistd](https://github.com/kaizenium/kaistd) : bibliothèque standard minimale (I/O, strings, collections) |
| IDÉE | [kaitest](https://github.com/kaizenium/kaitest) : outil de test |
| IDÉE | [kaibench](https://github.com/kaizenium/kaibench) : outil de benchmark |
 
## Phase 6 — Expansion des Plateformes
 
**Objectif :** Aller au-delà de Linux x86-64.
 
| Statut | Élément |
|---|---|
| IDÉE | Compilation croisée : `--target windows-x86_64` |
| IDÉE | Compilation croisée : `--target linux-arm64` |
| IDÉE | Compilation croisée : `--target riscv64` |
| IDÉE | Support macOS |
 
## Phase 7 — Expérience Développeur
 
**Objectif :** Support de niveau IDE et documentation.
 
| Statut | Élément |
|---|---|
| IDÉE | [kailsp](https://github.com/kaizenium/kailsp) : Language Server (autocomplétion, aller à la définition, diagnostics) |
| IDÉE | [kaidoc](https://github.com/kaizenium/kaidoc) : générateur de documentation |
| IDÉE | Écosystème de paquets (dépôt communautaire `shared/`) |
 
## Phase 8 — Auto-hébergement
 
**Objectif :** Que le compilateur Kai soit écrit en Kai.
 
| Statut | Élément |
|---|---|
| IDÉE | [kai-bootstrap](https://github.com/kaizenium/kai-bootstrap) : compilateur de bootstrap |
| IDÉE | Porter le compilateur existant vers Kai |
| IDÉE | Définir une ABI stable |
 
---
 
## Où En Sommes-Nous ?
 
Le projet est en **Phase 0** - la spécification du langage est en cours de développement actif. Le passage à la Phase 1 (Lexer et Parser) débutera une fois que la spécification sera suffisamment stable pour construire dessus.
 
## Envie de Contribuer ?
 
À ce stade, la contribution la plus précieuse est la discussion et les retours sur la spécification [about-kai](https://github.com/kaizenium/about-kai). Un appel séparé pour les contributions de code sera lancé une fois la Phase 1 commencée.
