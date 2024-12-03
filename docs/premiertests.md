# Tests de l'application

| Intitulé | Observation | Type | sévérité |
| Vulnérabilités dans les packets | Quand nous installons le projet, nom nous informe qu'il y a 14 vulnérabilités | Sécurité | Critique
| Fond | Le fond est bleu, ce qui n'es pas du tout existétique | Design | Normal |
| Peu de CSS | L'application est relativement pas estétique | Design | Normal |
| Absent de hash dans les mots de passe | Les mot de passe ne sont pas hashé | Sécurité | Critique |
| Information sensible dans la console | Dans la console, il y a des informations sensibles comme les informations utilisateurs avec l'adresse mail, mot de passe, etc. Mais il y a également les requêtes en clair | Sécurité | Critique |
| Absence de gestion d'erreurs dans le login | Il n'y a pas d'erreurs quand on se trompe de nom d'utilisateur ou de mot de passe | Optimisation | Critique
| L'application crash si le nom de l'utilisateur n'existe pas | / | Optimisation | Critique
| Task completed est inutile | Il n'y a aucun indicateur pour dire si la tâche est faite où non | Praticité | Elevé |
| Impossible de modifier une tâche | / | Praticité | Elevé
| Absent de gestion de droits | Actuellement, il n'y a pas de gestion de droits. N'importe qui connaissant les urls et les ids des utilisateurs peuvent accéder et modifier les données critiques | Sécurité | Critique |
| Absent d'un lien pour se déconnecter | / | Praticité | Critique
| Dans inscription, le champ "mot de passe" n'est pas masqué | Quand on tape le mot de passe dans le champ "mot de passe", on vois le texte en clair | Sécurité | Critique
| Champ "confirmation mot de passe" manquant | Dans l'inscription, il n'y a pas de champ pour confirmer la saisie du mot de passe | Praticité | Elevé |
| Absence d'une politique de mot de passe | Aucune politique de mot de passe n'est présente lors de l'inscription | Sécurité | Critique |
| L'application ne bloque pas l'inscription si un utilisateur et/ou une adresse mail est déjà utilisé | / | Sécurité | Critique |
| La suppression d'un utilisateur ne fonctionne pas | Sur la page /admin, la suppression d'un utilisateur ne fonctionne pas | Optimisation | Critique |
| La numération des tâches n'est pas correcte | Le numéro de tâche correspond à l'id de la tâche et non le numéro de la tâche créer par l'utilisateur | Praticité | Normal |