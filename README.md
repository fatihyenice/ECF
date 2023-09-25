# ECF PARTIE 1

Ce repo contient une application de gestion de formation.
Il s'agit d'un ECF back-end pour la validation du titre professionnel.

## Prérequis

- Linux, MacOS ou Windows
- Bash
- PHP 8
- Composer
- symfony-CLI
- Mariadb 10 

## Installation

```
git clone https://github.com/fatihyenice/ECF
cd ECF
composer install
```

Créez une base de données et un utilisateur dédié pour cette base de données.

## Configuration

Créez un fochier `.env` à la racine du projet :

```
APP_ENV=dev
App_DEBUG=true
APP_SECRET=98aeb0581fe939d58566d1eff95851ee
DATABASE_URL="mysql://symfony:15051505@127.0.0.1:3306/symfony?serverVersion=mariadb-10.6.12&charset=utf8mb4"
```

Pensez à changer la variable `APP_SECRET` et les codes d'accès dans la variable `DATABASE_URL`.

**ATTENTION : `APP_SECRET` doit être une chaine de caractère de 32 caractères en hexadecimal.**

## Migration et fixtures

Créer le fichier dofilo au sein du dossier bin et le rendre exécutable avec la commande:
$ sudo chmod +x ./nom_du_fichier

Et ajouter ces 4 lignes dans le fichier dofilo.sh
``` 
php bin/console doctrine:database:drop --force --if-exists
php bin/console doctrine:database:create --no-interaction
php bin/console doctrine:migrations:migrate --no-interaction
php bin/console doctrine:fixtures:load --no-interaction --group=test 
```

Pour que l'application soit utilisable, vous devez créer le schéma de BDD et charger les données :

```
bin/dofilo.sh
```

## Utilisation

Lancez le serveur web de developpement

```
symfony serve
```

Puis ouvrez la page suivante : [https://localhost:8000](https://localhost:8000).

## Mentions légales

Ce projet est sous licence MIT.

La licence est disponible ici [MIT LICENCE](LICENCE).
