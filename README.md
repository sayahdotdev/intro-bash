# Tutoriel d'initiation à Bash

Ce tutoriel présente les bases du shell Bash (Bourne Again Shell) pour les débutants. Bash est un interpréteur de commandes utilisé dans les systèmes Unix/Linux. Ce guide couvre les commandes essentielles, la navigation dans le système de fichiers, et la gestion des fichiers.

## Prérequis
- Un système Unix/Linux ou un terminal compatible (ex. : WSL sur Windows, macOS Terminal).
- Aucun prérequis en programmation.

## 1. Introduction à Bash
Bash est une interface en ligne de commande qui permet d'interagir avec le système d'exploitation. Vous tapez des commandes dans un terminal, et Bash les exécute.

Pour ouvrir un terminal :
- Sur Linux/macOS : ouvrez l'application "Terminal".
- Sur Windows : installez WSL (Windows Subsystem for Linux) et ouvrez un terminal Ubuntu.

## 2. Commandes de base

### 2.1. Afficher le répertoire courant
La commande `pwd` (print working directory) affiche le chemin absolu du répertoire actuel.

```bash
pwd
```
Exemple de sortie :
```
/home/user
```

### 2.2. Lister les fichiers et dossiers
La commande `ls` affiche le contenu du répertoire courant.

```bash
ls
```
Pour plus de détails (permissions, taille, date) :
```bash
ls -l
```
Pour inclure les fichiers cachés :
```bash
ls -a
```

### 2.3. Naviguer dans les répertoires
Utilisez `cd` (change directory) pour changer de répertoire.

- Aller dans un répertoire spécifique :
```bash
cd /chemin/vers/repertoire
```
- Revenir au répertoire parent :
```bash
cd ..
```
- Aller au répertoire personnel :
```bash
cd ~
```
- Revenir au répertoire précédent :
```bash
cd -
```

### 2.4. Afficher le contenu d'un fichier
La commande `cat` affiche le contenu d'un fichier.

```bash
cat fichier.txt
```
Pour lire un fichier long, utilisez `less` (quittez avec `q`) :
```bash
less fichier.txt
```

## 3. Gestion des fichiers et répertoires

### 3.1. Créer un fichier
Utilisez `touch` pour créer un fichier vide :
```bash
touch monfichier.txt
```

### 3.2. Créer un répertoire
La commande `mkdir` crée un répertoire :
```bash
mkdir monrepertoire
```

### 3.3. Copier des fichiers ou répertoires
Pour copier un fichier :
```bash
cp source.txt destination.txt
```
Pour copier un répertoire (avec son contenu) :
```bash
cp -r repertoire_source repertoire_destination
```

### 3.4. Déplacer ou renommer
La commande `mv` déplace ou renomme un fichier/répertoire :
```bash
mv ancien_nom.txt nouveau_nom.txt
mv fichier.txt /chemin/vers/destination/
```

### 3.5. Supprimer des fichiers ou répertoires
Pour supprimer un fichier :
```bash
rm fichier.txt
```
Pour supprimer un répertoire et son contenu :
```bash
rm -r repertoire
```
**Attention** : Les suppressions avec `rm` sont irréversibles.

## 4. Redirections et pipes

### 4.1. Rediriger la sortie
Redirigez la sortie d'une commande dans un fichier avec `>` :
```bash
ls > liste.txt
```
Pour ajouter à un fichier existant, utilisez `>>` :
```bash
echo "Nouvelle ligne" >> liste.txt
```

### 4.2. Utiliser les pipes
Les pipes (`|`) envoient la sortie d'une commande comme entrée à une autre :
```bash
ls -l | grep ".txt"
```
Cette commande liste les fichiers et filtre ceux avec l'extension `.txt`.

## 5. Gestion des permissions

### 5.1. Vérifier les permissions
Les permissions (lecture `r`, écriture `w`, exécution `x`) sont affichées avec `ls -l`. Exemple :
```
-rw-r--r--  1 user user  123  oct 10 12:00 fichier.txt
```
- `rw` : le propriétaire peut lire et écrire.
- `r--` : le groupe peut lire.
- `r--` : les autres peuvent lire.

### 5.2. Modifier les permissions
Utilisez `chmod` pour changer les permissions :
```bash
chmod u+x fichier.sh
```
Ajoute le droit d'exécution (`x`) pour le propriétaire (`u`).

### 5.3. Changer le propriétaire
Utilisez `chown` pour changer le propriétaire d'un fichier :
```bash
sudo chown nouveau_proprietaire fichier.txt
```

## 6. Scripts Bash simples

Un script Bash est un fichier contenant des commandes Bash. Exemple :

1. Créez un fichier `script.sh` :
```bash
touch script.sh
```

2. Éditez-le avec un éditeur comme `nano` :
```bash
nano script.sh
```

3. Ajoutez ce contenu :
```bash
#!/bin/bash
echo "Bonjour, monde !"
ls -l
```

4. Rendez le script exécutable :
```bash
chmod +x script.sh
```

5. Exécutez-le :
```bash
./script.sh
```

## 7. Commandes utiles supplémentaires

- Afficher les processus en cours :
```bash
ps aux
```
- Terminer un processus :
```bash
kill <pid>
```
- Rechercher un fichier :
```bash
find /chemin -name "fichier.txt"
```
- Rechercher du texte dans des fichiers :
```bash
grep "mot" fichier.txt
```

## 8. Conseils pratiques

- Utilisez la touche `Tab` pour l'auto-complétion des commandes et chemins.
- Consultez l'aide d'une commande avec `man` :
```bash
man ls
```
- Utilisez `Ctrl+C` pour arrêter une commande en cours.
- Historique des commandes : tapez `history` ou utilisez les flèches haut/bas.

## 9. Pour aller plus loin

- Apprenez à utiliser des variables :
```bash
MA_VARIABLE="valeur"
echo $MA_VARIABLE
```
- Explorez les structures conditionnelles (`if`, `else`) et boucles (`for`, `while`) pour des scripts plus complexes.
- Consultez des ressources comme la documentation officielle de Bash ou des tutoriels en ligne.

Ce tutoriel couvre les bases pour débuter avec Bash. Pratiquez régulièrement pour maîtriser ces commandes et explorez des fonctionnalités avancées au fur et à mesure.
