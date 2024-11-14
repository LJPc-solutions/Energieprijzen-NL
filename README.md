# Stroom- en gasprijzen in Nederland

![Laatste update](https://img.shields.io/badge/laatste%20update-2024--11--15%2000%3A00%20CET-brightgreen)

<a href="https://www.buymeacoffee.com/Lars-" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-orange.png" alt="Buy Me A Coffee" height="60" style="height: 60px !important;width: 217px !important;" ></a>

Deze repository bevat de huidige prijzen van energieleveranciers in Nederland die dynamische prijzen aanbieden. De prijzen worden elk uur automatisch geüpdatet.

## Why Dutch?

This readme is in Dutch (except this part) because the content is based on Dutch data. We cannot imagine that anyone outside the Netherlands would need this data. If you do, please let us know. Even with this Dutch readme, we think
everyone will understand how it works.

## Doel

Het aanbieden van prijsdata van bekende energieleveranciers in Nederland. Deze tool haalt elk uur de actuele energietarieven op van verschillende energieleveranciers die dynamische prijzen aanbieden. Door gebruik te maken van deze tool
krijg je een overzicht van de huidige tarieven en kun je beter inspelen op prijsschommelingen.

## Huidige prijzen

Prijzen van de leveranciers zijn inclusief toeslag en belasting, dus de prijs die je werkelijk betaalt.

### Stroom

Prijzen worden automatisch ieder uur geüpdatet.

 Bedrijf | Prijs per kWh 
---------|---------------
Beursprijs | € 0,110660
All in power | € 0,295799
ANWB Energie | € 0,313949
EasyEnergy | € 0,292399
Energie VanOns | € 0,313949
EnergieZero | € 0,315549
Frank Energie | € 0,283749
Groenestroom Lokaal | € 0,313949
Mijndomein Energie | € 0,313949
NextEnergy | € 0,285449
Tibber | € 0,287329
Vandebron | € 0,287429
Vrij op naam | € 0,285549
ZonderGas | € 0,313949
Zonneplan | € 0,285549


### Gas

Prijzen worden automatisch iedere dag rond 07.00 uur geüpdatet.

 Bedrijf | Prijs per m³ 
---------|--------------
Beursprijs EGSI | € 0,425713
Beursprijs EOD | € 0,426700
All in power | € 1,328243
ANWB Energie | € 1,279663
EasyEnergy | € 0,000000
Energie VanOns | € 1,279663
EnergieZero | € 1,280553
Frank Energie | € 1,301647
Groenestroom Lokaal | € 1,279663
Mijndomein Energie | € 1,279663
NextEnergy | € 1,279553
Vandebron | € 1,327173
Vrij op naam | € 1,300453
ZonderGas | € 1,279663
Zonneplan | € 1,300553


## Automatisering

Door deze repository is het mogelijk om de actuele prijzen in scripts te gebruiken.

**Voorbeeld 1: huidige stroomprijs van ANWB Energie**

```php
<?php
$price = (float)file_get_contents('https://energie.ljpc.nl/stroom/anwb-energie-nu.txt');

```

**Voorbeeld 2: alle stroomprijzen van ANWB Energie vandaag**

```php
<?php
$prices = json_decode(file_get_contents('https://energie.ljpc.nl/stroom/all-in-power-vandaag.json'),true);
foreach ($prices as $price) {
    $dateTime = new \DateTimeImmutable($price['datetime']);
    $price = $price['price'];
    // ...
}
```

## Actualiteit en betrouwbaarheid

Houd er rekening mee dat de informatie in deze tool alleen ter referentie wordt verstrekt. We doen ons best om de gegevens zo nauwkeurig en actueel mogelijk te houden, maar we kunnen de volledige nauwkeurigheid van de gegevens niet
garanderen. Gebruik deze informatie op eigen risico.

## Maatwerk

Geïnteresseerd in maatwerk op basis van deze gegevens of iets anders? Neem dan contact op
via [info@ljpc.nl](mailto:info@ljpc.nl?subject=Energie%20prijzen).

## Doneren

Als we je zojuist een hoop tijd, geld of gedoe bespaard hebben, zouden we het fijn vinden als je zou willen overwegen een
donatie te doen. Alle donaties worden gebruikt om systemen als dit mogelijk te
maken. [Klik hier](https://www.buymeacoffee.com/Lars-) om te doneren.
