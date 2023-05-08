# location_voiture
Ce code est une implémentation d'un système de gestion de base de données SQLite pour un blog. Il utilise la programmation orientée objet pour définir des classes de modèles pour les entités de la base de données (utilisateur, commentaire, publication), qui étendent une classe de base générique nommée Entity. Les classes de modèles ont des méthodes pour effectuer des opérations CRUD (créer, lire, mettre à jour, supprimer) sur leurs tables de base de données correspondantes.

La classe Entity a une méthode save() qui insère une nouvelle ligne dans la table correspondante dans la base de données. Cette méthode récupère le nom de la table à partir du nom de la classe, les noms des colonnes à partir des noms des attributs de l'objet et les valeurs des colonnes à partir des valeurs des attributs de l'objet. Les attributs de l'objet sont stockés dans un dictionnaire, qui est utilisé pour créer la requête SQL.

La classe User hérite de la classe Entity et définit des méthodes supplémentaires pour gérer les utilisateurs. Elle a des méthodes pour vérifier si un nom d'utilisateur existe déjà dans la base de données et pour connecter un utilisateur. La méthode login() demande à l'utilisateur de saisir son nom d'utilisateur et son mot de passe, puis recherche dans la base de données pour un utilisateur correspondant. Si un utilisateur correspondant est trouvé, ses informations sont stockées dans l'objet User qui appelle la méthode.

Enfin, la classe User a des méthodes pour créer, lire, mettre à jour et supprimer des publications et des commentaires. Les méthodes create_post() et create_comment() insèrent de nouvelles lignes dans les tables de base de données correspondantes. La méthode get_all_posts() sélectionne toutes les publications de la table de base de données et les affiche à l'utilisateur. Les méthodes delete_comment() et update_comment() suppriment et mettent à jour les commentaires existants dans la base de données, respectivement. La méthode close() ferme la connexion à la base de données SQLite.
Il y a ensuite plusieurs méthodes dans la classe User, qui sont :

create_account(self) : cette méthode permet de créer un nouveau compte utilisateur en demandant à l'utilisateur d'entrer un nom d'utilisateur, un mot de passe, une adresse email et un nom. Elle vérifie également que le nom d'utilisateur n'existe pas déjà dans la base de données avant de l'ajouter. Les informations sont stockées dans la table users de la base de données.
check_username_exists(self, username) : cette méthode vérifie si le nom d'utilisateur spécifié existe déjà dans la base de données.
login(self) : cette méthode permet à l'utilisateur de se connecter en entrant son nom d'utilisateur et son mot de passe. Si les informations sont correctes, un message de confirmation est affiché et les informations de l'utilisateur sont stockées dans les attributs de l'objet User.
create_post(self) : cette méthode permet de créer un nouveau post en demandant à l'utilisateur d'entrer un titre et un contenu. Les informations sont stockées dans la table posts de la base de données.
get_all_posts(self) : cette méthode permet d'afficher tous les posts dans la base de données.
create_comment(self) : cette méthode permet de créer un nouveau commentaire pour un post spécifique. Elle demande à l'utilisateur d'entrer le contenu du commentaire et le post auquel il est lié. Les informations sont stockées dans la table comments de la base de données.
get_comments_by_post(self) : cette méthode permet d'afficher tous les commentaires liés à un post spécifique.
delete_comment(self, comment_id) : cette méthode permet de supprimer un commentaire spécifique en vérifiant d'abord que l'utilisateur qui essaie de supprimer le commentaire en est l'auteur.
update_comment(self, comment_id) : cette méthode permet de mettre à jour le contenu d'un commentaire spécifique en vérifiant d'abord que l'utilisateur qui essaie de mettre à jour le commentaire en est l'auteur.
close(self) : cette méthode permet de fermer la connexion à la base de données.
a méthode init de la classe Car définit les propriétés d'un objet voiture, telles que sa marque, son modèle, son image, son type de carburant, le nombre de sièges, le type de transmission, le prix de location par jour et la disponibilité.

La fonction get_available_cars récupère toutes les voitures disponibles à partir de la table cars dans la base de données MySQL et les renvoie sous forme de liste d'objets Car. Elle utilise une requête SQL pour filtrer les résultats en fonction de la colonne de disponibilité de la table cars.

La fonction display_available_cars prend une liste d'objets Car en argument et affiche les détails de chaque voiture dans la console.

La déclaration CREATE TABLE à la fin du code crée une table cars dans la base de données MySQL avec des colonnes pour les propriétés d'un objet voiture définies dans la classe Car. La colonne id est définie comme clé primaire.

Dans l'ensemble, ce code fournit un exemple simple de la façon dont Python peut être utilisé pour interagir avec une base de données MySQL pour stocker et récupérer des données.
