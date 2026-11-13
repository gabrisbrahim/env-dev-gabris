# Aide-mémoire du terminal Linux

## Se déplacer

| Commande | Ce qu'elle fait | Exemple |
| -------- | --------------- | ------- |
| `pwd` | Affiche le dossier où je suis (*print working directory*) | `pwd` |
| `cd dev` | Entre dans le dossier `dev` (*change directory*) | `cd dev` |
| `cd ..` | Remonte d'un niveau vers le dossier parent | `cd ..` |
| `cd` | Revient au dossier personnel (`~`) | `cd` |
| `cd ~/dev` | Va directement dans le dossier dev de mon compte | `cd ~/dev` |
| `cd /` | Va à la racine de Linux | `cd /` |

## Fichiers et dossiers

| Commande | Ce qu'elle fait | Exemple |
| -------- | --------------- | ------- |
| `ls` | Affiche le contenu du dossier courant | `ls` |
| `ls -l` | Affiche le contenu en détail (droits, taille, date) | `ls -l` |
| `ls -a` | Affiche tout le contenu, y compris les fichiers cachés | `ls -a` |
| `ls -R` | Affiche le contenu du dossier et de ses sous-dossiers | `ls -R` |
| `mkdir projet` | Crée le dossier `projet` (*make directory*) | `mkdir projet` |
| `mkdir -p a/b/c` | Crée plusieurs niveaux de dossiers d'un coup | `mkdir -p projet/assets/images` |
| `touch vide.txt` | Crée un fichier vide | `touch test.md` |
| `cp a.txt b.txt` | Copie un fichier (*copy*) | `cp notes.txt copie.txt` |
| `cp -r dossier copie` | Copie un dossier et tout son contenu (*recursive*) | `cp -r projet projet-sauvegarde` |
| `mv a.txt dossier/` | Déplace un fichier dans un dossier (*move*) | `mv notes.txt archives/` |
| `mv ancien.txt nouveau.txt` | Renomme un fichier ou un dossier | `mv notes.txt idees.txt` |
| `rm notes.txt` | Supprime un fichier (attention : pas de corbeille !) | `rm notes.txt` |
| `rm -i notes.txt` | Supprime un fichier en demandant confirmation | `rm -i notes.txt` |
| `rm -r dossier` | Supprime un dossier et tout son contenu | `rm -r projet-sauvegarde` |
| `rmdir dossier` | Supprime un dossier vide | `rmdir photos` |
| `*` *(joker)* | Remplace n'importe quelle suite de lettres | `ls *.js` |

## Lire et chercher

| Commande | Ce qu'elle fait | Exemple |
| -------- | --------------- | ------- |
| `cat notes.txt` | Affiche tout le contenu du fichier | `cat README.md` |
| `less notes.txt` | Affiche le fichier page par page (Espace pour avancer, `q` pour quitter) | `less logs/app.log` |
| `head -n 5 notes.txt` | Affiche les 5 premières lignes | `head -n 5 notes.txt` |
| `tail -n 5 notes.txt` | Affiche les 5 dernières lignes | `tail -n 5 notes.txt` |
| `wc -l notes.txt` | Compte le nombre de lignes (*word count*, `-l` : lines) | `wc -l app.log` |
| `grep ERROR app.log` | Affiche les lignes qui contiennent le mot `ERROR` | `grep ERROR app.log` |
| `grep -i error app.log` | Cherche sans faire la différence majuscules/minuscules | `grep -i error app.log` |
| `grep -c ERROR app.log` | Compte le nombre de lignes qui contiennent le mot | `grep -c ERROR app.log` |
| `grep -r "todo" .` | Cherche dans tous les fichiers du dossier courant et sous-dossiers | `grep -r "todo" .` |
| `grep -r -l "todo" .` | Affiche seulement le nom des fichiers trouvés | `grep -r -l "todo" .` |
| `find . -name "*.js"` | Retrouve un fichier par son nom dans le dossier courant | `find . -name "*.js"` |

## Redirections et enchaînements

| Commande / Symbole | Ce qu'elle fait | Exemple |
| ------------------ | --------------- | ------- |
| `>` | Écrit le résultat dans un fichier (écrase le contenu précédent) | `ls > liste.txt` |
| `>>` | Ajoute le résultat à la fin du fichier sans effacer | `echo "Idée 2" >> idees.txt` |
| `\|` *(pipe)* | Donne le résultat d'une commande à la suivante | `grep ERROR app.log \| wc -l` |
| `sort` | Trie les lignes dans l'ordre alphabétique | `sort liste.txt` |

