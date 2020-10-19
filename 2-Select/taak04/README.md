# MYSQL-BASIC-TAAK-04

## SQL Functies & alias

- [MYSQL-BASIC-TAAK-04](#mysql-basic-taak-04)
  - [SQL-Functies & alias](#sql-functies--alias)
  - [Uitleg](#uitleg)
    - [Functie-overzicht](#functies-overzicht)
    - [Gebruik van functies met AVG() en SUM() als voorbeeld](#gebruik-van-functies-met-avg-en-sum-als-voorbeeld)
      - [Vertaling voorbeeld](#vertaling-voorbeeld)
      - [Syntax](#syntax)
    - [Round()](#round)
    - [Count()](#count)
    - [Max()](#max)
    - [Min()](#min)
  - [Leerdoelen](#leerdoelen)
  - [Opdracht](#opdracht)
  - [Eindresultaat](#eindresultaat)
  - [Bronnen](#bronnen)

## Uitleg

Bij de vorige taak kon je al veel vragen over de gegevens in de database beantwoorden. En, als je zou willen, deze ook in een applicatie tonen aan gebruikers. Toch zijn er misschien nog meer vragen die je na het werken met de `fifa2018`-database zou willen beantwoorden. Wat verdienen de spelers bij Ajax in totaal per maand? Hoeveel zijn ze gemiddeld waard volgens de FIFA? Of welke club betaalt het beste? Of welke speler verdient het meest?

Nu kun je natuurlijk wat gegevens ophalen en daarna een berekening uitvoeren met bijvoorbeeld PHP, maar SQL heeft zelf ook allemaal functies om berekeningen te doen. Deze worden uitgevoerd op de databaseserver. Vaak is het handig om de gegevens die je ophaalt uit de database zo terug te krijgen dat ze meteen binnen je applicatie getoond kunnen worden.

### Functie-overzicht

SQL kent hiervoor een aantal handige functies:
Functie | Doel
--- | ---
Count() | Telt het aantal rijen dat een SQL query teruggeeft
AVG() | Geeft een gemiddelde van de inhoud van een kolom met getallen
SUM() | Telt de inhoud van een kolom met getallen bij elkaar op
Min() | Geeft de kleinste waarde terug in een kolom
Max() | Geeft de grootste waarde terug in een kolom
ROUND() | Geeft een afgerond getal terug

### Gebruik van functies met AVG() en SUM() als voorbeeld

Hoe maak je nu gebruik van deze functies? Bijna op dezelfde manier zoals je een functie in Javascript of PHP gebruikt. Stel dat we van de `fifa2018` het gemiddelde inkomen van alle spelers bij Ajax willen weten dan kunnen we de onderstaande query schrijven:
```SQL
SELECT AVG(wage) FROM players WHERE club = "Ajax";
```
De WHERE-clausule blijft dus hetzelfde, die geeft alleen maar aan dat je alleen de rijen wilt hebben waarvan de waarde "Ajax" is in de `club`-kolom. 

De `AVG()` functie vraagt om één argument, namelijk de naam van de kolom waarop je de functie wilt uitvoeren, in dit geval de `wage` kolom.

Wat je dan terugkrijgt, als je deze query uitvoert, ziet er als volgt uit:

AVG(wage) | 
--- |
9034.4823 |

Het gemiddelde inkomen van de spelers bij Ajax in FIFA2018 ligt dus rond de 9000 euro. 

Wat je misschien opvalt is dat de kolom naam die je terugkrijgt niet `wage` is, maar letterlijk hetzelfde is als wat je invult na het SELECT- keyword: `AVG(wage)`. Dit is prima als je snel even iets wilt opzoeken in een database, maar is niet zo handig als je later met de gegevens iets wilt doen met PHP. Gelukkig heeft SQL een manier om de kolom namen die je terugkrijgt te veranderen in wat je zelf wilt. Dit doe je door gebruik te maken van een *alias*. Het keyword dat hier bij hoort is `AS`, bijvoorbeeld:

```SQL
SELECT AVG(wage) AS avg_wage FROM players WHERE club = "Ajax";
```
Wat je terugkrijg ziet er als volgt uit:

avg_wage | 
--- |
9034.4823 |

Dit is al een stuk duidelijker wanneer je de gegevens gaat gebruiken binnen een applicatie. 
> LET OP: avg_wage is een naam die je zelf moet bedenken, je kan ook `AS gemiddelde` gebruiken of `AS ajax_spelers_loon_gemiddeld`, zolang je maar een underscore (`_`) gebruikt i.p.v. spaties en het een naam is die duidelijk aangeeft wat de informatie is.

#### Vertaling voorbeeld

Nog even voor de duidelijkheid: wat vraag je precies van de databaseserver in gewone taal?

Taal | keyword | functie met kolom | keyword met eigen_naam |  keyword met tabel |Where clausule met conditie|
----|---------|----------|---------|---------- | ---- | --- | --- | --- |
SQL | `SELECT` | ` AVG(`wage`)` | `AS` avg_wage | `FROM` players |  `WHERE` club = "Ajax" | rank | = | 1 |
Vrij vertaald: | Geef mij | het gemiddelde van de kolom wage | als avg_wage | uit de players tabel | waar de waarde van de kolom club gelijk is aan "Ajax"

#### Syntax

De syntax is als volgt:
```SQL
SELECT functie(kolom) AS eigen_naam FROM tabel_naam WHERE conditie;
```
Nu nog één punt waar je misschien al over hebt nagedacht: wat als je nu meer kolommen terug wilt krijgen? Dit werkt hetzelfde als wanneer je dat doet met een gewone `SELECT kolom1, kolom2, ... FROM tabel` waarbij je de kolommen scheidt met een `,`

Dus stel, je wilt de volgende gegevens hebben: het totale inkomen én de gemiddelde waarde van de spelers van Ajax. 

```SQL
SELECT club, SUM(wage) AS sum_wage, AVG(value) AS avg_value FROM players WHERE club = "Ajax";
```
Wat je dan terugkrijgt is:
club | sum_wage | avg_value | 
--- | --- | --- |
Ajax | 262000 | 47098275.862068966

### Round()

Nu is dit resultaat al iets wat je gemakkelijk kan gebruiken in een applicatie. Alleen de avg_value is wel een heel onhandig getal met zoveel cijfers achter de komma. Je kunt in PHP dit getal afronden voor je het toont aan de gebruiker, maar je kan dit natuurlijk ook doen in je SQL-statement. Je gebruikt hiervoor de `ROUND()`-functie.

Dus als laatste toevoeging: in plaats van `AVG(value)` maken we er `ROUND(AVG(value))` van. 

Wat je dan terug krijgt is:

club | sum_wage | avg_value | 
--- | --- | --- |
Ajax | 262000 | 47098276

> LET OP: we vragen naar de kolom `Club` en krijgen de waarde "Ajax" terug omdat alle waardes in deze kolom "Ajax" zijn. Dit is zo omdat we in de WHERE-clausule een conditie hebben staan die alleen "Ajax"-waarden teruggeeft. Maar stel dat je in plaats van `Club` vraagt om de kolom `Name` dan krijg je de naam terug van één van de spelers die bij Ajax speelt:  

name | sum_wage | avg_value | 
--- | --- | --- |
K. Huntelaar | 262000 | 47098276

> Dat resultaat komt vreemd over voor ons want het is niet zo dat Huntelaar 262K verdient of een gemiddelde value heeft. Maar SQL kijkt niet of het resultaat logisch is, maar geeft precies terug waar *jij* om vraagt. Omdat je maar één rij terugkrijgt als je functies gebruikt zoals `AVG()`, wordt er maar één naam getoond (de eerste naam die SQL tegenkomt in de `name` kolom), terwijl wij weten dat het gemiddelde berekend is van *alle* spelers van Ajax. **Let dus goed op of het resultaat dat je terugkrijgt wel overeenkomt met je verwachtingen.**

Dan hebben we nog een aantal functies niet behandeld die wel handig kunnen zijn. Hieronder staan voorbeeld SQL-statements met het resultaat:

### Count()
```SQL
SELECT Count(*) As ajax_spelers_aantal FROM players WHERE club = "Ajax";
```
geeft:
ajax_spelers_aantal | 
--- |
29 | 
> LETOP: Als argument wordt bij de `Count()`-functie de waarde `*` meegegeven, maar je zou hetzelfde resultaat krijgen als in plaats daarvan een kolomnaam invult. Het gaat immers om het aantal rijen dat je terugkrijgt van je SQL-query.

### Max()
```SQL
SELECT Max(wage) As hoogste_loon_ajax_speler FROM players WHERE club = "Ajax";
```
geeft:
hoogste_loon_ajax_speler | 
--- |
17000 | 

### Min()
```SQL
SELECT Min(value) As ajax_speler_minste_waarde FROM players WHERE club = "Ajax";
```
geeft:
ajax_speler_minste_waarde | 
--- |
950000 |


## Leerdoelen

1. Ik kan de `Count()`-functie gebruiken om het aantal rijen te weten te komen die een query teruggeeft.
2. Ik kan de `SUM()`-functie gebruiken om getallen in een kolom op te tellen
3. Ik kan de `AVG()`-functie gebruiken om het gemiddelde van de getallen in een kolom te berekenen.
4. Ik kan de `ROUND()`-functie gebruiken om een getal af te ronden
5. Ik kan de `Max()` en `Min()` functies gebruiken om de grootste of de kleinste waarde in een kolom op te vragen.



## Opdracht

1. We maken weer gebruik van de `Fifa2018`- database. Als je deze nog niet hebt staan in PhpMyAdmin, maak dan een nieuwe database aan (met een duidelijke naam, bv. `mod-mysql-basic-fifa2018`) en importeer het `.sql`-bestand in de `db-export`-map van deze taak.
2. Open het SQL-tabblad in PhpMyAdmin en schrijf SQL-queries om de gevraagde gegevens te tonen:  
   **(vergeet niet na elke beantwoorde vraag de SQL-statement die je geschreven hebt te copy/pasten in `antwoorden.sql` en een bookmark met een logisch genaamd label aan te maken)**

Schrijf voor de onderstaande vragen een SQL-query die de informatie teruggeeft op de manier waarop staat aangeven.

1. Hoe hoog is het hoogste loon van een FC Utrecht-speler? Gebruik een alias met de naam `hoogste_loon_speler_fc_utrecht`.
2. Wat is het afgeronde gemiddelde inkomen van *alle* spelers? Gebruik een alias en verzin zelf een logische naam.
3. Wat is de som van het loon van alle spelers van FC Groningen? Gebruik een alias.
4. Hoeveel spelers hebben Manchester City en Manchester United samen? Gebruik een alias.
5. Wat is het gemiddelde inkomen van de spelers met een Nederlandse nationaliteit? Gebruik een alias.
6. Hoeveel verdient een speler gemiddeld als hij onder de 20 jaar oud is? Gebruik een alias.
7. En hoeveel verdient een speler gemiddeld als hij ouder is dan 20? Gebruik een alias.
8. Hoeveel zijn de spelers in totaal waard bij Chelsea? Gebruik een alias.
9. Wat is de afgeronde gemiddelde leeftijd van *alle* spelers? Gebruik een alias.
10. Toon de clubnaam, het totale inkomen en de afgeronde gemiddelde waarde van de spelers die spelen voor Liverpool. Gebruik aliassen.


## Eindresultaat

 

## Bronnen

[W3 Schools - SQL  MIN() and MAX() Functions](https://www.w3schools.com/sql/sql_min_max.asp)  
[W3 Schools - SQL COUNTR(), AVG() and SUM() Functions](https://www.w3schools.com/sql/sql_count_avg_sum.asp)  
[W3 Schools - MySQL ROUND() Function](https://www.w3schools.com/sqL/func_mysql_round.asp)  
[W3 Schools - aliases](https://www.w3schools.com/sql/sql_alias.asp)  

