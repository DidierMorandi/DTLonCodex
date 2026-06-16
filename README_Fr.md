# DTLonCodex

Documentation française d'OpenAI Codex, préparée dans l'esprit DEC/VSI et présentée avec la charte NetDTL.

Ce dépôt rassemble un guide utilisateur, un manuel de référence et une version HTML complète pour comprendre, utiliser et encadrer Codex dans des travaux de développement logiciel.

## Documents disponibles

- [Documentation complète](OpenAI_Codex_Documentation_NetDTL.html) : version HTML en une seule page, avec navigation et recherche.
- [Manuel de référence](DTLonCodex_Manuel_de_reference.html) : description fonctionnelle des surfaces, objets, mécanismes et capacités Codex.
- [Guide utilisateur](DTLonCodex_Guide_utilisateur.html) : mode d'emploi pratique pour démarrer, guider Codex, vérifier les résultats et traiter les scénarios courants.

## À quoi sert cette documentation

DTLonCodex aide à répondre à trois questions :

1. Quelles fonctions Codex met-il à disposition ?
2. Quelle surface utiliser selon le besoin : App, CLI, extension IDE, Web ou Cloud ?
3. Comment formuler, suivre, vérifier et finaliser une tâche confiée à Codex ?

Le manuel de référence décrit les notions durables : surfaces d'exécution, modèles, contexte, outils, Git, terminal intégré, navigateur intégré, personnalisation, permissions, bac à sable, automatisations, MCP, skills, plugins, hooks et subagents.

Le guide utilisateur transforme ces notions en procédures : préparer un projet, rédiger une demande, choisir un mode de travail, examiner un diff, lancer les tests, corriger une trajectoire, ajouter une instruction durable ou mettre en place une automation.

## Lecture recommandée

Pour découvrir Codex, commencez par le guide utilisateur :

1. Choisir la surface adaptée.
2. Préparer le projet et l'état Git.
3. Rédiger une demande courte, bornée et vérifiable.
4. Suivre le travail, les commandes et les approbations.
5. Examiner le diff et lancer les vérifications.

Pour administrer ou documenter un usage Codex, utilisez plutôt le manuel de référence :

1. Identifier les surfaces et modes disponibles.
2. Comprendre les objets de référence : projet, fil, worktree, chat, skill, plugin, serveur MCP, hook, automation.
3. Définir les règles de configuration, de permissions et de bac à sable.
4. Choisir les mécanismes de personnalisation ou d'intégration nécessaires.

## Résumé opérationnel

Avant de confier une tâche à Codex :

- ouvrez le bon dossier de projet ;
- vérifiez l'état Git ;
- indiquez l'objectif, les contraintes et les fichiers concernés ;
- précisez les tests ou preuves attendus ;
- limitez explicitement les refactorisations si le changement doit rester minimal.

Pendant le travail :

- surveillez les fichiers lus et modifiés ;
- réorientez Codex si le périmètre dérive ;
- accordez les permissions avec la portée la plus étroite raisonnable ;
- demandez une analyse avant correction lorsque la cause d'un problème n'est pas claire.

Avant de finaliser :

- relisez le résumé ;
- contrôlez le diff ;
- lancez les tests pertinents ;
- vérifiez qu'aucun fichier non lié n'a été modifié ;
- documentez les limites ou risques restants.

## Scénarios couverts

La documentation traite notamment des usages suivants :

- comprendre une base de code inconnue ;
- corriger un bug avec un changement minimal ;
- ajouter une petite fonctionnalité ;
- faire une revue de pull request ;
- travailler sur une interface web avec navigateur intégré ;
- produire un document ou un artefact ;
- mettre en place une automation ;
- ajouter une intégration externe ;
- nettoyer après une tâche ;
- écrire une instruction durable dans `AGENTS.md`.

## Personnalisation et sécurité

Codex peut être guidé par des instructions de projet, des fichiers `AGENTS.md`, des skills, des plugins, des serveurs MCP, des hooks et des automations.

Les opérations restent encadrées par les permissions, les approbations, le bac à sable, l'accès réseau et les politiques de l'organisation ou de l'environnement local. Les demandes doivent donc préciser les limites de fichiers, les commandes autorisées et les vérifications attendues lorsque le contexte est sensible.

## Sources

Ce README est synthétisé à partir de :

- `OpenAI_Codex_Ref_Man_FR.md`
- `OpenAI_Codex_UG_FR.md`
- `DTLonCodex_Manuel_de_reference.html`
- `DTLonCodex_Guide_utilisateur.html`

Les documents indiquent eux-mêmes comme sources principales les pages OpenAI Developers relatives à Codex Overview, Codex Quickstart, Codex App features, Codex CLI features, Codex customization, ainsi que la documentation liée à la configuration, aux permissions, au bac à sable, à MCP, aux skills et à l'automatisation.
