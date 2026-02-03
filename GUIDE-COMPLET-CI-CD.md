# Guide Complet : VS Code → GitHub → Netlify (CI/CD)

## 🎯 Objectif
Configurer un workflow professionnel de développement avec déploiement automatique sur un domaine gratuit Netlify pour tester avant de connecter ep-sophrologie.ch

**Temps total estimé : 30-45 minutes**

---

## 📋 Checklist des prérequis

Avant de commencer, assurez-vous d'avoir :
- [ ] VS Code installé
- [ ] Une connexion internet
- [ ] Les fichiers de votre site décompressés dans un dossier

**Note :** Pas besoin d'avoir Git ou GitHub déjà configurés, on va tout faire ensemble !

---

# PARTIE 1 : INSTALLATION ET CONFIGURATION (15 min)

## Étape 1 : Installer Git (5 min)

### Sur Windows :
1. Allez sur https://git-scm.com/download/win
2. Téléchargez la version 64-bit
3. Lancez l'installateur
4. **Important :** Lors de l'installation, acceptez toutes les options par défaut
5. À l'étape "Choosing the default editor", sélectionnez **"Use Visual Studio Code as Git's default editor"**
6. Continuez avec les options par défaut
7. Cliquez sur "Install"
8. Une fois terminé, fermez et rouvrez VS Code si vous l'aviez ouvert

### Sur Mac :
1. Ouvrez le Terminal (Applications → Utilitaires → Terminal)
2. Tapez : `git --version` et appuyez sur Entrée
3. Si Git n'est pas installé, le système vous proposera de l'installer
4. Suivez les instructions
5. Ou installez via Homebrew : `brew install git`

### Sur Linux :
```bash
sudo apt-get update
sudo apt-get install git
```

### Vérification :
1. Ouvrez VS Code
2. Menu : Terminal → New Terminal (ou Ctrl+ù)
3. Dans le terminal, tapez : `git --version`
4. Vous devriez voir quelque chose comme : `git version 2.43.0`
5. ✅ Git est installé !

---

## Étape 2 : Créer un compte GitHub (5 min)

1. Allez sur https://github.com
2. Cliquez sur **"Sign up"** (en haut à droite)
3. Remplissez le formulaire :
   - **Email :** Utilisez votre email professionnel
   - **Password :** Choisissez un mot de passe fort
   - **Username :** Par exemple `emeline-pollier` ou `epsophrologie`
4. Vérifiez le puzzle CAPTCHA
5. Cliquez sur "Create account"
6. GitHub va vous envoyer un code de vérification par email
7. Entrez le code
8. Choisissez "Free" pour le plan gratuit
9. Vous pouvez skip les questions optionnelles
10. ✅ Votre compte GitHub est créé !

---

## Étape 3 : Créer un compte Netlify (5 min)

1. Allez sur https://www.netlify.com
2. Cliquez sur **"Sign up"**
3. **Important :** Cliquez sur **"Sign up with GitHub"** (pas avec email)
   - C'est plus simple et connecte automatiquement les deux comptes
4. Autorisez Netlify à accéder à GitHub
5. ✅ Votre compte Netlify est créé et connecté à GitHub !

---

# PARTIE 2 : CONFIGURATION DE VS CODE (10 min)

## Étape 4 : Préparer votre projet dans VS Code

1. **Créez un dossier pour votre projet :**
   - Sur votre ordinateur, créez un dossier : `C:\Sites\ep-sophrologie` (Windows) ou `~/Sites/ep-sophrologie` (Mac/Linux)
   - Décompressez le fichier `ep-sophrologie-site.zip` dans ce dossier
   - Vous devriez avoir tous les fichiers .html, .css, images, etc. directement dans le dossier

2. **Ouvrez le projet dans VS Code :**
   - Lancez VS Code
   - Menu : **File → Open Folder** (ou Fichier → Ouvrir le dossier)
   - Sélectionnez le dossier `ep-sophrologie`
   - Cliquez sur "Sélectionner le dossier"
   - ✅ Vous voyez tous vos fichiers dans la barre latérale gauche

