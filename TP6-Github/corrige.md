# TP-6 : GitHub

## Objectif
Apprendre le workflow de contribution sur GitHub

## Étapes détaillées

### 1. Création d'un compte GitHub

- Allez sur [https://github.com](https://github.com)
- Cliquez sur **Sign up**
- Remplissez les informations :
  - Email
  - Mot de passe
  - Username
- Vérifiez votre email
- Complétez la configuration de votre profil

### 2. Fork du repository

- Allez sur le repository : [https://github.com/eazytrainingfr/webapp.git](https://github.com/eazytrainingfr/webapp.git)
- Cliquez sur le bouton **Fork** (en haut à droite)
- Le repository sera copié dans votre compte GitHub

### 3. Clone du repository forké
```bash
git clone https://github.com/VOTRE-USERNAME/webapp.git
cd webapp
```

### 4. Création d'une branche de travail
```bash
git checkout -b modification-readme
```

### 5. Modification du fichier README.md

- Ouvrez le fichier `README.md` dans votre éditeur
- Ajoutez votre prénom dans le fichier
- Exemple :
```md
  ## Contributeurs
  - Votre Prénom
```
- Sauvegardez le fichier

### 6. Commit et push des modifications
```bash
git add README.md
git commit -m "Ajout de mon prénom dans README.md"
git push origin modification-readme
```

### 7. Création d'une Pull Request (PR)

- Allez sur votre repository forké sur GitHub
- Cliquez sur **Compare & pull request**
- Vérifiez les branches :
  - Base repository : `eazytrainingfr/webapp` - branche `main`
  - Head repository : `VOTRE-USERNAME/webapp` - branche `modification-readme`
- Ajoutez un titre : "Ajout de mon prénom dans README.md"
- Ajoutez une description claire de votre modification
- Cliquez sur **Create pull request**

### 8. Vérification

- Vérifiez que votre PR est bien créée
- Attendez la revue et l'acceptation par le propriétaire du repository
- Une fois acceptée, votre contribution sera intégrée dans le projet original

## Bonnes pratiques

- Toujours créer une branche pour vos modifications
- Faire des commits clairs et descriptifs
- Tester votre code avant de faire une PR
- Respecter les conventions du projet