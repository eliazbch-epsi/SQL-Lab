# SQL-Lab

## À propos  

Laboratoire personnel SQL réalisé dans le cadre de ma formation Administrateur Systèmes et Réseaux avec une énorme base de données sur la musique
avec 6 tables : ALBUM, ARTISTE, CONTENU, GROUPE, MEMBRE_GROUPE, MORCEAU

## Notions étudiées  

  - SLECTIONNER
  - FROM
  - WHERE
  - AS
  - LIKE
  - INSERT
  - UPDATE
  - DELETE
  - Jointures
  - Clés primaires
  - Clés étrangères

## Projet 1 - Pour chaque album, donnez son titre, son genre et son prix.

Requête : SELECT nom, genre, prix 
          FROM ALBUM ;

capture : <img width="762" height="512" alt="image" src="https://github.com/user-attachments/assets/e9ab82ea-df69-4a2c-94e3-c743e28e18e6" />

## Projet 2 - Pour chaque morceau, indiquez son titre dans une colonne se nommant «.Le titre des morceaux ».

Requête 2 : SELECT TITRE as "Le titre des morceaux" 
            FROM MORCEAU ;

Capture : <img width="835" height="427" alt="image" src="https://github.com/user-attachments/assets/b616fb30-50af-460d-bf88-5b2ec0513352" />

## Projet 3 - Retrouvez les groupes dont le nom commence par « R ».

Requête : SELECT NOM FROM GROUPE 
          WHERE NOM LIKE 'R%' ;

Capture : <img width="766" height="406" alt="image" src="https://github.com/user-attachments/assets/8e66aeb4-9775-4e26-a7bb-f1e94ae2375c" />

## Projet 4 - Retrouvez les albums rock dont le prix est supérieur à 10€ (attention, il y a deux conditions à mettre dans le WHERE ici).

Requête : SELECT NOM 
          FROM ALBUM 
          WHERE PRIX > 10 AND GENRE = 'Rock' ;

Capture : <img width="870" height="516" alt="image" src="https://github.com/user-attachments/assets/5d7b7eca-b8eb-446e-8afc-a491535af6e1" />
