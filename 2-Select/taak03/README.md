# MYSQL-BASIC-TAAK-03

## SELECT WHERE met meerdere condities 

- [MYSQL-BASIC-TAAK-03](#mysql-basic-taak-03)
  - [SELECT WHERE met meerdere condities](#select-where-met-meerdere-condities)
  - [Uitleg](#uitleg)
    - [Database](#database)
    - [Syntax](#syntax)
  - [Leerdoelen](#leerdoelen)
  - [Opdracht](#opdracht)
  - [Eindresultaat](#eindresultaat)
  - [Bronnen](#bronnen)

## Uitleg

Soms wil je bij een WHERE-conditie niet alleen checken op de waarden van een enkele kolom, maar wil je twee of meer kolommen checken. 

### Database

We gebruiken voor deze taak weer een nieuwe database met daarin informatie over voetbalspelers uit het spel FIFA2018. De tabel heet `players` en bevat de onderstaande kolommen:

kolom | inhoud
--- | ---
id | Een **Uniek** getal
name | Naam van de speler
age | Leeftijd van de speler
nationality | Nationaliteit
club | club waarvoor de speler speelt
value | Waarde van de speler 
wage | Loon van de speler

Een voorbeeld van 2 rijen uit de `players` tabel:

id | name | age | nationality | club | value | wage
--- | --- | --- | --- | --- | --- | ---
| 41| Iniesta| 33| Spain| FC Barcelona| 295000000| 260000
| 7763| A. Pirlo| 38| Italy| New York City Football Club| 4000000| 10000

Stel dat we nu alle spelers willen vinden die uit Spanje komen én meer dan 260k per jaar verdienden in 2018. We moeten dan in een WHERE clausule checken bij twee kolommen (`nationality` en `wage`) voor twee verschillende waardes ("Spain" en 260000).

Gelukkig kun je in SQL meerdere condities toevoegen aan een WHERE-clause met de `AND`- en `OR`-keywords.

Je zou dit probleem kunnen oplossen met de onderstaande SQL-statement:
```SQL
SELECT * FROM players WHERE nationality = "Spain" AND wage = 260000;
```

### Syntax

De syntax is dus als volgt:
```SQL
SELECT kolom1, kolom2, ... FROM tabel_naam WHERE conditie1 AND conditie2;
```
Het werkt hetzelfde met het `OR`-keyword, alleen krijg je, als je dit zou doen bij bovenstaande query, alle spelers terug die *óf* de Spaanse nationaliteit hebben *óf* meer dan 260k verdiend hebben in 2018. Je krijgt dus ook Spaanse spelers die minder of meer hebben verdiend en spelers die meer dan 260k hebben verdiend en niet de Spaanse nationaliteit hebben.

## Leerdoelen

1. Ik kan meerdere condities toevoegen aan de WHERE-clausule met de `AND`- en `OR`-keywords.
   
## Opdracht

1. Open PhpMyAdmin in je browser en maak een nieuwe database aan (met een duidelijke naam, bv. `mod-mysql-basic-fifa2018`) en importeer het `.sql`-bestand in de `db-export`-map van deze taak.
2. Open het SQL-tabblad in PhpMyAdmin en schrijf SQL-queries om de gevraagde gegevens te tonen:  
   **(vergeet niet na elke beantwoorde vraag de SQL-statement die je geschreven hebt te copy/pasten in `antwoorden.sql` en een bookmark met een logisch genaamd label aan te maken)**

Schrijf voor de onderstaande vragen een SQL-query die de vraag beantwoordt. Gebruik tenzij anders vermeld gewoon een SELECT * FROM.

1. Welke spelers komen uit Spanje en spelen voor Chelsea?
2. Welke speler(s) van 17 jaar oud komen uit Spanje en hebben een loon van 15000?
3. Welke spelers spelen voor Liverpool en zijn ouder dan 20?
4. Welke spelers uit Nederland spelen voor Ajax?
5. Welke spelers spelen voor Ajax, maar hebben geen Nederlandse nationaliteit?

Toon voor de onderstaande vragen alleen de gevraagde gegevens:

6. Toon de naam en leeftijd van de spelers die voor AZ Alkmaar spelen. 
7. Toon de naam, leeftijd en club van de spelers die voor AZ Alkmaar spelen.
8. Toon de naam en het loon van alle Braziliaanse spelers die voor Machester City spelen.
9. Toon alleen de namen van de spelers die 30 jaar oud zijn en minder verdienen dan 10000.
10. Toon de namen en leeftijden van de spelers die uit Spanje (Spain) of uit Portugal (Portugal) komen.
11. Toon de namen, leeftijden en clubs van de spelers die uit Portugal komen of voor Chelsea spelen
12. Toon de namen en clubs van de spelers die ouder zijn dan 40 en meer verdienen dan 10000.
13. Toon alle kolommen (`*`) van de spelers die uit Nederland (Netherlands) komen en voor Ajax of FC Utrecht spelen. Let op: hiervoor moet je dus 3 (!) condities gebruiken.
14. Toon alle kolommen van de spelers die uit Engeland komen, ouder zijn dan 20 en meer verdienen dan 100k (100000).
15. Toon de naam, de leeftijd en de nationaliteit van de spelers die uit Argentinië of Brazilië en ouder zijn dan 25.


## Eindresultaat

 

## Bronnen

