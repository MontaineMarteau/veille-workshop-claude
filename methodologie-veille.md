# Méthodologie de veille stratégique automatisée

Ce document est la base de connaissance utilisée par Claude Cowork pour configurer un agent de veille de qualité. Il est aussi rédigé pour être lu directement par un humain qui veut comprendre les principes en jeu.

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

Si l'entretien de cadrage interroge l'utilisateur sur ses "problèmes de la semaine", l'agent sera programmé avec des requêtes trop restrictives et ringardisé en quelques mois. **Pour concevoir une veille durable, le questionnement doit cibler le territoire de responsabilité permanent et les signaux de rupture, pas le dossier du jour.**

---

## 3. Le protocole "Axes de Veille"

5 questions courtes qui déplacent l'utilisateur de son quotidien vers sa mission pérenne. L'intervieweur adopte une posture de traducteur, il laisse l'utilisateur parler, et extrait les variables logiques.

### 3.1. Zone de Maîtrise, l'axe permanent

**Formulation type** : "Dans votre quotidien professionnel, quel est le sujet technique ou méthodologique sur lequel vous devez impérativement rester la personne de référence d'ici un an, celle que vos collaborateurs ou clients viennent voir pour prendre de bonnes décisions ?"

**Pourquoi ça marche** : déplace le focus du "problème de la semaine" vers la mission pérenne. Donne à l'agent un cap stable.

**Ce qu'on en tire** : l'axe de surveillance permanent (`Taxonomy_Domain`) et les concepts sémantiques obligatoires (`Keywords_Required`).

### 3.2. Saut Technologique, les ruptures à anticiper

**Formulation type** : "Quelles nouvelles technologies, méthodes émergentes ou pratiques de conception, si elles se généralisaient d'ici 6 mois sans que vous le sachiez, risqueraient de ringardiser vos processus actuels ou de vous faire perdre votre avance ?"

**Pourquoi ça marche** : force la projection dans l'anticipation des ruptures, le cœur de la veille d'innovation.

**Ce qu'on en tire** : les concepts de rupture à intégrer en intersection (AND) pour éviter de remonter des évidences théoriques ou du contenu de débutant.

### 3.3. Zéro Surprise, les angles morts à combler

**Formulation type** : "Sur quel aspect de votre métier seriez-vous le plus mal à l'aise si un concurrent ou un client vous posait une question pointue ce matin, et sur lequel vous voulez absolument conserver un temps d'avance ?"

**Pourquoi ça marche** : cible les angles morts perçus par le décideur. La veille vient combler une lacune ressentie.

**Ce qu'on en tire** : le réglage du curseur rappel/précision (`Priorite_Cadrage`). Si la vulnérabilité est élevée, on penche vers "ne rien rater".

### 3.4. Allergie à la Hype, le filtre anti-bruit

**Formulation type** : "Quels sont les concepts à la mode, les mots-valises ou les débats d'experts qui saturent l'actualité de votre secteur mais qui sont, selon vous, totalement creux et sans valeur pour vos projets ?"

**Pourquoi ça marche** : sépare le bruit médiatique de la réalité de l'innovation industrielle.

**Ce qu'on en tire** : la liste noire (`Keywords_Excluded`) et les filtres NOT pour rejeter le superficiel.

### 3.5. Éclaireurs, le sourcing chaud

**Formulation type** : "Dans votre secteur, quels sont les 2 ou 3 acteurs, des entreprises pionnières, des laboratoires, des experts influents, qui ont toujours un coup d'avance dans leurs méthodes ou leurs partages d'expérience ?"

**Pourquoi ça marche** : identifie des émetteurs d'innovation plutôt que des annuaires passifs.

**Ce qu'on en tire** : la liste blanche (`Source_White_List`) orientée vers les flux des experts et blogs d'excellence.

---

## 4. La traduction en variables système

À partir de l'entretien, on dérive un jeu de paramètres exploitables.

| Variable | Définition | Source dans l'entretien |
| --- | --- | --- |
| `Taxonomy_Domain` | L'axe de surveillance permanent. | Question 1 |
| `Keywords_Required` | Termes obligatoires et leurs synonymes. | Questions 1 et 2 |
| `Keywords_Excluded` | Termes à bannir (NOT) pour éliminer le bruit. | Question 4 |
| `Source_White_List` | Sources prioritaires à interroger en premier. | Question 5 |
| `Scheduling_Frequency` | Fréquence d'exécution (expression cron). | À demander en fin d'entretien |
| `Priorite_Cadrage` | Curseur entre "ne rien rater" et "ne lire que l'essentiel". | Question 3 |

