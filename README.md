# Stroom- en gasprijzen in Nederland

![Laatste update](https://img.shields.io/badge/laatste%20update-2024--10--15%2023%3A00%20CET-brightgreen)

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
Beursprijs | € 0,042130
All in power | € 0,212877
ANWB Energie | € 0,231027
EasyEnergy | € 0,209477
Energie VanOns | € 0,231027
EnergieZero | € 0,232627
Frank Energie | € 0,208027
Groenestroom Lokaal | € 0,231027
Mijndomein Energie | € 0,231027
NextEnergy | € 0,202527
Tibber | € 0,204407
Vandebron | € 0,204507
Vrij op naam | € 0,202627
ZonderGas | € 0,231027
Zonneplan | € 0,202627


### Gas

Prijzen worden automatisch iedere dag rond 07.00 uur geüpdatet.

 Bedrijf | Prijs per m³ 
---------|--------------
Beursprijs EGSI | € 0,390514
Beursprijs EOD | € 0,390060
All in power | € 1,285652
ANWB Energie | € 1,237072
EasyEnergy | € 1,306011
Energie VanOns | € 1,237072
EnergieZero | € 1,237962
Frank Energie | € 1,257273
Groenestroom Lokaal | € 1,237072
Mijndomein Energie | € 1,237072
NextEnergy | € 1,236962
Vandebron | € 1,284582
Vrij op naam | € 1,257862
ZonderGas | € 1,237072
Zonneplan | € 1,257962


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
