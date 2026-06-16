# OpenAI Codex - Manuel de r?f?rence

Version de travail fran?aise, d'apr?s l? documentation officielle OpenAI Codex et l? pr?sentation documentaire DEC/VSI.

## Pr?face

Ce manuel de r?f?rence d?crit les fonctions d'OpenAI Codex. Il ne constitue pas un guide d'utilisation pas ? pas. Les commandes, menus et fichiers sont mentionnes uniquement pour identifier les fonctions qu'ils exposent.

Codex est l'agent de d?veloppement logiciel d'OpenAI. Il assiste les activit?s de programmation, d'analyse de code, de revue, de correction d'anomalies, de migration, de documentation, de tests et d'automatisation de travaux de d?veloppement.

## Public vis?

Ce manuel s'adresse aux d?veloppeurs, mainteneurs, responsables techniques, ?quipes de revue et administrateurs qui doivent connaitre les fonctions disponibles dans Codex et les limites de chaque surface d'ex?cution.

## Structure du document

Ce manuel contient les chapitres suivants :

- Chapitre 1 : presentation fonctionnelle de Codex.
- Chapitre 2 : surfaces d'ex?cution.
- Chapitre 3 : mod?les, raisonnement et contexte.
- Chapitre 4 : outils et op?rations sur le code.
- Chapitre 5 : personnalisation.
- Chapitre 6 : s?curit?, bac ? sable et approbations.
- Chapitre 7 : automatisation et int?grations.
- Chapitre 8 : objets de reference.
- Chapitre 9 : entrees de commande et de configuration.
- Chapitre 10 : matrice fonctionnelle.

## Documents associ?s

Les sources officielles principales sont les pages OpenAI Developers suivantes : Codex Overview, Codex Quickstart, Codex app features, Codex CLI features, Codex customization, ainsi que les pages relatives ? l? configuration, aux permissions, au bac ? sable, ? MCP, aux skills, aux hooks, aux plugins, aux subagents et aux automations.

## Conventions

Les noms de fichiers, options, commandes, variables et identifiants sont indiques en chasse fixe. Les termes App, CLI, IDE Extension, Web, Local, Worktree et Cloud designent les surfaces et modes Codex officiels.

# 1. Vue d'ensemble fonctionnelle

Codex fournit un agent interactif capable de lire un espace de travail, raisonner sur son contenu, proposer un plan, modifier des fichiers, ex?cuter des commandes, v?rifier des resultats et rendre compte de son travail.

Les fonctions principales comprennent :

- g?n?ration et modification de code ;
- comprehension et explication de bases de code ;
- revue de changements ;
- diagnostic et correction d'erreurs ;
- ex?cution de commandes locales ou distantes selon l? surface ;
- production et v?rification d'artefacts ;
- gestion de t?ches paralleles ;
- interaction avec des outils externes ;
- automatisation de t?ches r?currentes.

Codex applique les instructions du fil de discussion, les consignes de projet, les r?gles de configuration et les contraintes de s?curit? disponibles dans l'environnement actif.

# 2. Surfaces d'ex?cution

## 2.1 Codex App

L? Codex App est une application de bureau pour macOS et Windows. Elle fournit une experience centree sur les fils Codex, les projets, les worktrees, les automatisations et les fonctions Git int?gr?es.

Elle comprend notamment une liste de projets, des fils de discussion par projet, des modes Local, Worktree et Cloud, un terminal int?gr? par fil, un panneau de differences Git, des fonctions Git courantes, un navigateur int?gr?, l? prise en charge des artefacts et l? prise en charge des skills, MCP, notifications, m?moires et automatisations.

## 2.2 Codex CLI

Le client CLI fournit une interface terminale plein ecran et des sous-commandes non interactives. Il permet de travailler depuis un r?pertoire local, de reprendre des sessions et d'ex?cuter Codex dans des workflows automatises.

Les fonctions CLI comprennent le mode interactif conversationnel, le lancement avec prompt initial, l? reprise de sessions pr?c?dentes, l? s?lection de mod?le, l'affichage et l? copie de sorties, l'historique de prompts, l'ex?cution non interactive, le serveur d'application et le mode distant.

## 2.3 Extension IDE

L'extension IDE place Codex dans l'editeur. Elle fournit un contexte issu des fichiers ouverts et permet d'ex?cuter des t?ches directement depuis le projet de l'editeur.

