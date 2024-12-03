# Conclusion
L'application dans sa globalité à besoin d'une refonte complète à tous les niveaux.

## Problèmes de sécurité
Le point le plus critique est l'absence de la sécurité. Il n'y a aucune gestion des droits d'accès, aucune gestion d'erreurs, les mots de passe ne sont pas hashé, les requêtes SQL ne sont pas optimiser pour la sécurité, etc. Plusieurs pistes d'amélioration :
- Mettre en place une gestion de droits d'accès afin que chaque utilisateur est chacun leurs droits. Par exemple que seul les administrateurs on accés à la route ```/admin```. Que seul les utilisateurs connectés on accès à la route ```/task``` et accès uniquement à leurs informations. Les solutions peuvent être :
    - Mettre un champ dans la base de données afin de déterminer si l'utilisateur est administrateur ou non et vérifier dans le code si la valeur est bien à 1. Si il est un 1 on le laisse accès à la page, sinon on le redirige sur une autre page.
    - Pour les routes en ```/tasks``` on vérifie que l'utilisateur est connecté grâce à la présence d'un token JWT. Ce même token permettra à l'utilisateur d'intéragir avec ces données et non celle des autres.

- Mise en place d'une gestion d'erreurs afin que ça ne soit pas des messages d'erreurs du serveur ou de SQL. Cela est dû au fait que SQL par exemple, peuvent donner des informations sur la base de donnée par exemple afin de faire de l'injection SQL. Cela peut être utile également pour éviter les plantages, ou qu'un script toutes éternelments.

- Supprimer les paramètres ```userId=[nombre]``` et les remplacer par des sessions.

- Hasher les mots de passe avec un algorthime puissant comme SHA-256. Je conseil en plus de salé le hash le rendant plus puissant.

- Supprimer les console.log() qui peuvent donner des informations sensibles au utilisateur.

- Dans la page d'enregistrement, masqué le mot de passe saisie.

- Mettre à jour les dépendances.

## Problèmes visuelle 
Il y a plusieurs problèmes de visuelle notamment :
- Un fond bleu n'est pas une bonne idée. Un simple fond blanc est suffissant
- Le CSS n'est pas vraiment présent sur le site. Faut faire un grand travail dessus. Nous pouvons codé le CSS à la main ou utiliser une bibliothèque CSS comme Bootstrap ou TailwingCSS. Il faut refaire : formulaire, liste des tâches, etc...
- Rajouter un bouton de déconnection
- Changer le système de numérotation des tâches
- Remoderniser la page d'accueil et la page administrateur.

## Problèmes liées au code
Il y a des problèmes de lisibilité et de maintainibilité du code notamment :
- Dans certains fichiers, il y a des problèmes au niveau de l'indentation. Cela empêche le bon maintient du code
- La mise en commun des balises <head> afin de faciliter la maintenance. Surtout que nous pouvons faire ceci avec EJS
- Changer de place les appels à la base de données. Elle ne doit pas être dans les fichiers models qu'ils ont juste comme rôles de définir les données et ces tous. Ces requêtes douvent être appeler dans le dossier routes
- Changer le noms des fonctions. Cela permettra de mieux la retrouver si le compilateur retourne une erreur. On peu la nommé en "createTask" ou "createUser" par exemple
- Ils manquent des tests unitaires qui permet de vérifier qu'une fonctionnalité fonctionne toujours après un changement.