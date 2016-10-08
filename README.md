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
>>>>>>> eb4512f... Update week-2 & add Rails architecture explanation

Si vous ouvrez le dossier ````app````, vous découvrirez les dossiers suivants:
- contrôleur (````controllers````) : Ils réagissent aux actions des utilisateurs et vont chercher les données dans la base (grâce aux modèles) pour les mettre à disposition des vues.
- modèles (````models````) : Ce sont des objets assurant la gestion des données.
- vues (````views````) : Elles correspondent à la manière d'afficher les informations à l'utilisateur. Il s'agit généralement d'une combinaison de code HTML et de Ruby dans des fichiers .html.erb.
- ````assets```` : Ce sont les images, les morceaux de code javascript et les feuilles de style en CSS utilisés dans les vues.

Apres avoir navigué dans les différents dossiers, passons à la pratique !