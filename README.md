# 🎼 Introduction Symfony

## 🎦 Présentation MVC

[Présentation](https://docs.google.com/presentation/d/1WvroALZRKneGGJm7kLIDIpFqcrIT_ljOoweNtc1Q-PU)

## 🎦 Live coding

Installation d'un projet Symfony. Explication de l'arborescence du framework.

### Lien symbolique à partir de public vers htdocs

```bash
ln -s public htdocs
```

### Installation du pack apache pour laragon

```bash
composer require symfony/apache-pack
```

Utilisation de la documentation pour créer un contrôleur et la view associée.

[Symfony Documentation](https://symfony.com/doc/current/index.html)

```bash
php bin/console make:controller
```

Utilisation du contrôleur pour faire un traitement PHP, démonstration du système de routing.

```php
<?php
namespace App\Controller;

use Symfony\Bundle\FrameworkBundle\Controller\AbstractController;
use Symfony\Component\HttpFoundation\Response;
use Symfony\Component\Routing\Annotation\Route;

class HomeController extends AbstractController
{
    #[Route('/', name: 'app_home')]
    public function index(): Response
    {
        $variable = 'Totoooooo';

        return $this->render('home/index.html.twig', [
            'controller_name' => 'HomeController',
            'variable' => $variable,
        ]);
    }
}
```

Syntaxe du langage twig et utilisation des variables injecté.

```twig
{% if variable is not null %}
    {{ variable }}
{% else %}
    Je n'existe pas !!!
{% endif %}
```

## 🛠 MINI-TP Maquette interactive

Pour bien prendre en main la manipulation du MVC dans Symfony, nous allons créer une "maquette" interactive.

### Installation du projet :

- Installer Symfony sur Devilbox grâce à la [documentation Symfony](https://symfony.com/doc/current/index.html)
- Faire un lien symbolique entre le dossier public et htdocs

### Création d'un controller à la main :

Pour toute création de nouvelles classes PHP, on utilisera généralement la console de Symfony qui embarque une boîte à outils complète pour nous aider à aller plus vite.

Avec cette commande vous pouvez créer des controller custom :
```bash
php bin/console make:controller
```

- Vous l'appellerez Home (il s'appellera HomeController dans le dossier des controller) et il vous sera utile pour le routage de la page d'accueil.
- Vérifiez que le chemin du template mène à `index.html.twig` du dossier `home`.

### 🎨 Intégration

1. Récupérer les pages HTML du projet ici : [payetonpote](https://gitlab.com/simplon-roanne/paiement-collaboratif)
2. Copier le dossier "assets" du projet récuperé pour le mettre dans le dossier Symfony `assets` (c'est la racine des assets de symfony).
3. Copier toute la page `index.html` et la coller dans le fichier `base.html.twig` tout en
conservant le code existant. On va en réutiliser une partie (les balises twig !)
4. Repérer l'endroit où termine le header et où commence le footer. Couper ce code et le
coller dans la partie "block body" du template `index.html.twig` dans le dossier `home`.
5. De retour dans `base.html.twig`, il nous reste à replacer les blocks "stylesheets", "title",
"body", et "javascripts". **ATTENTION !** pour les blocks stylesheets et javascripts, on les
place après les scripts déjà existants. C'est parce qu'ils seront utilisés sur toutes les
pages. De plus, rajoutez un "/" aux liens de script dans le footer et de style dans le header.
6. Attention à mettre `{% block stylesheets %}{% endblock %}` sous les lignes d'appel du style
CSS (et à ne pas les englober) dans le head et `{% block javascripts %}{% endblock %}` sous
les lignes d'appel du Javascript (et à ne pas les englober) dans le footer.

La racine du projet doit mener sur la page `index.html.twig` du dossier home que vous venez
d'intégrer.

## 🏆 Objectifs

- J'ai compris le chemin du code dans un environnement MVC.
- Je sais router les pages de mon projet dans un controller.
