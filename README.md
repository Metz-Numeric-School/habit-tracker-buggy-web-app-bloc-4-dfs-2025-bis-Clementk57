# My Habits Tracker (A Buggy Web Application)

# Présentation du projet

MyHabitTracker est une application web conçu sur une architecture MVC et qui s'inspire de l'arborsence et du fonctionnement du framework Symfony.

Celle-ci est destiné à être utilisée à des fins pédgogique uniquement et dans le cadre de la sensibilisation aux failles de sécurités les plus courantes sur le web.

## Téchnologies

- PHP 8.3
- MySQL 5.7

## Objectifs

Les objectifs sont les suivants :

* Prendre connaissance du code existant
* Paramétrer votre environnement dans le fichier .env ou .env.local
* 1ère partie (3h)
* * Préparer le déploiement de l'application (sur votre machine Debian) en rédigeant votre procédure dans le fichier `doc/DEPLOY.md`
  * Répondez aux questions figurant dans le fichier `doc/QUESTIONS.md`
* 2ème partie (2h)
  * Corriger toutes les failles de sécurité/bugs (voir `doc/TODO.md`) et déployez un correctif (toutes les failles ne sont pas répértoriées)
  * Pensez à mettre à jour le fichier `CHANGELOG.md`

## Lancement du projet

### Création de la base de données

```

<?php

require 'vendor/autoload.php';
require 'config/bootstrap.php';

use Mns\Buggy\Core\MySqlConnector;

$pdo = MySqlConnector::getServerConnection();

// Chemin absolu vers le fichier SQL
$sqlFile = realpath(__DIR__ . '/../database.sql');

if (!$sqlFile || !file_exists($sqlFile)) {
    die("Fichier SQL introuvable !");
}

// Lit le contenu du fichier
$sql = file_get_contents($sqlFile);

try {
    // Si le fichier contient plusieurs instructions séparées par ;
    $statements = array_filter(array_map('trim', explode(';', $sql)));

    foreach ($statements as $statement) {
        if ($statement) {
            $pdo->exec($statement);
        }
    }

    echo "Base et tables créées avec succès !\n";
} catch (\PDOException $e) {
    echo "Erreur lors de l'exécution du script SQL : " . $e->getMessage() . "\n";
}

php bin/create-database
```

### Lancement du serveur

Pour lancer le projet, vous devez impérativement passer par la commande : `php bin/serve`

### Création de la base de données

Pour créer la base de données vous pouvez lancer la commande : `php bin/create-database `

Un compte admin et utilisateurs seront également créés *(vous trouverez les informations dans le script database.sql)*

Ensuite, vous pouvez alimenter la base de données avec des données démo en lançant la commande : `php bin/load-demo-data`

## Livrables

Le code doit impérativement être push sur le repo GitHub Classroom qui vous a été assigné et sur la branche principale `main`

**!!! ATTENTION : la partie 2 ne sera pas évaluée si ce n'est pas le cas !!!**

# BONNE CHANCE

DB

Rentrer les information
username :habit_tracker
password :bnffrwrSBcidRnH8



aapanel


**https://172.17.4.12:35185**

**username :MetzNumeric
password : azer**

J'ai rencontrer beacoup de probleme de dépence avec mon ordinateur j'ai trouver des solution pour certain et d'autres non vous pouvez voir dans le document deploy.MD
