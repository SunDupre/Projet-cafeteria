# Projet Cafeteria

Plate-forme de réservation des repas pour le restaurant de réalise.

## Développement

L’environnement de développement est basé sur docker grâce au fichier `docker-compose.yml` fourni
et peut être exécuté avec la commande

```bash
$ docker-compose up -d
```

Les services disponibles sont:

* Apache + PHP 7.3 sur les ports `80` et `443`.
* MariaDB sur le port `3306`.
* PhpMyAdmin sur le port `9000`.
* Mailhog sur le port `8025`.

Si c’est la première fois que vous utilisez les containers, il faut créer la base de données avec la commande

```bash
$ docker-compose exec mariadb mysql -u root -p -e "$(cat create_database.sql)"
```

et saisir le mot de passe pour l’utilisateur `root` de MariaDB défini dans le fichier `docker-compose.yml`.

Un set de données de test peut être généré grâce au script `fixture.php` au moyen de la commande

```bash
$ docker-compose exec webserver php fixture.php
```

### Tests

Dans le dossier `e2e` se trouvent tous les fichiers nécesaient pour l'exécution
des tests end-to-end. Ils se basent sur le framework [cypress](https://www.cypress.io/)

Une fois dans le dossier `e2e`, les dépendances nécessaires à leur bon fonctionnement peuvent être installées
avec la commande

```bash
$ npm install
```

Pour exécuter les tests, toujours dans le dossier `e2e`, il suffit d’exécuter la commande

```bash
$ ./node_modules/.bin/cypress open
```

## Détails d’implémentation
  
  Liste catégorie des plats

  1 = Entrée

  2 = Salade

  3 = Soupe

  4 = Sandwich

  5 = Panini

  6 = Pâtes

  7 = Plat du jour

  8 = Plat végétarien

  9 = Dessert