3. **Installez l'extension Live Server (optionnel mais très utile) :**
   - Cliquez sur l'icône Extensions (4 carrés à gauche) ou Ctrl+Shift+X
   - Cherchez **"Live Server"** par Ritwick Dey
   - Cliquez sur "Install"
   - ✅ Vous pourrez maintenant prévisualiser votre site localement

---

## Étape 5 : Configurer Git dans VS Code

1. **Ouvrez le terminal dans VS Code :**
   - Menu : Terminal → New Terminal (ou Ctrl+ù)
   - Un terminal s'ouvre en bas de la fenêtre

2. **Configurez votre identité Git :**
   ```bash
   git config --global user.name "Emeline Pollier"
   git config --global user.email "votre-email@exemple.ch"
   ```
   **Remplacez par vos vraies informations !**

3. **Vérifiez la configuration :**
   ```bash
   git config --global --list
   ```
   Vous devriez voir votre nom et email

4. ✅ Git est configuré !

---

## Étape 6 : Créer un fichier .gitignore

Ce fichier dit à Git quels fichiers ignorer.

1. Dans VS Code, créez un nouveau fichier : **Clic droit dans la barre latérale → New File**
2. Nommez-le exactement : `.gitignore` (avec le point au début !)
3. Collez ce contenu :
   ```
   # Fichiers système
   .DS_Store
   Thumbs.db
   
   # Éditeurs
   .vscode/
   .idea/
   *.swp
   *.swo
   
   # Temporaires
   *.tmp
   *.bak
   *~
   
   # Logs
   *.log
   ```
4. Sauvegardez (Ctrl+S)
5. ✅ Votre .gitignore est créé !

---

# PARTIE 3 : INITIALISER GIT ET POUSSER SUR GITHUB (10 min)

## Étape 7 : Initialiser Git dans votre projet

1. **Cliquez sur l'icône "Source Control"** (3ème icône à gauche, ressemble à une branche)
2. Vous verrez : **"No source control providers registered"**
3. Cliquez sur **"Initialize Repository"**
4. Git est maintenant activé pour ce projet
5. Vous verrez tous vos fichiers listés avec un "U" (Untracked = non suivis)
6. ✅ Git est initialisé !

---

## Étape 8 : Créer le repository sur GitHub

1. **Allez sur GitHub** dans votre navigateur
2. Cliquez sur le **"+"** en haut à droite → **"New repository"**
3. Remplissez le formulaire :
   - **Repository name :** `ep-sophrologie-site`
   - **Description :** "Site web professionnel de sophrologie"
   - **Visibilité :** Choisissez **"Public"** (gratuit, visible par tous) ou **"Private"** (gratuit aussi, caché)
   - **N'ajoutez RIEN d'autre** (pas de README, pas de .gitignore, rien)
4. Cliquez sur **"Create repository"**
5. GitHub vous montre des instructions - **GARDEZ CETTE PAGE OUVERTE**, on va l'utiliser

---

## Étape 9 : Faire le premier commit

Retour dans VS Code :

1. **Dans Source Control**, vous voyez tous vos fichiers
2. **Survolez "Changes"** et cliquez sur le **"+"** pour tout ajouter (Stage All Changes)
3. Tous les fichiers passent dans "Staged Changes"
4. **En haut, dans le champ "Message"**, écrivez :
   ```
   Premier commit - Site initial EP Sophrologie
   ```
5. **Cliquez sur la coche ✓** (ou Ctrl+Enter) pour faire le commit
6. Les fichiers disparaissent de la liste
7. ✅ Votre premier commit est fait !

---

## Étape 10 : Connecter à GitHub et pousser

### Méthode A : Via l'interface VS Code (Recommandé)