Elle prend en charge le mode agent par d?faut, l? lecture et l? modification dans le r?pertoire du projet, l? synchronisation avec l? Codex App lorsque les deux surfaces sont ouvertes sur le meme projet, les commandes IDE, les commandes slash et le contexte automatique des fichiers consultes.

## 2.4 Codex Web et Cloud

L? surface Web permet d'ex?cuter des t?ches Codex dans des environnements cloud configures. Les environnements cloud decouplent l'ex?cution de l? machine locale et permettent des t?ches paralleles ou deleguees.

Les fonctions cloud dependent de l? configuration d'environnement, de l'acces au d?p?t, des politiques r?seau et des int?grations actives.

## 2.5 Modes Local, Worktree et Cloud

Le mode Local travaille dans le r?pertoire courant du projet. Le mode Worktree isole les modifications dans un worktree Git s?par?. Le mode Cloud ex?cute le travail dans un environnement distant configure.

Les modes Local et Worktree s'ex?cutent sur l'ordinateur de l'utilisateur. Le mode Worktree fournit une isolation Git entre le travail courant et les changements produits par Codex.

# 3. Mod?les, raisonnement et contexte

## 3.1 Mod?les

Codex utilise des mod?les OpenAI adaptes aux t?ches de d?veloppement. L? documentation officielle indique `gpt-5.5` comme mod?le recommande pour l? plupart des t?ches Codex, avec un accent sur le codage complexe, l'utilisation d'outils, l? planification et les travaux multi-?tapes.

L? disponibilit? des mod?les depend du plan, de l? surface et des droits du compte.

## 3.2 Raisonnement

Codex peut decomposer une demande, ?tablir un plan, lire les fichiers pertinents, effectuer des modifications, lancer des v?rifications et ajuster son travail selon les resultats obtenus.

Le raisonnement est contraint par le contexte acc?ssible, les instructions syst?me et utilisateur, les r?gles du projet, les outils disponibles, les permissions, le bac ? sable et l? politique d'approbation.

## 3.3 Contexte de conversation

Un fil Codex conserve les messages, decisions, plans et resultats pertinents pour le travail en cours. Les sessions peuvent ?tre reprises lorsque l? surface le permet.

Le contexte peut comprendre le prompt courant, les messages pr?c?dents, le contenu de fichiers lus, les sorties de commandes, les images ou documents fournis, les consignes de projet et les donn?es d'outils connectes.

## 3.4 M?moires

Lorsque l? fonction est disponible, les m?moires transportent des informations stables entre fils, telles que preferences, conventions de projet ou habitudes r?currentes. Elles completent les consignes de projet mais ne remplacent pas les instructions explicites du fil.

# 4. Outils et op?rations sur le code

## 4.1 Lecture et modification de fichiers

Codex peut lire les fichiers acc?ssibles, analyser leur structure et produire des changements. Les modifications sont limitees par l'espace de travail, le bac ? sable et les permissions accordees.

## 4.2 Ex?cution de commandes

Codex peut ex?cuter des commandes vi? l? surface active, notamment pour inspecter un projet, lancer des tests, d?marrer un serveur local, formater du code ou v?rifier un resultat. L'ex?cution est soumise aux approbations et aux restrictions du bac ? sable.

## 4.3 Revue de code

Codex fournit une fonction de revue qui recherche anomalies, regressions, risques de comportement et lacunes de test. Dans l? Codex App, le panneau de diff permet d'examiner les changements, de commenter des lignes et de demander des corrections.

## 4.4 Git

Codex int?gr? ou utilise des fonctions Git selon l? surface : affichage de diff, staging, commit, push, cr?ation de pull request, travail en worktree et inspection de l'?tat du d?p?t.

## 4.5 Terminal int?gr?

Dans l? Codex App, chaque fil dispose d'un terminal associ? au projet ou au worktree. Ce terminal fournit un canal local pour les commandes de v?rification et d'exploitation du projet.

## 4.6 Navigateur int?gr? et Browser Use

L? Codex App fournit un navigateur int?gr? pour previsualiser, commenter et v?rifier des pages locales, des previews de fichiers ou des pages publiques ne necessitant pas de connexion.

Browser Use permet ? Codex d'operer certaines pages, notamment des serveurs de d?veloppement locaux et des previews de fichiers, lorsque les permissions et plugins requis sont presents.

## 4.7 Computer Use

