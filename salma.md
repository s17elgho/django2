# Django le framework !

1. Introduction à Django
    1. Qu’est ce qu’un framework ?
    2. Types de frameworks
    3. Frameworks : Quels avantages et quels inconvénients ?
    4. Django, c'est quoi ?
    5. MVC/MVT
2. Créer son premier projet sur Django
    1. Créer un projet et une première application
    2. Conception des premiers modèles
    3. Le traitement des données avec les vues et le routage d'URL
    4. Présentation du contenu avec les templates
    5. Administration du projet avec le scaffolding

# I - Introduction à Django

## 1 - Qu'est ce qu'un framework ?  
Un framework est l'ensemble de composants logiciels à la base d'un logiciel ou d'une application( bibliothèques,classes, helpers..etc).Il décrit les types de programmes à concevoir et leur mode d'interaction.  
Un framework permet de **simplifier le travail des développeurs informatiques** en offrant une architecture réutilisable et adaptée à leurs besoins. En outre, il peut être amélioré par l'expérience des développeurs.Les frameworks sont utilisés pour développer une application mobile, un site web, un jeu,..etc 

## 2 - Types de frameworks  
On peut classer les frameworks de la manière suivante:  
* **Frameworks d'infrastructure système** utilisés pour le développement des systèmes d'exploitation et des interfaces graphiques (Microsoft .Net, Apache Struts,...).
* **Frameworks d'intégration intergicielle** permettent l'interconnexion de systèmes divers.
* **Frameworks d'entreprises** sont spécifiques aux applications utilisées par les entreprises. 
* **Frameworks de gestion de contenu** sont les fondations d'un système de gestion de contenu — pour la création, la collecte, le classement, le stockage et la publication de « biens numérisés ».

