# Prise en main

Pour bien prendre en main la manipulation du MVC dans Symfony, nous allons créer une "maquette" interactive.

## Installation du projet :

- Installer Symfony grâce à [la documentation Symfony](https://symfony.com/doc/current/setup.html).
- Faire un lien symbolique entre le dossier public et htdocs (pour ceux sur Linux et Devilbox).

## Création d'un controller à la main :

Pour toute création de nouvelles classes PHP, on utilisera généralement la console de Symfony qui embarque une boîte à outils complète pour nous aider à aller plus vite. Avec cette commande, vous pouvez créer des controllers personnalisés :

```bash
php bin/console make:controller
```

- Vous l'appellerez Home (il s'appellera HomeController dans le dossier des controller) et
il vous sera utile pour le routage de la page d'accueil.
- Vérifiez que le chemin du template mène à index.html.twig du dossier home.
