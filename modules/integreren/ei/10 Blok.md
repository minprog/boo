# Het twitter-ei!

Schrijf een functie `twitter()` die de oppervlakte van het Twitter-ei berekent. De omtrek van het ei wordt gegeven door: 

$$ \sqrt{x^2+y^2} + \frac{2}{3}\sqrt{x^2+\left(\frac{5}{6}-y \right)^2 } = 1$$

![](TwitterEiCombi.png)

Gooi in totaal 1 miljoen punten en bereken de juiste oppervlakte. Bewaar na elke 1000 punten dat je gooit de schatting van de oppervlakte op dat moment. Als het goed is convergeert je antwoord en zie je dat je een betere schatting krijgt naarmate je meer punten gooit.

Je programma moet vier dingen doen:

- Er moet een functie `twitter()` zijn die met hulp van `return` de oppervlakte geeft

- De oppervlakte moet ook op het scherm geprint worden, op 2 decimalen nauwkeurig:

        De oppervlakte van het Twitter ei is x.xx

- Er moet een plot verschijnen van de distributie van de goede en slechte punten (zoals in de rechterplot hierboven)

- Geef ook in de grafiek aan wat de oppervlakte is, eveneens op 2 decimalen nauwkeurig
