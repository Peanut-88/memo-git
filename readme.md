# Mémo Git - Ligne de commande


Git est un outil de gestion de version décentralisée.
Il permet tracer les modifications et d'organiser un projet.
Il est par exemple possible grâce à git de connaître la raison de chaque modification, et si un bug est détecté après un developpement de revenir à une version antérieur.
Cet outil facilite également le travail collaboratif, et permet de savoir quand a été réalisé une modification et par qui.

GitHub est un service permettant d'héberger du code dans ce qu'on appel un dépot ou Repository (autres services similaires : GitBucket, GitLab...).
Avec ce dépot centralisé, chaque développeur peut accéder au code du projet.
Avec GitHub comme tout le code est sur un serveur, il n'y a aucun risque de le perdre par accident.


## Les différents espaces
* Working directory (L'espace de travail) : espace dans lequel modifie mon code
* Staging Area (L'index) : espace dans lequel je place les fichiers que j'ai validé et que je suis pret à partager
* Repository (L'historique) : espace dans lequel se trouve les fichiers que j'ai décidé de partager (après un commit)


### Installation et configuration 
https://git-scm.com/

### Installation de Git
https://git-scm.com/

### Vérifier que Git est bien installer / Vérifier la version de git
`$ git --version`

### Configuration de l'utilisateur (l'option --global permet de le faire qu'une seule fois)
`$ git config --global user.name "<Prénom et Nom>"`
`$ git config --global user.email "<Email>"`

### Afficher info sur la configuration 
`git config --list`



## Initialisation du projet

### Création d'un nouveau projet / dépot
`$ git init` Cette commande va créer un dossier caché nommé '.git'

### Afficher le repository GitHub vers lequel le Repository Local pointe
`$ git remote -v `

### Cloner un Repository (Récupération un Repository depuis GitHub)
`git clone <URL du dépot / repository>`

### Modifier la connection vers le repository GitHub (à utiliser si repository a été cloné)
`$ git remote set-url origin <url> `

### Ajouter la connection du repository GitHub (dans le cas où $ git remote -v  ne retourne rien), pour connecter le repository local à celui de GitHub
`git remote add origin <github-repository-url>`



## Gestion des fichiers en Local
### Visualiser état des fichiers 
`$ git status`

### Ajouter un fichier à l'index (Staging area)
`$ git add -A`

### Ajouter tous les fichiers à l'index (Staging area)
`$ git add <chemin du fichier>`

### Retirer un fichier à l'index (Staging area)
`$ git reset <chemin du fichier>`

### Ajouter un fichier au repository (Le commit se fait sur le repo en local)
`$ git commit -m "<Commentaire>"`

### Modifier le commentaire du dernier commit
`$ git commit --amend -m "<Commentaire modifié>"`

### Ajouter un fichier au dernier commit
`$ git add fichierAAjouter.html`
`$ git commit --amend --no-edit`

### Restaurer un fichier modifié ou supprimé (Récupération de la dernière version du repository local)
`$ git checkout --<nom du fichier>`


## Repository GitHub
### Envoyer les changement sur GitHub
`$ git push origin <nom de la branche> `(généralement branche = master = branche principale du projet / utilisé pour la production)

### Récuperer la version du dépot / repoitory Github
`$ git pull origin master`
 
 
## Les branches
### Lister les branches du repository
`$ git branch`

### Créer une nouvelle branche
`$ git branch <nom de la branche>` La branche principale (master) est créé au premier comit d'un fichier

### Supprimer une branche
`$ git branch -d <nom de la branche>` Lorsqu'une branche n'est plus utile penser à la supprimer

### Se placer sur une branche
`$ git checkout <nom de la branche>`

### Créer une branche et se placer dessus en une seule commande
`$ git checkout -b <nom de la nouvelle branche>`

### Merger une branche 'toto' à la branche principale
`$ git checkout master` (Se placer sur la branche principale)
`$ git merge toto` (pour merger)
`$ git push origin master` (ensuite je peux envoyer sur repo github)



## Rappels ligne commande
`$ pwd` print working directory, ou dossier courant

`$ cd <Chemin>` Changer de chemin

`$ mkdir <Nom dossier>` Créer un nouveau dossier
`$ touch <Nom fichier>`: Créer un fichier

## Divers
Fork Copie d'un projet open source sur github
Nom de la branche principal : master, c'est sur cette branche que l'on veut toutes le modifications
Créer une nouvelle branche lors du développement d'une nouvelle fonctionnalité. Lorsque ce développement est terminé et testé, cette branche pourra être fusionné avec la branche principal (master)
