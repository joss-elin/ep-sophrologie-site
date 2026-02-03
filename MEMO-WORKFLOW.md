# 🚀 AIDE-MÉMOIRE RAPIDE - Workflow Quotidien

## ⚡ Version Ultra-Rapide (pour quand vous connaissez déjà)

### Modifier votre site :

```
1. Ouvrir VS Code avec votre projet
2. Modifier les fichiers
3. Sauvegarder (Ctrl+S)
4. Source Control → Stage All (+)
5. Écrire un message de commit
6. Cliquer sur la coche ✓
7. Cliquer sur "Sync Changes"
8. Attendre 1 minute
9. ✅ Site mis à jour sur Netlify !
```

---

## 📝 Workflow Détaillé Illustré

```
┌─────────────────────────────────────────────────────────────┐
│                    VOTRE ORDINATEUR                         │
│                                                             │
│  VS Code                                                    │
│  ├── 📝 Modifier index.html                                │
│  ├── 💾 Sauvegarder (Ctrl+S)                               │
│  ├── 👁️  Prévisualiser (Live Server)                       │
│  └── ✅ Satisfait du résultat                               │
│                          ↓                                   │
│                     GIT COMMIT                              │
│  ├── 📋 Source Control                                     │
│  ├── ➕ Stage All Changes                                   │
│  ├── 💬 Message: "Mise à jour de la page Ateliers"        │
│  └── ✓ Commit                                              │
│                          ↓                                   │
│                      GIT PUSH                               │
│  └── 🔄 Sync Changes                                        │
└─────────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────────┐
│                       GITHUB                                │
│                    (Dans le cloud)                          │
│                                                             │
│  📦 Repository: ep-sophrologie-site                         │
│  ├── 💾 Code sauvegardé                                     │
│  ├── 📜 Historique des versions                             │
│  └── 🔔 Notifie Netlify du changement                       │
└─────────────────────────────────────────────────────────────┘
                           ↓
┌─────────────────────────────────────────────────────────────┐
│                       NETLIFY                               │
│                  (Hébergement gratuit)                      │
│                                                             │
│  🤖 Détection automatique du changement                     │
│  ├── 📥 Récupère le code de GitHub                          │
│  ├── 🏗️  Build le site (30 secondes)                        │
│  ├── 🚀 Déploie sur les serveurs                            │
│  ├── 🔒 Active le SSL (HTTPS)                               │
│  └── ✅ Site en ligne !                                      │
│                                                             │
│  🌐 Accessible à :                                          │
│     https://ep-sophrologie-test.netlify.app                 │
└─────────────────────────────────────────────────────────────┘
```

---

## 🎯 Commandes Git - Mémo Visuel

### 📊 Vérifier l'état actuel
```bash
git status
```
**Montre :** Fichiers modifiés, ajoutés, supprimés

### ➕ Ajouter des fichiers
```bash
git add .                    # Ajouter TOUS les fichiers
git add fichier.html         # Ajouter UN fichier spécifique
```

### 💾 Faire un commit
```bash
git commit -m "Votre message descriptif"
```
**Bon message :** "Ajout de la section témoignages"
**Mauvais message :** "update" ou "fix"

### 🚀 Pousser vers GitHub
```bash
git push
```

### 📥 Récupérer de GitHub
```bash
git pull
```

### 🌿 Créer une branche de test
```bash
git checkout -b nom-branche    # Créer et basculer
git push -u origin nom-branche # Pousser la branche
```

### ↩️ Retourner à la branche principale
```bash
git checkout main
```

### 📜 Voir l'historique
```bash
git log --oneline              # Historique compact
git log --oneline --graph      # Avec graphique
```

---

## 🔧 Interface VS Code - Où cliquer ?

### Icônes importantes dans la barre latérale gauche :

```
┌──────┐
│  📁  │  Explorer - Voir vos fichiers
├──────┤
│  🔍  │  Search - Rechercher dans les fichiers
├──────┤
│  🔀  │  Source Control - GIT (c'est là que vous irez souvent !)
├──────┤
│  🐛  │  Debug - Debugger (pas nécessaire pour vous)
├──────┤
│  🧩  │  Extensions - Installer des extensions
└──────┘
```

### Zone Source Control (🔀) :

```
Source Control
├── Message: [Écrivez votre message de commit ici]
│            [                                    ]
│   
├── ✓ Commit (cliquez ici après avoir écrit le message)
│
├── ... More Actions (3 points)
│   ├── Push
│   ├── Pull
│   └── Sync
│
└── Changes (fichiers modifiés)
    ├── index.html (M)
    ├── styles.css (M)
    └── [Cliquez sur + pour "Stage"]
```

### En bas de VS Code :

```
┌────────────────────────────────────────────────────────────┐
│ main ✓  ↑0 ↓0  ⚠ 0  ⓘ 0                          UTF-8   │
│  │       │      │     │                                     │
│  │       │      │     └─ Nombre d'infos                    │
│  │       │      └─ Nombre d'avertissements                │
│  │       └─ Commits à pousser/tirer                       │
│  └─ Branche actuelle                                       │
└────────────────────────────────────────────────────────────┘
```

---

## ⚠️ Messages d'erreur courants et solutions

