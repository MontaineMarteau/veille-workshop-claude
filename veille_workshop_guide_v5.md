# Veille hebdomadaire — tous domaines (v5)

## Ce que produit ce skill

Une veille récurrente, fiable et lisible en 10 minutes, sur le domaine choisi par l'utilisateur.

Le livrable principal est **une page interactive (artifact)** filtrable par partie et par édition, plus une tâche programmée qui la régénère chaque semaine. Optionnellement un document Word/PDF.

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
- **Pour des options ouvertes où le participant doit pouvoir amender ou ajouter** (sous-axes, ruptures, allergies, éclaireurs, améliorations) : rester en **conversation textuelle** avec propositions dans le chat.

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

L'usage en particulier change le format des items et surtout les **game changers proposés en étape 6**. Un game changer pertinent pour "brief direction" n'est pas le même que pour "newsletter LinkedIn".

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

### Étape 5 — Générer la page interactive

Utiliser le gabarit hébergé ici :

```text
https://raw.githubusercontent.com/MontaineMarteau/veille-workshop-claude/main/assets/template.html
```

Marche à suivre :

1. **Récupérer** `assets/template.html` depuis l'URL ci-dessus.
2. **Renseigner** le titre et le sous-titre.
3. **Remplir** `ITEMS` (schéma documenté en haut du fichier).
4. **Compléter** `GLOSSARY` en calibrant la densité au niveau (cf. 1.4).
5. **Ne PAS toucher** au moteur d'annotation (`annotate`, `SENT`). Le modifier crée des bugs subtils.
6. **Publier** via `create_artifact` (ou `update_artifact` les semaines suivantes, en ajoutant la nouvelle édition en tête et en gardant l'historique).

### Étape 6 — Propositions d'amélioration (avant planification)

Une fois la page générée, regardez-la avec un œil critique. Ce qui se joue ici : transformer une première édition correcte en un objet que le participant a vraiment envie d'ouvrir chaque semaine.

Présentez des propositions **personnalisées à SON cas** (domaine, rôle, niveau, usage final). Mobilisez votre expertise pour identifier ce qui ferait la différence pour CETTE personne, pas des ajustements paramétriques génériques type "tu veux ajuster l'équilibre des 3 parties ?".

Équilibrez vos propositions sur deux registres.

#### Quick wins (5 min, on se dit "ah ouais, c'est mieux")

Des micro-améliorations à intégrer tout de suite. Exemples pour vous donner le niveau, à adapter au domaine :

- Badge spécial pour les acteurs majeurs du domaine (Adecco/Randstad dans l'intérim, OpenAI/Anthropic en IA, Cour de cassation en droit...) → repérage instantané
- Lien direct vers la source primaire pour les items réglementaires (Legifrance pour un décret, arXiv pour un paper)
- Compteur "J-2, J-5" en plus de la date
- Bouton "copier le lien" prêt à partager
- Surligner les chiffres clés (résultats, montants de levée, %)

#### Game changers (refontes qui transforment l'usage)

Des refontes audacieuses qui sortent la veille de "encore une newsletter hebdo" pour en faire un objet stratégique. Exemples calibrés sur l'usage final :

- **"À glisser dans ta prochaine réunion"** (si usage = brief direction ou partage interne) : 2-3 items reformulés en phrase punchy + chiffre + question, prêts à dire à l'oral
- **"Newsletter draft"** (si usage = publication LinkedIn ou newsletter sortante) : un brouillon de paragraphe rédigé que le participant peut publier tel quel
- **Vue longitudinale** : à chaque édition, comparer aux 3 précédentes pour signaler "ce sujet monte depuis 3 semaines" ou "X, silencieux depuis un mois, vient de publier" → la veille devient un radar temporel
- **Watchlist nominative** : 2-3 acteurs spécifiques (concurrents directs, leaders du domaine) avec section dédiée
- **"Décrypte"** : pour les items denses (décret, paper), 1 phrase "ce que ça change concrètement pour vous"

#### L'esprit, pas la liste

Ces exemples ne sont pas une checklist à dérouler. Ils sont là pour vous donner le **niveau d'audace attendu** et débloquer votre imagination. Pour CE participant, inventez vos propres propositions en tirant parti de tout ce que vous savez de SON cas. Ce que vous proposez à un CPO d'ETT française n'est pas ce que vous proposez à un dev freelance ou à une avocate en droit social belge.

Présentez 2-4 propositions concrètes par registre (pas une liste exhaustive), en mode conversationnel. Le participant pioche, biffe, en propose d'autres. Vous appliquez les changements demandés au template (sans toucher au moteur d'annotation) et regénérez l'artifact.

### Étape 7 — Programmer la veille automatique

Une fois la première édition validée et ajustée, proposer de programmer une tâche récurrente (par défaut **vendredi 17h**). Le prompt de la tâche doit être **autonome** : domaine, trois angles, méthode de recherche datée/vérifiée, sources de référence connues, format de sortie, rôle/niveau/usage du participant, et instruction de mettre à jour l'artifact existant.

**Inclure aussi dans le prompt l'instruction de lire le journal de feedback** (cf. étape 8) au démarrage et d'ajuster en conséquence.

Gabarit du prompt à utiliser (cron par défaut : `0 17 * * 5`, vendredi 17h) :

```text
Tu es un analyste de veille spécialisé en [DOMAINE]. Chaque [JOUR], produis la VEILLE
[DOMAINE] de la semaine écoulée et ajoute-la à la page interactive persistante dont
l'id d'artifact est « [ID_ARTIFACT] ».

CONTEXTE PARTICIPANT : rôle [RÔLE], niveau d'expertise [NIVEAU], usage final [USAGE].
Calibre la profondeur, le ton, le « so what » et les game changers en conséquence.

AVANT DE COMMENCER : lis « veille_reports/feedback_log.md » s'il existe. Tiens compte
des retours des éditions passées (sources notées "rien apporté" à retirer, catégories
peu lues à alléger, types de signaux à privilégier).

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
   Respecte le schéma du gabarit. Ne touche pas au moteur d'annotation/glossaire.
2. À la fin du rapport, inclus un encart « Retour express » qui invite l'utilisateur
   à un retour rapide (item le plus utile, source à retirer, etc.).
3. (Optionnel) Présente aussi un document récapitulatif daté.

Termine par un résumé de 2-3 phrases des points marquants de la semaine.
```

**Rappels à donner à l'utilisateur** : faire un *« Run now »* une première fois pour pré-autoriser les outils, et préciser que la tâche ne s'exécute que lorsque l'application est ouverte.

### Étape 8 — Boucle de feedback (continue, après chaque édition)

Chaque rapport produit se termine par un encart **"Retour express"** qui invite à un retour rapide en 30 secondes. Quelques exemples de questions à mobiliser :

- "Quel item t'a le plus servi cette semaine ?"
- "Y a-t-il une partie qui n'a rien apporté ?"
- "Une source à retirer ou à ajouter ?"

Le participant répond en chat (ou ignore, c'est non bloquant). Quand il répond, **consigner sa réponse dans `veille_reports/feedback_log.md`** avec date, édition concernée, et nature du retour.

Au run suivant, la tâche programmée lit ce journal (cf. étape 7) et **ajuste explicitement** : sources notées "rien apporté" plusieurs fois → retirées de la liste, type d'item "très utile" → privilégier, catégorie peu lue → alléger.

Cumulé sur 4-6 semaines, la veille se calibre vraiment au participant, sans intervention. C'est ce qui distingue une veille "qui fonctionne" d'une veille "à laquelle on tient".

Mentionner cette boucle au participant en clôture de l'atelier : *« à chaque édition, tu peux me dire 2 mots de retour. Je m'ajuste. »*

## Les principes qui font la qualité

- **Dates vérifiées, jamais inventées** — la règle n°1.
- **Un « so what » par item** — une info sans implication concrète ne rentre pas.
- **Trois parties équilibrées** — experts + secteur + signaux.
- **Des sources de qualité, dont locales** — au moins 2-3 dans la langue/zone de l'utilisateur.
- **Calibré au rôle, niveau et usage** du participant — c'est ce qui rend la veille personnelle, pas générique.
- **Format scannable** — titres, dates visibles, définitions au survol, lisible en 10 minutes.
- **Boucle de feedback continue** — la veille s'ajuste, elle n'est pas figée.

## Bonnes pratiques de conversation

Commencer par produire une **première édition « à la main »** pour valider format et sources avec l'utilisateur, AVANT de programmer la tâche. Une fois le format validé et les améliorations apportées (étape 6), la tâche reproduira ce rendu chaque semaine, en s'ajustant via la feedback (étape 8).

Pas de questionnaire fermé en série : alternez ouverture, propositions, reformulation, jusqu'à ce que vous ayez assez de matière pour calibrer.
