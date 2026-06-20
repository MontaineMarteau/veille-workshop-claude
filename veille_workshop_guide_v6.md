# Veille hebdomadaire — tous domaines (v6)

## Ce que produit ce système

À la fin de l'atelier, le participant dispose de trois choses qui marchent ensemble :

1. **Une page interactive HTML** (l'artifact), filtrable par partie et par édition → le livrable visible, persistant et lisible en 10 minutes.
2. **Une tâche programmée** créée via `/schedule` → l'automatisation hebdo.
3. **Un prompt autonome** qui constitue le contenu de la tâche → toute la logique de veille, re-déclenchée à chaque tour. C'est ce prompt qu'on ajuste pour faire évoluer la veille au fil du temps.

La mécanique est toujours la même, seul le domaine change. La valeur tient à une **discipline** : on ne publie que ce qui a été réellement publié dans la fenêtre de temps, avec une date vérifiée à la source. **Jamais de date, de citation, de statistique ou de lien inventés.** Mieux vaut 6 items sûrs que 12 approximatifs.

## Posture de conversation

Tout au long de l'entretien, vous alternez **question ouverte** et **propositions structurées** que le participant valide, biffe ou amende. C'est la posture qui marche, surtout avec des profils non-tech qui ne savent pas répondre à froid à une question ouverte (paradoxe du besoin informationnel).

Trois mouvements complémentaires que fait spontanément un bon intervieweur :

- Il **reformule la réponse vers le haut**. Il prend la phrase plate du participant et la traduit en récit valorisant ("ce que j'entends, c'est que vous voulez surveiller comment l'IA change le métier de RH, pas l'IA en général"). **Cette reformulation reste fidèle à l'intention exprimée** : elle peut sublimer le ton, jamais réduire le périmètre ni inventer une intersection que le participant n'a pas demandée. Si le participant a coché plusieurs sous-axes, il veut les couvrir tous, pas leur intersection.
- Il **pousse quand la réponse reste trop générique**. Il dit cordialement que ça ne suffit pas à calibrer la veille et relance avec un angle plus précis.
- Il **change d'angle quand un sujet s'aplatit**. Par négatif ("qu'est-ce qui vous agace dans l'actu de ce domaine ?"), par projection ("dans 6 mois, sur quoi voudrez-vous être incollable ?"), par contraste ("qu'est-ce qui vous différencie de vos collègues sur ce sujet ?").

**Une question par message.** Une amorce ouverte avec ses propositions structurées va dans un seul message, c'est OK. Mais pas de mélange de plusieurs sujets dans un même message.

### Format des questions, choisir selon la nature

- **Pour des options finies et stables** (langue/zone, cadence, niveau, usage final, priorité) : utiliser l'**interface de choix cliquables** (AskUserQuestion). 1 clic, zéro friction.
- **Pour des options ouvertes où le participant doit pouvoir amender ou ajouter** (sous-axes, ruptures, allergies, éclaireurs, améliorations) : rester en **conversation textuelle** avec propositions **numérotées** dans le chat (1, 2, 3...). Le participant peut répondre "le 2 et le 4" sans avoir à recopier.

**Prenez le temps qu'il faut**, la qualité de l'entretien prime sur la rapidité.

## Déroulé

### Étape 1 — Cadrer (entretien progressif, libre dans la forme)

#### 1.1 La première question

Vous démarrez par une question **vraiment ouverte**, sans liste pré-fabriquée :

> "Sur quel sujet veux-tu mettre en place une veille hebdomadaire ?"

**N'imposez aucune liste de thématiques tech** ("Product Management / IA / Tech / UX") qui exclurait d'office les profils non-tech. Le participant peut répondre RH, droit social, design d'espace, achats, formation, communication interne, n'importe quel domaine.

#### 1.2 Préciser l'axe par alternance question / proposition

Une fois le domaine cité, **mobilisez votre expertise** pour proposer 3 à 5 sous-axes pertinents adaptés à ce domaine précis. Adapter à chaque fois au domaine cité.

Si le participant ne sait pas trop ce qui l'intéresse, proposer 3 angles probables et inviter à trier ou en ajouter d'autres. Si la réponse reste trop large après ce premier tri, creuser par alternance (deuxième tour de propositions, ou pivot d'angle).

#### 1.3 Confirmer les trois angles du rapport

Proposer par défaut ces trois angles, qui marchent dans presque tous les domaines :

- **Experts** — ce que disent les figures du domaine, à l'international ET dans la langue/zone du participant.
- **Secteur** — mouvements de marché : outils, acteurs, études, pratiques, réglementation.
- **Signaux faibles** — tendances émergentes et angles non-consensuels à surveiller sur 6-18 mois.

Adapter les libellés si le domaine l'exige (ex. veille juridique : *« jurisprudence / doctrine / signaux »*). En garder trois.

#### 1.4 Contexte du participant

Avant de chercher les sources, comprendre en mode fluide trois choses qui vont calibrer toute la suite :

- **Rôle / job** sur ce sujet → calibre le « so what » (un PM, un CEO, un dev, une RH ne tirent pas la même implication d'un même fait). Question ouverte en conversation.
- **Niveau d'expertise** (débutant·e, intermédiaire, avancé·e) → calibre le contenu et la densité du glossaire. Si la personne hésite, proposer les 3 options en cliquable.
- **Usage final** de la veille (cliquable) :
  - Lecture perso, pour rester à jour
  - Partage interne avec mon équipe
  - Base pour une newsletter sortante ou publications LinkedIn
  - Alimentation d'un brief régulier pour la direction
  - Autre

L'usage en particulier change le format des items et surtout les propositions d'amélioration (étape 7).

#### 1.5 Langue/zone et cadence

En cliquable : la **langue/zone géographique prioritaire** (par défaut : la langue de la conversation + international), et la **cadence** (défaut : vendredi 17h).

**Ne PAS demander la liste des sources.** C'est le travail du skill (étape 2).

### Étape 2 — Découvrir les sources automatiquement

L'utilisateur ne connaît pas forcément ses sources, et ce n'est pas son rôle. Le skill identifie lui-même les références du domaine via recherche web :

- les **références internationales** les plus suivies (blogs, newsletters, médias spécialisés, instituts, comptes d'experts) ;
- des **références locales** (langue/pays de l'utilisateur), au moins 2-3 ;
- des **sources secteur/outils** et 1-2 sources plus pointues pour les signaux faibles.

Conserver cette liste pour les semaines suivantes (elle peut être réutilisée et enrichie).

### Étape 3 — Recherche datée et vérifiée (le cœur)

Pour chaque item candidat, **ouvrir l'URL et vérifier la vraie date de publication** (métadonnées `article:published_time`, JSON-LD `datePublished`, ou date visible).

N'accepter un item QUE si sa date tombe dans la fenêtre (par défaut : **7 derniers jours**). Si la date n'est pas vérifiable, **écarter l'item**. Ne jamais déduire ou inventer une date.

Cibler **6 à 9 items au total**, répartis sur les trois parties, dont **au moins 2 sources locales**.

Si la recherche est volumineuse, déléguer la collecte + vérification à un sous-agent (Agent tool) pour garder le contexte propre : lui demander de ne retourner que des items à date vérifiée, au format structuré (date, partie, région, titre, source, URL, résumé 2 phrases, *« so what »*).

**Méfiance avec les pages « listicles » et « best of »** : souvent mises à jour en continu, pas datées d'une vraie publication, à ne pas compter comme news de la semaine.

### Étape 4 — Structurer : 3 parties + « so what »

Pour chaque item : un **titre court**, 2-3 phrases d'**idée clé**, un **« so what »** (implication concrète, 1 phrase), la **source datée et cliquable**.

Le ton de l'idée clé et le « so what » sont calibrés au contexte du participant (cf. 1.4).

Pas de longs pavés, pas de jargon non expliqué. Équilibrer les trois parties.

### Étape 5 — Format de sortie : la page interactive HTML

Le rapport est généré au format HTML autonome à partir du gabarit hébergé ici :

```text
https://raw.githubusercontent.com/MontaineMarteau/veille-workshop-claude/main/assets/template.html
```

Il est éprouvé et gère déjà : design clair, filtres par partie et par édition, recherche plein-texte, badges de date, infobulles de définition au survol (glossaire).

Ce que la tâche programmée (étape 6) devra faire à chaque exécution :

1. **Récupérer** `assets/template.html` depuis l'URL ci-dessus.
2. **Renseigner** le titre et le sous-titre.
3. **Remplir** `ITEMS` (schéma documenté en haut du fichier).
4. **Compléter** `GLOSSARY` en calibrant la densité au niveau (cf. 1.4).
5. **Ne PAS toucher** au moteur d'annotation (`annotate`, `SENT`). Le modifier crée des bugs subtils.
6. **Publier** via `create_artifact` (1ère édition) ou `update_artifact` (éditions suivantes, en ajoutant la nouvelle en tête et en gardant l'historique).

### Étape 6 — Programmer la tâche, puis Run now immédiat

**Programmer la tâche AVANT d'afficher la première édition.** C'est ce qu'on oublie le plus facilement si on commence par regarder le rapport. Une fois la tâche créée, on déclenche un Run now qui produit la 1ère édition (et pré-autorise les outils web par la même occasion).

#### 6.1 Créer la tâche via `/schedule`

Cron par défaut : `0 17 * * 5` (vendredi 17h). Le prompt de la tâche est **autonome** : il contient tout le cadrage (domaine, angles, sources, rôle/niveau/usage, format de sortie) car il s'exécute sans mémoire de la conversation initiale.

Gabarit du prompt à utiliser :

```text
Tu es un analyste de veille spécialisé en [DOMAINE]. Chaque [JOUR], produis la VEILLE
[DOMAINE] de la semaine écoulée et ajoute-la à la page interactive persistante dont
l'id d'artifact est « [ID_ARTIFACT] » (à la 1ère exécution, créer l'artifact).

CONTEXTE PARTICIPANT : rôle [RÔLE], niveau d'expertise [NIVEAU], usage final [USAGE].
Calibre la profondeur, le ton, le « so what » et les game changers en conséquence.

OBJECTIF : du contenu dense, sourcé, actionnable et DATÉ. Couvre uniquement les ~7
derniers jours.

MÉTHODE :
1. Recherches web réelles. Pour CHAQUE item, vérifie la VRAIE date de publication en
   ouvrant l'URL. N'accepte un item QUE si sa date tombe dans les 7 derniers jours.
   N'invente jamais une date, une citation, une stat ou un lien.
2. Sources de référence connues : [SOURCES INTERNATIONALES] ; [SOURCES LOCALES].
   Inclure au moins 2 items locaux.

CONTENU — 3 parties équilibrées (4-6 items chacune) :
- [ANGLE 1, ex. Experts] : prises de parole notables.
- [ANGLE 2, ex. Secteur] : outils, acteurs, études, pratiques, réglementation.
- [ANGLE 3, ex. Signaux faibles] : tendances émergentes et angles non-consensuels.

LIVRAISON :
1. Mets à jour l'artifact « [ID_ARTIFACT] » : ajoute un chip d'édition en tête (date du
   jour) et insère les nouveaux items EN TÊTE du tableau ITEMS (garde l'historique).
   Respecte le schéma du gabarit (cf. étape 5). Ne touche pas au moteur d'annotation/glossaire.
2. (Optionnel) Présente aussi un document récapitulatif daté.

Termine par un résumé de 2-3 phrases des points marquants de la semaine.
```

#### 6.2 Run now immédiat

Une fois la tâche créée, déclencher un **Run now** sans attendre. Cela permet trois choses :

- Pré-autoriser les outils web (nécessaire pour les exécutions récurrentes futures)
- Produire la 1ère édition de la page interactive
- Vérifier en conditions réelles que la tâche tourne correctement

Rappel à donner à l'utilisateur : la tâche ne s'exécute que lorsque l'application est ouverte.

### Étape 7 — Propositions d'amélioration sur la 1ère édition

Une fois la 1ère édition produite par le Run now, regardez-la avec un œil critique.

**L'enjeu est de diverger.** Cet atelier réunit environ 20 personnes. Les 20 doivent finir avec **20 veilles vraiment différentes**, pas avec 20 variantes de la même structure. Vos propositions sont la clé de cette divergence : si elles ressemblent à celles que vous feriez à un autre participant du même atelier, vous n'avez pas assez creusé.

#### Comment inventer (questions à se poser avant de proposer)

Ne piochez pas dans une banque d'idées générique. Interrogez-vous d'abord sur le cas spécifique avec ces questions :

1. **Qu'est-ce qui dans le métier de CE participant ne serait pertinent pour PERSONNE d'autre dans le même atelier ?** (l'angle unique)
2. **Si CE participant devait expliquer en 30 secondes ce qui le différencie de ses pairs sur ce sujet, qu'est-ce qu'il dirait ?** (l'angle de signature) Comment la veille peut amplifier ça ?
3. **Quelle action concrète CE participant fait chaque semaine** que la veille pourrait outiller directement (préparer un point, alimenter une décision, nourrir une publication, justifier un arbitrage, briefer un collaborateur...) ? (l'angle opérationnel)
4. **Quel signal CE participant repère mieux que la moyenne, et qu'il pourrait codifier dans sa veille ?** (l'angle d'expertise tacite)

Vos propositions sortent de ces interrogations, pas d'une liste préfabriquée.

#### Niveau d'audace attendu (à dépasser)

Pour vous calibrer, voici deux idées **déjà proposées à d'autres participants**. Pour CE participant, proposez du **plus spécifique et plus personnel** :

- *Quick win type* — un badge spécial pour les acteurs majeurs du domaine (ex. "MAJOR" sur Adecco/Randstad dans une veille intérim) → repérage instantané
- *Game changer type* — une section "À glisser dans ta prochaine réunion" : 2-3 items reformulés en phrase punchy + chiffre + question, prêts à dire à l'oral

**Si vos propositions ressemblent trop à ces exemples, vous n'avez pas assez creusé le cas.** La règle : vos propositions doivent **surprendre le participant**, pas confirmer ce qu'il aurait pu imaginer tout seul. Elles doivent lui faire dire "ah tiens, je n'y avais pas pensé, mais c'est exactement ça."

#### Présentation au participant

Présentez 3-4 propositions concrètes, numérotées, pour faciliter le tri. Le participant pioche, biffe, en propose d'autres.

#### Appliquer les améliorations retenues

Quand le participant retient des propositions, **modifier le prompt de la tâche programmée** (créée en 6.1) pour intégrer les changements. Puis relancer un **Run now** pour produire une nouvelle édition mise à jour. Itérer si besoin.

### Étape 8 — Affiner la veille au fil du temps (opt-in, conversationnel)

La veille n'est pas figée. À tout moment, le participant peut revenir vers vous pour ajuster.

Cas typiques :

- "Source X ne m'apporte rien, retire-la."
- "Je veux suivre nominativement Y, ajoute-le."
- "Tel type d'item revient trop souvent, allège."
- "Je veux ajouter une rubrique 'à débattre'."

Quand le participant dit ça, vous **modifiez le prompt de la tâche programmée existante** pour intégrer le changement (la tâche se trouve dans `/schedule`, le prompt est éditable). Pas de fichier journal annexe, pas de mécanisme dans le HTML : le prompt est central, c'est là qu'on ajuste.

L'artifact HTML est dédié à la veille, pas au process. Pas d'encart "Retour express" dans le rapport. La boucle est conversationnelle et opt-in.

Mentionner cette possibilité au participant en clôture de l'atelier : *« à tout moment, tu reviens vers moi avec un ajustement, je modifie le prompt de la tâche, et la prochaine édition en tient compte. »*

## Les principes qui font la qualité

- **Dates vérifiées, jamais inventées** — la règle n°1.
- **Un « so what » par item** — une info sans implication concrète ne rentre pas.
- **Trois parties équilibrées** — experts + secteur + signaux.
- **Des sources de qualité, dont locales** — au moins 2-3 dans la langue/zone de l'utilisateur.
- **Calibré au rôle, niveau et usage** du participant — c'est ce qui rend la veille personnelle, pas générique.
- **Divergence assumée** — sur un atelier de 20 personnes, l'objectif est 20 veilles vraiment différentes.
- **Format scannable** — titres, dates visibles, définitions au survol, lisible en 10 minutes.
- **La veille s'ajuste au fil du temps** — le participant revient avec des retours, on modifie le prompt de la tâche.

## Bonnes pratiques de conversation

Programmer la tâche dès que le cadrage est posé (étape 6), pour ne pas l'oublier. Le Run now immédiat produit la 1ère édition qu'on regarde ensemble pour proposer les améliorations (étape 7). Les ajustements suivants se font en modifiant le prompt de la tâche (étape 8).

Pas de questionnaire fermé en série : alternez ouverture, propositions, reformulation, jusqu'à ce que vous ayez assez de matière pour calibrer.
