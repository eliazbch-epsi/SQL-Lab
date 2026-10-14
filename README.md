# SQL-Lab

## À propos  

Laboratoire personnel SQL réalisé dans le cadre de ma formation Administrateur Systèmes et Réseaux avec une énorme base de données sur la musique
avec 6 tables : ALBUM, ARTISTE, CONTENU, GROUPE, MEMBRE_GROUPE, MORCEAU

## Notions étudiées :

    SELECT
    FROM
    WHERE
    AS  
    LIKE
    INSERT
    UPDATE    
    DELETE
    Jointures
    Clés primaires
    Clés étrangères

## Projet 1 - Pour chaque album, donnez son titre, son genre et son prix.

Requête : 

          SELECT nom, genre, prix 
          FROM ALBUM ;

capture : 

<img width="762" height="512" alt="image" src="https://github.com/user-attachments/assets/e9ab82ea-df69-4a2c-94e3-c743e28e18e6" />

## Projet 2 - Pour chaque morceau, indiquez son titre dans une colonne se nommant «.Le titre des morceaux ».

Requête 2 : 

            SELECT TITRE as "Le titre des morceaux" 
            FROM MORCEAU ;

Capture : 

<img width="835" height="427" alt="image" src="https://github.com/user-attachments/assets/b616fb30-50af-460d-bf88-5b2ec0513352" />

## Projet 3 - Retrouvez les groupes dont le nom commence par « R ».

Requête : 

          SELECT NOM FROM GROUPE 
          WHERE NOM LIKE 'R%' ;

Capture : 

<img width="766" height="406" alt="image" src="https://github.com/user-attachments/assets/8e66aeb4-9775-4e26-a7bb-f1e94ae2375c" />

## Projet 4 - Retrouvez les albums rock dont le prix est supérieur à 10€ (attention, il y a deux conditions à mettre dans le WHERE ici).

Requête : 

          SELECT NOM 
          FROM ALBUM 
          WHERE PRIX > 10 AND GENRE = 'Rock' ;

Capture : 

<img width="870" height="516" alt="image" src="https://github.com/user-attachments/assets/5d7b7eca-b8eb-446e-8afc-a491535af6e1" />

## Projet 5 - Les Jointures SQL

Explication
Une jointure permet de relier plusieurs tables grâce aux clés primaires (PK)
et aux clés étrangères (FK).

Exemple :

ARTISTE.IND_GROUPE (FK)
↓
GROUPE.IDENT (PK)

La jointure permet donc de retrouver le groupe auquel appartient un artiste.

1. Affichez le nom des artistes et le nom des albums en utilisant une jointure interne sur la table artiste.

Requête : 
        
        SELECT ARTISTE.NOM, ALBUM.NOM
        FROM ALBUM
        INNER JOIN ARTISTE
        ON ALBUM.IDENT_ARTISTE = ARTISTE.IDENT ;

Capture : 

<img width="852" height="691" alt="image" src="https://github.com/user-attachments/assets/10c15f55-5055-4922-96d4-7eccdcde4f56" />

2. Réalisez un travail similaire avec les groupes.

Requête : 

        SELECT * FROM ALBUM
        INNER JOIN GROUPE 
        ON ALBUM.IDENT_GROUPE = GROUPE.IDENT ; 

Capture :

<img width="1627" height="610" alt="image" src="https://github.com/user-attachments/assets/1dd88814-f997-4013-b741-fd6d6a57e10e" />

3. Affichez le nom des groupes et chaque artiste le composant en utilisant des jointures internes.

Requête :

        SELECT GROUPE.NOM, ARTISTE.PRENOM 
        FROM GROUPE
        INNER JOIN MEMBRE_GROUPE ON MEMBRE_GROUPE.IDENT_GROUPE = GROUPE.IDENT
        INNER JOIN ARTISTE ON ARTISTE.IDENT = MEMBRE_GROUPE.IDENT_ARTISTE

Capture :

<img width="992" height="622" alt="image" src="https://github.com/user-attachments/assets/17679b9b-e9b3-4eca-b52f-be1778ca020f" />

5. Affichez le genre des albums ainsi que chaque morceau inscrit dans le genre, en utilisant des jointures internes.

Requête :

        SELECT ALBUM.GENRE, MORCEAU.TITRE 
        FROM ALBUM
        INNER JOIN CONTENU ON CONTENU.IDENT_ALBUM = ALBUM.IDENT
        INNER JOIN MORCEAU ON  MORCEAU.IDENT = CONTENU.IDENT_MORCEAU 

Capture :

<img width="917" height="802" alt="image" src="https://github.com/user-attachments/assets/16daaf76-e1e8-4ea7-94ad-34b292126a1f" />

Projet 6 - Reprenez la dernière requête pour n’y afficher que les musiques provenant d’artiste.

Requête :

        SELECT ALBUM.GENRE, MORCEAU.TITRE 
        FROM ALBUM
        INNER JOIN CONTENU ON CONTENU.IDENT_ALBUM = ALBUM.IDENT
        INNER JOIN MORCEAU ON  MORCEAU.IDENT = CONTENU.IDENT_MORCEAU 
        INNER JOIN ARTISTE ON ALBUM.IDENT_ARTISTE = ARTISTE.IDENT
        
Capture :

<img width="895" height="592" alt="image" src="https://github.com/user-attachments/assets/ceb07b19-2ed0-4ba5-9aa8-a5ecb292e7ec" />

## à retenir :

PRIMARY KEY (PK) = Identifiant unique d'une table

FOREIGN KEY (FK) = Clé faisant référence à une autre table

INNER JOIN = Relier deux tables ayant une information commune

LEFT JOIN = Afficher toutes les lignes de la table de gauche même sans correspondance

RIGHT JOIN = Afficher toutes les lignes de la table de droite même sans correspondance

FULL JOIN = Afficher toutes les lignes des deux tables

ON = Définir la relation entre deux tables

Exemple :

SELECT ALBUM.NOM, ARTISTE.NOM
FROM ALBUM
INNER JOIN ARTISTE
ON ALBUM.IDENT_ARTISTE = ARTISTE.IDENT;

→ Afficher le nom des albums avec le nom de leur artiste

SELECT = Afficher des données

FROM = Choisir une table

WHERE = Filtrer des données

AS = Renommer une colonne

AND = Ajouter une condition

OR = Accepter plusieurs conditions

LIKE = Rechercher du texte

IN = Vérifier qu'une valeur appartient à une liste

BETWEEN = Vérifier qu'une valeur est comprise entre deux bornes

ORDER BY = Trier les résultats

ASC = Tri croissant

DESC = Tri décroissant

COUNT(*) = Compter les lignes

DISTINCT = Supprimer les doublons

'R%' = Commence par R

'%R' = Finit par R

'%R%' = Contient R

= = Égal à

> = Supérieur à

< = Inférieur à

>= = Supérieur ou égal à

<= = Inférieur ou égal à

<> = Différent de

'Rock' = Chaîne de caractères
