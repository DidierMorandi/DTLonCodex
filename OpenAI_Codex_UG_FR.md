# OpenAI Codex - Guide utilisateur

Version de travail fran?aise, d'apr?s l? documentation officielle OpenAI Codex et l? pr?sentation documentaire DEC/VSI.

## Pr?face

Ce guide explique comment se servir d'OpenAI Codex pour travailler sur du code, reviser des changements, automatiser des t?ches et exploiter les surfaces App, CLI, IDE et Web.

Il suppose que l'utilisateur dispose d'un compte ou d'une cle API autorisee et que Codex est disponible dans son plan ou son organisation.

## Public vis?

Ce guide s'adresse aux utilisateurs qui veulent lancer Codex, choisir une surface, confier une t?che, examiner les changements et r?gler les principaux m?canismes de personnalisation et de s?curit?.

## Structure du document

Ce guide contient les chapitres suivants :

- Chapitre 1 : d?marrage et choix de surface.
- Chapitre 2 : utilisation de l? Codex App.
- Chapitre 3 : utilisation du CLI.
- Chapitre 4 : utilisation de l'extension IDE.
- Chapitre 5 : utilisation de Codex Web et Cloud.
- Chapitre 6 : guider Codex.
- Chapitre 7 : v?rifier et finaliser le travail.
- Chapitre 8 : personnaliser Codex.
- Chapitre 9 : permissions, bac ? sable et d?pannage courant.
- Chapitre 10 : scenarios courants.

## Conventions

Les commandes sont donn?es en chasse fixe. Les exemples doivent ?tre adaptes au projet, au shell et aux r?gles locales. Les op?rations qui modifient des fichiers, ex?cutent des commandes ou accedent au r?seau peuvent demander une approbation.

# 1. D?marrer

## 1.1 Choisir l? surface ? utiliser

Utilisez l? Codex App lorsque vous voulez piloter plusieurs projets, gerer des fils en parallele, travailler avec des worktrees, examiner des diffs et utiliser les fonctions int?gr?es de bureau.

Utilisez le CLI lorsque vous travaillez principalement dans un terminal ou que vous voulez automatiser des t?ches.

Utilisez l'extension IDE lorsque vous voulez que Codex voie naturellement le contexte de l'editeur et travaille au plus pres des fichiers ouverts.

Utilisez Codex Web ou Cloud lorsque vous voulez deleguer un travail ? un environnement distant configure.

## 1.2 Pr?parer un projet

Avant de lancer une t?che :

1. Ouvrez le dossier du projet.
2. V?rifiez l'?tat Git.
3. Notez les commandes de test ou de v?rification importantes.
4. D?crivez clairement le resultat attendu.
5. Pr?cisez les limites : fichiers ? ne pas toucher, style ? conserver, tests ? ex?cuter.

Il est prudent de cr?er un point de contr?le Git avant une t?che qui peut modifier le code.

## 1.3 Rediger une bonne demande

Une demande efficace contient l'objectif, le contexte utile, les contraintes, les fichiers ou zones concernees, le niveau de risque accepte et l? v?rification attendue.

Exemple :

```text
Trouve pourquoi le test de paiement echoue et corrige uniquement l? cause probable.
Lis d'abord les fichiers de test et de service de paiement.
Garde les changements minimaux et lance le test concerne.
```

# 2. Utiliser l? Codex App

## 2.1 Installer et ouvrir

Installez l'application Codex pour macOS ou Windows depuis l? page officielle. Ouvrez l'application, puis connectez-vous avec un compte ChatGPT ou une cle API OpenAI.

Certaines fonctions peuvent varier selon le mode d'authentification, le plan et les politiques d'organisation.

## 2.2 S?lectionner un projet

Dans l'application, ajoutez ou s?lectionnez le dossier du projet. Un projet correspond ? un codebase ou ? une partie coherentement bornee d'un codebase.

Si un d?p?t contient plusieurs applications independantes, cr?ez des projets distincts afin de garder un perim?tre de travail clair.

## 2.3 Choisir le mode du fil

Au lancement d'un fil, choisissez un mode :

- Local : Codex travaille dans le dossier courant.
- Worktree : Codex cr?e un worktree Git pour isoler les changements.
- Cloud : Codex travaille dans un environnement distant configure.

Choisissez Worktree pour essayer une idee, ex?cuter plusieurs t?ches en parallele ou proteger votre r?pertoire courant.

## 2.4 Envoyer une premiere demande

Dans le compositeur, d?crivez l? t?che. Pour un premier contact avec un projet, demandez une analyse :

