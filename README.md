# Préambule

Ce tutoriel a pour objectif d'expliquer l'architecture de base d'un projet Ruby Ob Rails et de comprendre comment utiliser des plug-ins déjà existants, dans le cadre du cycle 1 des ateliers Women On Rails.

# Étape 1 : Rappels

Vous pouvez retrouver les commandes utiles pour le terminal, git et la console Ruby On Rails [ici](https://women-on-rails.github.io/guide/main_commands).

# Étape 2 : Notions utiles

Ouvrez votre projet avec Cloud9, ou l'éditeur que vous utilisez si vous avez une installation native.

Si vous utilisez SublimeText, vous pouvez faire ````subl .```` dans la console pour ouvrir directement votre projet.
(````subl```` c'est SublimeText, l'espace c'est parce que la commande est finie, et le point c'est pour dire "ouvre dans Sublime Text tout le dossier dans lequel je suis, en un coup").

### Découvrir l'univers de Ruby en voyageant sur de bonnes Rails

Regardez l'architecture du projet.
Vous devriez voir plusieurs fichiers et dossiers, dont les principaux :
- ````app```` : Contient principalement les contrôleur, les vues, les modèles et les assets de l'application
- ````config```` : Contient les fichiers de configuration relatifs à l'application
- ````db```` : Contient tout ce qui permet de construire la base de donnée
- ````Gemfile```` : Contient la liste des plug-ins déjà existants qui vont être utilisés dans l'application

Si vous ouvrez le dossier ````app````, vous découvrirez les dossiers suivants:
- contrôleur (````controllers````) : Ils réagissent aux actions des utilisateurs et vont chercher les données dans la base (grâce aux modèles) pour les mettre à disposition des vues.
- modèles (````models````) : Ce sont des objets assurant la gestion des données.
- vues (````views````) : Elles correspondent à la manière d'afficher les informations à l'utilisateur. Il s'agit généralement d'une combinaison de code HTML et de Ruby dans des fichiers .html.erb.
- ````assets```` : Ce sont les images, les morceaux de code javascript et les feuilles de style en CSS utilisés dans les vues.

Apres avoir navigué dans les différents dossiers, passons à la pratique !

# Étape 3 : 1ère approche de l'application Rails

But: Ajouter à notre application une page d'accueil.

## Créons notre page vide

Tout d'abord, tapez la commande ``` rails generate controller home index ```.

Cela veut dire que l'on demande à Ruby On Rails de nous créer un controlleur appelé ``` home ``` qui contiendra une méthode ``` index ``` et sa vue associée (``` /home/index.html ```). Nous verrons ces notions plus en détails dans les prochains ateliers du cycle.

![Générer home](/images/readme/generator.png)

Puis, allez dans le fichier ```/config/routes.rb``` et ajoutez la ligne suivante ``` root 'home#index' ``` avant la ligne ``` get 'home/index' ```.

![Routes](/images/readme/routes.png)

Cela permet de faire en sorte que la page de notre application sur laquelle les utilisateurs arrivent soit la page ``` index.html ``` liée au controlleur ``` home ```.

Après avoir ajouté ces fichiers à votre application, lancez un serveur Rails avec le bouton ``` Run Project ``` dans votre workspace Cloud9 pour pouvoir visualiser vos changements (ou avec la commande ``` rails server ``` dans votre terminal si vous avez une installation native). L'url à utiliser dans le navigateur sera indiquée dans le terminal.

A ce stade, vous devriez avoir une page qui s'affiche mais qui n'est pas très élaborée.

![Page de base](/images/readme/page_navigateur_base.png)

Maintenant, on va y ajouter du contenu et la 'pimper' un peu avec Bootstrap !

## Contenu et style

Ouvrez le fichier ```index.html``` situé dans le dossier ```/app/views/home``` et rajoutez-y le HTML que vous souhaitez.

![Mise à jour HTML](/images/readme/index.png)

Allez regarder sur le navigateur ce que votre page affiche.

![Nouveau contenu](/images/readme/page_navigateur_contenu.png)

Apres avoir ajouté du contenu, passons au style.

[Boostrap](http://getbootstrap.com/) est un ensemble d'outils HTML, CSS et Javascript qui, utilisés, apportent des fonctionalités et une cohérence visuelle "responsive" (adaptée à tout format) à une application.

Nous allons inclure ce framework (bibliothèque de fonctionalités) dans notre application, à l'aide d'un [plug-in Ruby On Rails](https://github.com/seyhunak/twitter-bootstrap-rails),  pour la rendre un peu plus sympa à regarder.

> Astuce : On appelle les plug-ins Ruby On Rails des gems.

Pour cela, ouvrez le fichier ``` gemfile ``` et ajoutez-y la ligne suivante : ``` gem "twitter-bootstrap-rails" ```.

![gemfile](/images/readme/gemfile.png)

> Astuce : N'oubliez pas de sauvegarder régulièrement les fichiers que vous mettez à jour.
> Vous pouvez sauvegarder le fichier courant avec la commande ``` CTRL + S ``` (ou ``` CMD + S ``` si vous etes sous MAC).

Ajouter cette gem au gemfile permet d'informer l'application qu'elle devra utiliser cette gem dorenavant. Pour installer la gem, vous devez ensuitelancer la commande ``` bundle install ``` dans votre terminal.

![Bundle install](/images/readme/bundle_install.png)

La gem installée, nous pouvons l'utiliser.
