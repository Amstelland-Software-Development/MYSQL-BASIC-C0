# MYSQL-BASIC-TAAK-01

## DELETE

- [MYSQL-BASIC-TAAK-01](#mysql-basic-taak-01)
  - [DELETE](#delete)
  - [Uitleg](#uitleg)
    - [Syntax](#syntax)
  - [Leerdoelen](#leerdoelen)
  - [Opdracht](#opdracht)
  - [Bronnen](#bronnen)

## Uitleg

Soms wil je gegevens verwijderen uit een database. We hebben al gezien dat je met een SELECT-statement gegevens kunt ophalen. De syntax voor het verwijderen van gegevens is bijna hetzelfde:

### Syntax
```SQL
DELETE FROM tabel_naam WHERE conditie 
```
> LETOP!  
> Je gebruikt praktisch *altijd* een WHERE-clausule bij een DELETE-statement. Als je dit niet zou doen dan worden *alle* rijen uit de tabel verwijderd.

Als we onderstaand voorbeeld nemen uit de `FIFA2018` database:

id | name | age | nationality | club | value | wage
--- | --- | --- | --- | --- | --- | ---
| 148803| K. Huntelaar| 33| Netherlands| Ajax| 55000000| 17000
| 172143| L. Sch ne| 31| Denmark| Ajax| 75000000| 15000
| 186452| S. de Jong| 28| Netherlands| Ajax| 75000000| 16000

De onderstaande SQL-query zou alleen Huntelaar verwijderen.
```SQL
DELETE FROM player WHERE name = "K. Huntelaar";
```
En de volgende SQL-query zou alleen de Nederlandse spelers verwijderen.
```SQL
DELETE FROM player WHERE nationality = "Netherlands";
```
Terwijl de onderstaande SQL-query alle spelers verwijdert die meer dan (maar **niet** precies 15000!) verdienen. Dus alleen Huntelaar wordt verwijderd.
```SQL
DELETE FROM player WHERE wage > 15000;
```



## Leerdoelen

1. [ ] Ik kan een DELETE-statement schrijven met een WHERE-clausule

## Opdracht

1. We maken weer gebruik van de `Fifa2018`-database. Als je deze nog niet hebt staan in PhpMyAdmin, maak dan een nieuwe database aan (met een duidelijke naam, bv: `mod-mysql-basic-fifa2018`) en importeer het `.sql`-bestand in de `db-export`-map van deze taak.
2. Open het SQL-tabblad in PhpMyAdmin en schrijf SQL-queries om de gevraagde gegevens te tonen:  
   **(vergeet niet na elke beantwoorde vraag de SQL-statement die je geschreven hebt te copy/pasten in `antwoorden.sql` en een bookmark met een logisch genaamd label aan te maken)**

Schrijf DELETE-statements om de onderstaande opdrachten uit te voeren

1. Verwijder de speler David Sylva
2. Verwijder alle spelers van Willem II
3. Verwijder alle belgische spelers die spelen voor FC Barcelona
4. Verwijder alle spelers die ouder of even oud zijn dan 38
5. Verwijder de spelers met id 167905 of 169595

## Bronnen

[W3 Schools - DELETE Statement](https://www.w3schools.com/sql/sql_delete.asp)  