```text
Explique l'organisation de ce projet et indique les commandes utiles pour le tester.
```

Pour une modification ciblee :

```text
Ajoute l? validation manquante dans le formulaire d'inscription.
Respecte le style existant et lance les tests pertinents.
```

## 2.5 Suivre le travail

Pendant l'ex?cution, surveillez le plan propose, les fichiers lus, les commandes demandees, les changements produits, les messages d'erreur et les demandes d'approbation. Reorientez Codex si le travail sort du perim?tre voulu.

## 2.6 Utiliser le terminal int?gr?

Chaque fil dispose d'un terminal associ? au projet ou au worktree. Utilisez-le pour lancer des commandes de v?rification :

```text
git status
npm test
pnpm run lint
```

Codex peut lire l? sortie du terminal lorsque l? surface le permet. Vous pouvez donc lui demander d'analyser un ?chec de test d?j? visible.

## 2.7 Examiner les differences Git

Ouvrez le panneau de diff pour voir les fichiers modifies. V?rifiez que les bons fichiers ont change, que les modifications sont minimales, que les tests ou preuves sont presents et qu'aucune donn?e sensible n'? ete ajoutee.

Ajoutez des commentaires inline si vous voulez que Codex corrige une ligne ou une section pr?cise.

## 2.8 Commit, push et pull request

Lorsque les changements sont corrects, utilisez les fonctions Git int?gr?es ou le terminal pour pr?parer le commit.

Avant de pousser :

1. Relisez le diff.
2. Lancez les tests requis.
3. V?rifiez le message de commit.
4. Cr?ez l? pull request si le workflow du projet le demande.

## 2.9 Utiliser le navigateur int?gr?

Pour v?rifier une application web locale :

1. Demarrez le serveur de d?veloppement.
2. Ouvrez l? page dans le navigateur int?gr?.
3. Inspectez le rendu.
4. Ajoutez des commentaires sur les ?l?ments visuels ? corriger.
5. Demandez ? Codex d'appliquer les corrections.

Le navigateur int?gr? ne remplace pas un navigateur connecte ? votre profil. Il n'est pas destine aux flux d'authentification complexes.

## 2.10 Utiliser des images et artefacts

Glissez une image dans le prompt pour l? fournir comme contexte. Pour des documents, feuilles de calcul, presentations ou PDF, indiquez le type de fichier attendu, l? structure, les criteres de v?rification et le chemin de sortie souhaite si n?cessaire.

# 3. Utiliser le CLI

## 3.1 Lancer une session interactive

Depuis le r?pertoire du projet :

```text
codex
```

Vous pouvez aussi fournir une demande initiale :

```text
codex "Explique cette base de code"
```

Codex ouvre une interface terminale interactive qui peut lire le d?p?t, proposer un plan, modifier des fichiers et ex?cuter des commandes selon les autorisations.

## 3.2 Interagir pendant une session

Pendant une session CLI, envoyez des prompts et extraits de code, examinez les plans et diffs, acceptez ou refusez les op?rations contr?lees, utilisez les commandes slash disponibles et quittez l? session lorsque le travail est termine.

## 3.3 Reprendre une session

Pour rouvrir une session recente :

```text
codex r?sum?
```

Pour reprendre l? derniere session du r?pertoire courant :

```text
codex r?sum? --last
```

Pour afficher aussi les sessions d'autres r?pertoires :

```text
codex r?sum? --all
```

L? reprise conserve le transcript, l'historique de plan et le contexte utile de l? session.

## 3.4 Lancer avec un mod?le particulier

Lorsque vous devez choisir explicitement un mod?le :

```text
codex --model gpt-5.5
```

Dans une session, utilisez l? commande de changement de mod?le fournie par l'interface.

## 3.5 Ex?cuter en mode non interactif

Pour des workflows automatises, utilisez le mode non interactif lorsque disponible :

```text
codex exec "Execute les tests et r?sum? les ?checs"
```

Le mode non interactif convient aux t?ches bornees. Fournissez un prompt pr?cis et configurez les permissions avant de l'int?gr?r ? une cha?ne automatique.

## 3.6 Utiliser le mode distant

Un serveur d'application peut exposer une connexion WebSocket. Le client CLI peut s'y connecter avec une URL distante et une authentification configuree.

N'utilisez une connexion non chiffree que pour `localhost` ou un tunnel de confiance. Pour une machine distante, prevoyez authentification et TLS selon les r?gles officielles.

# 4. Utiliser l'extension IDE

## 4.1 Installer l'extension