## Processus

| Commande | Ce qu'elle fait | Exemple |
| -------- | --------------- | ------- |
| `sleep 300 &` | Lance un programme en arrière-plan (`&`) sans bloquer le terminal | `sleep 300 &` |
| `jobs` | Liste les programmes lancés en arrière-plan depuis ce terminal | `jobs` |
| `ps` | Liste les processus de ce terminal avec leur PID | `ps` |
| `ps aux` | Liste tous les processus d'Ubuntu | `ps aux` |
| `ps aux \| grep sleep` | Retrouve les processus `sleep` dans la liste | `ps aux \| grep sleep` |
| `kill 1234` | Demande au processus n° 1234 de s'arrêter proprement | `kill 1234` |
| `kill -9 1234` | Force l'arrêt immédiat du processus n° 1234 | `kill -9 1234` |
| `pkill sleep` | Arrête tous les processus qui s'appellent `sleep` | `pkill sleep` |
| `top` | Affiche les processus en temps réel (`q` pour quitter) | `top` |
| `Ctrl + C` | Arrête le programme qui occupe le terminal | `Ctrl + C` |

## Droits et utilisateurs

| Commande | Ce qu'elle fait | Exemple |
| -------- | --------------- | ------- |
| `whoami` | Affiche mon nom d'utilisateur | `whoami` |
| `sudo commande` | Exécute une commande avec les droits administrateur (root) | `sudo apt update` |
| `chmod a-w notes.txt` | Retire le droit d'écriture à tous (lecture seule) | `chmod a-w notes.txt` |
| `chmod u+w notes.txt` | Rend le droit d'écriture au propriétaire | `chmod u+w notes.txt` |
| `chmod +x script.sh` | Ajoute le droit d'exécution : le fichier peut être lancé | `chmod +x scripts/verifier.sh` |
| `chmod 644 notes.txt` | Droits classiques d'un fichier ordinaire (`rw-r--r--`) | `chmod 644 notes.txt` |
| `chmod 755 script.sh` | Droits d'un script exécutable par tous (`rwxr-xr-x`) | `chmod 755 script.sh` |
| `chmod 600 secret.txt` | Fichier secret : seul le propriétaire peut le lire (`rw-------`) | `chmod 600 secret.txt` |

## Variables d'environnement

| Commande | Ce qu'elle fait | Exemple |
| -------- | --------------- | ------- |
| `echo $USER` | Affiche mon nom d'utilisateur | `echo $USER` |
| `echo $HOME` | Affiche le chemin de mon dossier personnel | `echo $HOME` |
| `echo $PATH` | Affiche la liste des dossiers où le terminal cherche les programmes | `echo $PATH` |

## Paquets (apt)

| Commande | Ce qu'elle fait | Exemple |
| -------- | --------------- | ------- |
| `sudo apt update` | Met à jour la liste des paquets disponibles | `sudo apt update` |
| `sudo apt upgrade` | Met à jour les logiciels déjà installés | `sudo apt upgrade` |
| `apt search htop` | Cherche un paquet dans le catalogue | `apt search htop` |
| `apt show htop` | Affiche la description d'un paquet | `apt show htop` |
| `sudo apt install -y tree` | Installe un paquet (`-y` valide automatiquement) | `sudo apt install -y tree htop nano` |
| `sudo apt remove htop` | Désinstalle un paquet | `sudo apt remove htop` |
| `apt list --installed` | Liste les paquets installés sur la machine | `apt list --installed` |

## Scripts et versions

| Commande / Élément | Ce qu'elle fait | Exemple |
| ------------------ | --------------- | ------- |
| `#!/bin/bash` | Première ligne obligatoire d'un script pour indiquer d'utiliser bash | `#!/bin/bash` |
| `./script.sh` | Lance un script situé dans le dossier où je suis (`./`) | `./scripts/verifier.sh` |
| `which ls` | Affiche le dossier où est installé le programme | `which node` |
| `git --version` | Affiche le numéro de version d'un outil | `node --version` |
| `ls --help` | Affiche l'aide de la commande | `cp --help` |
| `clear` | Efface l'écran du terminal | `clear` |
