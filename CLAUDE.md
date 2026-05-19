# CLAUDE.md — Constitution du projet Altitude Exec AI

Ce fichier est lu automatiquement par Claude Code à chaque session dans ce dossier.
Il définit le contexte, les conventions, et les règles du projet.

## Contexte produit

**Altitude** est un SaaS d'évaluation de risques environnementaux pour entreprises et investisseurs.
Ce projet construit une couche au-dessus : transformer un export Excel Altitude brut en une **synthèse exécutive de 2 pages** destinée au directeur d'une participation, envoyée par son fond d'investissement.

**Persona cible** : directeur·rice d'une participation (PME ou ETI). Pas un expert ESG/environnement. A 5 minutes pour lire. Veut savoir : "où sont mes risques majeurs, et qu'est-ce que je dois faire ?"

## Stack technique

- **N8N** (local Docker) : orchestration des workflows
- **Mistral API** (tier gratuit) : génération du contenu IA
- **Claude Code** : développement et maintenance des skills/prompts
- **GitHub** : repo partagé équipe Produit Altitude

## Conventions

### Langue
- Toute la documentation, les commentaires, les prompts et les sorties IA sont en **français**.
- Code et noms de variables en anglais (standard).

### Sécurité — règle absolue
- **Aucune donnée client réelle** ne doit jamais être commit sur GitHub.
- Les exports Altitude vont dans `samples/` qui est gitignored.
- Les clés API vont dans `.env` (gitignored), jamais en dur dans le code.
- Avant tout commit : vérifier `git status` pour t'assurer qu'aucun fichier sensible n'est ajouté.

### Style des prompts (très important)
- Les prompts pour Mistral sont versionnés dans `prompts/` avec un nom explicite et un numéro de version (ex: `exec-summary-v1.md`).
- Chaque prompt commence par un commentaire qui explique : à quoi il sert, quelles variables il attend, quel format de sortie il produit.
- Quand on itère sur un prompt, on crée une nouvelle version (`v2`, `v3`...) plutôt que d'écraser — pour pouvoir comparer.

### Skills Claude Code
- Un skill = un mini-expert sur une tâche précise.
- Format : un dossier dans `skills/<nom-du-skill>/` avec un `SKILL.md` qui décrit quand l'utiliser et comment.
- Skills prévus : `parser-altitude`, `rediger-exec`, plus un agent orchestrateur.

### N8N
- Tout workflow est exporté en JSON et versionné dans `n8n-workflows/`.
- Quand on modifie un workflow dans l'UI N8N, on ré-exporte avant de commit.

## Workflow équipe (Git)

1. Avant de bosser : `git pull`
2. Créer une branche : `git checkout -b nom-court-de-la-feature`
3. Faire ses changements + commit : `git commit -m "verbe descriptif"`
4. Pousser : `git push -u origin nom-court-de-la-feature`
5. Ouvrir une Pull Request sur GitHub pour relecture avant fusion sur `main`.

## Comportement attendu de Claude

- Quand on te demande de modifier un prompt ou un skill : explique d'abord ce que tu vas changer et pourquoi, attends validation avant d'écrire.
- Ne jamais inventer la structure d'un export Altitude : se référer à `docs/altitude-schema.md`.
- Si tu vois une donnée client réelle dans le contexte (nom de société, chiffres financiers concrets), alerte avant de continuer.
