﻿# Présentation Symfony

 lien

# Passage à la pratique

Pour bien prendre en main la manipulation du MVC dans Symfony, nous allons créer une "maquette" interactive.

## Installation du projet :

- Installer Symfony grâce à [la documentation Symfony](https://symfony.com/doc/current/setup.html).
- Faire un lien symbolique entre le dossier public et htdocs (pour ceux sur Linux et Devilbox).

## Création d'un controller à la main :

Pour toute création de nouvelles classes PHP, on utilisera généralement la console de Symfony qui embarque une boîte à outils complète pour nous aider à aller plus vite. Avec cette commande, vous pouvez créer des controllers personnalisés :

```bash
php bin/console make:controller
```

- Vous l'appellerez Home (il s'appellera `HomeController` dans le dossier des controller) et
il vous sera utile pour le routage de la page d'accueil.
- Vérifiez que le chemin du template mène à `index.html.twig` du dossier `home`.

## Intégration :

- Récupérer les pages HTML du projet [ici](https://gitlab.com/simplon-roanne/paiement-collaboratif).
- Copier le dossier "assets" dans le dossier Symfony "public" (c'est la racine du serveur web).
- Copier toute la page "index.html" et la coller dans le fichier "base.html.twig" tout en conservant le code existant. On va en réutiliser une partie (les balises twig !).
- Réagencer le code pour garder les parties communes : le footer et la navbar.
- Repérer l'endroit où termine le header et où commence le footer. Couper ce code et le coller dans la partie "block body" du template "index.html.twig" dans le dossier home.
- De retour dans "base.html.twig", il nous reste à replacer les blocks "stylesheets", "title", "body", et "javascripts". ATTENTION ! pour les blocks stylesheets et javascripts, on les place après les scripts déjà existants. C'est parce qu'ils seront utilisés sur toutes les pages. De plus, ajoutez un "/" aux liens de script dans le footer et de style dans le header.
- Attention à mettre `{% block stylesheets %}{% endblock %}` sous les lignes d'appel du style CSS (et à ne pas les englober) dans le head et `{% block javascripts %}{% endblock %}` sous les lignes d'appel du Javascript (et à ne pas les englober) dans le footer.

La racine du projet doit mener sur la page `index.html.twig` du dossier home que vous venez d'intégrer.

## 🏆 Objectifs

- J'ai compris le chemin du code dans un environnement MVC.
- Je sais router les pages de mon projet dans un controller.

## 🧠 A retenir

- N'hésitez pas à parcourir la documentation de Symfony très complète, en français et de très bonne qualité : [Symfony Documentation](https://symfony.com/doc/current/index.html).
