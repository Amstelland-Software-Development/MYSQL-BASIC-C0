# MYSQL-BASIC-TAAK-01

## SELECT
- [MYSQL-BASIC-TAAK-01](#mysql-basic-taak-01)
  - [SELECT](#select)
  - [Uitleg](#uitleg)
    - [Vertaling voorbeeld](#vertaling-voorbeeld)
    - [Syntax](#syntax)
    - [Meerdere kolommen ophalen](#meerdere-kolommen-ophalen)
  - [Leerdoelen](#leerdoelen)
  - [Opdracht](#opdracht)
  - [Eindresultaat](#eindresultaat)
  - [Bronnen](#bronnen)
## Uitleg

In deze taak gaan we voor het eerst echt oefenen met SQL! 

Een simpele SQL-statement (ookwel query) zoals `SELECT * FROM movies;` is opgebouwd uit SQL-keywords en de namen van kolommen en tabellen die je wilt ophalen. Je gebruikt het SELECT-keyword om gegevens op te halen. Je kunt de bovenstaande SQL-statement als volgt interpreteren: geef mij de informatie uit alle kolommen van de tabel movies.

### Vertaling voorbeeld

Taal | Keyword | kolom- namen | keyword | tabel- naam | 
----|---------|----------|---------|---------- |
SQL | `SELECT` | `*`  | `FROM`  | `movies;`  
Vrij vertaald: | Geef mij  | alle kolommen | van de tabel | movies

> LETOP! We gebruiken voor alle SQL-code die we schrijven de volgende conventies:  
1. Net als bij andere programmeertalen sluit je elke regel code af met `;`
2. SQL-keywords zoals `SELECT` en `FROM` schrijf je in hoofdletters.

> PhpMyAdmin is heel vergevingsgezind en laat toe dat je-SQL keywords in kleine letters schrijft of een `;` vergeet aan het einde van je SQL-statement, maar net als inspringing in je code zorgt het aanhouden van deze conventies voor leesbaardere code. Je vermijdt fouten als je straks met PHP SQL-code gaat uitvoeren.

### Syntax

De syntax voor het schrijven van een SELECT-statement is als volgt:
```SQL
SELECT kolom1, kolom2, ... FROM tabel_naam;
```

### Meerdere kolommen ophalen

Zoals je bij het bovenstaande voorbeeld misschien al bedacht had, kun je ook aangeven in je SQL-statement dat je niet *alle* kolommen maar alleen *bepaalde* kolommen terugkrijgt. Je doet dit door de namen van de kolommen op te geven gescheiden door een `,` in plaats van het gebruik van `*` dat alle kolommen van een tabel ophaalt.

In onderstaand voorbeeld worden de kolommen genaamd `title` en `rating` opgehaald uit de tabel `movies`.
```sql
SELECT title, rating FROM movies;
```

## Leerdoelen

1. [ ] Ik kan een SQL-statement schrijven die alle kolommen ophaalt uit een tabel
2. [ ] Ik kan een SQL-statement schrijven die alleen bepaalde kolommen ophaalt uit een tabel.

## Opdracht

1. [ ] We gebruiken een nieuwe database-export genaamd `mod-mysql-basic-worldhappiness.sql`. Deze vind je in de `db-export` map.
2. [ ] Om te beginnen: open PhpMyAdmin in je browser, maak een nieuwe database aan en noem deze `mod-mysql-basic-worldhappiness`. Importeer `mod-mysql-basic-worldhappiness.sql`. Vergeet niet de database eerst te selecteren voor je de import doet.
3. [ ] Deze database bevat twee tabellen genaamd `jaar2015` en `jaar2016` met allebei de volgende kolommen: `country`, `region`, `rank` en `score`. Beide tabellen zien er ongeveer zo uit:
   country | region | rank | score |
   --------| -------| -----| ------|
   Switzerland | Western Europe | 1 | 7587 |
   Iceland | Western Europe | 2 | 7561 |
   ... | ... | ... | ...|

4. [ ] Open het SQL-tabblad in PhpMyAdmin en schrijf SQL queries om de gevraagde gegevens te tonen:
   **(vergeet niet na elke beantwoorde vraag de SQL statement die je geschreven hebt te copy/pasten in `antwoorden.sql` en een bookmark met een logisch label aan te maken)**
   1. **Voorbeeld**: Schrijf een SQL-statement die de hele inhoud van de `jaar2016` tabel toont.  
    **Antwoord**: `SELECT * FROM jaar2016`
   2. **Opdracht**: Schrijf een SQL-statement die de hele inhoud van de `jaar2015` tabel toont.
   3. **Opdracht**: Schrijf een SQL-statement die alleen de landen met hun score laat zien uit 2016
   4. **Opdracht**: Schrijf een SQL-statement die alleen de regios laat zien uit 2015
   5. **Opdracht**: Schrijf een SQL-statement die alleen de regios laat zien met hun score uit 2015
   6. **Opdracht**: Schrijf een SQL-statement die alleen de score en rank laat zien uit 2016

## Eindresultaat

Onderstaand plaatje geeft gedeeltelijk aan wat je zou moeten terugkrijgen als je de voorbeeldopdracht i hebt uitgevoerd.

![Output opdracht 1 - SELECT* FROM jaar2016](https://github.com/ROC-van-Amsterdam-College-Amstelland/MYSQL-BASIC/blob/master/2-Select/taak01/img/output.jpg)

Onderstaand plaatje laat zien hoe het eruit ziet als je maar een bepaald aantal kolommen opvraagt zoals in opdracht iii.

![Output opdracht 1 - SELECT* FROM jaar2016](https://github.com/ROC-van-Amsterdam-College-Amstelland/MYSQL-BASIC/blob/master/2-Select/taak01/img/output2.jpg)

## Bronnen


[W3 Schools - SQL SELECT Statement](https://www.w3schools.com/sql/sql_select.asp) 