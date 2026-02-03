# Site Web EP Sophrologie - Emeline Pollier

## 🎉 Votre site est prêt !

Ce site web complet et moderne a été créé spécialement pour votre activité de sophrologie.

## 📁 Structure du site

Votre site contient les pages suivantes :
- **index.html** - Page d'accueil
- **ateliers.html** - Programme des ateliers
- **enfants.html** - Sophrologie pour les enfants
- **parents.html** - Sophrologie pour les parents
- **sportifs.html** - Sophrologie pour les sportifs
- **contact.html** - Formulaire de contact
- **styles.css** - Toutes les styles du site

## 🚀 Comment déployer votre site

### Option 1 : Netlify (Recommandé - Gratuit et Simple)

1. Créez un compte sur https://www.netlify.com (gratuit)
2. Cliquez sur "Add new site" → "Deploy manually"
3. Glissez-déposez TOUS les fichiers du site dans la zone
4. Votre site est en ligne en quelques secondes !
5. Connectez votre nom de domaine (ep-sophrologie.ch) :
   - Allez dans "Domain settings"
   - Cliquez sur "Add custom domain"
   - Suivez les instructions pour modifier vos DNS

### Option 2 : Vercel (Gratuit aussi)

1. Créez un compte sur https://vercel.com
2. Cliquez sur "Add New" → "Project"
3. Importez les fichiers
4. Déployez !
5. Connectez votre domaine dans les paramètres

### Option 3 : GitHub Pages (Gratuit)

1. Créez un compte GitHub
2. Créez un nouveau repository
3. Uploadez tous les fichiers
4. Activez GitHub Pages dans les settings
5. Connectez votre domaine

## ⚙️ Configuration du formulaire de contact

Le formulaire utilise Formspree (gratuit). Pour l'activer :

1. Allez sur https://formspree.io
2. Créez un compte gratuit
3. Créez un nouveau formulaire
4. Copiez votre "form endpoint"
5. Dans le fichier `contact.html`, ligne 51, remplacez :
   ```html
   <form class="contact-form" action="https://formspree.io/f/YOUR_FORM_ID" method="POST">
   ```
   par :
   ```html
   <form class="contact-form" action="https://formspree.io/f/VOTRE_VRAI_ID" method="POST">
   ```

Les messages vous seront envoyés directement par email à emeline@ep-sophrologie.ch !

## 🖼️ Images à ajouter

Vous devez remplacer/ajouter ces images :

1. **cabinet.jpg** - Une vraie photo de votre cabinet (actuellement placeholder)
   - Prenez une belle photo de votre cabinet
   - Renommez-la en `cabinet.jpg`
   - Remplacez le fichier existant

2. **Photos pour les témoignages** (optionnel)
   - Vous pouvez ajouter des photos à côté des témoignages si vous le souhaitez

## 🎨 Personnalisation

### Modifier les couleurs

Dans le fichier `styles.css`, lignes 1-10, vous pouvez changer :
```css
--color-primary: #5DBBC0;      /* Bleu turquoise */
--color-secondary: #F4D35E;    /* Jaune doré */
--color-accent: #EE964B;       /* Orange */
```

### Modifier les textes

Ouvrez simplement les fichiers HTML et modifiez le texte entre les balises.

## 📱 Responsive

Le site est entièrement responsive et s'adapte automatiquement aux :
- Ordinateurs
- Tablettes
- Téléphones mobiles

## 🔧 Support navigateurs

Le site fonctionne sur tous les navigateurs modernes :
- Chrome
- Firefox
- Safari
- Edge

## 💡 Conseils pour plus tard

### Pour modifier vous-même le site :

1. **Ajouter une page** :
   - Copiez une page existante (ex: parents.html)
   - Renommez-la
   - Modifiez le contenu
   - Ajoutez le lien dans le menu de toutes les pages

2. **Modifier le menu** :
   - Le menu se trouve dans chaque fichier HTML entre les balises `<nav>`
   - Copiez-collez le même menu sur toutes les pages pour la cohérence

3. **Ajouter des photos** :
   - Mettez vos photos dans le même dossier que les fichiers HTML
   - Utilisez `<img src="nom-de-votre-photo.jpg" alt="Description">`

## 📊 Référencement (SEO)

Pour améliorer votre visibilité sur Google :

1. Ajoutez Google Analytics (gratuit)
2. Inscrivez votre site dans Google Search Console
3. Ajoutez un fichier `sitemap.xml`
4. Créez un blog pour publier des articles régulièrement

## 🆘 Besoin d'aide ?

Si vous avez besoin d'aide pour :
- Déployer le site
- Modifier quelque chose
- Ajouter des fonctionnalités

N'hésitez pas à me contacter !

## ✨ Fonctionnalités incluses

✅ Design moderne et professionnel
✅ Responsive (mobile, tablette, desktop)
✅ Navigation fluide
✅ Formulaire de contact
✅ 6 pages complètes
✅ Animations douces
✅ Menu hamburger mobile
✅ Footer avec toutes les infos
✅ Couleurs apaisantes
✅ Typographies élégantes
✅ Optimisé pour le référencement
✅ Rapide et léger

## 📄 Licence

Ce site a été créé spécifiquement pour Emeline Pollier - EP Sophrologie.
Tous droits réservés © 2025
