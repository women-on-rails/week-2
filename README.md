# Préambule

Slides du cours disponibles [ici](http://slides.com/women_on_rails/week-2)

Ce tutoriel a pour objectif d'expliquer l'architecture de base d'un projet Ruby On Rails et de comprendre comment utiliser des plug-ins déjà existants, dans le cadre du cycle 1 des ateliers Women On Rails.

# Étape 1 : Rappels

Vous pouvez retrouver les commandes utiles pour le terminal, git et la console Ruby On Rails [ici](https://women-on-rails.github.io/guide/main_commands).

# Étape 2 : Notions utiles

Ouvrez votre projet avec Cloud9, ou l'éditeur que vous utilisez si vous avez une installation native.

Pour les installations natives:

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

Tout d'abord, tapez la commande ``` rails generate controller home index ``` dans votre terminal.

Cela veut dire que l'on demande à Ruby On Rails de nous créer un controlleur appelé ``` home ``` qui contiendra une méthode ``` index ``` et sa vue associée (``` /home/index.html ```). Nous verrons ces notions plus en détails dans les prochains ateliers du cycle.

![Générer home](/images/readme/generator.png)

Puis, allez dans le fichier ```/config/routes.rb``` et ajoutez la ligne suivante ``` root 'home#index' ``` avant la ligne ``` get 'home/index' ```

![Routes](/images/readme/routes.png)

Cela permet de faire en sorte que la page de notre application sur laquelle les utilisateurs arrivent soit la page ``` index.html ``` liée au controlleur ``` home ```.

Après avoir ajouté ces fichiers à votre application, lancez un serveur Rails avec le bouton ``` Run Project ``` dans votre workspace Cloud9 pour pouvoir visualiser vos changements (ou avec la commande ``` rails server ``` dans votre terminal si vous avez une installation native). L'url à utiliser dans le navigateur sera indiquée dans le terminal.

A ce stade, vous devriez avoir une page qui s'affiche mais qui n'est pas très élaborée.

![Page de base](/images/readme/page_navigateur_base.png)

Maintenant, on va y ajouter du contenu et la 'pimper' un peu avec Bootstrap !

### Visualiser l'application sur le navigateur

Apres avoir lancé votre serveur, vous pourrez ouvrir votre navigateur pour y coller l'URL fournie par votre terminal. (généralement http://localhost:3000/ si vous avez une installation native)
Vous devriez visualiser le contenu de la vue que vous avez ouverte précédement.
Apres avoir fait des modifications sur cette vue et les avoir enregistrées, vous n'aurez qu'à recharger la page du navigateur pour voir vos modifications apparaître.

Enregistrer avec l'éditeur de texte : ``` CTRL + S ``` sous windows, ``` CMD + S ``` sous mac
Rafraichir la page web : F5 ou ````CTRL + R```` sous windows, ````CMD + R```` sous mac

## Contenu et style

Ouvrez le fichier ```index.html``` situé dans le dossier ```/app/views/home``` et rajoutez-y le HTML que vous souhaitez.

![Mise à jour HTML](/images/readme/index.png)

Allez regarder sur le navigateur ce que votre page affiche.

![Nouveau contenu](/images/readme/page_navigateur_contenu.png)

Apres avoir ajouté du contenu, passons au style.

[Bootstrap](http://getbootstrap.com/) est un ensemble d'outils HTML, CSS et Javascript qui, utilisés, apportent des fonctionalités et une cohérence visuelle "responsive" (adaptée à tout format) à une application.

Nous allons inclure ce framework (bibliothèque de fonctionalités) dans notre application, à l'aide d'un [plug-in Ruby On Rails](https://github.com/seyhunak/twitter-bootstrap-rails),  pour la rendre un peu plus sympa à regarder.

> Astuce : On appelle les plug-ins Ruby On Rails des gems. On peut en trouver toute une liste [ici](http://guides.rubygems.org/rubygems-basics/)

Pour cela, ouvrez le fichier ``` gemfile ``` et ajoutez-y la ligne suivante : ``` gem "twitter-bootstrap-rails" ```

![gemfile](/images/readme/gemfile.png)

> Rappel : N'oubliez pas de sauvegarder régulièrement les fichiers que vous mettez à jour sinon vous ne verrez pas vos changements sur le navigateur.

Ajouter cette gem au gemfile permet d'informer l'application qu'elle devra utiliser cette gem dorenavant. Pour installer la gem, vous devez ensuite lancer la commande ``` bundle install ``` dans votre terminal.

![Bundle install](/images/readme/bundle_install.png)

Puis, tapez la commande ``` rails generate bootstrap:install static ``` dans votre terminal pour créer les assets (images, css et autres) utiles au bon fonctionnement de la gem.
La gem installée, nous pouvons maintenant l'utiliser.

Ouvrez le fichier ``` /app/views/layouts/application.html.erb ```.

![Layout sans bootstrap](/images/readme/application_sans_bootstrap.png)

Ce fichier est le "layout" de notre application. C'est à dire qu'il s'occupe de la mise en page générale utilisée par toutes les pages de l'application.

> Important : Dans le fichier ``` /app/views/layouts/application.html.erb ```, le contenu des pages de l'application est inclus grace à la ligne ``` <%= yield %> ```.

Dans votre terminal, tapez la commande suivante : ``` rails g bootstrap:layout application ```

Le navigateur vous demandera confirmation, tapez ``` Y ``` (pour ``` yes ```).

![Generateur Bootstrap](/images/readme/commande_layout.png)

Cette action permet d'appliquer le formattage de Bootstrap sur le fichier ``` /app/views/layouts/application.html.erb ```.

![Layout avec bootstrap](/images/readme/application_avec_bootstrap.png)

Relancez votre serveur et rafraichissez votre application sur votre navigateur. Tadaaa ! Votre page d'accueil est un peu plus sympa et le formattage autour des données sera maintenant le meme pour toute nouvelle page de votre application.

> Si Bootstrap ne fonctionne pas, vérifiez que vous avez bien lancé la commande ``` rails generate bootstrap:install static ``` dans votre terminal.
> Si c'est le cas, vous aurez besoin d'ajouter les lignes suivantes au fichier ``` /app/views/layouts/application.html.erb ``` pour faire fonctionner Bootstrap :
> ```
> <link rel='stylesheet' href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/css/bootstrap.min.css">
> <script src='https://maxcdn.bootstrapcdn.com/bootstrap/3.3.4/js/bootstrap.min.js'></script>
> ```

![Layout avec bootstrap et URLs](/images/readme/application_avec_bootstrap_et_urls.png)

![Page web avec Bootstrap](/images/readme/page_web_avec_bootstrap.png)

# Étape 4 : Pour aller plus loin

Votre application a maintenant une super mise en page de base.
N'hésitez pas à modifier le fichier ``` /app/views/layouts/application.html.erb ``` à votre gout et à utiliser de nouveaux composants [Bootstrap](http://getbootstrap.com/) en vous aidant de la documentation officielle.

# Étape 5 : Enregistrer les modifications sur le répertoire distant

[Enregistrer vos modifications et les envoyer sur votre répertoire Github](https://women-on-rails.github.io/guide/push_project)

# Liens Utiles
- Les layouts : https://openclassrooms.com/courses/initiez-vous-a-ruby-on-rails/utilisez-le-layout
- Ce qu'est un partial : http://blogs.wefrag.com/Sky/2011/06/27/ruby-on-rails-les-partials/
- Le protocole HTTP : https://openclassrooms.com/courses/les-requetes-http
- Les actions CRUD : https://fr.wikipedia.org/wiki/CRUD
- Avoir une définition succincte de Ruby On Rails : https://fr.wikipedia.org/wiki/Ruby_on_Rails
- La documentation officielle de Ruby On Rails : http://guides.rubyonrails.org/
- Notions intéressantes Ruby On Rails : http://geekmeup.fr/les-10-avantages-de-ruby-on-rails-pour-apprendre-a-bien-coder/
- "Rails is like Burger King", par Simon Courtois : http://fr.slideshare.net/happynoff/rails-king
- la doc de Bootstrap : http://getbootstrap.com/

# Et ensuite ?
Venez vous essayer à la console Ruby et comprendre l'utilisation du langage Ruby dans le projet ```Curiosities``` avec le tutoriel [Week-3](https://github.com/women-on-rails/week-3)