Installez l'extension Codex dans l'editeur pris en charge. Ouvrez ensuite le panneau Codex depuis l? barre laterale.

## 4.2 Se connecter

Connectez-vous avec votre compte ChatGPT ou une cle API OpenAI. L'extension demarre en mode agent par d?faut lorsque l? configuration l'autorise.

## 4.3 Travailler avec le contexte de l'editeur

Ouvrez les fichiers pertinents avant de poser une question. Vous pouvez demander :

```text
Explique le fichier ouvert et indique les fonctions ? risque.
```

Ou :

```text
Corrige le probleme dans l? fonction s?lectionnee sans modifier l'API publique.
```

## 4.4 Synchroniser avec l? Codex App

Lorsque l? Codex App et l'extension IDE sont ouvertes sur le meme projet, elles peuvent synchroniser le contexte et les fils. Utilisez cette synchronisation pour alterner entre travail dans l'editeur et revue plus large dans l'application.

# 5. Utiliser Codex Web et Cloud

## 5.1 Choisir une t?che cloud

Utilisez Cloud pour les t?ches qui peuvent s'ex?cuter dans un environnement distant : analyse de d?p?t, correction isolee, migration, g?n?ration de tests, revue ou t?che parallele longue.

Evitez d'envoyer une t?che cloud lorsque le resultat depend d'un fichier local non pousse, d'un secret local ou d'un outil indisponible dans l'environnement.

## 5.2 Configurer l'environnement

Avant de confier une t?che cloud, v?rifiez l'acces au d?p?t, les dependances, les commandes de test, l'acces r?seau, les variables et secrets autorises, ainsi que les politiques d'organisation.

## 5.3 Recuperer les resultats

Examinez le r?sum?, les fichiers modifies, les logs et les tests ex?cutes. Ramenez les changements dans votre workflow Git selon les proc?dures du projet.

# 6. Guider Codex

## 6.1 Donner des instructions courtes et verifiables

Preferez :

```text
Ajoute un test pour le cas ou le montant est nul, puis corrige l? validation si le test echoue.
```

Evitez les demandes trop larges sans critere :

```text
Ameliore tout le module.
```

## 6.2 Encadrer les changements

Indiquez clairement les fichiers autorises, les fichiers interdits, le niveau de refactorisation accepte, les tests obligatoires et le format de reponse attendu.

## 6.3 Demander une revue

Pour une revue de code :

```text
Fais une revue de ce diff. Priorise les bugs, regressions, risques de s?curit? et tests manquants.
Ne modifie pas les fichiers.
```

## 6.4 Demander une correction prudente

Pour une correction :

```text
Trouve l? cause l? plus probable de l'?chec et corrige-l? avec le plus petit changement raisonnable.
Explique les fichiers modifies et les tests lances.
```

## 6.5 Fournir des preuves attendues

Ajoutez l? v?rification desiree :

```text
Lance le test unitaire concerne et indique le resultat exact.
Si le test ne peut pas ?tre lance, explique pourquoi.
```

# 7. V?rifier et finaliser

## 7.1 Lire le r?sum?

? l? fin d'une t?che, v?rifiez que le r?sum? repond ? l? demande initiale : objectif atteint, fichiers modifies, tests lances, limitations et suites possibles.

## 7.2 Contr?ler le diff

Avant de valider :

```text
git status
git diff
```

Assurez-vous qu'aucun fichier non lie n'est modifie.

## 7.3 Lancer les tests

Lancez les tests recommandes par Codex ou ceux du projet :

```text
npm test
pnpm test
pytest
cargo test
```

Adaptez ces commandes ? votre stack.

## 7.4 Demander une deuxieme passe

Si un detail manque :

```text
Le changement est bon, mais ajoute un test pour le cas limite X et relance uniquement ce test.
```

Si le resultat est trop large :

```text
Reviens ? une correction plus minimale. Garde uniquement les changements n?cessaires au bug signale.
```

# 8. Personnaliser Codex

## 8.1 Ajouter un fichier AGENTS.md

Dans le d?p?t, cr?ez un fichier `AGENTS.md` pour les r?gles durables :

```markdown
# Instructions pour Codex

- Utiliser pnpm, pas npm.
- Lancer `pnpm test` avant de proposer un commit.
- Ne pas modifier les fichiers g?n?res dans `dist/`.
- Pour les composants React, suivre les patterns de `src/components`.
```

Placez un `AGENTS.md` plus sp?cifique dans un sous-r?pertoire si des r?gles diff?rentes s'appliquent ? cette zone.

## 8.2 Mettre ? jour AGENTS.md apres une erreur recurrente

