# Veille hebdomadaire — tous domaines (v3)

## Ce que produit ce skill

Une veille récurrente, fiable et lisible en 10 minutes, sur le domaine choisi par l'utilisateur.

Le livrable principal est **une page interactive (artifact)** filtrable par partie et par édition, plus une tâche programmée qui la régénère chaque semaine. Optionnellement un document Word/PDF.

La mécanique est toujours la même, seul le domaine change. La valeur tient à une **discipline** : on ne publie que ce qui a été réellement publié dans la fenêtre de temps, avec une date vérifiée à la source. **Jamais de date, de citation, de statistique ou de lien inventés.** Mieux vaut 6 items sûrs que 12 approximatifs.

## Posture de conversation

Tout au long de l'entretien, vous alternez **question ouverte** et **propositions structurées** que le participant valide, biffe ou amende. C'est la posture qui marche, surtout avec des profils non-tech qui ne savent pas répondre à froid à une question ouverte (paradoxe du besoin informationnel).

Trois mouvements complémentaires que fait spontanément un bon intervieweur :

- Il **reformule la réponse vers le haut**. Il prend la phrase plate du participant et la traduit en récit valorisant ("ce que j'entends, c'est que vous voulez surveiller comment l'IA change le métier de RH, pas l'IA en général").
- Il **pousse quand la réponse reste trop générique**. Il dit cordialement que ça ne suffit pas à calibrer la veille et relance avec un angle plus précis.
- Il **change d'angle quand un sujet s'aplatit**. Par négatif ("qu'est-ce qui vous agace dans l'actu de ce domaine ?"), par projection ("dans 6 mois, sur quoi voudrez-vous être incollable ?"), par contraste ("qu'est-ce qui vous différencie de vos collègues sur ce sujet ?").

**Une question par message.** Une amorce ouverte avec ses propositions structurées va dans un seul message, c'est OK. Mais pas de mélange de plusieurs sujets dans un même message (ex. langue + cadence ensemble).

**Prenez le temps qu'il faut**, la qualité de l'entretien prime sur la rapidité. Ne raccourcissez pas pour aller vite.

## Déroulé

### Étape 1 — Cadrer (entretien progressif, libre dans la forme)

#### 1.1 La première question

Vous démarrez par une question **vraiment ouverte**, sans liste pré-fabriquée :

> "Sur quel sujet veux-tu mettre en place une veille hebdomadaire ?"

**N'imposez aucune liste de thématiques tech** ("Product Management / IA / Tech / UX") qui exclurait d'office les profils non-tech. Le participant peut répondre RH, droit social, design d'espace, achats, formation, communication interne, n'importe quel domaine.

#### 1.2 Préciser l'axe par alternance question / proposition

Une fois le domaine cité, **mobilisez votre expertise** pour proposer 3 à 5 sous-axes pertinents adaptés à ce domaine précis :

- Si "RH" → "talent acquisition / formation / qualité de vie au travail / SIRH et data RH / droit social"
- Si "droit social" → "contentieux prud'hommes / négociation collective / temps de travail / restructurations / paie et obligations légales"
- Si "design d'espace" → "ergonomie post-Covid / coworking et flex office / acoustique et bien-être / matériaux et impact carbone / espaces hybrides"

Etc. Adaptez à chaque fois au domaine cité.

Si le participant ne sait pas trop ce qui l'intéresse, proposez 3 angles probables sur la base du peu qu'il a dit, et invitez-le à trier ou en proposer d'autres. Si la réponse reste trop large après ce premier tri, creusez par alternance (deuxième tour de propositions, ou pivot d'angle).

#### 1.3 Confirmer les trois angles du rapport

Proposer par défaut ces trois angles, qui marchent dans presque tous les domaines :

- **Experts** — ce que disent les figures du domaine, à l'international ET dans la langue/zone du participant.
- **Secteur** — mouvements de marché : outils, acteurs, études, pratiques, réglementation.
- **Signaux faibles** — tendances émergentes et angles non-consensuels à surveiller sur 6-18 mois.

Adapter les libellés si le domaine l'exige (ex. veille juridique : *« jurisprudence / doctrine / signaux »*). En garder trois.

#### 1.4 Langue/zone et cadence

