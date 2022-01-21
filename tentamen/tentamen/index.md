# Tentamen

21 januari 2021  9:00–12:00

> Regels voor het tentamen:
> 
> - De opgaven worden om 9:00 uur per e-mail vrijgegeven.
> - Je moet je oplossingen uiterlijk om 11:59 ingeleverd hebben via deze website. Geen mails.
> - Er zijn twee inleverplekken onderaan de pagina, één voor C en één voor Python.
> - Neem contact op met Martijn via <https://uva-live.zoom.us/j/86091575813>. Inhoudelijke vragen kunnen niet beantwoord worden maar als er onduidelijkheden of fouten zijn heeft het wellicht zin om even te spreken. Het kan zijn dat je een tijdje moet wachten als er koffie gehaald wordt of als iemand anders aan de beurt is!

Hieronder vind je vijf opdrachten. Het doel van het tentamen is te demonstreren dat je zelfstandig een oplossing voor een probleem kunt ontwikkelen, en daarbij gebruik kunt maken van de basistechnieken van programmeren, zoals bijvoorbeeld de verschillende soorten loops, if-else-constructies, enzovoort.

Je hoeft niet alle opdrachten goed te hebben om het tentamen te halen. Je moet wel genoeg werkende code produceren van enige complexiteit om zonder twijfel te kunnen concluderen dat je de basis voldoende beheerst. Elke opdracht geeft een kans om dit voor een deel te doen.

Op dit moment in de cursus zou je alle opdrachten goed moeten kunnen maken zonder begeleiding. Door de tijdsbeperking kan het best zijn dat je een opdracht niet kunt maken! Dat hoeft geen probleem te zijn, als maar overtuigend zichtbaar is dat je het programmeren beheerst.

Als bronnen mag je gebruiken:

1. de lecture notes (en de rest van deze website),
2. de CS50 Manual waarin allerlei nuttige C-functies genoemd staan,
3. en je eigen uitwerkingen van eerdere opdrachten.

En dan nog wat basisregels:

- In je uitwerking mag je alleen gebruik maken van de library-functies die ook in de CS50 Manual staan. Als je Python gebruikt mag je géén libraries importeren (ook geen `math`), behalve als aangegeven in de opdracht.

- Vanwege het doel van het tentamen heeft het geen zin om alleen het juiste antwoord uit te printen zodat `check50` tevreden is (het zogenaamde "hardcoden"). Je moet je programmeerkunst demonstreren.

- De input van gebruikers hoeft alleen gecontroleerd te worden als dit duidelijk in de opdracht vermeld staat.

- (Ook) voor het oefententamen is het essentieel dat je dit eerst doet zonder gebruik van internet of hulp van anderen. Alleen zo begrijp je waar je zelf nog vastloopt.

- In Python kun je losse letters of strings printen zonder newline door gebruik te maken van deze constructie:

    print(letter, end='')

Succes!

## 1. Dobbelsteen

Een dobbelstenenmaker wil zich ervan verzekeren dat haar dobbelstenen eerlijk zijn. Om dit te testen gooit ze heel vaak met dezelfde dobbelsteen en houdt ze voor elk aantal ogen (1-6) bij hoevaak ze gegooid zijn. Wij schrijven een programma om te helpen.

Schrijf een programma dat de gebruiker herhaaldelijk vraagt welk aantal ogen geggooid is. Als de gebruiker iets anders dan de nummers 1, 2, 3, 4, 5 of 6 invult is het klaar en print je het aantal worpen voor elk aantal.

    $ ./dobbelsteen
    Hoeveel heb je gegooid? 1
    Hoeveel heb je gegooid? 3
    Hoeveel heb je gegooid? 5
    Hoeveel heb je gegooid? 5
    Hoeveel heb je gegooid? 2
    Hoeveel heb je gegooid? 6
    Hoeveel heb je gegooid? 3
    Hoeveel heb je gegooid? 1
    Hoeveel heb je gegooid? 2
    Hoeveel heb je gegooid? 3
    Hoeveel heb je gegooid? 6
    Hoeveel heb je gegooid? 5
    Hoeveel heb je gegooid? 3
    Hoeveel heb je gegooid? 0
    Totalen:
    1: 2
    2: 2
    3: 4
    4: 0
    5: 3
    6: 3

    $ ./dobbelsteen
    Hoeveel heb je gegooid? 0
    Je hebt niet gegooid.

    $ ./dobbelsteen
    Hoeveel heb je gegooid? 100
    Je hebt niet gegooid.

    $ ./dobbelsteen
    Hoeveel heb je gegooid? 1
    Hoeveel heb je gegooid? 0
    Totalen:
    1: 1
    2: 0
    3: 0
    4: 0
    5: 0
    6: 0

