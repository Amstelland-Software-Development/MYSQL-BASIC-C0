# MYSQL-BASIC-TAAK-02

## Primary Keys

- [MYSQL-BASIC-TAAK-02](#mysql-basic-taak-02)
  - [Primary Keys](#primary-keys)
  - [Uitleg](#uitleg)
  - [Leerdoelen](#leerdoelen)
  - [Opdracht](#opdracht)
  - [Resultaat](#resultaat)
  - [Bronnen](#bronnen)

## Uitleg

Als je rijen uit een database verwijdert, wil je meestal alleen specifieke rijen verwijderen. Als we het onderstaande voorbeeld nemen, welke kolom zou je gebruiken in de conditie van je WHERE-clausule om alleen K. Huntelaar te verwijderen?

id | name | age | nationality | club | value | wage
--- | --- | --- | --- | --- | --- | ---
| 148803| K. Huntelaar| 33| Netherlands| Ajax| 55000000| 17000
| 172143| L. Sch ne| 31| Denmark| Ajax| 75000000| 15000
| 186452| S. de Jong| 28| Netherlands| Ajax| 75000000| 16000

Je zou de `name`-kolom kunnen pakken:
```SQL
DELETE FROM players WHERE name = "K. Huntelaar";
```
Dit werkt. Totdat zijn jongere broertje Kees Huntelaar wordt toegevoegd aan FIFA. Stel dat broertje is net 20 geworden. we kunnen dan onze DELETE-statement uitbreiden:
```SQL
DELETE FROM players WHERE name = "K. Huntelaar" AND age = 33;
```
Zo verwijderen we alleen Klaas-Jan. Maar het is wel een beetje gedoe en foutgevoelig. Wat je eigenlijk wilt is dat er een kolom is die uniek is voor elke speler. Die kolom wil je gebruiken om een enkele speler te verwijderen.

Gelukkig is die kolom er: `id`. Deze kolom bevat een uniek nummer dat voor elke speler anders is. Je kan dan als je de `id` weet van Huntelaar het volgende doen:
```SQL
DELETE FROM players WHERE id = 148803;
```
Veel simpeler en er is geen kans dat je per ongeluk ook andere rijen verwijdert uit de database.

Zo'n `id`-kolom met unieke getallen noem je de `primary key` van de tabel. De waarde in deze kolom geeft je toegang tot één enkele rij in een tabel. Net als een sleutel toegang geeft tot één slot.

> In de praktijk zul je niet met een SQL-query eerste de primary key hoeven opzoeken van een bepaalde speler om deze te verwijderen maar neem je de `id` kolom mee als je alle spelers ophaalt in een applicatie. Deze gebruik je dan weer in bijvoorbeeld PHP om een query te maken die een specifieke speler verwijdert.  

De `FIFA2018`-database die we de hele tijd gebruiken heeft een `id`-kolom maar als je kijkt in PhpMyAdmin bij het tabblad `Structure` dan zie je bij de `id`-kolom niet staan dat het een primary key is. In de volgende opdracht gaan we kijken of we dat kunnen fixen. 

## Leerdoelen

1. [ ] Ik kan een DELETE-statement schrijven met een WHERE-clausule
2. [ ] Ik weet waarom een primary-key-kolom alleen unieke waardes bevat

## Opdracht

1. We maken weer gebruik van de `Fifa2018`-database. Als je deze nog niet hebt staan in PhpMyAdmin maak dan een nieuwe database aan (met een duidelijke naam, bv.: `mod-mysql-basic-fifa2018`) en importeer het `.sql`-bestand in de `db-export`-map van deze taak.
2. In de PhpMyAdmin interface selecteer de `players`-tabel en ga naar het tabblad `Structure`. Zet een vinkje naast de `id`-kolom. Klik vervolgens op de knop `Primary` in de optiebalk. Wat gebeurt er?
   ![Structure options](https://github.com/ROC-van-Amsterdam-College-Amstelland/MYSQL-BASIC/blob/master/3-Delete/taak02/img/phpmyadmin-structure-options.jpg)
3. Je krijgt een foutmelding dat er rijen zijn gevonden met dezelfde id. Gelukkig geeft PhpMyAdmin aan welke id dubbel is. Schrijf een SQL-query die alle spelers ophaalt met die id. (**copy/paste de SQL-query ook in `antwoorden.sql` en sla een bookmark op**)
4. Ah, Rodrigo staat er dubbel in! Wat je nu eigelijk zou willen doen is één van de dubbele rijen verwijderen. Maar hoe? Als je `DELETE FROM players WHERE id = 198329` doet worden ze allebei verwijderd. En elke ander kolom die je in je conditie kan gebruiken levert hetzelfde resultaat op(of zelf nog meer andere spelers). Dit is een reden dat je altijd een unieke id wilt hebben voor elke rij in je database, want stel dat Rodrigo er twee keer in zou staan met dezelfde informatie in alle kolommen *behalve* de `id`-kolom. Dan zouden we hem makkelijk kunnen verwijderen. Voor nu willen we voor elkaar krijgen dat de `id`-kolom alleen nog maar unieke waardes bevat en geven me minder om volledigheid van de gegevens in de database. Verwijder dus maar beide Rodrigo-rijen door een DELETE-statement uit te voeren op basis van zijn id.
5. Als het goed is zie nadat je de DELETE-statement hebt uitgevoerd de volgende boodschap terug in PhpMyAdmin.
   ![Delete dupes](https://github.com/ROC-van-Amsterdam-College-Amstelland/MYSQL-BASIC/blob/master/3-Delete/taak02/img/phpmyadmin-delete-dupes.jpg)
  Er zijn 2 (!) rows veranderd door de DELETE-statement. Dit wil je dus niet zien als je een rij verwijdert op basis van een "unieke" id. Het mag er altijd maar één zijn.
6. Probeer nu weer een primary key aan maken voor de `id`-kolom in PhpMyAdmin zoals je ook bij opdracht 2 hebt gedaan.
7. Niet gelukt? Verwijder ook deze rijen waarvan de id hetzelfde is.
8. Ga zo door tot het lukt om de primary key toe te kennen aan de `id`-kolom in PhpMyadmin. (Lukt het niet via de optionsbalk kijk dan bij `More` > `Primary`)

## Resultaat



## Bronnen

[W3 Schools - DELETE Statement](https://www.w3schools.com/sql/sql_delete.asp)   

