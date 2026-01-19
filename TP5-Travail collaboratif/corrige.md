# TP-5 : Travail collaboratif sur GitLab

## Objectif
Mettre en place un environnement de travail collaboratif avec GitLab

## Étapes détaillées

### 1. Création des comptes utilisateurs

#### Accès à l'interface d'administration
- Connectez-vous à GitLab en tant qu'administrateur
- Cliquez sur l'icône **Menu** (en haut à gauche)
- Allez dans **Admin Area** (ou **Zone d'administration**)

#### Création du compte `manager`
- Dans Admin Area, cliquez sur **Users** → **New User**
- Remplissez les informations :
  - Name : `Manager User`
  - Username : `manager`
  - Email : `manager@example.com`
- Cochez **Create user**
- Définissez un mot de passe (ou envoyez un email de réinitialisation)

#### Création du compte `dev1`
- Répétez l'opération :
  - Name : `Developer 1`
  - Username : `dev1`
  - Email : `dev1@example.com`
- Créez l'utilisateur et définissez le mot de passe

#### Création du compte `dev2`
- Répétez l'opération :
  - Name : `Developer 2`
  - Username : `dev2`
  - Email : `dev2@example.com`
- Créez l'utilisateur et définissez le mot de passe

### 2. Création du groupe de projet

- Déconnectez-vous du compte admin
- Connectez-vous avec le compte `manager`
- Cliquez sur **Groups** → **New Group**
- Sélectionnez **Create group**
- Remplissez les informations :
  - Group name : `eazytraining`
  - Visibility level : **Private** (recommandé)
- Cliquez sur **Create group**

### 3. Ajout des membres au groupe

- Dans le groupe `eazytraining`, cliquez sur **Manage** → **Members**
- Ajoutez `manager` :
  - Recherchez : `manager`
  - Role : **Owner**
  - Cliquez sur **Invite**
- Ajoutez `dev1` :
  - Recherchez : `dev1`
  - Role : **Developer**
  - Cliquez sur **Invite**
- Ajoutez `dev2` :
  - Recherchez : `dev2`
  - Role : **Developer**
  - Cliquez sur **Invite**

### 4. Création du repository

- Restez connecté avec `manager`
- Dans le groupe `eazytraining`, cliquez sur **New project**
- Sélectionnez **Create blank project**
- Remplissez :
  - Project name : `deploy-users`
  - Visibility level : **Private**
  - Cochez **Initialize repository with a README** (optionnel)
- Cliquez sur **Create project**

### 5. Configuration Git locale et push du code

#### Configuration
```bash
git config --global user.name "manager"
git config --global user.email "manager@example.com"
```

#### Clone du repository
```bash
git clone http://your-gitlab-url/eazytraining/deploy-users.git
cd deploy-users
```

#### Ajout du code
```bash
# Copiez vos fichiers dans le dossier deploy-users
cp -r /chemin/vers/votre/code/* .
```

#### Push
```bash
git add .
git commit -m "Initial commit: ajout du code deploy-users"
git push origin main
```

### 6. Test de collaboration

#### Connexion en tant que dev1
- Déconnectez-vous du compte `manager`
- Connectez-vous avec `dev1`

#### Clone et modification
```bash
git clone http://your-gitlab-url/eazytraining/deploy-users.git
cd deploy-users
git checkout -b feature-dev1
```

#### Modification d'un fichier
```bash
# Modifiez un fichier, par exemple README.md
echo "Modification par dev1" >> README.md
git add README.md
git commit -m "Ajout modification par dev1"
git push origin feature-dev1
```

#### Création d'une Merge Request
- Sur GitLab, allez dans le projet `deploy-users`
- Cliquez sur **Merge Requests** → **New Merge Request**
- Sélectionnez :
  - Source branch : `feature-dev1`
  - Target branch : `main`
- Remplissez le titre et la description
- Cliquez sur **Create Merge Request**

#### Validation par le manager
- Déconnectez-vous de `dev1`
- Connectez-vous avec `manager`
- Allez dans **Merge Requests**
- Examinez la Merge Request
- Cliquez sur **Merge** pour accepter

## Vérification finale

- Vérifiez que le code de `dev1` est bien intégré dans la branche `main`
- Répétez le test avec `dev2` pour confirmer le workflow collaboratif