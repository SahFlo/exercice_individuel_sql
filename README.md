# Exercice indivudel SQL - novembre 2024

Enoncé complet en bas de la page

## Choix d'outils
Excel pour la conception de BDD, https://simple-sqlite-editor.vercel.app/ pour les requêtes SQL

📸 **Pour partager mon travail je dois donc passer par des captures d'écran**

## Structuration de la BDD

**Etape 1** BDD avec :
- Le prénom
- Le nom
- L’email
- La date de signature

**Etape 2** Créer deux BDD pour isoler l'information redondante, donc la signature et lier les deux BDD

 ![Capture d'écran des deux étapes](Assets\schema_bdd_etapes_1_et_2.png)


## Les requêtes

### Niveau facile

- **Sélectionner toutes les lignes de la table users**  
SELECT *   
FROM users

- **Sélectionner uniquement la ligne où le prénom est Ada dans la table users**  
SELECT *  
FROM users  
WHERE firstname = 'Ada'  
   OR name = 'Ada'; -

- **Sélectionner les lignes dont la première lettre du prénom est un B dans la table users**  
SELECT *   
FROM users  
WHERE firstname LIKE 'B%';

- **Compter le nombre de ligne qu’il y a dans la table users**  
SELECT COUNT(*)   
FROM users

- **Compter le nombre de ligne dont la première lettre du prénom est un B dans la table users**  
SELECT COUNT(*)   
FROM users  
WHERE firstname LIKE 'B%';

- **Afficher uniquement la colonne contenant le prénom de la table users**  
SELECT firstname  
FROM users  

### Niveau moyen

- **Insérer une ligne dans la table edusign qui correspond à la user Ada avec comme date de signature le 2024-05-30 09:30:00**  
Soit en deux étapes
récupérer l'id
-- SELECT id  
-- FROM users  
-- WHERE firstname = 'Ada';  

Faire un insert avec le bon id
INSERT INTO edusign (users_id, created_at)  
VALUES (1, '2024-05-30 09:30:00');

Soit en une étape
INSERT INTO edusign (users_id, created_at)  
VALUES (  
    (SELECT id FROM users WHERE firstname = 'Ada'),  
    '2024-05-30 09:30:00'  
);

- **Insérer une ligne dans la table edusign qui correspond à la user Bella avec comme date de signature le 2024-05-30 09:30:00**  
Après avoir récupéré l'id - 3,  
INSERT INTO edusign (users_id, created_at)  
VALUES (3, '2024-05-30 09:30:00');

- **Insérer toutes les lignes de la table users dans la table edusign avec pour date de signature le 2024-09-01 09:30:00**  
INSERT INTO edusign (users_id, created_at)  
VALUES   
(1, '2024-09-01 09:30:00'),  
(2, '2024-09-01 09:30:00'),  
(3, '2024-09-01 09:30:00'),  
(4, '2024-09-01 09:30:00');  

- **Sélectionner toutes les lignes de la table edusign ordonnées par date de signature de la plus récente à la plus ancienne et par user_id ascendant.**  
SELECT *  
FROM edusign  
ORDER BY created_at DESC  

- **Sélectionner toutes les lignes de la table edusign dont la date est 2024-05-30 09:30:00**  

