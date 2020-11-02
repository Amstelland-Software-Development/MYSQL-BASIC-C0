# MYSQL_BASIC-Eindtaak

## Video Game Sales database

We gebruiken voor deze eindtaak van de MYSQL-BASIC-module een nieuwe database met gegevens over spelverkoop van 1000 bekende spellen. 

## Uitleg

De database heeft 1 tabel genaamd `videogamesales` met 11 kolommen.

Kolom | Betekenis
--- | ---
id | Primary Key
name | Naam van het spel
platform | Platform waarop het spel gespeeld kan worden
year | Jaar dat het spel is uitgekomen
genre | Genre van het spel
publisher | Uitgever van het spel
NA_Sales | Aantal spellen in duizendtallen verkocht in Noord Amerika
EU_Sales | Aantal spellen in duizendtallen verkocht in Europa
JP_Sales | Aantal spellen in duizendtallen verkocht in Japan
Other_Sales | Aantal spellen in duizendtallen verkocht in overige gebieden van de wereld
Global_Sales | Aantal spellen in duizendtallen verkocht werelwijd

Voor de onderstaande opdrachten maak je gebruik alle in de deze module behandelde onderwerpen:

Onderwerp | Taak | SQL syntax / onderwerpen
--- | --- | ---
Databases | taak01 | PhpMyAdmin database import + werkwijze
Select | taak01  | `SELECT` `FROM`
Select | taak02 | `SELECT` `WHERE` 
Select | taak03 |  `WHERE` met `AND` `OR`
Select | taak04 | Aliasses en Functies: `MAX()` `MIN()` `AVG()` `SUM()` `COUNT()` `ROUND()`
Delete | taak01 | `DELETE FROM` 
Delete | taak02 | Primary Keys

## Leerdoelen

//TODO: add leerdoelen

## Opdracht

1. Maak een nieuwe database aan genaamd `mod-mysql-basic-opdracht` en importeer de database-exportfile `videogamesales.sql` in de `db-export` map.
2. Open het SQL-tabblad in PhpMyAdmin en schrijf SQL-queries om de gevraagde gegevens te tonen:  
   **(vergeet niet na elke beantwoorde vraag de SQL-statement die je geschreven hebt te copy/pasten in `antwoorden.sql` en een bookmark met een logisch genaamd label aan te maken)**

Schrijf voor de onderstaande vragen een SQL-query die de gevraagde informatie teruggeeft of verwijdert. Gebruik aliassen (`AS`) om een goed beschrijvende kolomnaam terug te krijgen als je functies gebruikt.

1. Toon alle gegevens in de `videogamesales` tabel.
2. Hoeveel spellen uit de database zijn uitgebracht in 1999?
3. Hoeveel spellen zijn er in het genre Sports verkocht in Noord-Amerika?
4. Toon de naam en het platform van alle spellen die zijn uitgebracht door Nintendo tussen 1990 en 2005.
5. Welk spel heeft het hoogste aantal verkopen wereldwijd? 
6. Hoeveel spellen zijn er gemiddeld verkocht in het genre Puzzle in Europa?
7. Toon de naam, het genre en de uitgever van het spel dat 532 verkochte spellen heeft in Japan. 
8.  Hoeveel spellen zijn er totaal verkocht van Nintento wereldwijd?
9.  Toon de naam en het jaar van uitgave van alle spellen die zijn uitgebracht van het genre Racing door Nintendo of Activision.
10. Toon de gemiddelde verkoop aantallen in Noord Amerika, Europa en Japan. Gebruik een duidelijke ALIAS.
11. Verwijder het spel Halo 2 voor de XB.
12. Verwijder alle spellen uit 2012 of die gemaakt zijn door Ubisoft.
13. Verwijder alle spellen van het genre Adventure gemaakt door Nintendo
14. Verwijder alle spellen van Nintendo waarvan het aantal verkopen wereldwijd onder de 1000 ligt.
15. Verwijder alle spellen die zijn uitgebracht in 1997 en waarvan er in Noord Amerika meer dan 200 duizend zijn verkocht.


## Eindresultaat


## Bronnen


[W3 Schools - PHP Functions](https://www.w3schools.com/php/php_functions.asp)  

