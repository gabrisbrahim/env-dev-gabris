# env-dev-gabris – Mon environnement de développement (B1 DEV, IFRAN)

Environnement de développement de GABRIS Brahim – B1 DEV, IFRAN.
Fiche de mon poste de travail sous Ubuntu avec WSL et guide d'installation.

## Mon ordinateur

| Élément | Valeur |
| ----------- | ------------------- |
| Système | Windows 11 Famille |
| Processeur | 13th Gen Intel(R) Core(TM) i7-13620H |
| Mémoire | 16 Go |
| Éditeur | VS Code |

## Mon Ubuntu

| Élément | Valeur |
| ------------ | -------------------- |
| Version | Ubuntu 26.04.1 LTS |
| Lancé avec | WSL |
| Processeurs | 16 |
| Mémoire | 7,6 Go |
| Utilisateur | gabri |

## Logiciels installés dans Ubuntu

| Logiciel | Version | Commande d'installation |
| -------- | -------- | ---------------------------------------------- |
| Git | 2.53.0 | déjà présent dans Ubuntu |
| tree | 2.3.1 | `sudo apt install -y tree` |
| htop | 3.4.1 | `sudo apt install -y htop` |
| nano | 8.7.1 | `sudo apt install -y nano` |
| Node.js | v22.22.1 | dépôt NodeSource, puis `sudo apt install -y nodejs` |
| npm | 11.16.0 | installé avec Node.js |

## Installation

### 1. Installer Ubuntu et VS Code

- **Windows :** dans le Terminal (administrateur), taper `wsl --install`, redémarrer, puis choisir un nom d'utilisateur et un mot de passe Ubuntu.
- **Mac :** installer Homebrew depuis [brew.sh](https://brew.sh), puis taper `brew install colima docker`, `colima start` et `colima ssh`.
- Installer VS Code depuis [code.visualstudio.com](https://code.visualstudio.com).

### 2. Installer les outils dans Ubuntu

1. Ouvrir Ubuntu et aller dans le dossier du projet : `cd ~/dev/env-dev-gabris`
2. Lancer le script d'installation : `./scripts/installer.sh`

## Vérification

Lancer `./scripts/verifier.sh` dans Ubuntu.
Résultat attendu : une version pour Ubuntu, Git, Node.js, npm et tree.

## Contenu du dossier

| Fichier ou dossier | Rôle |
| ------------------------ | -------------------------------------------- |
| `README.md` | Cette documentation |
| `JOURNAL.md` | Le journal de mes choix |
| `docs/aide-memoire.md` | Mon aide-mémoire des commandes Linux |
| `scripts/installer.sh` | Installe les outils dans Ubuntu |
| `scripts/verifier.sh` | Vérifie que tout est prêt |

## Historique  Ce dossier est suivi avec Git depuis le sous-module 2. 
Ce dossier est suivi avec Git depuis le sous-module 2.

## Guide d'utilisation du projet

1. **Cloner le projet :**
   ```bash
   git clone https://github.com/gabrisbrahim/env-dev-gabris.git
   cd env-dev-gabris
   ```
2. **Lancer les scripts d'environnement :**
   ```bash
   ./scripts/installer.sh
   ./scripts/verifier.sh
   ```
3. **Consulter l'aide-mémoire :**
   Le fichier `docs/aide-memoire.md` répertorie toutes les commandes nécessaires pour Linux, Git et les branches.