### ❌ "Please commit your changes or stash them before you can merge"
**Signifie :** Vous avez des modifications non sauvegardées
**Solution :** Committez d'abord vos changements

### ❌ "fatal: Authentication failed"
**Signifie :** VS Code n'arrive pas à se connecter à GitHub
**Solution :** Reconnectez-vous à GitHub via VS Code

### ❌ "error: failed to push some refs"
**Signifie :** GitHub a des changements que vous n'avez pas
**Solution :**
```bash
git pull
git push
```

### ❌ "CONFLICT: Merge conflict in fichier.html"
**Signifie :** Le même fichier a été modifié à 2 endroits
**Solution :**
1. Ouvrez le fichier dans VS Code
2. VS Code montre les 2 versions
3. Choisissez "Accept Current Change" ou "Accept Incoming Change"
4. Sauvegardez et committez

---

## 📋 Checklist Avant Chaque Modification

Avant de commencer à travailler :
- [ ] J'ai ouvert VS Code avec le bon projet
- [ ] Je suis sur la bonne branche (`main` en bas à gauche)
- [ ] J'ai fait `git pull` pour avoir la dernière version
- [ ] Live Server est lancé pour prévisualiser

Avant de pousser :
- [ ] J'ai testé mes modifications en local
- [ ] Toutes les pages fonctionnent
- [ ] Pas d'erreurs dans la console du navigateur (F12)
- [ ] Mon message de commit est descriptif
- [ ] J'ai ajouté tous les fichiers nécessaires

Après avoir poussé :
- [ ] J'attends 1-2 minutes
- [ ] Je vérifie le déploiement dans Netlify
- [ ] Je teste le site en ligne
- [ ] Tout fonctionne ? ✅ Parfait !

---

## 🎨 Bonnes Pratiques

### ✅ Bons messages de commit :
```
✓ "Ajout de la section témoignages sur la page d'accueil"
✓ "Modification des tarifs dans la page Ateliers"
✓ "Correction de l'erreur de lien sur la page Contact"
✓ "Mise à jour de la photo du cabinet"
```

### ❌ Mauvais messages de commit :
```
✗ "update"
✗ "fix"
✗ "changes"
✗ "test"
✗ "asdf"
```

### 📦 Quand commiter ?

**Committez souvent !** Idéalement :
- ✅ Après chaque fonctionnalité terminée
- ✅ Après chaque correction de bug
- ✅ À la fin de chaque session de travail
- ✅ Avant de tester quelque chose de nouveau

**Ne committez pas :**
- ❌ Du code qui ne fonctionne pas
- ❌ Des fichiers temporaires ou de test
- ❌ Des mots de passe ou informations sensibles

---

## 🔄 Workflow selon votre objectif

### 🎯 Petite modification (changement de texte, mise à jour)
```
1. Modifier le fichier
2. Sauvegarder
3. Commit + Push
4. Attendre le déploiement
```
**Temps total :** 2-3 minutes

### 🎨 Grosse modification (nouveau design, nouvelle page)
```
1. Créer une branche de test
2. Faire les modifications
3. Tester en local
4. Commit + Push de la branche
5. Vérifier la prévisualisation Netlify
6. Si OK : merger dans main
7. Si pas OK : continuer à modifier ou abandonner
```
**Temps total :** Variable selon la taille

### 🐛 Correction urgente
```
1. Identifier le problème
2. Modifier directement sur main
3. Commit avec message clair : "FIX: ..."
4. Push immédiat
5. Vérifier le déploiement
```
**Temps total :** 5 minutes

---

## 📞 Contacts Utiles en Cas de Problème

**Documentation :**
- Git : https://git-scm.com/doc
- GitHub : https://docs.github.com
- Netlify : https://docs.netlify.com
- VS Code : https://code.visualstudio.com/docs

**Communautés (en français) :**
- Stack Overflow (français) : https://fr.stackoverflow.com
- Discord des développeurs francophones
- Reddit r/learnprogramming

**Vous pouvez aussi :**
- Me recontacter sur Claude 😊
- Chercher sur YouTube : "git [votre problème] français"
- Demander à ChatGPT ou Claude

---

## 💾 Sauvegarder ce mémo

**Imprimez cette page** et gardez-la près de votre ordinateur !

Ou créez un fichier `MEMO.md` dans votre projet avec vos propres notes.

---

## 🎓 Progression Suggérée

### Semaine 1-2 : Les Bases
- ✅ Modifier → Sauvegarder → Commit → Push
- ✅ Vérifier le déploiement sur Netlify
- ✅ S'habituer au workflow

### Semaine 3-4 : Intermédiaire
- ✅ Utiliser les branches pour tester
- ✅ Revenir en arrière en cas d'erreur
- ✅ Bien rédiger les messages de commit

### Mois 2+ : Avancé
- ✅ Utiliser GitLens pour voir l'historique
- ✅ Comparer les versions
- ✅ Travailler avec plusieurs branches en parallèle

---

**🎉 Vous êtes maintenant équipé pour gérer votre site comme un pro !**

Gardez ce mémo à portée de main et n'hésitez pas à y revenir quand vous avez un doute.

**Bon développement ! 🚀**
