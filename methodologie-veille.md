# Méthodologie de veille stratégique automatisée

Ce document est la base de connaissance utilisée par Claude Cowork pour configurer un agent de veille de qualité. Il est aussi rédigé pour être lu directement par un humain qui veut comprendre les principes en jeu.

---

## 0. Posture d'entretien, alternance question / proposition

C'est le cœur de l'entretien. Beaucoup de participants ne savent pas répondre à des questions ouvertes sur leur veille, par effet du **paradoxe du besoin informationnel** (impossible de formuler ce qu'on ignore). Si l'agent se contente de poser une question ouverte et d'attendre, l'entretien se grippe.

La posture qui marche, c'est l'alternance.

1. **Question ouverte** : "votre veille, c'est sur quoi ?"
2. **Réponse libre** du participant ("product management").
3. **L'agent mobilise son expertise** et propose 3 à 5 options structurées : "le PM est vaste, lesquels collent à votre quotidien ? Cochez, biffez, ajoutez ce qui manque."
4. **Le participant trie** sur la base concrète qui lui est présentée.
5. **L'agent creuse** sur les choix retenus avec une nouvelle question ouverte ou de nouvelles propositions.

Ce mode hybride libère le participant non-tech de l'effort de formulation à froid. Il mobilise l'expertise du modèle comme accélérateur, pas comme contrainte. Il s'applique à chaque ancre du protocole Axes de Veille (section 3).

Mini-dialogue d'illustration plus bas (section 3bis).

---

## 1. Le vrai problème, équilibrer bruit et silence

Toute veille automatisée se heurte à deux écueils opposés.

- Le **bruit documentaire**, l'excès d'informations inutiles qui sature les capacités d'analyse. On reçoit 200 alertes par semaine, on les ferme toutes sans les lire, la veille n'est plus consultée.
- Le **silence documentaire**, l'inverse. On rate les signaux faibles qu'il aurait fallu voir. Une réglementation qui passe sous le radar, une rupture technologique discrète, un acteur émergent qu'on découvrira trop tard.

Une veille de qualité est calibrée. Ni trop large, ni trop étroite.

---

## 2. La rupture méthodologique, veille permanente vs recherche ponctuelle

Erreur fréquente, confondre,

- la **recherche ponctuelle**, qui résout un problème immédiat (s'arrête quand le problème est résolu, périmètre étroit, valeur utilitaire),
- la **veille stratégique permanente**, qui s'inscrit dans la durée pour anticiper (continue, structurée autour d'axes thématiques, valeur prospective).

| | Recherche ponctuelle | Veille permanente |
| --- | --- | --- |
| Objectif | Éteindre un incendie opérationnel | Anticiper les ruptures et tendances |
| Temporalité | Instantanée, court terme | Continue, moyen et long terme |
| Périmètre | Ultra-spécifique au problème | Axes de surveillance transversaux |
| Valeur | Corrective | Décisionnelle et prospective |

Si l'entretien interroge l'utilisateur sur ses "problèmes de la semaine", l'agent sera ringardisé en quelques mois. **Le questionnement doit cibler le territoire de responsabilité permanent et les signaux de rupture, pas le dossier du jour.**

---

## 3. Le protocole "Axes de Veille"

5 ancres qui déplacent l'utilisateur de son quotidien vers sa mission pérenne. Pour chaque ancre : une formulation ouverte d'amorce, et des **exemples de propositions à mobiliser** quand le participant a besoin d'être aidé (cf. section 0).

### 3.1. Zone de Maîtrise, l'axe permanent

**Amorce ouverte** : "Dans votre métier, sur quel sujet devez-vous rester la personne de référence d'ici un an, celle que vos collègues ou clients viennent voir pour prendre de bonnes décisions ?"

Si la réponse est large (ex. "product management"), proposer **5 sous-axes plausibles à trier**. À adapter au domaine. Exemple sur le PM :

- Stratégie produit et roadmap
- Discovery et user research
- Product ops et tooling
- IA dans le produit (intégration, agents, MCP)
- Pricing et monétisation

**Ce qu'on en tire** : l'axe de surveillance permanent (`Taxonomy_Domain`) et les concepts sémantiques obligatoires (`Keywords_Required`).

### 3.2. Saut Technologique, les ruptures à anticiper

**Amorce ouverte** : "Quelles nouvelles technologies ou méthodes émergentes, si elles se généralisaient d'ici 6 mois sans que vous le sachiez, risqueraient de ringardiser vos pratiques actuelles ?"

Si la réponse est floue, proposer **3 à 5 ruptures probables sur l'axe identifié**. Exemple sur "PM + IA produit" :

- Workflows agentiques opérationnels (l'IA exécute des chaînes de tâches, pas seulement assiste)
- Model Context Protocol (MCP) comme standard de connexion outils-IA
- AI-first product operating model (PM devient orchestrateur)
- Vibecoding / Design-to-Code par IA
- Évaluation et observabilité des features IA en production

Le participant valide, biffe, en ajoute.

**Ce qu'on en tire** : les concepts de rupture qui croisent l'axe permanent. Ce sont eux qui empêchent la veille de retomber sur des trend articles génériques.

### 3.3. Zéro Surprise, les angles morts à combler

**Amorce ouverte** : "Sur quel aspect seriez-vous mal à l'aise si un concurrent ou un client vous posait une question pointue ce matin ?"

Cette question révèle la vulnérabilité ressentie. C'est le meilleur indicateur pour régler le curseur "ne rien rater" vs "ne lire que l'essentiel" (`Priorite_Cadrage`).

Si la réponse est "tout va bien", proposer **des angles morts typiques** du domaine pour relancer. Sur le PM : "réglementation IA Act, benchmarks de pricing concurrents, mouvements d'acquisition, papers académiques sur l'évaluation des LLM ?".

### 3.4. Allergie à la Hype, le filtre anti-bruit

**Amorce ouverte** : "Quels concepts à la mode, mots-valises ou débats d'experts saturent l'actualité de votre secteur mais sont, pour vous, totalement creux ?"

Si la réponse hésite, proposer **les mots-valises courants** à exclure par défaut. Sur le PM : "agile, framework, canvas, growth hacking, north star metric, MVP, OKR comme contenu d'articles ?".

**Ce qu'on en tire** : la liste noire (`Keywords_Excluded`).

### 3.5. Éclaireurs, le sourcing chaud

**Amorce ouverte** : "Quels 2 ou 3 acteurs, experts ou collectifs ont toujours un coup d'avance dans votre domaine ?"

Si le participant ne nomme rien (cas fréquent en non-tech), **proposer 5 éclaireurs probables sur l'axe identifié**, en mixant types (newsletter, blog, podcast, compte LinkedIn) et langues (FR + EN). Sur "PM + IA produit" :

- Lenny Rachitsky (newsletter Lenny's Newsletter)
- Mind The Product (blog + conférences)
- Reforge (essais long format)
- Andrew Chen (a16z, growth + IA)
- Le Ticket (newsletter FR)

Le participant marque ceux qu'il connaît, ceux qu'il veut suivre, en propose d'autres.

**Ce qu'on en tire** : la liste blanche (`Source_White_List`). C'est elle qui empêchera la veille de retomber sur des trend articles SEO.

---

## 3bis. Mini-dialogue d'illustration, la posture en action

Participant : "je veux une veille sur le product management."

Agent : "OK. Le PM est vaste. Voici 5 sous-axes possibles, dites-moi lesquels collent à votre quotidien. Cochez, biffez, ajoutez ce qui manque.

1. Stratégie produit et roadmap
2. Discovery et user research
3. Product ops et tooling
4. IA dans le produit (intégration, agents, MCP)
5. Pricing et monétisation"

Participant : "Le 4 surtout, et un peu le 2."

Agent : "Bien. Sur l'IA dans le produit, deux angles : (a) intégrer l'IA dans mes produits (POC, déploiement, modèles), (b) l'IA change mon métier de PM (workflows, outils). Lequel ou les deux ?"

Participant : "Plutôt b."

Agent : "Pour vous protéger des ruptures, je vois 5 sujets qui pourraient impacter votre métier d'ici 6 mois. Lesquels vous inquiètent vraiment ?

1. Workflows agentiques opérationnels
2. MCP comme standard
3. AI-first product operating model
4. Vibecoding
5. Évaluation des features IA en production"

Participant : "1 et 3 me parlent. 5 aussi."

Agent : "Côté éclaireurs, vous suivez qui le matin ?"

Participant : "Honnêtement je sais pas trop, je tape sur Google."

Agent : "OK, voici 5 références reconnues sur votre angle. Marquez ceux que vous voulez suivre.

1. Lenny Rachitsky (newsletter Lenny's)
2. Mind The Product
3. Reforge
4. Andrew Chen
5. Le Ticket (FR)"

Etc.

L'entretien se déroule en 7-10 minutes, le participant n'est jamais bloqué, et l'agent ressort avec une matière qualifiée.

---

## 4. La traduction en variables système

À partir de l'entretien, on dérive un jeu de paramètres exploitables.

| Variable | Définition | Source dans l'entretien |
| --- | --- | --- |
| `Taxonomy_Domain` | L'axe de surveillance permanent. | Ancre 1 |
| `Keywords_Required` | Termes obligatoires et leurs synonymes. | Ancres 1 et 2 |
| `Keywords_Excluded` | Termes à bannir pour éliminer le bruit. | Ancre 4 |
| `Source_White_List` | Sources prioritaires à interroger en premier. | Ancre 5 |
| `Scheduling_Frequency` | Fréquence d'exécution (expression cron). | À demander en fin d'entretien |
| `Priorite_Cadrage` | Curseur entre "ne rien rater" et "ne lire que l'essentiel". | Ancre 3 |

La présentation de cette synthèse à l'interviewé, avant de générer le skill, est un moment important. C'est là qu'il valide ou ajuste.

---

## 5. Le curseur, ne rien rater vs ne lire que l'essentiel

Toute veille demande un arbitrage entre deux postures qu'on ne peut pas maximiser en même temps.

- **Priorité à ne rien rater**, à privilégier quand passer à côté d'une info coûte cher. Veille réglementaire, surveillance concurrentielle critique, alertes sécurité. Plus de synonymes, on tolère un peu de bruit.
- **Priorité à ne lire que l'essentiel**, à privilégier quand le temps de lecture est court. Synthèses pour un décideur qui a 10 minutes par semaine. Exclusions strictes, expressions exactes.

L'ancre 3 (Zéro Surprise) est le meilleur indicateur. Frustration "j'ai raté une info critique" → priorité à ne rien rater. Frustration "j'ai perdu deux heures à lire du vent" → priorité à l'essentiel.

---

## 6. Comment travailler comme un veilleur senior

C'est la posture de recherche du skill. Pas un protocole, une description de méthode.

Un veilleur senior ne tape pas une seule requête sur Google. Il fait **3 ou 4 passes successives** sous des angles différents.

- **Passe 1, large sur l'axe** : recherche ouverte sur le `Taxonomy_Domain` croisé avec un mot de rupture. Permet de capter ce qui circule.
- **Passe 2, sur les éclaireurs** : visite directe des pages des sources de la `Source_White_List`. Lit les publications de la semaine. C'est là que se trouvent les signaux primaires.
- **Passe 3, sur les ruptures concrètes** : recherche ciblée sur chaque concept de rupture identifié à l'ancre 2 (ex. "MCP", "workflows agentiques"), pour repérer annonces produit, papers, lancements.
- **Passe 4, optionnelle** : recherche élargie hors liste blanche pour ne pas rater l'inattendu.

Puis, **le tri éditorial sévère** :

- **Fraîcheur stricte** : sur une fréquence hebdo, ce qui n'est pas daté avec un jour précis ET de moins de 7 jours, dégagé. Sur du mensuel, < 30 jours. Pas de "2026" tout seul, pas de "récemment".
- **Concret seulement** : on retient les annonces produit, les lancements, les papers, les chiffres, les prises de position originales d'éclaireurs identifiés. On rejette les trend articles SEO génériques ("Top 10 trends 2026", "What's changed in...", "Every X needs to know").
- **Pas de doublons sémantiques** : si trois articles disent la même chose, on prend le plus primaire (l'annonce originale, pas la reprise).
- **Mieux 3 vrais signaux que 8 items mous**. On préfère un rapport court mais affûté à un rapport long mais creux.

Si le tri sévère ne laisse rien : on le dit honnêtement dans la synthèse exécutive ("semaine calme sur votre axe, voici 2 signaux faibles à garder à l'œil") plutôt que de gonfler avec du remplissage.

---

## 7. Annexe, l'ingénierie booléenne (outil parmi d'autres)

L'agent peut, s'il le juge utile, construire en interne des équations booléennes pour ses passes de recherche. C'est un outil, pas un passage obligé.

| Opérateur | Usage | Effet |
| --- | --- | --- |
| `AND` | Intersection obligatoire entre concepts | Réduit le bruit |
| `OR` | Union de synonymes ou variantes | Augmente le rappel |
| `NOT` (ou `-`) | Exclusion d'un terme | Réduit le bruit |
| `( )` | Encapsulation pour structurer l'ordre logique | Permet des requêtes complexes |
| `" "` | Expression exacte | Réduit le bruit sur les dénominations figées |
| `*` | Troncature | Capture les variantes |
| `site:` | Restriction à un domaine | Priorise les sources fiables |

L'équation type pour une passe ciblée,

```text
(concept_axe OR synonymes) AND (concept_rupture OR synonymes)
NOT (terme_exclu_1 OR terme_exclu_2)
```

À utiliser librement. La rigueur de la veille ne vient pas de la sophistication de l'équation, elle vient du tri éditorial qui suit.