Computer Use permet ? Codex d'interagir avec des applications macOS ou Windows en voyant, cliquant et tapant. Cette fonction vis? les tests d'applications de bureau, l? reproduction d'anomalies GUI et les flux non acc?ssibles par API ou plugin.

## 4.8 Entrees image et g?n?ration d'images

Codex accepte des images comme contexte. Il peut aussi g?n?rer ou modifier des images dans un fil lorsque l? fonction est disponible, notamment pour des assets d'interface, illustrations, placeholders ou sprites.

## 4.9 Artefacts non-code

Codex peut produire et v?rifier des artefacts tels que PDF, documents, feuilles de calcul et presentations. L? Codex App peut afficher ces artefacts dans l? barre laterale de t?che.

# 5. Personnalisation

## 5.1 AGENTS.md

`AGENTS.md` fournit des consignes durables pour un d?p?t ou une partie de d?p?t. Les fichiers les plus proches du r?pertoire de travail ont priorite sur les fichiers plus g?n?raux.

`AGENTS.md` sert ? d?crire les commandes de build et de test, conventions de code, attentes de revue, chemins ou fichiers ? privil?gier et instructions propres ? une arborescence.

## 5.2 Configuration

Codex peut ?tre configure par fichiers de configuration, variables d'environnement et reglages de surface. L? configuration couvre notamment mod?les, approbations, bac ? sable, outils, MCP, hooks et preferences d'ex?cution.

## 5.3 Skills

Les skills sont des capacit?s reutilisables, definies par un dossier contenant un fichier `SKILL.md` et, eventuellement, des scripts, references et assets.

Elles permettent d'encapsuler des workflows repetables, une expertise de domaine, des mod?les et ressources, des proc?dures avec validations et des int?grations indirectes vi? MCP.

## 5.4 Plugins

Les plugins sont des unites distribuables qui peuvent inclure skills, outils, serveurs MCP, hooks, assets ou applications. Ils servent ? empaqueter des capacit?s partageables.

## 5.5 MCP

Le Model Context Protocol relie Codex ? des outils et syst?mes externes. Les configurations MCP sont partagees entre l? Codex App, le CLI et l'extension IDE lorsque l? surface les prend en charge.

## 5.6 Hooks

Les hooks permettent d'associer des traitements ? des ?v?nements du cycle de vie Codex. Ils servent ? appliquer ou v?rifier des politiques techniques autour des op?rations de l'agent.

## 5.7 Subagents

Les subagents representent des agents specialises auxquels Codex peut deleguer des parties de travail. Ils sont destines aux t?ches qui beneficient d'une expertise ou d'un contexte specialise.

# 6. S?curit?, bac ? sable et approbations

## 6.1 Bac ? sable

Le bac ? sable definit les ressources acc?ssibles ? Codex : fichiers lisibles, emplacements modifiables, acc?s r?seau et autres capacit?s d'ex?cution. Par d?faut, Codex limite son travail au projet actif lorsque l? surface le permet.

## 6.2 Approbations

Les approbations determinent les op?rations qui exigent une confirmation de l'utilisateur ou une revue automatique. Elles peuvent ?tre accordees pour une action unique ou pour une portee plus large selon l? surface et l? politique.

## 6.3 Permissions

Les permissions contr?lent l'acces aux fichiers, commandes, r?seaux, applications locales et outils externes. Les permissions peuvent provenir de l? configuration locale, de l? politique admin ou d'une approbation utilisateur.

## 6.4R?seau

L'acces r?seau peut ?tre desactive, limite, mis en cache ou accorde selon le mode. L? recherche web de premiere partie est disponible dans certaines surfaces et peut fonctionner vi? cache ou resultats en direct selon l? configuration.

# 7. Automatisation et int?grations

## 7.1 Automations

Les automations ex?cutent des t?ches r?currentes ou planifiees. Elles peuvent produire rapports, v?rifier erreurs, surveiller changements ou continuer un suivi.

Les automations de fil conservent le contexte d'une conversation particuliere. Les automations de projet ou autonomes lancent des travaux r?currents avec un contexte de depart defini.

## 7.2 Mode non interactif

Le mode non interactif permet d'ex?cuter Codex dans des scripts ou cha?nes d'integration. Il convient aux t?ches definies par un prompt et une configuration.

## 7.3 Codex SDK

