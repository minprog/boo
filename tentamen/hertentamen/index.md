# Hertentamen Basis Objectgeorienteerd Programmeren (INF4ALL)

1 april 2022  12:30–15:30, op locatie UvA


## Regels

- Je mag tot uiterlijk 30 minuten na de begintijd starten.
- Je moet minimaal tot 30 minuten na de begintijd in de zaal blijven.
- Leg je collegekaart klaar op tafel (of een andere ID met foto).
- Stilte in de zaal.
- Er is geen pauze, overdrijf niet met drinken, toiletbezoek op verzoek.
- Klaar is klaar, dan kun je inleveren en weggaan.
- Vóór inleveren steek je je hand op, de surveillant komt controleren voordat je inlevert.
- Je mag alleen werken in de CS50 IDE via https://ide.cs50.io/

## Beoordeling

Hieronder vind je vijf opdrachten. Het doel van het tentamen is te demonstreren dat je zelfstandig een oplossing voor een probleem kunt ontwikkelen, en daarbij gebruik kunt maken van de basistechnieken van programmeren, zoals bijvoorbeeld de verschillende soorten loops, if-else-constructies, enzovoort.

Je hoeft niet alle opdrachten goed te hebben om het tentamen te halen. Je moet wel genoeg werkende code produceren van enige complexiteit om zonder twijfel te kunnen concluderen dat je de basis voldoende beheerst. Elke opdracht geeft een kans om dit voor een deel te doen.

De input van gebruikers hoeft alleen gecontroleerd te worden als dit duidelijk in de opdracht vermeld staat.

## Hulpbronnen

Als bron mag je je eigen uitwerkingen van eerdere opdrachten gebruiken.

In je uitwerking mag je alleen gebruik maken van de library-functies die standaard in de CS50 Manual staan. Neem geen shortcuts.

Vanwege het doel van het tentamen heeft het geen zin om alleen het juiste antwoord uit te printen zodat check50 tevreden is (het zogenaamde "hardcoden").



## 1. Collatz

Schrijf een programma `collatz.c` dat een collatz-reeks uitprint. De collatz-reeks van een bepaald getal telt uiteindelijk altijd terug tot het getal 1.

Hiervoor moet je elke stap één regel toepassen:

-   Als het getal **even** is moet het gedeeld worden door 2.
-   Als het getal **oneven** is moet het vermenigvuldigd worden met 3, 
    en daarna moet er 1 bij opgeteld worden.

De collatz-reeksen werken helemaal met gehele getallen, dus integers.

Het programma moet als volgt werken:

    $ ./collatz
    Geef een positief geheel getal: 3
    Stap: 1     Getal: 10
    Stap: 2     Getal: 5
    Stap: 3     Getal: 16
    Stap: 4     Getal: 8
    Stap: 5     Getal: 4
    Stap: 6     Getal: 2
    Stap: 7     Getal: 1

    $ ./collatz
    Geef een positief geheel getal: 16
    Stap: 1     Getal: 8
    Stap: 2     Getal: 4
    Stap: 3     Getal: 2
    Stap: 4     Getal: 1

Tip: een **even** getal is deelbaar door 2. Dus getal % 2 is gelijk aan 0.


## 2. Makelaar

De waarde van een huis in een bepaalde wijk is afhankelijk van het aantal vierkante meters. Bovendien maken het aantal badkamers en slaapkamers ook uit voor de prijs.

- Voor wijk 1 is de vierkantemeterprijs voor een woning 5000,-, elke slaapkamer voegt 20000,- euro toe aan de prijs en als de woning meer dan 1 badkamer heeft dan komt er 2% bovenop de totale prijs (vermenigvuldig met 1.02).
- Voor wijk 2 is de vierkantemeterprijs voor een woning 6000,-, elke slaapkamer voegt 10000,- euro toe aan de prijs en het aantal badkamers maakt niet uit.