Source : [Wikipedia](https://fr.wikipedia.org/wiki/Framework)

## 3 - Frameworks : Quels avantages et quels inconvénients ?  
En utilisant les frameworks, les développeurs codent de façon homogène. Ainsi, quand un développeur rejoint un projet basé sur un framework qu'il connaît, la compréhension de l'architecture lui sera plus simple et plus rapide que s'il avait dû s'approprier les outils au préalable. De plus, l'adoption d'une structure commune garantit un code organisé et facilement réutilisable. 

En revanche, les frameworks doivent être souples et modulables afin qu'ils soient adaptés à différents projets. Certains nécessitent cependant un temps d'apprentissage plus long que d'autres. 

Source: [Openclassrooms](https://openclassrooms.com/fr/courses/1871271-developpez-votre-site-web-avec-le-framework-django/1871361-creez-vos-applications-web-avec-django)  

## 4 - Django, c'est quoi ?  

Django est l'un des  frameworks applicatifs Python destinés au développement d’applications web. Créé en 2003 dans une agence de presse, Lawrence Journal-World, le framework est proposé au grand public deux ans plus tard. En 2008, la fondation Django Software a été créée. Aujourd'hui, Django est très populaire. Il est utilisé dans des applications web très célèbres comme *Instagram* ou *Pinterest*.  

Django permet le développement rapide de meilleures et plus performantes applications web. Il automatise des tâches répétitives  telles que l'écriture de requêtes destinées à une base de données. Il propose d'autres fonctionnalités comme une bibliothèque de traduction on un espace membres. 

## 5-**MVC/MVT**:   

Le Modèle-vue-contrôleur ou MVC est un type d'architecture logicielle destiné aux interfaces graphiques lancé en 1978 et très populaire pour les applications web. Le motif est composé de trois types de modules assurant différents rôles:  
   * Un modèle (Model) contient les données à afficher.
   * Une vue (View) contient la présentation de l'interface graphique.  
   * Un contrôleur (Controller) contient la logique concernant les actions effectuées par l'utilisateur.source: [Wikipédia](https://fr.wikipedia.org/wiki/Mod%C3%A8le-vue-contr%C3%B4leur)  
   ![](https://upload.wikimedia.org/wikipedia/commons/b/b4/MVC_Diagram_%28Model-View-Controller%29.svg)  
   source:[MVC](https://fr.wikipedia.org/wiki/Mod%C3%A8le-vue-contr%C3%B4leur)  
   Django utilise l'architecture MVT (modèle-vue-template)qui s'inspire de MVC:   
   * Le **modèle** interagit avec une base de données.Un **ORM** (Object Relational Mapping) traduit les réponses à une requête [SQL](file:///C:/Users/admin/Documents/EGDownloads/Sql_1_Cours.pdf) ( langage de consultation de base de données) en **objets Python** exploitables par le programme.Tous les modèles sont réunis dans un fichier python **models.py**.  
   * La **vue** reçoit [une requête HTTP](https://openclassrooms.com/fr/courses/1118811-les-requetes-http) et renvoie une réponse HTTP convenable (par exemple si la requête est une interaction avec une base de données, la vue appelle un modèle pour récupérer les items demandés).Les vues se trouvent dans le fichier **views.py**
   * Le **template** est un fichier [HTML](https://openclassrooms.com/fr/courses/1603881-apprenez-a-creer-votre-site-web-avec-html5-et-css3/1604361-votre-premiere-page-web-en-html) récupéré par la vue et envoyé au visiteur.  
   La figure ci-dessous montre comment les différents composants de l'architecture MVC interagissent pour répondre à la requête d'un utilisateur.  
   ![](https://camo.githubusercontent.com/2fd581466b72e4b92e5893ea842b0ee085fff68d/68747470733a2f2f646f63732e676f6f676c652e636f6d2f64726177696e67732f642f314c456f30356854445f45435a355647356f664d6468327434445f4c6769416e626c752d65305435386645342f7075623f773d39363026683d373230)  
   source: [github](https://github.com/emencia/emencia-django-training/wiki/Mod%C3%A8le-MVT)  


# II - Créer son premier projet sur Django
## 1 - Créer un projet et une première application
Après avoir installé Django, nous pouvons créer un nouveau projet.
La première étape est de créer un répertoire qui contient des fichiers utiles au fonctionnement du projet. Pour créer ce répertoire, on tape la commande suivante:  
$ django-admin.py startproject mon_projet  
Ce répertoire *mon_projet* contient un script manage.py qui permettra d'exécuter des commandes utiles au sein du projet. Il contient aussi des fichiers propres au projet: settings.py contient la configuration globale du projet, urls.py est le contrôleur frontal du projet et wsgi.py est un fichier de configuration relatif au serveur qui executera le projet.
Nous pouvons vérifier que le projet fonctionne avec la commande:  
$ python manage.py runserver  
Cette commande lance le serveur de développement Django et affiche des informations dont l'URL du projet Django que nous venons de créer.

__Création d'une application au sein du projet__

Créer une application est très simple. Il faut tout d'abord se placer dans le répertoire du projet puis taper la commande suivante:  
$ django-admin.py startapp chistera
Un répertoire *chistera* a été créé dans le répertoire du projet et contient plusieurs fichiers: le fichier models.py qui est destiné à accueillir les modèles de l'application, le fichier views.py qui sert à accueillir les contrôleurs de l'application et le fichier tests.py qui va accueillir les tests.

## 2 - Conception des premiers modèles
## 3 - Le traitement des données avec les vues et le routage d'URL
## 4 - Présentation du contenu avec les templates
## 5 - Administration du projet avec le scaffolding

Une des grandes forces de Django est de proposer la création très rapide d'une interface permettant d'administrer son site. Pour cela on va utiliser les fonctionnalités de _scaffolding_ (littéralement _échaffaudage_ ou _structure_) de Django.

La première étape est d'ajouter l'application d'administration dans la liste des applications utilisées dans notre projet. Pour ce faire il faut modifier la variable `INSTALLED_APPS` dans le ficher `settings.py` du projet :

```python
INSTALLED_APPS = (
    ...,
    'django.contrib.admin',
    ...,
)
```

Maintenant que l'application est active, il faut permettre son accès. Pour ce faire il faut rajouter une route pointant vers l'interface d'administration. Modifiez le fichier `urls.py` du projet (et non de l'application) pour rajouter ces lignes :

```python
from django.contrib import admin

admin.autodiscover()

urlpatterns = [
    ...,
    path('admin/', admin.site.urls),
    ...,
]
```

Ne vous attardez pas trop sur la ligne `admin.autodiscover()`, il nous permet simplement _"d'ajouter"_ tous nos modèles dans l'interface d'administration.

Afin de pouvoir utiliser notre interface, il nous faut créer un utilisateur qui a les droits d'accès à l'interface. Dans une console, se placer dans le dossier de notre projet, là où se trouve le fichier `manage.py` et taper : `python manage.py createsuperuser` (ou `python3 manage.py createsuperuser` si vous utilisez Python 3) puis suivez les étapes affichées. Une fois cette étape effectuée, vous pouvez lancer le serveur pour tester votre interface.
