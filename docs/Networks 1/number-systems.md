---
tags:
  - Number Systems
---

# Hoofstuk 5
Bij dit hoofdstuk ga je alles over decimaal, binary en hexadecimaal hebben.

## Binary Number System

### Binary and IPv4 Addresses

- Het **binary** (binair) bestaat uit **1** en **0**, die **bits** worden genoemd.
- Het **decimal** (decimaal) bestaat uit de cijfers **0 tot en met 9**.
- Hosts, servers en netwerkapparatuur gebruiken **binaire adressing** om elkaar te identificeren.
- Een IPv4-adres bestaat uit een reeks van **32 bits**, verdeeld in vier secties die **octets** worden genoemd.
- Elk octet bevat **8 bits** (of 1 byte), gescheiden door een **punt**.
- Voor menselijk gemak wordt deze binaire notatie omgezet naar **dotted decimaal notation**.

### Binary Positional Notation

- **Positional Notation** betekent dat een **cijfer verschillende worden vertegenwoordigt** afhankelijk van de **positie** die het inneemt in de reeks getallen.

De binaire positionele notatie staat hieronder in een tabel hoe deze werkt.

![Binaire Positional Notation](/assets/binaire-positional-notation.png){ width=800px }

### Convert Binary to Decimal
Om een binair getal om te zetten naar decimaal kan je hieronder vinden.

![Binair naar Decimaal](/assets/binair-naar-decimaal.png){ width=800px }

### Decimal to Binary Conversion
Gebruik de binaire positionele tabel om een decimaal getal om te zetten.

![Decimaal naar Binair](/assets/decimal-to-binary.png){ width=800px }

### IPv4 Addresses
Routers en computers kunnen alleen binary verstaan. Maar mensen werken met decimaal. Dus het is belangrijk dat je verstand hebt van de 2 numbering system en hoe ze gebruikt worden in networking.

|192|.|168|.|10|.|10
|-------|-|-------|-|-------|-|-------|
|11000000|.| 10101000|.|00001010|.|00001010

## Hexadecimal Number System

### Hexadecimal and IPv6 Addresses
Om IPv6-adressen te begrijpen, moet je kunnen omzetten tussen hexadecimal (hexadecimaal) en decimaal

- Hexadecimal is een base 16 getallenstelsel dat de cijfers 0 t/m 9 en de letters A t/m F gebruikt.
- Het is gemakkelijker om een waarde uit te drukken als één hexadecimaal cijfer dan als vier binaire bits

Hexadecimaal wordt gebruikt voor IPv6 addresses en MAC addresses

- Een IPv6-adres is 128 bits lang. Elke 4 bits worden vertegenwoordigd door één hexadecimaal getal, wat een totaal van 32 hexadecimale waarden maakt.
- Elke groep van vier hexadecimale tekens wordt een hextet genoemd

### Decimal to Hexadecimal Conversions
Stappen voor omzetting:
- Zet het decimale getal om naar een 8-bit binaire string.
- Verdeel de binaire string in groepen van vier (vanaf rechts)
- Zet elke groep van vier binaire getallen om naar het equivalente hexadecimale cijfer.

### Hexadecimal to Decimal Conversions
Stappen voor omzetting:

- Zet het hexadecimale cijfer om naar een 4-bit binaire string.
- Maak een 8-bit binaire groep en start van de rechterkant.
- Zet de 8-bit binaire groep om naar het equivalente decimale getal.

## Quiz
Elk hoofdstuk heeft een quiz waar je een aantal vragen moet beantwoorden zodat je jezelf kan oefenen of je genoeg kennis hebt voor het hoofdstuk.