Si Codex repete une mauvaise hypothese, demandez-lui de formaliser l? correction :

```text
Ajoute dans AGENTS.md que les migrations de base de donn?es doivent ?tre cr?ees avec l'outil interne, pas ? l? main.
```

## 8.3 Utiliser une skill

Utilisez une skill lorsqu'un workflow revient souvent : release, revue, g?n?ration de documentation, v?rification de donn?es ou cr?ation d'artefact.

Vous pouvez invoquer explicitement une skill si son nom est connu :

```text
$nom_de_skill Pr?pare l? note de version ? partir du diff courant.
```

## 8.4 Configurer MCP

Utilisez MCP lorsque Codex doit acceder ? des outils ou donn?es externes : tickets, docs internes, bases de connaissances, d?p?ts, services de design ou autres syst?mes d'?quipe.

Dans l? Codex App, ouvrez l? section MCP des reglages pour activer un serveur recommande ou ajouter une configuration.

## 8.5 Utiliser les hooks

Employez les hooks pour automatiser des contr?les autour des actions Codex, par exemple v?rifier une politique avant une commande ou journaliser certains ?v?nements.

## 8.6 Utiliser les automations

Pour cr?er une t?che recurrente, d?crivez l? frequence, le projet concerne, l? demande, le resultat attendu et le canal de notification ou de r?sum?.

Exemple :

```text
Cr?e une automation quotidienne qui v?rifie les ?checs de tests recents et produit un court rapport.
```

Utilisez une automation de fil lorsque l? r?currence doit conserver le contexte de l? conversation courante.

# 9. Permissions, bac ? sable et d?pannage

## 9.1 Comprendre les approbations

Lorsque Codex demande une approbation, lisez l'action demandee, les fichiers ou ressources concernes, l? dur?e de l'autorisation et le niveau de risque.

Si vous hesitez, accordez l? portee l? plus etroite ou refusez et demandez une autre approche.

## 9.2 Comprendre le bac ? sable

Le bac ? sable limite l'acces de Codex. Si une commande echoue par manque d'acces, choisissez entre accorder une permission ciblee, deplacer les fichiers n?cessaires dans le projet, demander une solution qui n'? pas besoin de cet acc?s ou ouvrir un projet plus adapte.

## 9.3 Gerer l'acces r?seau

Si Codex doit v?rifier une information recente ou installer une dependance, il peut avoir besoin du r?seau. Accordez l'acces seulement si l? t?che le justifie et si l? politique du projet l'autorise.

## 9.4 Quand Codex ne trouve pas les bons fichiers

Donnez une indication de routage :

```text
Lis d'abord `src/payments/` et `tests/payments/`. Ignore `legacy/` sauf si n?cessaire.
```

Si cette indication ser? utile ? long terme, ajoutez-l? dans `AGENTS.md`.

## 9.5 Quand Codex propose trop de changements

Reformulez avec une contrainte explicite :

```text
Reduis le changement au minimum n?cessaire. Pas de refactorisation hors du fichier concerne.
```

## 9.6 Quand les tests echouent

Demandez une analyse bornee :

```text
Analyse cet ?chec de test. Ne modifie rien avant d'avoir identifie l? cause probable.
```

Puis, si l? cause est claire :

```text
Applique l? correction minimale et relance ce test uniquement.
```

## 9.7 Quand utiliser une autre surface

Passez ? l'IDE si le contexte principal est un fichier ouvert ou une s?lection. Passez ? l? Codex App si vous devez gerer des fils, worktrees, diffs et artefacts. Passez au CLI si le travail est terminal-first ou scriptable. Passez au Cloud si l? t?che doit ?tre deleguee ? distance.

# 10. Scenarios courants

## 10.1 Comprendre une base de code inconnue

Demandez d'abord une cartographie avant toute modification :

```text
Explique l'organisation de ce projet. Identifie les modules principaux, les commandes de v?rification et les fichiers ? lire avant de modifier le code.
Ne modifie rien.
```

Si le projet est volumineux, bornez l? recherche :

```text
Concentre-toi sur le parcours d'authentification. Lis les fichiers pertinents et r?sum? le flux de bout en bout.
```

Lorsque l? synthese est correcte, demandez ? Codex de proposer une consigne durable :

```text
Propose une section AGENTS.md courte pour aider les procha?nes sessions ? trouver les bons fichiers d'authentification.
```

## 10.2 Corriger un bug avec risque faible

Commencez par l? reproduction :