La présentation de cette synthèse à l'interviewé, avant de générer le skill, est un moment important. C'est là qu'il valide ou ajuste.

---

## 5. Le curseur, ne rien rater vs ne lire que l'essentiel

Toute veille demande un arbitrage entre deux postures opposées qu'on ne peut pas maximiser en même temps.

- **Priorité à ne rien rater**, à privilégier quand passer à côté d'une info coûte cher. Veille réglementaire, surveillance concurrentielle critique, alertes sécurité. Plus de synonymes (OR), troncatures larges (`*`), exclusions modérées.
- **Priorité à ne lire que l'essentiel**, à privilégier quand le temps de lecture est court. Veille de tendances pour un décideur qui a 10 minutes par semaine. Expressions exactes (`" "`), exclusions strictes (NOT), contraintes de proximité (NEAR).

Dans l'entretien, la question 3 (Zéro Surprise) est le meilleur indicateur du bon réglage.

> En littérature de veille, ces deux postures correspondent au compromis classique entre rappel et précision, mesuré par la F-mesure. Pour ce qui nous intéresse ici, parler en clair suffit.

---

## 6. L'ingénierie des requêtes booléennes

Une fois les variables collectées, l'agent traduit le besoin en équation de recherche structurée.

| Opérateur | Usage | Effet |
| --- | --- | --- |
| `AND` | Intersection obligatoire entre concepts | Réduit le bruit |
| `OR` | Union de synonymes ou variantes | Augmente le rappel, contre le silence |
| `NOT` (ou `-`) | Exclusion d'un terme ou d'une thématique | Réduit le bruit |
| `( )` | Encapsulation pour structurer l'ordre logique | Permet des requêtes complexes |
| `" "` | Expression exacte | Réduit le bruit sur les dénominations figées |
| `*` | Troncature, capture les variantes d'une racine | Lutte contre le silence |
| `NEAR/n` | Proximité, deux termes dans n mots d'écart | Fiabilise le lien sémantique |
| `site:` | Restriction à un domaine web | Priorise les sources fiables |

### Structure type d'une équation

```text
(Concept_1 OR synonymes) AND (Concept_2 OR synonymes) AND (Concept_3 OR synonymes)
NOT (terme_exclu_1 OR terme_exclu_2)
```

On peut encapsuler dans une liste blanche de sources,

```text
(site:source1.fr OR site:source2.com OR (équation principale))
```

---

## 7. Exemple complet, un architecte frontend

### L'entretien (résumé)

> "Je ne veux pas qu'on me parle de mes petits soucis techniques de la semaine, dans six mois mon sprint sera fini et je n'en aurai plus rien à faire. Mon rôle permanent, c'est de piloter l'architecture de nos interfaces de demain et de garantir que notre code reste évolutif. Le vrai saut technologique que je redoute, c'est le Design-to-Code automatisé par l'IA et l'automatisation des tests de régression visuelle par des agents. Si ces outils deviennent mûrs, nos méthodes de développement changent du tout au tout. J'ai besoin de savoir comment les géants de la tech intègrent ces outils dans leurs Design Systems. Ce qui m'énerve, ce sont les tutoriels de code pour débutants ou les comparatifs marketing du genre React vs Vue. Je veux voir comment Vercel ou Figma déploient l'automatisation de leurs interfaces à l'échelle. Je lis déjà de temps en temps Frontend Focus."

### Les variables extraites

```json
{
  "Taxonomy_Domain": "Architecture frontend, Design Systems, automatisation UI",
  "Keywords_Required": [
    "design system", "design-to-code",
    "visual regression testing", "AI-driven development",
    "UI automation"
  ],
  "Keywords_Excluded": [
    "beginner", "tutorial", "framework vs framework",
    "how to learn", "marketing pitch", "simple UI"
  ],
  "Source_White_List": [
    "frontend-focus.curated.co", "vercel.com/blog",
    "figma.com/blog", "news.ycombinator.com"
  ],
  "Scheduling_Frequency": "0 9 * * 1",
  "Priorite_Cadrage": "Ne lire que l'essentiel"
}
```

### L'équation générée

```text
(site:vercel.com/blog OR site:figma.com/blog OR site:curated.co)
AND ("design system" OR "design-to-code")
AND ("visual regression" OR "AI-driven" OR "UI automation")
NOT (beginner OR tutorial OR framework* OR "how to learn" OR simple)
```

La requête garantit que chaque résultat traite d'architecture de Design System (Concept 1), avec un angle d'automatisation ou d'IA (Concept 2), sur des sources d'innovation (Concept 3), en excluant systématiquement le contenu débutant et marketing.