Le SDK Codex fournit une interface de programmation pour int?gr?r Codex dans des workflows applicatifs ou outils internes.

## 7.4 App Server et mode distant

L'app server permet ? un client Codex de se connecter ? un serveur distant par WebSocket ou socket local, avec m?canismes d'authentification appropries.

## 7.5 Int?grations GitHub, Slack et Linear

Les int?grations relient Codex ? des syst?mes de collaboration et de suivi. Leur disponibilit? depend de l'installation, des autorisations de compte et de l? configuration d'organisation.

# 8. Objets de reference

## 8.1 Projet

Un projet associ? Codex ? un r?pertoire ou d?p?t. Il definit le perim?tre de travail principal.

## 8.2 Fil

Un fil est une conversation op?rationnelle avec Codex. Il contient les demandes, reponses, plans, sorties et modifications associees ? une t?che ou serie de t?ches.

## 8.3 Worktree

Un worktree est une copie de travail Git s?par?e, utilisee pour isoler les modifications d'un fil par rapport au r?pertoire principal.

## 8.4 Chat

Un chat est un fil qui ne depend pas n?cessairement d'un dossier projet ou d?p?t. Il convient ? l? recherche, l? planification et les workflows d'outils connectes.

## 8.5 Skill

Une skill est un module d'instructions et de ressources reutilisables s?lectionne par Codex lorsqu'une t?che correspond ? s? description.

## 8.6 Plugin

Un plugin est un paquet installable qui regroupe des capacit?s Codex.

## 8.7 MCP server

Un serveur MCP expose des outils, ressources ou actions externes ? Codex.

## 8.8 Hook

Un hook est un traitement associ? ? un ?v?nement Codex.

## 8.9 Automation

Une automation est une ex?cution planifiee ou recurrente d'une instruction Codex.

## 8.10 Bac ? sable

Le bac ? sable est l'ensemble des limites d'acces appliquees aux actions de Codex.

# 9. Entrees de commande et de configuration

Ce chapitre d?crit les principales entrees fonctionnelles. Il ne constitue pas une proc?dure d'utilisation.

## 9.1 Commande `codex`

L? commande `codex` repr?sente le point d'entree principal du client terminal. Elle ouvre une session interactive lorsque lancee sans sous-commande et accepte un prompt initial lorsque du texte lui est fourni.

Fonctions associees :

- initialisation d'une conversation dans le r?pertoire courant ;
- s?lection d'un mod?le ou d'options de session ;
- interaction avec le bac ? sable et les approbations ;
- affichage de plans, diffs et sorties ;
- reprise ou delegation ? des sous-commandes.

## 9.2 Sous-commande `resume`

`resume` repr?sente l? fonction de reprise de session. Elle ratt?che une nouvelle ex?cution ? un transcript existant et conserve les ?l?ments de contexte pertinents de l? conversation pr?c?dente.

Les variantes de reprise distinguent l? derniere session, une session choisie dans une liste, une session sp?cifique par identifiant et, selon l'option, les sessions hors du r?pertoire courant.

## 9.3 Sous-commande `exec`

`exec` repr?sente l'ex?cution non interactive. Elle traite une instruction fournie au lancement et produit une sortie destinee aux scripts, cha?nes d'integration ou t?ches reproductibles.

Cette fonction conserve les contraintes de s?curit? de Codex : bac ? sable, approbations, configuration, instructions de projet et limites d'outils.

## 9.4 Sous-commandes serveur

Les fonctions serveur, notamment l'app server et les modes distants, exposent une session Codex ? un client se connectant par canal local ou WebSocket. Elles fournissent une s?paration entre le processus de service et le client d'interaction.

Les fonctions serveur comprennent :

- ecoute sur une adresse locale ou distante ;
- authentification par jeton ou m?canisme configure ;
- connexion de clients distants ;
- contr?le d'une session depuis une autre surface.

## 9.5 Commandes slash

Les commandes slash representent des actions de session disponibles dans les interfaces interactives. Elles exposent des fonctions telles que l'affichage d'?tat, le changement de mod?le, l? gestion de contexte, l? sortie de session ou l'acces ? l'aide.

L? disponibilit? exacte varie selon CLI, IDE et App.

## 9.6 Fichier `AGENTS.md`

`AGENTS.md` est un fichier d'instructions durables. Il est lu comme guidance de projet et peut exister ? plusieurs niveaux : global utilisateur, racine du d?p?t et sous-r?pertoires. Les fichiers plus proches du r?pertoire de travail definissent les consignes les plus sp?cifiques.