## 2. Som van absoluten

Gegeven een reeks getallen zoals [2, -5, -3, 1] kun je de absolute som definiëren als de som van de absolute waarden van de getallen. De absolute waarde is altijd positief, en de som dus ook. Schrijf een programma dat een reeks getallen als command-line arguments accepteert en de absolute som van de getallen print. Als geen getallen worden opgegeven moet exact onderstaande foutmelding worden geprint.

    ./absoluut 2 -5 -3 1
    11
    ./absoluut 0
    0
    ./absoluut
    Usage: ./absoluut num...

Importeren van `sys.argv` is natuurlijk prima hier.

## 3. Samenvatten

Lange teksten lezen is vervelend. Schrijf een programma dat teksten inkort door van elk woord alleen de eerste en laatste letter te behouden. Alleen letters en cijfers horen tot "woorden". Alle andere tekens zoals spaties en komma's horen hier niet bij, en die moeten gewoon allemaal geprint worden.

Om dit te doen loop je door de string heen, letter voor letter. Gebruik een boolean variabele die representeert of je nu "in een woord" bent. Daarmee kun je beslissen welke letters en andere tekens geprint moeten worden. Je kunt de de functie `isalnum` uit `ctype.h` gebruiken om te kijken of iets een letter of cijfer is. Het algoritme in pseudocode:

- start met woord=false
- vraag invoer
- check elk teken uit de ingevoerde string, drie opties:
    1. als isalnum(teken) en woord=false: 
            -> dan woord=true en print teken
    2. als isalnum(teken) en woord=true en ook nog
         (dit is laatste teken van string of isalnum(volgende teken)):
            -> dan woord=false en print teken
    3. als geen letter/cijfer:
            -> dan woord=false en print teken
- print newline

En hier twee voorbeelden:

    $ ./samenvatten
    Tekst: Nederlanders worden steeds ouder, vooral doordat ze na hun 65ste
    langer in leven blijven.
    Ns wn ss or, vl dt ze na hn 6e lr in ln bn.

    $ ./samenvatten
    Tekst: Verloren! Zaterdag 5 september. Gouden armband met papa erin.
    Vn! Zg 5 sr. Gn ad mt pa en.

## 4. Splitsen

Schrijf een programma dat gegeven een string eerst de letters op de oneven posities print, en dan de letters op de even posities.

    ./splits
    boodschap: hvealkea nftiijen!e!
    hele fijne
    vakantie!!

Het aantal tekens in de string moet ook *even* zijn om deze goed te kunnen opdelen. Als het aantal letters oneven is, vraag dan opnieuw:

    ./splits
    boodschap: twhaes  ghreirnec h
    boodschap: vhreite satl ?
    vriest
    het al?

## 5. Arrays

Neem een vierkante array van `bool`s:

    bool data[][4] =  {
        {true, true, true, true},
        {true, false, false, true},
        {true, false, false, true},
        {true, true, true, true}
    };
    int DATA_SIZE = 4;

De waarde op de derde regel, laatste kolom kun je bijvoorbeeld zo opvragen: `data[2][3]`. Eerst de regel en dan de kolom dus.

Schrijf een programma `arrays.c` dat door de hele array heen gaat en alle waarden "inverteert": true wordt false en false wordt true. De waarden van de array moet in deze stap dus aangepast worden.

Zorg dat de aangepaste array daarna als volgt wordt uitgeprint, waarbij alle `true` een `X` is en alle `false` een `.`:

    ....
    .XX.
    .XX.
    ....

Je kunt de constante `DATA_SIZE` gebruiken voor de hoogte en breedte van de array.

## Inleveren

Zorg dat je vóór je inlevert alle opdrachten zorgvuldig hebt gecontroleerd met **alle** voorbeelden. Zorg dat je de juiste opdracht op de juiste plek inlevert, anders wordt er automatisch afgekeurd.
