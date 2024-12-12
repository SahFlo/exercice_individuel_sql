# Exercice indivudel SQL - novembre 2024

Enoncé complet en bas de la page

## Choix d'outils
Excel pour la conception de BDD, https://simple-sqlite-editor.vercel.app/ pour les requêtes SQl

** 📸 Pour partager mon travail je dois donc passer par des captures d'écran**

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

- Sélectionner toutes les lignes de la table users
![Capture d'écran des deux étapes](Assets\schema_bdd_etapes_1_et_2.png)

- Sélectionner uniquement la ligne où le prénom est Ada dans la table users
- Sélectionner les lignes dont la première lettre du prénom est un B dans la table users
- Compter le nombre de ligne qu’il y a dans la table users
- Compter le nombre de ligne dont la première lettre du prénom est un Bdans la table users
- Afficher uniquement la colonne contenant le prénom de la table users. Résultat attendu 👇