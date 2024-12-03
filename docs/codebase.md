# Qualité du code
## Côté front
Il y a des problèmems de lisibilité du code. Je commence par le fichier register.ejs, dans la balise from, un champ est égal à une ligne au lieu d'un bloc.
Exemple :
👎
```
<label for="username">username : </label><input type="text" name="username">
<label for="email">email :</label><input type="text" name="email">
```
👍
```
<label for="username">username : </label>
<input type="text" name="username">

<label for="email">email :</label>
<input type="text" name="email">
```

L'indentation des fichiers index.ejs et admin.ejs dot être refais. Dans index.ejs il y a des fins de bâlises ejs sur une autre ligne.
Exemple :
👎
```
<% }else{
            %> 
```
👍
```
<% }else{ %>
```
Nous avons le même problème avec le fichier index.ejs mais cette fois ci avec avec la balise ```<li>```
Exemple :
👎
```
<li>username: <%= user.username %> - 
    <a href="/admin/delete-user?idToDelete=<%= user.id %>">Remove User</a></li>
```
👍
```
<li>username: <%= user.username %> - 
    <a href="/admin/delete-user?idToDelete=<%= user.id %>">Remove User</a>
</li>
```

De manière générale, il fait centraliser la balise ```<head></head>``` à tous les fichiers. Cela permettra d'éviter d'aller à chaque fichier quand on doit faire une mise à jour

## Côté back
On ne fait pas de requête et de manipulation de données dans les fichiers models. Cela doit se faire lors des appels à des routes (ici dans le dossier ```routes```)

Certains noms de fonctions sont flous. Notamments par le fait qu'il manque le nom du modèle. Exemple :

```
createTask
updateTask
deleteTask
```

# Qualité de l'architecture
Il manque un dossier ```middleware``` afin de mettre les middlewares et mettre la fonction ```authenticate``` dans un middleware

Il manque un dossier ```test``` afin de stocker les tests

# Qualité des tests 
Les tests n'existent pas.