Demander la **langue/zone géographique prioritaire** si ce n'est pas évident (par défaut : la langue de la conversation + international).

Demander la **cadence** (défaut : vendredi 17h).

**Ne PAS demander la liste des sources.** C'est le travail du skill (étape 2).

### Étape 2 — Découvrir les sources automatiquement

C'est un point important : l'utilisateur ne connaît pas forcément ses sources, et ce n'est pas son rôle. Le skill identifie lui-même les références du domaine via recherche web :

- les **références internationales** les plus suivies (blogs, newsletters, médias spécialisés, instituts, comptes d'experts) ;
- des **références locales** (langue/pays de l'utilisateur), au moins 2-3 ;
- des **sources secteur/outils** et 1-2 sources plus pointues pour les signaux faibles.

Une bonne façon d'amorcer : rechercher *« sources / newsletters / experts les plus suivis en [DOMAINE] »* et croiser plusieurs listes. Conserver cette liste pour les semaines suivantes (elle peut être réutilisée et enrichie).

### Étape 3 — Recherche datée et vérifiée (le cœur)

Pour chaque item candidat, **ouvrir l'URL et vérifier la vraie date de publication** (métadonnées `article:published_time`, JSON-LD `datePublished`, ou date visible).

N'accepter un item QUE si sa date tombe dans la fenêtre (par défaut : **7 derniers jours**). Si la date n'est pas vérifiable, **écarter l'item**. Ne jamais déduire ou inventer une date.

Cibler **6 à 9 items au total**, répartis sur les trois parties, dont **au moins 2 sources locales**.

Si la recherche est volumineuse, déléguer la collecte + vérification à un sous-agent (Agent tool) pour garder le contexte propre : lui demander de ne retourner que des items à date vérifiée, au format structuré (date, partie, région, titre, source, URL, résumé 2 phrases, *« so what »*).

**Méfiance avec les pages « listicles » et « best of »** : elles sont souvent mises à jour en continu et non datées d'une vraie publication, ne pas les compter comme news de la semaine.

### Étape 4 — Structurer : 3 parties + « so what »

Pour chaque item :

- un **titre court**,
- 2-3 phrases d'**idée clé**,
- un **« so what »** (implication concrète pour le praticien, 1 phrase),
- la **source datée et cliquable**.

Pas de longs pavés, pas de jargon non expliqué. Équilibrer les trois parties.

### Étape 5 — Générer la page interactive

Utiliser le gabarit hébergé ici :

```text
https://raw.githubusercontent.com/MontaineMarteau/veille-workshop-claude/main/assets/template.html
```

Il est éprouvé et gère déjà : design clair, filtres par partie et par édition, recherche plein-texte, badges de date, infobulles de définition au survol (glossaire).

Marche à suivre :

1. **Récupérer** `assets/template.html` depuis l'URL ci-dessus et le déposer dans le dossier de travail (outputs).
2. **Renseigner** le titre et le sous-titre (domaine, édition, fenêtre de dates).
3. **Remplir** le tableau `ITEMS` (un objet par item, schéma documenté en haut du fichier).
4. **Compléter** l'objet `GLOSSARY` avec les termes spécifiques du domaine et une définition courte et simple pour chacun.
5. **Ne PAS toucher** au moteur d'annotation (`annotate`, la constante `SENT`) : il est conçu pour ne pas casser les nombres (dates, pourcentages) ni les liens. Le modifier crée des bugs subtils.
6. **Publier** via `create_artifact` (ou `update_artifact` les semaines suivantes, en ajoutant la nouvelle édition en tête et en gardant l'historique).

### Étape 6 — Proposer des améliorations (avant planification)

Une fois la page générée, ouvrez la discussion sur les axes d'amélioration possibles **avant** de programmer la tâche. Quatre angles à mobiliser librement, selon ce qui semble pertinent vu le résultat :

- **Contenu** : équilibre des 3 parties, fraîcheur moyenne des items, présence/absence d'items vraiment locaux, pertinence des « so what ». Ex. "j'ai trouvé 7 items dont 2 sur la partie signaux faibles, tu trouves ça équilibré ?"
- **Process** : sources qui ont saturé en bruit ou qui sont muettes, sources non consultées qu'il faudrait ajouter, fenêtre de fraîcheur à élargir si le domaine publie moins fréquemment. Ex. "j'ai consulté X et Y, je n'ai pas regardé Z, est-ce que tu voudrais que je l'ajoute ?"
- **Format** : les 3 parties suffisent-elles ? Ajouter une rubrique "à débattre" / "agenda" / "papier de la semaine" / "outil testé" ? Modifier le découpage ?
- **Visuel** : couleurs, densité, taille de police, ordre des parties, ajout d'icônes ou de badges spécifiques au domaine.

Les propositions sont ouvertes et conversationnelles, pas un questionnaire. Le participant pioche ce qui l'intéresse, modifie, ajoute. Vous appliquez les changements demandés au template (sans toucher au moteur d'annotation) et regénérez l'artifact.

C'est cette étape qui transforme une première édition correcte en une veille **sur-mesure** que le participant a vraiment envie d'ouvrir chaque semaine.

### Étape 7 — Proposer la veille automatique

Une fois la première édition validée et ajustée, proposer de programmer une tâche récurrente (par défaut **vendredi 17h**). Le prompt de la tâche doit être **autonome** : domaine, trois angles, méthode de recherche datée/vérifiée, sources de référence connues, format de sortie, et instruction de mettre à jour l'artifact existant en ajoutant la nouvelle édition en tête.

Gabarit du prompt à utiliser (cron par défaut : `0 17 * * 5`, vendredi 17h) :

```text
Tu es un analyste de veille spécialisé en [DOMAINE]. Chaque [JOUR], produis la VEILLE
[DOMAINE] de la semaine écoulée et ajoute-la à la page interactive persistante dont
l'id d'artifact est « [ID_ARTIFACT] ».

OBJECTIF : du contenu dense, sourcé, actionnable et DATÉ. Couvre uniquement les ~7
derniers jours (vérifie la date du jour).

MÉTHODE :
1. Recherches web réelles. Pour CHAQUE item, vérifie la VRAIE date de publication en
   ouvrant l'URL (métadonnées ou date visible). N'accepte un item QUE si sa date tombe
   dans les 7 derniers jours. N'invente jamais une date, une citation, une stat ou un lien.
2. Sources de référence connues : [SOURCES INTERNATIONALES] ; [SOURCES LOCALES].
   Inclure au moins 2 items locaux.

CONTENU — 3 parties équilibrées (4-6 items chacune) :
- [ANGLE 1, ex. Experts] : prises de parole notables (qui, idée clé, « so what », source datée).
- [ANGLE 2, ex. Secteur] : outils, acteurs, études, pratiques, réglementation.
- [ANGLE 3, ex. Signaux faibles] : tendances émergentes et angles non-consensuels (3-5 items).

LIVRAISON :
1. Mets à jour l'artifact « [ID_ARTIFACT] » : ajoute un chip d'édition en tête (date du
   jour) et insère les nouveaux items EN TÊTE du tableau ITEMS (garde l'historique).
   Respecte le schéma d'item du gabarit. Ne touche pas au moteur d'annotation/glossaire.
2. (Optionnel) Présente aussi un document récapitulatif daté.

Termine par un résumé de 2-3 phrases des points marquants de la semaine.
```

**Rappels à donner à l'utilisateur** : faire un *« Run now »* une première fois pour pré-autoriser les outils (recherche web), et préciser que la tâche ne s'exécute que lorsque l'application est ouverte.

## Les principes qui font la qualité

- **Dates vérifiées, jamais inventées** — la règle n°1.
- **Un « so what » par item** — une info sans implication concrète ne rentre pas.
- **Trois parties équilibrées** — experts + secteur + signaux.
- **Des sources de qualité, dont locales** — au moins 2-3 dans la langue/zone de l'utilisateur.
- **Format scannable** — titres, dates visibles, définitions au survol ; lisible en 10 minutes.

## Bonnes pratiques de conversation

Commencer par produire une **première édition « à la main »** pour valider format et sources avec l'utilisateur, AVANT de programmer la tâche. Une fois le format validé et les améliorations apportées (étape 6), la tâche reproduira ce rendu chaque semaine.

Pas de questionnaire fermé en série : alternez ouverture, propositions, reformulation, jusqu'à ce que vous ayez assez de matière pour calibrer.
