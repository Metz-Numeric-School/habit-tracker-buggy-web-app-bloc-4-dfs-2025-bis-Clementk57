# TODO

Suite à un audit effectué en amont, voici les failles et les bugs qui ont été identifés comme prioritaire.

## FAILLES

* Des utilsateurs non admin ont des accès à l'interface de gestion des utilisateurs

  ![1759318476466](image/TODO/1759318476466.png)
* Les mots de passes ne sont pas chiffrée en base de données...
  ![1759319703938](image/TODO/1759319703938.png)

  **il suffit d'utliser la fontion password comme j'ai fait ducoup tout les prochain mot de passe seront haset mais on peut aussi le faire dans le code
  dans le sql
  `password_hash($plain, PASSWORD_DEFAULT)`**
* Des injections de type XSS ont été détéctées sur certains formulaires
* On nous a signalé des injections SQL lors de la création d'une nouvelles habitudes

  * exemple dans le champs "name" : foo', 'INJECTED-DESC', NOW()); --

## BUGS

* Une 404 est détéctée lors de l'accès à l'URL ``/habit/toggle``
* Fatal error: Uncaught Error: Class "App\Controller\Api\HabitsController" lorsque l'on accède à l'URL  ``/api/habits``

  j'ai fait la route et maitneant cela fontionne
  ![1759321024684](image/TODO/1759321024684.png)

**ATTENTION : certains bugs n'ont pas été listé**
