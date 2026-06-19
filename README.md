# ⚡ Atelier 25 Min : Créez votre Agent de Veille Automatique avec Claude Cowork

Bienvenue dans cet atelier pratique ! L'objectif aujourd'hui est d'apprendre à configurer, générer et automatiser un **agent de veille personnalisé de haute qualité** dans votre domaine d'activité en seulement 25 minutes.

Pour ce faire, nous allons utiliser **Claude Cowork** (Antigravity), notre agent de codage autonome, et lui faire lire nos instructions directement depuis ce dépôt GitHub.

---

## 📅 Programme de l'Atelier (25 Minutes)

1. **0:00 - 0:05 | Lancement & Préparation** : Introduction de l'animateur, choix de votre sujet et récupération de l'URL du guide.
2. **0:05 - 0:10 | Entretien & Génération** : Claude Cowork vous pose 5 questions pragmatiques (sans blabla technique) pour cerner vos besoins exacts et génère votre skill de veille local.
3. **0:10 - 0:15 | Planification** : Enregistrement de la tâche automatique récurrente à l'aide de la commande `/schedule`.
4. **0:15 - 0:20 | Validation** : Lancement du premier test de veille et lecture du rapport généré.
5. **0:20 - 0:25 | Trucs & Astuces** : Bonnes pratiques pour affiner sa veille, brancher des webhooks Slack/Discord, etc.

---

## 🛠️ Comment participer (Au choix)

### Option A : Le parcours "Zero-Git / Sans Fork" (Recommandé ⚡)
*Idéal si vous n'avez pas de compte GitHub configuré ou si vous voulez aller le plus vite possible.*

1. Copiez l'URL brute de notre fichier guide :
   `https://raw.githubusercontent.com/MontaineMarteau/veille-workshop-claude/main/veille_workshop_guide.md`
2. Lancez **Claude Cowork** dans votre terminal de projet.
3. Collez le prompt minimaliste suivant dans le chat :
   > **`Suis ce guide : https://raw.githubusercontent.com/MontaineMarteau/veille-workshop-claude/main/veille_workshop_guide.md`**
4. Laissez-vous guider par Claude Cowork !

---

### Option B : Le parcours "Fork" (Pour les technophiles 🍴)
*Idéal si vous souhaitez éditer vous-même votre fichier de configuration sur GitHub.*

1. **Forkez** ce dépôt sur votre compte GitHub.
2. Ouvrez le fichier `veille_profile_template.yaml` directement dans votre navigateur sur GitHub, cliquez sur l'icône de crayon pour le modifier, renseignez vos propres mots-clés, puis validez les changements (Commit).
3. Lancez **Claude Cowork** dans votre terminal de projet.
4. Collez le prompt suivant :
   > **`Configure mon skill de veille à partir de mon profil ici : https://github.com/[VOTRE-COMPTE]/veille-workshop-claude`**
5. L'agent clonera votre dépôt personnel, analysera votre YAML et créera le skill en tâche de fond.

---

## 🧠 L'Entretien de Cadrage : "L'Ancre Opérationnelle"

Pendant l'atelier, Claude Cowork va vous poser 5 questions simples mais très ciblées pour concevoir la meilleure veille possible sans capter de bruit inutile. **Préparez vos réponses en 2 minutes :**

* **Q1. L'Ancre Temporelle** : Quel est le problème réel, le dossier chaud ou le sujet de discussion clé que vous avez traité la semaine dernière ? (Définit votre niche métier).
* **Q2. Le Réflexe Sémantique** : Qu'avez-vous cherché sur Google pour résoudre ce problème ? Quel site ou document avez-vous ouvert en premier ? (Définit vos mots-clés de base).
* **Q3. La Dernière Frustration** : Quelle info importante avez-vous découverte trop tard récemment ? (Définit l'urgence et la fréquence).
* **Q4. L'Allergie et les Faux Amis** : Quel type de contenu vous agace le plus lorsque vous faites des recherches ? (Définit les mots-clés à bannir pour éviter le bruit).
* **Q5. Les Fétiches** : Quels sites ou blogs consultez-vous tous les matins par réflexe ? (Définit vos sources prioritaires de confiance).

---

## 📦 Ce que Claude Cowork va créer pour vous

À la fin de l'atelier, vous disposerez de deux éléments majeurs dans votre projet :

1. **Le Skill de Veille (`.agents/skills/domain-veille/SKILL.md`)** :
   Ce fichier décrit la logique de recherche complexe (équations booléennes, recherche Google, arXiv, PubMed) construite sur-mesure pour votre sujet.
2. **Le Planificateur (`/schedule`)** :
   Une tâche de fond qui se lance à la fréquence choisie (ex. : tous les lundis matin à 9h00) pour exécuter la veille sans votre intervention.
3. **Vos Rapports de Veille (`veille_reports/report_latest.md`)** :
   Chaque exécution générera ou mettra à jour un rapport en Markdown structuré avec les actualités fraîches de la semaine.
