# MYSQL-BASIC-TAAK-01

- [MYSQL-BASIC-TAAK-01](#mysql-basic-taak-01)
  - [Uitleg](#uitleg)
  - [Leerdoelen](#leerdoelen)
  - [Opdracht](#opdracht)
  - [Eindresultaat](#eindresultaat)
  - [Bronnen](#bronnen)

## Uitleg

Als het goed is heb je Xampp al geïnstalleerd en weet je hoe je de database-server (MySQL) opstart. Daarnaast weet je hoe je de webserver binnen Xampp (Apache) opstart zodat je gebruik kan maken van PhpMyAdmin.

## Leerdoelen

1. [ ] Ik kan via het Xampp Controlepaneel de MySQL-database server opstarten
2. [ ] Ik kan via het Xampp Controlepaneel de Apache-webserver opstarten
3. [ ] Ik kan PhpMyAdmin openen in een browser
4. [ ] Ik kan een een databasebestand importeren in een nieuwe database in PhpMyAdmin.
5. [ ] Ik kan een SQL-query uitvoeren in PhpMyAdmin
6. [ ] Ik kan een uitgevoerde SQL-query bookmarken in PhpMyAdmin

## Opdracht

1. Start via het Xampp-controlepaneel MySQL en Apache op.
2. Ga in je browser naar [http://localhost/phpmyadmin](http://localhost/phpmyadmin/)
3. Maak een nieuwe database aan.
   > Je zal veel verschillende databases aanmaken, dus is het slim om een logische naam te kiezen zodat je het overzicht behoudt. Noem de database voor deze taak: `mod_mysql_basic_imdb_movies`.  
4. Selecteeer je nieuwe database: als het goed is zie je de onderstaande regel staan boven in PhpMyAdmin:  
![Database Selected](https://github.com/ROC-van-Amsterdam-College-Amstelland/MYSQL-BASIC/blob/master/1-databases/taak01/img/db-selected.jpg?raw=true)

5. We gaan nu een databasebestand importeren in de nieuw aangemaakte database. Voor je dat doet, open je het bestand `imdb_movies.sql` dat in de `db-export` map staat bij deze taak in VS Code en bekijk de inhoud.
    > Het ziet er misschien ingewikkeld uit en er zijn veel termen die misschien niet duidelijk zijn, maar als je goed kijkt zie je wel dat er een tabel wordt aangemaakt (CREATE TABLE) en dat er gegevens in die tabel worden gezet (INSERT INTO). Deze code is letterlijk de SQL-code die wordt uitgevoerd als je de database importeert.

6. Importeer de database: kies uit het menu de knop `Import` en dan in het scherm dat wordt geladen `Choose File` en selecteer het bestand `imdb_movies.sql` in de `db-export` map en kies `Go`.  
   ![PhpMyAdmin import](https://github.com/ROC-van-Amsterdam-College-Amstelland/MYSQL-BASIC/blob/master/1-databases/taak01/img/phpmyadmin-options-import.jpg)  

    > Als het gelukt is, zie je dat bovenaan staan: Import has been succesfully finished... (imdb_movies.sql) Als je foutmeldingen krijgt: kijk of je database waarin je gaat importeren wel hebt geselecteerd.
7. We gaan nu een eerste SQL-query uitvoeren en gegevens ophalen uit de database. Kies uit het menu de optie `SQL`.
![PhpMyAdmin SQL](https://github.com/ROC-van-Amsterdam-College-Amstelland/MYSQL-BASIC/blob/master/1-databases/taak01/img/phpmyadmin-options-sql.jpg)  

8. Je ziet een codevenster waarin je SQL-code kan schrijven. Schrijf de ondestaande SQL-code in dat venster: (als er al iets staat haal dit dan weg)   
   ```SELECT * FROM movies ``` 

   klik op de `Go` knop rechtsonder om de query uit te voeren.

9. Als het goed is krijg je een overzicht van de inhoud van de tabel `movies` te zien. Om nu te laten zien dat je de taak hebt volbracht doe je het volgende:
    Copy/Paste de gemaakte query in het `antwoorden.sql` bestand op regel 2 en sla deze op. 
10.  Als laatste onderdeel van deze taak gaan we de query bookmarken.  
Voer bij de het invulveld label de volgende naam in: `mod-mysql-basic-taak01` in en klik op de `Bookmark this SQL query` knop.  
![PhpMyAdmin bookmark query](https://github.com/ROC-van-Amsterdam-College-Amstelland/MYSQL-BASIC/blob/master/1-databases/taak01/img/bookmark-query.jpg)  
> Dit is handig voor als je dezelfde query nog een keer wilt gebruiken maar is ook de manier om snel een query op te halen zodat je deze met een docent kan bespreken.
    
> **LET OP!** Een docent kan je vragen om de query's in je bookmarks te laten zien. Zorg er dus voor dat je elke query opslaat in je bookmarks. Gebruik een logische naam voor de label van de query.


## Tips

Als je straks gaat werken met PhpMyAdmin om query's uit te voeren, dan zijn er een paar handigheidjes die het gemakkelijker maken:  
1. Bij het tabblad SQL kun je rechts boven op het tandwiel klikken om opties in te stellen: zet een vinkje bij de `Retain Query Box` optie zodat je niet telkens opnieuw het invoerveld moet openen na elke uitgevoerde query.
2. Je weet al hoe je bookmarks kunt opslaan. Maar als je snel wat verschillende query's wilt uitproberen, maar niet telkens de query's wilt opslaan in een bookmark, kun je regels van commentaar voorzien, net als bij programmeercode. SQL gebruikt hier voor twee streepjes met een spatie erachter (`-- `).
```SQL
-- Deze query bewaar ik even als commentaar 
-- SELECT * FROM table

-- Maar deze query wordt wel uitgevoerd als ik op GO druk in PhpMyAdmin
SELECT kolom1, kolom2 FROM table
```

## Eindresultaat

## Bronnen

