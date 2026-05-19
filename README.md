# Altitude Exec AI

Génération automatique d'une synthèse exécutive de 2 pages à partir d'un export Excel Altitude (évaluation de risques environnementaux).

## Use case

Un fond d'investissement reçoit un export Altitude d'une de ses participations.
Plutôt que de l'envoyer brut au directeur de la participation, le fond veut transmettre une **synthèse 2 pages "Exec"** qui met en lumière l'essentiel : risques majeurs, tendances, recommandations d'action.

Cette application automatise cette transformation :

```
[Email avec Excel Altitude]
   ↓
[N8N reçoit et parse l'Excel]
   ↓
[Appel API Mistral avec prompt structuré]
   ↓
[Génération PDF 2 pages]
   ↓
[Email au directeur de la participation]
```

## Stack

- **Claude Code** : développement assisté, skills réutilisables, agent orchestrateur
- **N8N** : automatisation du workflow email → traitement → email
- **Mistral API** : génération du contenu de l'Exec
- **GitHub** : versioning et collaboration équipe

## Structure du repo

| Dossier | Contenu |
|---|---|
| `skills/` | Skills Claude Code (parser, rédacteur) |
| `prompts/` | Prompts utilisés par N8N pour appeler l'API IA |
| `n8n-workflows/` | Workflows N8N exportés en JSON |
| `docs/` | Documentation : schema Altitude, exemple Exec cible |
| `samples/` | Exports de test — **JAMAIS commit** (gitignored) |

## Démarrage

Voir `docs/SETUP.md` (à venir).