```text
Reproduis ou localise l'?chec signale. Ne corrige rien avant d'avoir indique l? cause probable et les fichiers concernes.
```

Puis demandez l? correction :

```text
Applique l? correction minimale pour cette cause probable. Evite toute refactorisation non n?cessaire. Lance le test le plus cible.
```

Terminez par une v?rification :

```text
Resume le changement, le test lance et les risques restants.
```

## 10.3 Ajouter une petite fonctionnalite

Fournissez l? definition de fini :

```text
Ajoute le filtre "archives" ? l? liste des dossiers.
Le filtre doit ?tre visible dans l'interface, persiste dans l'URL et couvert par un test.
Respecte les patterns existants.
```

Si Codex propose une architecture trop large :

```text
Garde l'implementation locale ? ce module. Ne cr?e pas de nouvelle abstraction sauf si elle existe d?j? dans le projet.
```

## 10.4 Faire une revue de pull request

Dans une surface qui voit le diff, demandez :

```text
Fais une revue de ce diff comme reviewer senior.
Liste d'abord les bugs ou regressions probables, avec fichier et ligne.
Mentionne ensuite les tests manquants.
Ne commente pas le style sauf s'il cache un risque.
```

Pour transformer l? revue en corrections :

```text
Corrige uniquement les points P1 et P2 de l? revue. Laisse le reste intact.
```

## 10.5 Travailler sur une interface web

Demarrez le serveur local, puis demandez ? Codex de v?rifier :

```text
Ouvre l'application locale dans le navigateur int?gr?, v?rifie l? page de connexion et corrige les problemes visibles de mise en page.
Teste desktop et mobile si possible.
```

Ajoutez des commentaires dans le navigateur int?gr? si un ?l?ment visuel pr?cis doit ?tre corrige, puis demandez :

```text
Traite les commentaires du navigateur et v?rifie ? nouveau le rendu.
```

## 10.6 Produire un document ou artefact

Donnez l? forme attendue :

```text
Cr?e un document Markdown de reference pour ce module.
Structure : preface, public vise, concepts, API, erreurs, exemples.
Ne documente que le comportement present dans le code.
```

Pour un artefact bureautique :

```text
Cr?e une presentation de 8 diapositives ? partir de ces notes.
Ajoute une diapositive de synthese, une diapositive risques et une diapositive procha?nes ?tapes.
V?rifie le rendu avant de me donner le fichier.
```

## 10.7 Mettre en place une automation

D?crivez l? r?currence et le resultat attendu :

```text
Cr?e une automation hebdomadaire pour ce projet.
Chaque lundi matin, elle doit v?rifier les dependances obsoletes, r?sum?r les mises ? jour importantes et ne modifier aucun fichier.
```

Pour un suivi dans le meme fil :

```text
Ajoute une automation de fil qui me relance toutes les 30 minutes tant que le deploiement n'est pas termine.
```

## 10.8 Ajouter une integration externe

Lorsque l'information vit hors du d?p?t, preferez MCP ou un plugin :

```text
Configure ou utilise le connecteur approprie pour lire le ticket Linear lie ? cette branche, puis r?sum? les criteres d'acceptation.
```

Si l'outil n'est pas disponible :

```text
Indique quelle integration manque, quelles permissions seraient n?cessaires et quelle information je peux te fournir manuellement.
```

## 10.9 Nettoyer apres une t?che

Avant de clore :

```text
V?rifie l'?tat Git, liste les fichiers modifies et indique les commandes de test ex?cutees.
Signale tout fichier non lie ? l? t?che.
```

Si les changements doivent ?tre s?par?s :

```text
Propose un decoupage en commits logiques. Ne stage rien sans confirmation.
```

## 10.10 Ecrire une instruction durable

Apres plusieurs corrections de trajectoire, demandez :

```text
Transforme mes corrections r?currentes en instructions AGENTS.md courtes, sans dupliquer ce qui existe d?j?.
```

Relisez l? proposition avant de l'accepter. Les instructions durables doivent rester petites, sp?cifiques et utiles aux procha?nes sessions.

# Sources

- OpenAI Developers, Codex Overview, consulte le 12 juin 2026.
- OpenAI Developers, Codex Quickstart, consulte le 12 juin 2026.
- OpenAI Developers, Codex app features, consulte le 12 juin 2026.
- OpenAI Developers, Codex CLI features, consulte le 12 juin 2026.
- OpenAI Developers, Codex customization, consulte le 12 juin 2026.
- OpenAI Developers, documentation Codex liee ? sandboxing, configuration, MCP, skills et automatisation, consultee le 12 juin 2026.
