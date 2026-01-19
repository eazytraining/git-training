# TP-1 : Installation de Git

## Objectif
Installer et configurer Git sur votre système

## Étapes détaillées

### 1. Installation de Git sur Linux

#### Pour Ubuntu/Debian
```bash
sudo apt update
sudo apt install git -y
```

#### Pour CentOS/RHEL
```bash
sudo yum install git -y
```

#### Pour Fedora
```bash
sudo dnf install git -y
```

### 2. Installation de Git sur Windows

#### Téléchargement
- Allez sur [https://git-scm.com/download/windows](https://git-scm.com/download/windows)
- Téléchargez la dernière version de Git pour Windows
- Lancez l'installateur `.exe`

#### Installation
- Suivez l'assistant d'installation
- Laissez les options par défaut (recommandé)
- Options importantes :
  - Éditeur par défaut : choisissez votre éditeur préféré
  - PATH environment : sélectionnez "Git from the command line and also from 3rd-party software"
  - Line ending conversions : "Checkout Windows-style, commit Unix-style"
- Cliquez sur **Install**
- Terminez l'installation

### 3. Vérification de l'installation

Ouvrez un terminal (Linux) ou Git Bash (Windows) et exécutez :
```bash
git --version
```

Vous devriez voir la version de Git installée, par exemple :
```
git version 2.34.1
```

### 4. Configuration de Git

#### Configuration de l'identité

Configurez votre nom et email (obligatoire pour les commits) :
```bash
git config --global user.name "Votre Nom"
git config --global user.email "votre.email@example.com"
```

#### Configuration de l'éditeur par défaut (optionnel)
```bash
# Pour nano
git config --global core.editor "nano"

# Pour vim
git config --global core.editor "vim"

# Pour VS Code
git config --global core.editor "code --wait"
```

#### Configuration des couleurs (optionnel)
```bash
git config --global color.ui auto
```

### 5. Vérification de la configuration

Affichez votre configuration :
```bash
git config --list
```

Ou vérifiez des paramètres spécifiques :
```bash
git config user.name
git config user.email
```

## Résultat attendu

Après ces étapes, Git est installé et configuré sur votre machine. Vous êtes prêt à l'utiliser pour vos projets.