Schrijf een programma dat de prijs van een woning berekent.

    $ ./makelaar
    Hoeveel vierkante meters heeft de woning? 55
    Hoeveel slaapkamers heeft de woning? 1
    Hoeveel badkamers heeft de woning? 1
    In welke wijk ligt de woning? 1
    De waarde van het huis is EUR 295000,-

    $ ./makelaar
    Hoeveel vierkante meters heeft de woning? 150
    Hoeveel slaapkamers heeft de woning? 3
    Hoeveel badkamers heeft de woning? 3
    In welke wijk ligt de woning? 1
    De waarde van het huis is EUR 826200,-

    $ ./makelaar
    Hoeveel vierkante meters heeft de woning? 150
    Hoeveel slaapkamers heeft de woning? 3
    Hoeveel badkamers heeft de woning? 3
    In welke wijk ligt de woning? 2
    De waarde van het huis is EUR 930000,-

Het bedrag moet precies zo geprint worden als hierboven: een getal bestaande uit een aantal cijfers en dan een komma en een streepje er direct achter.



## 3. Morse

Bekijk de onderstaande tabel met morse codes voor de cijfers:

    1: .----
    2: ..---
    3: ...--
    4: ....-
    5: .....
    6: -....
    7: --...
    8: ---..
    9: ----.
    0: -----

Schrijf een programm dat een willekeurig geheel getal kan omzetten naar morse code.

Je moet de functie `get_string()` gebruiken om invoer te vragen, zodat je de cijfers stap voor stap kunt doorlopen.

     $ ./morse
     Getal: 156
     .---- ..... -....

     $ ./morse
     Getal: 92316
     ----. ..--- ...-- .---- -....

## 4. Kortingsactie

Schrijf een programma dat de totale besparing berekent bij een kortingsactie voor avocado's in de supermarkt. De normale prijs en het aantal avocado's in de actie worden meegegeven als *command-line arguments*.

    $ ./korting 3.35 2
    Elke avocado kost: 3.35
    Korting! 2 avocado's voor de prijs van 1

Je kunt bovenstaande al implementeren voordat je verder gaat. Maar het is nog niet het einde van de opgave!

Schrijf in je programma een loop die om input vraagt. Hierin geeft de gebruiker op *hoeveel avocado's zij willen aanschaffen*. Het programma berekent dan de totale besparing op de prijs. Doorgaand op bovenstaande voorbeeld krijg je dan:

    $ ./korting 3.35 2
    Elke avocado kost: 3.35
    Korting! 2 avocado's voor de prijs van 1
    Hoeveel avocado's? 4
    Besparing voor 4 avocado's is: 6.70

Printen van een float met 2 cijfers achter de komma gaat zo: %.2f

En ook nu is het programma nog niet klaar. Het moet namelijk meermaals om het aantal avocado's vragen en de berekening doen, totdat de gebruiker het aantal van 0 invoert:

    $ ./korting 3.35 2
    Elke avocado kost: 3.35
    Korting! 2 avocado's voor de prijs van 1
    Hoeveel avocado's? 4
    Besparing voor 4 avocado's is: 6.70
    Hoeveel avocado's? 0
    $                                    <--- programma stopt

Dan nog een paar voorbeelden:

    $ ./korting 2.35 3
    Elke avocado kost: 2.35
    Korting! 3 avocado's voor de prijs van 2
    Hoeveel avocado's? 2
    Besparing voor 2 avocado's is: 0.00
    Hoeveel avocado's? 3
    Besparing voor 3 avocado's is: 2.35
    Hoeveel avocado's? 7   
    Besparing voor 7 avocado's is: 4.70
    Hoeveel avocado's? 0
    $                                    <--- programma stopt

## 5. Alfabetisch

Schrijf een programma dat test of een string op alfabetische volgorde staat. Je mag aannemen dat de gebruiker alleen maar alfabetische karakters invult.

Begin met een tekst die alléén hoofdletters bestaat:

    $ ./alfa
    Tekst: ABDEUW
    Deze tekst staat op alfabetische volgorde.

    $ ./alfa
    Tekst: ABEDUW
    Deze tekst staat niet op alfabetische volgorde.

Zorg dat spaties worden genegeerd:

    $ ./alfa
    Tekst: ABD EUW
    Deze tekst staat op alfabetische volgorde.

    $ ./alfa
    Tekst: ABE DUW
    Deze tekst staat niet op alfabetische volgorde.

Zorg dat het werkt ongeacht kleine- of hoofdletters:

    $ ./alfa
    Tekst: AbD euw
    Deze tekst staat op alfabetische volgorde.

    $ ./alfa
    Tekst: Abe Duw
    Deze tekst staat niet op alfabetische volgorde.
