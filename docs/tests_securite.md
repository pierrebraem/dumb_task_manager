# Contrôle d'accès et d'autorisation
Il n'y a aucun contrôle des droits d'accès et d'autorisation. On peu par exemple, accéder aux informations de l'utilisateur en tapant simplement ```?userId=[nombre]``` dans l'url. Pas de vérification côté back non plus quand on manipule une tâche pour vérifier si c'est bien le propriétaire du compte à l'origine des manipulations des données.

# Défaillances cryptographiques
Absence de hashage des mots de passe. Aucun message d'erreur dite personnalité (c'est-à-dire que c'est le serveur qu'il retourne l'erreur est non une condition prévue par l'application).