Attributs fonctionnels :

- portee durable ;
- versionnable avec le d?p?t lorsqu'il est place dans le projet ;
- priorite par proximite ;
- adaptation du comportement de Codex avant le travail ;
- support des conventions, commandes et attentes de revue.

## 9.7 Fichier de configuration

Le fichier de configuration Codex repr?sente les reglages persistants du client et de l'agent. Il peut definir les valeurs par d?faut relatives au mod?le, aux permissions, au bac ? sable, aux serveurs MCP, aux hooks et aux preferences d'ex?cution.

Les reglages effectifs resultent de l? combinaison entre configuration globale, configuration projet, options de lancement, politiques gerees et choix d'interface.

## 9.8 Variables d'environnement

Les variables d'environnement fournissent un canal de configuration externe au fichier de configuration. Elles conviennent aux secrets, aux chemins propres ? l'environnement et aux reglages injectes par une cha?ne d'ex?cution.

Une variable d'environnement peut ?tre ignoree ou surclassee si l? surface, l? politique d'organisation ou l? configuration active impose une autre valeur.

## 9.9 R?gles et hooks

Les r?gles definissent des politiques d'autorisation ou de refus autour des commandes et actions. Les hooks fournissent des points d'ex?cution autour d'?v?nements Codex.

Les r?gles sont declaratives. Les hooks sont proceduraux. Les deux m?canismes completent les approbations utilisateur et les limites du bac ? sable.

## 9.10 Profils de permissions

Les profils de permissions representent des ensembles de capacit?s accordees ou refusees : lecture, ecriture, ex?cution, acc?s r?seau, acc?s ? des r?pertoires supplementaires ou utilisation d'outils externes.

Les profils peuvent ?tre definis localement, geres par une organisation ou demandes pendant une session.

# 10. Matrice fonctionnelle

## 10.1 Fonctions par surface

L? Codex App couvre les fils paralleles, worktrees, terminal int?gr?, diffs Git, artefacts, navigateur int?gr?, automations, notifications et synchronisation IDE.

Le CLI couvre l'interaction terminale, les sessions scriptables, l? reprise de conversation, les modes non interactifs, les options de lancement et les modes serveur ou distant.

L'extension IDE couvre le contexte de l'editeur, les fichiers ouverts, les s?lections, les commandes IDE et l'iteration directement dans l'environnement de d?veloppement.

Codex Web et Cloud couvrent l'ex?cution distante, les environnements configures, les t?ches deleguees et les int?grations cloud.

## 10.2 Fonctions par type de t?che

Pour comprehension de code, Codex utilise lecture de fichiers, analyse de structure, synthese et explication.

Pour modification de code, Codex utilise planification, edition, ex?cution de commandes, v?rification et r?sum?.

Pour revue, Codex utilise inspection de diff, recherche de bugs, risques, regressions et tests manquants.

Pour automatisation, Codex utilise prompts r?currents, contexte de projet, worktrees ou environnement local, skills et notifications.

Pour integration externe, Codex utilise MCP, plugins, connecteurs, API ou surfaces cloud selon l? configuration.

## 10.3 Relations entre m?canismes

`AGENTS.md` d?crit les r?gles durables du d?p?t. Les skills decrivent des workflows reutilisables. Les plugins empaquetent des capacit?s. MCP connecte Codex ? des syst?mes externes. Les hooks imposent des traitements autour d'?v?nements. Les automations planifient l'ex?cution.

Ces m?canismes sont complementaires : `AGENTS.md` oriente le comportement, les skills decrivent comment realiser des workflows, MCP donne acc?s ? des donn?es ou actions, les hooks encadrent l'ex?cution et les automations declenchent le travail dans le temps.

# Sources

- OpenAI Developers, Codex Overview, consulte le 12 juin 2026.
- OpenAI Developers, Codex Quickstart, consulte le 12 juin 2026.
- OpenAI Developers, Codex app features, consulte le 12 juin 2026.
- OpenAI Developers, Codex CLI features, consulte le 12 juin 2026.
- OpenAI Developers, Codex customization, consulte le 12 juin 2026.
- OpenAI Developers, documentation Codex liee ? sandboxing, configuration, MCP, skills et automatisation, consultee le 12 juin 2026.
