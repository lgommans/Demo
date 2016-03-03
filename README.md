# Branching demo

Deze git repository is bedoeld om het git branching model te demonstreren.

## Branching model

Hieronder zullen we ons model toelichten.

### Basis

De master branch is de branch waar men heen pusht. De code in deze branch moet
compilen en geen grote regressies hebben zodat men ervan kan pullen zonder
telkens hun build te moeten fixen. Niet elke lokale commit hoeft dus gepushed
te worden. De versie van de master branch is altijd "de laatste versie," of
"de volgende release".

Wanneer een release wordt gedaan, bijvoorbeeld versie 3, dan wordt van master
af gebranched met een branch genaamd v3.0 die tevens ook als v3.0 is getagged.
Verdere development aan versie 3, zoals bug fixes, worden gedaan op deze branch
en krijgen de tag `v3.0.1`, `v3.0.2`, enz.

### Afwijkende branches

Indien er afwijkende situaties, zoals bij pair programming waar de code
op 2 computers aanwezig moet zijn omdat men wisselt van 'driver' (degene die
typt), wordt een nieuwe branch gemaakt van master met een zelf te bepalen
duidelijke naam.

Een andere dergelijke situatie is een grote wijziging, die pas over enkele
versies uit gaat komen. Bijvoorbeeld als we nu versie 2.0 af hebben en nog 3.0
willen releasen met features X en Y, maar men ondertussen ook wil werken aan
een complete rewrite (die waarschijnlijk als versie 4 of 5 zal uitkomen). In
dat geval zal uiteraard ook een nieuwe branch moeten worden aangemaakt.

### Automatic deployments

Voor automatische deploys is het wellicht handig om een tag genaamd `latest`
bij te houden, een tag die altijd wijst naar de laatste release. Op het moment
dat versie 3 bugfix 8 gereleased is wijst `latest` dus naar dezelfde commit als
de tag `v3.0.8`. Als versie 4 nu uitkomt zal `latest` naar dezelfde commit als
de tag `v4.0` wijzen.

