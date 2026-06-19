# Méthodologie de veille stratégique automatisée

Ce document est la base de connaissance utilisée par Claude Cowork pour configurer un agent de veille de qualité. Il est aussi rédigé pour être lu directement par un humain qui veut comprendre les principes en jeu.

Source : adapté d'une recherche approfondie sur les pratiques de veille stratégique, d'intelligence économique et d'ingénierie documentaire.

---

## 1. Le vrai problème, équilibrer bruit et silence

Toute veille automatisée se heurte à deux écueils opposés.

- Le **bruit documentaire**, c'est l'excès d'informations inutiles qui sature les capacités d'analyse. On reçoit 200 alertes par semaine, on les ferme toutes sans les lire, la veille n'est plus consultée.
- Le **silence documentaire**, c'est l'inverse. On rate les signaux faibles qu'il aurait fallu voir. Une nouvelle réglementation qui passe sous le radar, une annonce concurrente discrète, un article de recherche qui sortira en discussion six mois plus tard.

Une veille de qualité, c'est une veille calibrée. Ni trop large (bruit), ni trop étroite (silence). Pour calibrer, il faut une donnée d'entrée précise sur,

- la **niche réelle** du décideur (pas le "domaine" générique),
- son **vocabulaire naturel** (les mots qu'il tape vraiment dans Google),
- son **seuil de tolérance** entre rater une info et lire du superflu.

Le rôle de l'entretien de cadrage est d'extraire cette matière.

---

## 2. Le protocole de l'Ancre Opérationnelle

C'est un guide d'entretien décomplexé, adapté aux profils opérationnels qui n'ont pas de culture veille. Au lieu de demander à l'interviewé d'imaginer un livrable idéal (ce qui produit du silence), on ancre la conversation dans son vécu récent et concret.

L'intervieweur adopte une posture de traducteur, il laisse l'utilisateur raconter sa semaine, et extrait lui-même les variables logiques nécessaires.

### Les 5 ancres

#### 1. Ancre temporelle, la réalité du métier

**Formulation type** : "Oublions la veille un instant. Parlons de votre semaine dernière. Quel a été le problème le plus concret, le dossier le plus chaud, la discussion la plus marquante avec un collègue ou un client ?"

**Pourquoi ça marche** : ça désamorce la pression du "bon mot-clé". L'interlocuteur raconte une histoire réelle, ce qui révèle immédiatement le périmètre métier.

**Ce qu'on en tire** : la niche réelle (Taxonomy_Domain) et les premiers mots-clés obligatoires (Keywords_Required).

#### 2. Réflexe sémantique, le comportement de recherche

**Formulation type** : "Pour avancer sur ce dossier ou résoudre ce problème, qu'avez-vous cherché sur Google ? Quel est le premier document, la première norme, le premier site que vous avez ouvert ?"

**Pourquoi ça marche** : ça révèle le vocabulaire spontané de l'utilisateur sous contrainte de temps, plutôt qu'un jargon théorique reconstruit pour faire bonne impression.

**Ce qu'on en tire** : les mots-clés exacts utilisés et les expressions à conserver telles quelles (entre guillemets dans la requête).

#### 3. Dernière frustration, le signal d'urgence

**Formulation type** : "Racontez-moi la dernière fois où vous avez découvert une information trop tard. Si vous l'aviez sue trois jours plus tôt, ça vous aurait évité quoi ?"

**Pourquoi ça marche** : l'erreur passée est le meilleur indicateur de la valeur de l'information. Elle révèle la vulnérabilité opérationnelle.

**Ce qu'on en tire** : la fréquence de la veille (Scheduling_Frequency) et la priorité au rappel si l'erreur a été coûteuse (F-Beta élevé).

#### 4. Allergies et faux amis, le filtre du bruit

**Formulation type** : "Quand vous lisez des actualités dans votre métier, qu'est-ce qui vous énerve le plus ? Quel type d'article vous fait dire encore du temps perdu à lire du vent ?"

**Pourquoi ça marche** : il est cognitivement plus simple pour un humain de lister ce qu'il rejette que de formaliser ce qui lui est utile.

**Ce qu'on en tire** : le dictionnaire d'exclusion (Keywords_Excluded) et les filtres anti-bruit.

#### 5. Sources fétiches, la cartographie de confiance

**Formulation type** : "Quels sont les 2 ou 3 sites, blogs, comptes LinkedIn que vous ouvrez par réflexe le matin, même sans recherche précise en tête ?"

**Pourquoi ça marche** : ça cartographie les sources de confiance déjà validées par l'usage quotidien.

**Ce qu'on en tire** : la liste blanche prioritaire (Source_White_List) et les filtres `site:` à encoder.

---

## 3. La traduction en variables système

À partir de l'entretien, on dérive un jeu de paramètres exploitables par un agent automatisé.

| Variable | Définition | Source dans l'entretien |
|---|---|---|
| `Taxonomy_Domain` | La niche ultra-ciblée du décideur, formulée comme un sous-domaine opérationnel. | Ancre 1 |
| `Keywords_Required` | Liste des termes obligatoires et de leurs synonymes (jargon technique, acronymes, variantes). | Ancres 1 et 2 |
| `Keywords_Excluded` | Liste des termes à bannir (NOT) pour éliminer le bruit. | Ancre 4 |
| `Source_White_List` | Sites ou bases de données prioritaires à interroger en premier. | Ancre 5 |
| `Scheduling_Frequency` | Fréquence d'exécution de la veille (expression cron). | Ancre 3 |
| `Priorite_Cadrage` | Curseur entre "ne rien rater" et "ne lire que l'essentiel". | Ancre 3 |

La présentation de cette synthèse à l'interviewé, avant de générer le skill, est un moment important. C'est là qu'il valide ou ajuste, et c'est ce qui transforme la conversation en spécification.

---

## 4. Le curseur, ne rien rater vs ne lire que l'essentiel

Toute veille demande un arbitrage entre deux postures opposées qu'on ne peut pas maximiser en même temps.

- **Priorité à ne rien rater**, à privilégier quand passer à côté d'une info coûte cher. Veille réglementaire, surveillance concurrentielle critique, alertes sécurité. On accepte de lire un peu de bruit pour ne laisser passer aucun signal important. Dans la requête, ça se traduit par plus de synonymes (OR), des troncatures larges (`*`), et des exclusions modérées.

- **Priorité à ne lire que l'essentiel**, à privilégier quand le temps de lecture est court et qu'on cherche une synthèse opérationnelle. Veille de tendances pour un décideur qui a 10 minutes par semaine. On accepte de rater des signaux faibles pour ne lire que ce qui compte vraiment. Dans la requête, ça se traduit par des expressions exactes (`" "`), des exclusions strictes (NOT), et des contraintes de proximité (NEAR).

Dans l'entretien, la question 3 (dernière frustration) est le meilleur indicateur du bon réglage. Si la frustration est "j'ai raté une info critique", c'est priorité à ne rien rater. Si c'est "j'ai perdu deux heures à lire du vent", c'est priorité à l'essentiel.

> En littérature de veille, ces deux postures correspondent au compromis classique entre rappel et précision, mesuré par la F-mesure. Pour ce qui nous intéresse ici, parler en clair suffit largement.

---

## 5. L'ingénierie des requêtes booléennes

Une fois les variables collectées, l'agent traduit le besoin en équation de recherche structurée. Les opérateurs utiles,

| Opérateur | Usage | Effet |
|---|---|---|
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

## 6. Exemple complet, un chef de chantier BTP

### L'entretien (résumé)

> "La semaine dernière, mon gros sujet c'était le traitement des gravats de béton sur un chantier de démolition. J'ai cherché sur Google norme recyclage béton chantier. On a failli prendre une amende parce qu'un décret sur le tri à la source est sorti il y a un mois et qu'on ne l'avait pas vu. Ce qui me fait perdre du temps, ce sont les communiqués marketing des fabricants de concasseurs et les articles syndicaux. Moi je veux de la réglementation pure. Quand j'ai un doute, je vais sur preventionbtp.fr ou sur la section actualités du Moniteur."

### Les variables extraites

```json
{
  "Taxonomy_Domain": "BTP, recyclage déchets, réglementation",
  "Keywords_Required": [
    "décret", "réglementation", "recyclage",
    "gravats", "béton", "tri à la source"
  ],
  "Keywords_Excluded": [
    "fabricant", "concasseur", "syndicat",
    "politique", "communiqué de presse", "matériel"
  ],
  "Source_White_List": [
    "preventionbtp.fr", "lemoniteur.fr", "legifrance.gouv.fr"
  ],
  "Scheduling_Frequency": "0 7 * * 1",
  "Priorite_Cadrage": "Ne rien rater"
}
```

### L'équation générée

```text
(site:preventionbtp.fr OR site:lemoniteur.fr OR site:legifrance.gouv.fr OR (recyclage AND décret))
AND (béton NEAR/5 (gravat* OR déchet* OR tri))
AND (réglementation OR norme*)
NOT (fabricant OR concasseur OR syndicat OR politique OR "communiqué de presse" OR matériel)
```

La requête garantit que chaque résultat traite obligatoirement du béton (avec ses variantes proches comme gravats ou déchets), dans un contexte réglementaire, sur des sources de confiance, en excluant systématiquement les contenus marketing et politiques.
