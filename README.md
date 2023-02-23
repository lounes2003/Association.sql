# Association.sql
Analyse d'une base de données d'une association

2022/2023
Projet Base
De Données
Réalisé par :
BOUDINAR Lounes
KACEM Mohamed Riad
Encadré par :
ANGARITA AROCHA Rafael
FERDAOUI Asmaa
BASE DE DONNEES RELATIONELLES 2
Sommaire :
1. Présentation du projet .
1.1 Choix du sujet
1.2 Description de la base de données.
2. Modele relationnel de données
3. Création des tables et l’insertion des tables.
4. Modèle relationnel EER finale.
5. Les requêtes d’interrogations et Mises à jour de
la Database
5.1 Interrogation de la base
5.2 Mise a jour de la base
6. Conclusion
BASE DE DONNEES RELATIONELLES 3
1.PRESENTATION DU PROJET
Nous avons choisi une base de données Excel composée de quatre
tables avec des champs plutôt intéressants pour pouvoir la manipuler.
L’objectif de ce projet est de créer une base de données sous MySQL et
de s’habituer à la modélisation d’un système de gestion de base de données
afin que nous puissions nous familiariser avec les requêtes SQL.
La base de données a pour but de montrer les demandes de
subventions des associations dirigées par certaines directions.
2.LE MODELE RELATIONNEL DE LA BASE DE
DONNEES
BASE DE DONNEES RELATIONELLES 4
3. CREATION DES TABLES ET L’INSERTION DES
TUPLES ET CONTRAINTES
Création des tables :
 La création des tables s’est obtenue par le shéma relationnel avec la
commande CREATE TABLE nom_table (les attribus que l’on a besoin) .
Exemple :
Create table if not exists Refus (
RefDossier varchar(10) NOT NULL PRIMARY KEY ,
Annéebudgétaire int ,
RefSiret bigint,
Motif varchar(100) default "DonnéesInsuffisantes"
);
 DEFAULT : Permet de mettre une valeur par default dans le champs
Motif quand il n’ y a aucune valeur insérée.
Cette table « Refus » ne fait pas partie de la base de données initiale mais nous
avons créer cette table où on a regroupé toutes les données où le
« Montantvoté » est de 0 dans la table « Subvention ».
 Création des clés etrangères avec la commande ALTER TABLE (foreign
key).
Exemple :
ALTER TABLE Refus ADD FOREIGN KEY (RefSiret) references associations(N°Siret);
L’insertion de tuples dans les differentes tables :
Pour l’insertion on a utilisé le site CSV To SQL Converter (convertcsv.com)
pour la transformation du fichier csv en un script SQL contenant la série des requêtes
d’insertions en modifiant les types de données des tables par rapport aux valeurs.
BASE DE DONNEES RELATIONELLES 5
L’insertion des contraintes:
 CHECK : sert a mettre une condition qui doit être respecter pour pouvoir
insérer des valeurs dans le champs.
 UNIQUE : Permet de ne pas insérer de doublons dans le champs.
4.MODELE EER* FINALE
EER: Enhanced Entity-Relationship qui signifie modèle relationnel entre entité.
BASE DE DONNEES RELATIONELLES 6
Tables père-fils:
• Table père : Direction, Associations
• Table père-fils : Demande
• Table fils : Subvention, Refus
5.MISES A JOUR ET INTERROGATIONS DE
LA DATABASE
4.1 Interrogation de la Database:
 Les requêtes LID avec et sans jointures :
 Afficher les associations pour lesquelles le montant voté des subventions
est supérieur ou égale à 2000.
 Afficher les demandes où l’année budgétaire est supérieure à 2020.
 Afficher par nom du bénéficiaire les subventions supérieurs à 0.
 Afficher les N°Siret des associations qui se trouvent dans la table
« Refus » qui ont un premier chiffre différent de 4.
 Afficher les N°Siret des associations avec les 2 derniers chiffres supérieur
aux deux premiers.
