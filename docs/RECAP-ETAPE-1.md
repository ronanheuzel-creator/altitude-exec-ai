# 📖 Récap Étape 1 — Le Setup (expliqué simplement)

> Objectif du projet : transformer un export Excel Altitude en une synthèse "Exec" de 2 pages, automatiquement, avec l'aide de l'IA.
> Ce document explique ce qu'on a fait dans l'étape 1 (la préparation), avec des analogies simples.

---

## 🧱 L'analogie générale : on construit une usine

Imagine qu'on veut construire une **petite usine** qui prend de la matière première (un fichier Excel) et fabrique un produit fini (une synthèse de 2 pages).

Avant de fabriquer quoi que ce soit, il faut **préparer l'atelier**. C'est tout ce qu'on a fait dans l'étape 1.

```
   MATIÈRE PREMIÈRE           L'USINE (à construire)            PRODUIT FINI
   ┌─────────────┐         ┌──────────────────────┐         ┌─────────────┐
   │  Excel       │  ────>  │   IA + automatisation │  ────>  │  Exec 2 pages│
   │  Altitude    │         │   (étapes suivantes)  │         │  (PDF)       │
   └─────────────┘         └──────────────────────┘         └─────────────┘
```

---

## ✅ Ce qu'on a fait dans l'étape 1

### 1. On a rangé l'atelier 🗂️

On a créé un dossier `altitude-exec-ai` avec des **tiroirs étiquetés** :

```
altitude-exec-ai/
├── 📄 README.md          → l'affiche à l'entrée : "voici ce que fait l'usine"
├── 📜 CLAUDE.md          → le manuel d'instructions pour le robot-assistant
├── 🚫 .gitignore         → la liste "NE PAS sortir de l'atelier" (secrets)
├── 📁 skills/            → tiroir des "savoir-faire" de l'IA
├── 📁 prompts/           → tiroir des "consignes" données à l'IA
├── 📁 n8n-workflows/     → tiroir des "chaînes de montage"
├── 📁 docs/              → tiroir de la documentation
└── 📁 samples/           → tiroir des échantillons de test (reste à l'atelier !)
```

**Analogie** : c'est comme préparer ton bureau avant un gros projet de LEGO — tu tries les pièces dans des boîtes étiquetées AVANT de commencer, sinon c'est le chaos.

---

### 2. On a écrit le "manuel du robot" 🤖 (CLAUDE.md)

Le fichier `CLAUDE.md` est lu **automatiquement** par notre assistant IA (Claude Code) à chaque fois qu'on travaille.

**Analogie** : c'est comme la **notice qu'un robot lit avant de t'aider**. Dedans on a écrit :
- "Voici le projet et à quoi il sert"
- "Parle toujours en français"
- "Ne sors JAMAIS les données clients de l'atelier"
- "Voici comment l'équipe travaille ensemble"

Comme ça, le robot connaît les règles de la maison sans qu'on ait à les répéter à chaque fois.

---

### 3. On a posé la règle de sécurité n°1 🔒 (.gitignore)

Certains fichiers ne doivent **JAMAIS** sortir de l'atelier : les données clients (Excel) et les mots de passe (clés secrètes).

Le `.gitignore` est la liste de ces fichiers interdits de sortie.

**Analogie** : c'est comme une étiquette **"NE PAS METTRE DANS LE SAC D'ÉCOLE"** sur ton journal intime. Même si tu fais ta valise à la va-vite, ces trucs-là restent à la maison.

---

### 4. On a installé une "machine à remonter le temps" ⏪ (Git)

Git prend des **photos** de ton projet à des moments précis (on appelle ça des *commits*). Si tu casses quelque chose plus tard, tu peux revenir à une photo d'avant.

**Analogie** : c'est exactement comme les **points de sauvegarde dans un jeu vidéo**. Tu sauvegardes avant un boss difficile ; si tu meurs, tu recharges la sauvegarde.

On a pris notre première photo : *"Initial commit"* = l'état "atelier rangé, prêt à bosser".

---

### 5. On a déménagé l'atelier au bon endroit 📦

Au début, l'atelier s'était installé dans un dossier connecté au cloud de l'entreprise (OneDrive). Pour respecter les règles de confidentialité, on l'a déplacé dans un dossier **privé et local** sur l'ordinateur (`~/Dev/`).

**Analogie** : on a déplacé ton journal intime du placard partagé de la famille vers **ton propre tiroir fermé à clé**.

---

### 6. On a créé un casier partagé en ligne ☁️ (GitHub)

GitHub, c'est un **casier dans le cloud** où l'équipe entière peut accéder au code, voir l'historique, et travailler ensemble sans s'écraser les uns les autres.

**Analogie** : c'est comme un **Google Drive, mais spécialement conçu pour le code**, avec en plus une machine à remonter le temps géante et un système pour que plusieurs personnes bossent sans tout casser.

On a "poussé" (uploadé) notre projet dans ce casier en ligne.

```
   TON ORDI (local)                    GITHUB (cloud, partagé équipe)
   ┌──────────────────┐    push  ───>  ┌──────────────────────────┐
   │ altitude-exec-ai │                │ github.com/.../altitude  │
   │  (ta copie)      │  <───  pull    │  (la copie de référence) │
   └──────────────────┘                └──────────────────────────┘
       Tes collègues feront "pull" pour récupérer le projet chez eux.
```

---

### 7. On a créé un badge d'accès sécurisé 🪪 (Personal Access Token)

Pour prouver à GitHub que c'est bien toi qui pousses du code, il faut un **badge d'accès** (un token). On l'a rangé dans le **coffre-fort de l'ordinateur** (le trousseau macOS), pas dans un fichier en clair.

**Analogie** : c'est comme le **badge magnétique** pour entrer dans un immeuble sécurisé. On l'a mis dans ton portefeuille (le coffre-fort du Mac), pas collé sur la porte.

---

## 🎯 Où on en est

```
[✅ ÉTAPE 1] Setup de l'atelier          ← ON EST ICI (terminé)
[  ÉTAPE 2] Comprendre la matière première (Excel Altitude)
[  ÉTAPE 3] Dessiner le produit fini (l'Exec modèle)
[  ÉTAPE 4] Apprendre à l'IA à fabriquer (Skills + Agent)
[  ÉTAPE 5] Construire la chaîne de montage (N8N)
[  ÉTAPE 6] Tester et améliorer
[  ÉTAPE 7] Allumer l'usine pour de vrai (Prod)
```

**En résumé** : l'atelier est rangé, sécurisé, sauvegardable, et partagé avec l'équipe. On peut maintenant commencer à construire la vraie machine. 🚀

---

## 🧰 Le vocabulaire qu'on a appris (mini-lexique)

| Mot technique | En langage simple |
|---|---|
| **Repository (repo)** | Le dossier du projet, suivi par Git |
| **Commit** | Une photo / point de sauvegarde du projet |
| **Git** | La machine à remonter le temps |
| **GitHub** | Le casier partagé en ligne (Google Drive pour code) |
| **Push** | Envoyer ses photos vers le casier en ligne |
| **Pull** | Récupérer les photos des autres depuis le casier |
| **.gitignore** | La liste "ne pas sortir de l'atelier" |
| **Token (PAT)** | Le badge d'accès sécurisé à GitHub |
| **CLAUDE.md** | Le manuel d'instructions du robot-assistant |
