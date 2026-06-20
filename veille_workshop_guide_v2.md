# Veille hebdomadaire — tous domaines (v2)

## Ce que produit ce skill

Une veille récurrente, fiable et lisible en 10 minutes, sur le domaine choisi par l'utilisateur.

Le livrable principal est **une page interactive (artifact)** filtrable par partie et par édition, plus une tâche programmée qui la régénère chaque semaine. Optionnellement un document Word/PDF.

La mécanique est toujours la même, seul le domaine change. La valeur tient à une **discipline** : on ne publie que ce qui a été réellement publié dans la fenêtre de temps, avec une date vérifiée à la source. **Jamais de date, de citation, de statistique ou de lien inventés.** Mieux vaut 6 items sûrs que 12 approximatifs.

## Déroulé

### Étape 1 — Cadrer (court)

Demander à l'utilisateur, en une question, le domaine et confirmer les trois angles. Proposer par défaut ces trois angles, qui marchent dans presque tous les domaines :

- **Experts** — ce que disent les figures du domaine, à l'international ET dans la langue/le pays de l'utilisateur.
- **Secteur** — mouvements de marché : outils, acteurs, études, pratiques, réglementation.
- **Signaux faibles** — tendances émergentes et angles non-consensuels à surveiller sur 6-18 mois.

Adapter les libellés si le domaine l'exige (ex. veille juridique : *« jurisprudence / doctrine / signaux »*). En garder trois.

Demander aussi la **langue/zone géographique prioritaire** si ce n'est pas évident, et la **cadence souhaitée** (défaut : vendredi 17h).

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

Il est éprouvé et gère déjà : le design clair (mode clair), les filtres par partie et par édition, la recherche plein-texte, les badges de date, et les infobulles de définition au survol (glossaire).

Marche à suivre :

1. **Récupérer** `assets/template.html` depuis l'URL ci-dessus et le déposer dans le dossier de travail (outputs).
2. **Renseigner** le titre et le sous-titre (domaine, édition, fenêtre de dates).
3. **Remplir** le tableau `ITEMS` (un objet par item, schéma documenté en haut du fichier).
4. **Compléter** l'objet `GLOSSARY` avec les termes spécifiques du domaine et une définition courte et simple pour chacun. Garder l'objet à jour : c'est ce qui rend la veille accessible à un néophyte.
5. **Ne PAS toucher** au moteur d'annotation (`annotate`, la constante `SENT`) : il est conçu pour ne pas casser les nombres (dates, pourcentages) ni les liens. Le modifier crée des bugs subtils.
6. **Publier** via `create_artifact` (ou `update_artifact` les semaines suivantes, en ajoutant la nouvelle édition en tête et en gardant l'historique).

### Étape 6 — Proposer la veille automatique

Proposer de programmer une tâche récurrente (par défaut **vendredi 17h**). Le prompt de la tâche doit être **autonome** : domaine, trois angles, méthode de recherche datée/vérifiée, sources de référence connues, format de sortie, et instruction de mettre à jour l'artifact existant en ajoutant la nouvelle édition en tête.

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

Commencer par produire une **première édition « à la main »** pour valider format et sources avec l'utilisateur, AVANT de programmer la tâche. Une fois le format validé, la tâche reproduira exactement ce rendu chaque semaine.

Garder les échanges courts : poser le minimum de questions (domaine, langue/zone, cadence) puis avancer.
