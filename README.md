# Etape 1: Récuperer le projet week-2

Ouvrez une console et entrez dans votre répertoire de travail (aidez vous des commandes ````cd```` (changement de dossier) et ````ls```` (listing des fichiers)).
Créez un nouveau dossier de travail (````mkdir````: make directory):
``` Console
mkdir week-2
````

Entrez dans ce dossier:
``` Console
cd week-2
````

Initialisez GIT pour votre projet:
``` Console
git init
````
Vous allez maintenant lier votre répertoire ````week-2```` situé sur votre ordinateur avec un répertoire distant week-2 situé sur votre compte github. Le lien sera appelé ````origin````.
Pour cela, créez un nouveau répertoire appelé ````week-2```` sur Github et copiez l'url de ce répertoire.
Puis, faites la commande suivante, en remplaçant l'url par la votre:
``` Console
git remote add origin git@github.com:(votre compte)/week-2.git
````
Cela vous permet de synchroniser votre compte github avec les modifications que vous ferez sur le projet week-2 sur votre ordinateur.

A cette étape, si vous faites ````ls```` dans votre console, le dossier ````week-2```` doit etre vide.

Maintenant, vous allez lier votre répertoire ````week-2```` situé sur votre ordinateur avec le répertoire distant ````week-2```` situé sur le compte des Women On Rails. Le lien sera appelé ````upstream````. 
Pour cela, fites la commande suivante:
``` Console
git remote add upstream git@github.com:women-on-rails/wow-curiosites-1.git
````
Cela va vous permettre de récupérer facilement le code existant nécessaire pour la suite de l'exercice. 

Pour récupérer ce code, faites la commande suivante:
``` Console
git pull upstream week-2
````

Cela remplit le dossier ````week-2```` sur votre ordinateur avec tout ce que contient le projet ````week-2```` sur le compte Github des Women On Rails. 
En faisant un ````ls````, vous pourrez voir la liste des fichiers copiés. 

Vous voila prete pour l'exercice ! 

# Etape 2: Lire l'exercice et se lancer

## Challenges du jour :

#### HTML : 
Ajoutez votre propre curiosité ! Personnalisez la page pour qu'elle vous ressemble. 
#### CSS : 
Changez le style pour qu'il vous ressemble. Vous l'aimez tel quel ? Amusez-vous à tout changer pour bien comprendre ce que fait chaque ligne puis revenez à la normale. 

## Challenge supplémentaire pour la semaine : 
Changez toutes les curiosités et ajoutez un footer avec un lien vers la page de votre choix. 

Utilisez des images qui sont sur internet:
``` HTML
<img src="https://pbs.twimg.com/profile_images/616542814319415296/McCTpH_E.jpg">
````
Ou ajoutez des images dans le dossier images pour les utiliser avec la balise <img>:
``` HTML
<img src="images/votre_image.png">.
````
## Avancé : 
- Ajoutez les liens vers vos réseaux sociaux avec une icône. La page de destination doit ouvrir un nouvel onglet. Concernant le design vous pouvez vous inspirer de [celui de Webibli](http://webibli.fr/users/1128), créé par Lisa.
- Découvrez la [grille de Bootstrap](http://getbootstrap.com/css/#grid) et créez une seconde section pour afficher les photos de vacances de votre personnage. 
- HTML : Intéressez-vous à [Schema.org et au web sémantique](https://openclassrooms.com/courses/decouper-une-maquette/ajouter-les-metatags).


# Etape 3: Enregistrer les modifications sur le répertoire distant

Lorsque vous avez fait des modifications dans votre projet ````week-2````, vous pouvez avoir besoin de les enregistrer pour ne pas les effacer malencontreusement. Pour cela, vous allez les 'committer'. 

Pour committer ces changements, vous devez d'abord les ajouter aux modifications à prendre en compte avec la commande:
``` Console
git add .
````

Si vous souhaitez ne prendre en compte que certaines modifications et pas d'autres, vous pouvez utiliser la commande:
``` Console
git add -p 
````
Cela vous permettra de visualier chaque modification et de l'ajouter (````y````) ou non (````n````). 

Pour rendre l'enregistrement des modifications effectif, il faut faire la commande:
``` Console
git commit 
````

Si vous voulez décrire le contenu de votre commit, vous pouvez y ajouter une option:
``` Console
git commit -m "description blabla"
````
Cela permet de savoir rapidement à quoi correspond le commit, au lieu de regarder sa composition. 

Pour envoyer votre commit vers votre dossier remote (sur github), vous devez ensuite utiliser la commande ````push````:
```Console
git push 
````

Allez voir sur github, vos modifications apparaitront :)

# Pour aller plus loin : 
- Commencer avec GIT : http://christopheducamp.com/2013/12/15/github-pour-nuls-partie-1/
- Aller plus loin avec les répertoires distants : https://git-scm.com/book/fr/v1/Les-bases-de-Git-Travailler-avec-des-d%C3%A9p%C3%B4ts-distants
- Premiers pas en CSS : http://css.mammouthland.net/premiers-pas-en-css.php
- Principales balises en HTML : https://openclassrooms.com/courses/apprenez-a-creer-votre-site-web-avec-html5-et-css3/memento-des-balises-html ou http://www.vieytes.org/tbalises.html
- Guide complet sur le HTML : http://www.lehtml.com/html/index.htm
