# Étape 1 : Récuperer le projet week-2

[Récuperer un projet Women On Rails](https://women-on-rails.github.io/guide/get_project)

# Étape 2 : Lire l'exercice et se lancer

## Challenges du jour :

#### HTML : 
Ajoutez votre propre curiosité ! Personnalisez la page pour qu'elle vous ressemble. 
#### CSS : 
Changez le style pour qu'il vous ressemble. Vous l'aimez tel quel ? Amusez-vous à tout changer pour bien comprendre ce que fait chaque ligne puis revenez à la normale. 

## Challenge supplémentaire pour la semaine : 
Changez toutes les curiosités et ajoutez un footer avec un lien vers la page de votre choix. 

Utilisez des images qui sont sur internet :
``` HTML
<img src="https://pbs.twimg.com/profile_images/616542814319415296/McCTpH_E.jpg">
````
Ou ajoutez des images dans le dossier images pour les utiliser avec la balise <img>:
``` HTML
<img src="/images/votre_image.png">.
````
## Avancé : 
- Ajoutez les liens vers vos réseaux sociaux avec une icône. La page de destination doit ouvrir un nouvel onglet. Concernant le design vous pouvez vous inspirer de [celui de Webibli](http://webibli.fr/users/1128), créé par Lisa.
- Découvrez la [grille de Bootstrap](http://getbootstrap.com/css/#grid) et créez une seconde section pour afficher les photos de vacances de votre personnage. 
- HTML : Intéressez-vous à [Schema.org et au web sémantique](https://openclassrooms.com/courses/decouper-une-maquette/ajouter-les-metatags).


# Étape 3 : Enregistrer les modifications sur le répertoire distant

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

PS: Si vous voulez simplement visualiser les fichiers modifiés, faites:
``` Console
git status
````

Pour rendre l'enregistrement des modifications effectif, il faut faire la commande:
``` Console
git commit 
````

Si vous voulez décrire le contenu de votre commit, vous pouvez y ajouter une option:
``` Console
git commit -m "description blabla"
````
Cela permet de savoir rapidement à quoi correspond le commit, au lieu de regarder sa composition. 

Pour envoyer votre commit vers votre repertoire distant (sur Github), vous devez ensuite utiliser la commande ````push````:
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
