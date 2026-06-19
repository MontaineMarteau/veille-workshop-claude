# ⚡ Atelier 25 Min : Créez votre Agent de Veille Automatique avec Claude Cowork

Bienvenue dans cet atelier pratique ! L'objectif aujourd'hui est d'apprendre à configurer, générer et automatiser un **agent de veille personnalisé de haute qualité** dans votre domaine d'activité en seulement 25 minutes.

Pour ce faire, nous allons utiliser **Claude Cowork** (Antigravity), notre agent de codage autonome, et lui faire lire nos instructions directement depuis ce dépôt GitHub.

---

## 📅 Programme de l'Atelier (25 Minutes)

1. **0:00 - 0:05 | Lancement & Préparation** : Introduction de l'animateur, choix de votre sujet et récupération de l'URL du guide.
2. **0:05 - 0:10 | Entretien & Génération** : Claude Cowork mène un entretien interactif et chaleureux avec vous pour cerner vos besoins exacts de veille et génère votre skill local.
3. **0:10 - 0:15 | Planification** : Enregistrement de la tâche automatique récurrente à l'aide de la commande `/schedule`.
4. **0:15 - 0:20 | Validation** : Lancement du premier test de veille et lecture du rapport généré.
5. **0:20 - 0:25 | Trucs & Astuces** : Bonnes pratiques pour affiner sa veille, brancher des webhooks Slack/Discord, etc.

---

## 🛠️ Comment participer (Parcours "Zero-Git" ⚡)

*Pas besoin de compte GitHub ni de manipulation Git. Vous utilisez directement le fichier guide partagé par l'animateur.*

1. Copiez l'URL brute de notre fichier guide :
   `https://raw.githubusercontent.com/MontaineMarteau/veille-workshop-claude/main/veille_workshop_guide.md`
2. Lancez **Claude Cowork** dans votre terminal de projet.
3. Collez le prompt minimaliste suivant dans le chat :
   > **`Suis ce guide : https://raw.githubusercontent.com/MontaineMarteau/veille-workshop-claude/main/veille_workshop_guide.md`**
4. Laissez-vous guider par Claude Cowork ! La conversation s'adaptera dynamiquement à vos réponses.

---

## 🧠 L'Entretien de Cadrage : "L'Ancre Opérationnelle"

Pendant l'atelier, Claude Cowork va mener une conversation informelle avec vous. Ce n'est pas un formulaire rigide, il va rebondir sur vos réponses. Pour vous préparer, réfléchissez à ces 5 piliers :

* **L'Ancre Temporelle** : Quel est le dossier chaud ou le sujet de discussion clé que vous avez traité la semaine dernière ? (Définit votre niche réelle).
* **Le Réflexe Sémantique** : Qu'avez-vous cherché sur Google ou sur vos sites de référence pour résoudre ce problème ? (Définit vos mots-clés naturels).
* **La Dernière Frustration** : Quelle info importante avez-vous découverte trop tard récemment ? (Définit l'urgence et la fréquence de veille).
* **L'Allergie et les Faux Amis** : Quels types de contenus ou de sujets vous polluent ou vous énervent lors de vos lectures ? (Définit les mots-clés à bannir pour éviter le bruit).
* **Les Sources Fétiches** : Quels sites ou blogs consultez-vous par réflexe le matin ? (Définit vos sources de confiance).

---

## 📦 Ce que Claude Cowork va créer pour vous

À la fin de l'atelier, vous disposerez de deux éléments majeurs dans votre projet :

1. **Le Skill de Veille (`.agents/skills/domain-veille/SKILL.md`)** :
   Ce fichier d'instructions (le format natif de personnalisation de l'agent) décrit la logique de recherche sur-mesure (requêtes booléennes, croisement de sources web et académiques).
2. **Le Planificateur (`/schedule`)** :
   Une tâche de fond qui se lance à la fréquence choisie (ex. : tous les lundis matin à 9h00) pour exécuter la veille sans votre intervention.
3. **Vos Rapports de Veille (`veille_reports/report_latest.md`)** :
   Chaque exécution générera un rapport structuré en Markdown (ou sous un autre format comme HTML ou JSON si vous le préférez).