1. Dans Source Control, cliquez sur les **3 points** (...) en haut à droite
2. Cliquez sur **"Remote" → "Add Remote"**
3. Collez l'URL de votre repository GitHub :
   ```
   https://github.com/VOTRE-USERNAME/ep-sophrologie-site.git
   ```
   (Remplacez VOTRE-USERNAME par votre vrai nom d'utilisateur GitHub)
4. Appuyez sur Entrée
5. Quand demandé, entrez le nom : `origin` et appuyez sur Entrée
6. Cliquez sur **"Publish Branch"** en bas de la fenêtre Source Control
7. VS Code va vous demander de vous connecter à GitHub - **Autorisez**
8. Attendez quelques secondes...
9. ✅ Votre code est sur GitHub !

### Méthode B : Via le terminal (Alternative)

Si la méthode A ne marche pas, dans le terminal :

```bash
# Ajoutez l'origine (remplacez VOTRE-USERNAME)
git remote add origin https://github.com/VOTRE-USERNAME/ep-sophrologie-site.git

# Vérifiez
git remote -v

# Renommez la branche en main
git branch -M main

# Poussez vers GitHub
git push -u origin main
```

Lors du premier push, GitHub vous demandera de vous connecter.

---

## Étape 11 : Vérifier sur GitHub

1. **Allez sur GitHub** dans votre navigateur
2. Rafraîchissez la page de votre repository
3. Vous devriez voir tous vos fichiers !
4. ✅ Votre code est bien sur GitHub !

---

# PARTIE 4 : DÉPLOIEMENT SUR NETLIFY (10 min)

## Étape 12 : Connecter GitHub à Netlify

1. **Allez sur Netlify** : https://app.netlify.com
2. Cliquez sur **"Add new site" → "Import an existing project"**
3. Cliquez sur **"GitHub"**
4. **Autorisez Netlify** à accéder à vos repositories
5. Si on vous demande, sélectionnez **"All repositories"** ou seulement `ep-sophrologie-site`
6. ✅ Netlify peut maintenant accéder à GitHub

---

## Étape 13 : Configurer le déploiement

1. Dans Netlify, **sélectionnez votre repository** `ep-sophrologie-site` dans la liste
2. Netlify détecte les paramètres :
   - **Branch to deploy :** `main` (c'est bon !)
   - **Build command :** (laissez vide)
   - **Publish directory :** (laissez vide ou mettez `/`)
3. Cliquez sur **"Deploy ep-sophrologie-site"**
4. Netlify commence le déploiement
5. Attendez 30-60 secondes (vous verrez une barre de progression)
6. ✅ Votre site est déployé !

---

## Étape 14 : Tester votre site sur le domaine gratuit Netlify

1. Une fois le déploiement terminé, vous verrez :
   ```
   Site deployed successfully!
   https://random-name-12345.netlify.app
   ```
2. **Cliquez sur cette URL**
3. Votre site s'ouvre ! 🎉
4. **Testez toutes les pages** : naviguez, vérifiez que tout fonctionne
5. ✅ Votre site est en ligne sur un domaine gratuit !

---

## Étape 15 : Personnaliser le nom du domaine Netlify (optionnel)

Le nom `random-name-12345.netlify.app` n'est pas joli. Changeons-le :

1. Dans Netlify, allez dans **"Site settings"**
2. Cliquez sur **"Change site name"** (ou "Site information" → "Change site name")
3. Entrez un nom unique, par exemple : `ep-sophrologie-test`
4. Cliquez sur "Save"
5. Votre site est maintenant accessible à : `https://ep-sophrologie-test.netlify.app`
6. ✅ Vous avez un joli nom de domaine gratuit !

---

# PARTIE 5 : WORKFLOW DE DÉVELOPPEMENT (Comment travailler au quotidien)

## 🔄 Cycle de développement

Maintenant que tout est configuré, voici comment vous allez travailler :

### 1️⃣ Modifier votre site localement

1. **Ouvrez VS Code** avec votre projet
2. **Testez localement** (optionnel mais recommandé) :
   - Clic droit sur `index.html` → "Open with Live Server"
   - Votre site s'ouvre dans le navigateur
   - Les changements se voient en direct pendant que vous éditez
3. **Faites vos modifications** :
   - Modifiez un fichier HTML (ex: changez un texte)
   - Modifiez le CSS (ex: changez une couleur)
   - Ajoutez une image
   - etc.
4. **Sauvegardez** (Ctrl+S)

### 2️⃣ Commiter vos changements

1. **Allez dans Source Control** (icône à gauche)
2. Vous voyez vos **fichiers modifiés** avec un "M" (Modified)
3. **Survolez "Changes"** et cliquez sur le **"+"** pour tout stager
4. **Écrivez un message de commit descriptif** :
   ```
   Mise à jour de la page Ateliers
   
   - Ajout de la date du prochain atelier
   - Modification des tarifs
   ```
5. **Cliquez sur la coche ✓** pour commiter

### 3️⃣ Pousser vers GitHub

1. En bas de VS Code, vous verrez une **flèche vers le haut** avec un chiffre
2. **Cliquez dessus** (ou cliquez sur "Sync Changes" dans Source Control)
3. Vos changements sont poussés vers GitHub
4. ✅ GitHub est à jour !

### 4️⃣ Netlify déploie automatiquement !

1. **Attendez 30-60 secondes**
2. Netlify détecte le changement sur GitHub
3. Il re-déploie automatiquement votre site
4. **Rafraîchissez votre site Netlify** : `https://ep-sophrologie-test.netlify.app`
5. ✅ Vos modifications sont en ligne !

### 📊 Suivi du déploiement

Pour voir le déploiement en cours :

1. Allez sur **Netlify Dashboard**
2. Cliquez sur votre site
3. Vous voyez **"Deploys"** avec :
   - ✅ Published (en ligne)
   - 🟡 Building (en cours)
   - ❌ Failed (échec - rare)
4. Cliquez sur un déploiement pour voir les détails

---

# PARTIE 6 : FONCTIONNALITÉS AVANCÉES

## 🔍 Voir l'historique de vos changements

### Dans VS Code :
1. Installez l'extension **"GitLens"** (très utile !)
2. Vous verrez l'historique de chaque fichier
3. Vous pouvez comparer les versions

### Dans GitHub :
1. Allez sur votre repository GitHub
2. Cliquez sur "Commits"
3. Vous voyez l'historique complet
4. Cliquez sur un commit pour voir les changements

## ⏮️ Revenir en arrière

### Dans Netlify (le plus simple) :
1. Allez dans **"Deploys"**
2. Trouvez un ancien déploiement qui fonctionnait
3. Cliquez sur les **3 points** → **"Publish deploy"**
4. ✅ Votre site revient à cette version !

### Dans Git (plus technique) :
```bash
# Voir l'historique
git log --oneline

# Revenir au commit précédent
git revert HEAD

# Pousser le changement
git push
```

## 🌿 Travailler avec des branches (pour tester sans risque)

### Créer une branche de test :
```bash
# Dans le terminal VS Code
git checkout -b test-nouveau-design

# Faites vos modifications
# Committez normalement

# Poussez la branche
git push -u origin test-nouveau-design
```

**Magie de Netlify :** Il crée automatiquement une **prévisualisation** de cette branche !

1. Allez dans Netlify → "Deploys" → "Branch deploys"
2. Vous verrez : `https://test-nouveau-design--ep-sophrologie-test.netlify.app`
3. Testez votre nouveau design sans toucher au site principal !
4. Si c'est bon, mergez la branche dans `main` :
   ```bash
   git checkout main
   git merge test-nouveau-design
   git push
   ```
5. Si ce n'est pas bon, supprimez juste la branche

---

# PARTIE 7 : PASSER EN PRODUCTION AVEC VOTRE VRAI DOMAINE

## Quand vous êtes prêt à utiliser ep-sophrologie.ch :

1. **Dans Netlify → Domain settings**
2. Cliquez sur **"Add custom domain"**
3. Entrez : `ep-sophrologie.ch`
4. Suivez les instructions pour configurer les DNS dans Infomaniak
5. Attendez que le SSL s'active
6. ✅ Votre site est en ligne sur votre vrai domaine !

**Note :** Le domaine de test `ep-sophrologie-test.netlify.app` continuera de fonctionner, vous pouvez le garder pour tester.

---

# AIDE-MÉMOIRE : COMMANDES GIT ESSENTIELLES

```bash
# Vérifier le statut de vos fichiers
git status

# Voir les différences avant de commiter
git diff

# Ajouter tous les fichiers modifiés
git add .

# Commiter avec message
git commit -m "Votre message ici"

# Pousser vers GitHub
git push

# Tirer les derniers changements de GitHub (si vous travaillez sur plusieurs machines)
git pull

# Voir l'historique
git log --oneline

# Créer une nouvelle branche
git checkout -b nom-de-la-branche

# Changer de branche
git checkout main

# Annuler les modifications non committées
git checkout .
```

---

# DÉPANNAGE - PROBLÈMES COURANTS

## ❌ "Failed to push"
**Cause :** Quelqu'un d'autre (ou vous sur une autre machine) a modifié GitHub
**Solution :**
```bash
git pull
git push
```

## ❌ "Authentication failed"
**Cause :** GitHub a besoin de vos identifiants
**Solution :**
1. VS Code devrait ouvrir une fenêtre de connexion
2. Connectez-vous à GitHub
3. Autorisez VS Code

## ❌ Le site ne se met pas à jour sur Netlify
**Solutions :**
1. Attendez 2-3 minutes (parfois c'est juste lent)
2. Vérifiez dans Netlify → Deploys que le déploiement est terminé
3. Faites Ctrl+F5 dans votre navigateur pour vider le cache
4. Vérifiez que vous avez bien poussé sur GitHub

## ❌ Erreur "merge conflict"
**Cause :** Vous avez modifié le même fichier à deux endroits différents
**Solution :**
1. Ouvrez le fichier en conflit dans VS Code
2. VS Code vous montre les deux versions
3. Choisissez celle que vous voulez garder
4. Sauvegardez et committez

---

# ✅ CHECKLIST FINALE

Configuration initiale :
- [ ] Git installé et configuré
- [ ] Compte GitHub créé
- [ ] Compte Netlify créé (via GitHub)
- [ ] Projet ouvert dans VS Code
- [ ] Repository GitHub créé
- [ ] Code poussé sur GitHub
- [ ] Site déployé sur Netlify
- [ ] Domaine gratuit Netlify configuré et testé
- [ ] Extension Live Server installée (optionnel)
- [ ] Extension GitLens installée (optionnel)

Vérifications :
- [ ] Tous les fichiers sont sur GitHub
- [ ] Le site s'affiche correctement sur Netlify
- [ ] Toutes les pages fonctionnent
- [ ] Les images s'affichent
- [ ] La navigation fonctionne
- [ ] Le formulaire est présent (configuration Formspree à faire séparément)

Test du workflow :
- [ ] J'ai modifié un fichier localement
- [ ] J'ai fait un commit
- [ ] J'ai poussé vers GitHub
- [ ] Netlify a déployé automatiquement
- [ ] Les changements sont visibles sur le site

---

# 🎓 RESSOURCES POUR ALLER PLUS LOIN

**Git et GitHub :**
- Documentation Git en français : https://git-scm.com/book/fr/v2
- GitHub Learning Lab : https://lab.github.com/
- Git Cheat Sheet : https://education.github.com/git-cheat-sheet-education.pdf

**Netlify :**
- Documentation : https://docs.netlify.com/
- Tutoriels : https://www.netlify.com/blog/tags/tutorial/

**VS Code :**
- Documentation : https://code.visualstudio.com/docs
- Extensions recommandées : GitLens, Live Server, Prettier

**Tutoriels vidéo YouTube (en français) :**
- "Git et GitHub pour les débutants"
- "VS Code pour les débutants"
- "Déployer un site sur Netlify"

---

# 🎉 FÉLICITATIONS !

Vous avez maintenant un workflow de développement professionnel :

✅ Versioning de votre code avec Git
✅ Sauvegarde automatique sur GitHub
✅ Déploiement automatique sur Netlify
✅ Site accessible sur un domaine gratuit pour tester
✅ Possibilité de revenir en arrière facilement
✅ Prévisualisation des branches de test
✅ SSL gratuit et automatique
✅ Performance optimale

**C'est exactement comme travaillent les développeurs professionnels !**

Vous pouvez maintenant :
1. Tester votre site sur le domaine Netlify
2. Faire des modifications et voir qu'elles se déploient automatiquement
3. Quand vous êtes satisfait, connecter votre vrai domaine ep-sophrologie.ch

**Besoin d'aide ? N'hésitez pas à demander !** 😊
