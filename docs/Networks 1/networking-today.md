---
tags:
  - Networking Today
---

# Hoofdstuk 1
Bij dit hoofdstuk ga je alles over de moderne technologies van netwerken praten en nog veel meer.

## Network Components

### Host Roles
Elke computer op een netwerk wordt een host of end device genoemd.

**Servers:** Computers met software die informatie (zoals e-mail of webpagina's) leveren aan andere apparaten op het netwerk.

- Email server
- Web server
- File server.

**Clients:** Computers met software die informatie opvragen bij de server.

### Peer-To-Peer
In een Peer-to-Peer network kunnen apparaten zowel client als server zijn voor elkaar. Dit netwerk is alleen aanbevolen voor **heel kleine netwerken**.

| Voordelen | Nadelen |
|-----------|--------------|
| Eenvoudig op te zetten | Geen gecentraliseerde administratie |
| Minder complex | Minder veilig |
| Goedkoper | Niet schaalbaar **(not scalable)** |

### End Devices
Een **end device** is de bron of de bestemming van een bericht dat over het netwerk wordt verzonden.

### Intermediary Network Devices
Een **intermediary device** verbindt de **end devices** met elkaar.

**Voorbeelden:**

- Switches
- Wireless Access Points
- Routers
- Firewalls

**Functies:** Gegevenssignalen regenereren, informatie over paden bijhouden en fouten melden.

### Network Media
Communicatie vindt plaats via een **medium** dat de mogelijkheid biedt voor het transport van berichten.

**Types**

- **Metal Wires (Copper):** Gebruikt elektrische impulsen.
- **Glass or plastic fibers (Fiber-Optic):** Gebruikt lichtpulsen.
- **Wireless transmission:** Gebruikt elektromagnetische golven.

## Network Representations and Topologies

### Network Representations
Symbolen worden gebruikt om netwerkapparaten weer te geven in topology diagrammen.

**Belangrijke termen:**

- Network Interface Card (NIC)
- Physical Port
- Interface

**Opmerking:** Soms worden de termen port en interface door elkaar gehaald.

### Topology Diagrams
**Pysical Topology:** Toont de fysieke locatie van apparaten en de installatie van kabels.

**Logical Topology:** Toont apparaten, poorten en het IP-adresseringsschema.

## Common Types of Networks

### Network Sizes
- **Small Home Networks:** Voor een paar mensen en apparaten.
- **Small Office/Home Office (SOHO):** Voor mensen die thuis of in een klein kantoor werken.
- **Medium to Large Networks:** Voor locaties met honderden of duizenden verbonden apparaten.
- **World Wide Networks:** Verbindt miljoenen apparaten wereldwijd (Internet).

### LANs and WANs
Netwerk infrastructuren variëren sterk in termen van:

- Omvang van het gebied dat wordt bestreken
- Aantal aangesloten gebruikers
- Aantal en soorten beschikbare diensten
- Verantwoordelijkheidsgebied

Twee meest voorkomende types van netwerken:

- **Local Area Network (LAN):** Een netwerkinfrastructuur die een **klein geografisch gebied** is en beheerd wordt door één organisatie.
- **Wide Area Network (WAN):** Verbindt LAN's over **grote geografische gebied**. Wordt beheerd door een Internet Service Provider (ISP).

### The Internet
Een wereldwijde verzameling van verbonden netwerken.

- LANs die aan elkaar verbonden zijn met gebruik van WANs.
- WANs kan kopere draden gebruiken, fiber optic kabels en wireless transmissions.

De internet is niet eigenaar van een persoon of groep.

### Intranets and Extranets
**Intranet:** Een privéverbinding van LAN's en WAN's die alleen toegankelijk is voor leden van een organisatie.

**Extranet:** Biedt veilige toegang tot een deel van het netwerk aan externe partijen (bijv. leveranciers of klanten).

## Internet Connections

### Home and Small Office Connections

**Connecties:**

- **Cable:** Hoge bandbreedte, altijd aan, internet door de kabel tv service providers.
- **DSL:** Hoge bandbreedte, altijd aan, internet verbinding via de telefoonlijn.
- **Cellular:** Internet via het mobiele telefoonnetwerk.
- **Satellite:** Gebruikt voor locaties waar geen andere verbinding mogelijk is.
- **Dial-up telephone:** Goedkoop, lage bandbreedte optie bij gebruik van een modem.

### Business Internet Connections

Verbindingen van bedrijven kunnen de volgende eisen:
- Hogere bandbreedte
- Beheerde Diensten

**Type van connecties:**

- **Dedicated Lease Line:** Een gereserveerd circuit voor verbindingen tussen kantoren.
- **Ethernet WAN:** Breidt LAN-technologie uit naar het WAN.
- **DSL:** Vaak symmetrisch (upload en download zijn even snel).
- **Satellite:** Dit kan een connectie voorzien als er geen bekabelde manier beschikbaar is.

### The Converging Network

Voor converged netwerken, een organisatie moest een aparte kabel voor telefonie, video en data voorzien. Elk van die netwerken moesten een verschillende technologie gebruiken om de signalen door te geven.

Converged Networks kunnen verschillende soorten data (zoals spraak, video en computerdata) over dezelfde infrastructuur kunnen versturen met dezelfde regels en standaarden.

## Reliable Networks

### Network Architecture
Een betrouwbaar netwerk moet voldoen aan vier basisvereisten:

- **Fault Tolerance:** Het netwerk moet blijven werken als er een onderdeel faalt. Dit gebeurt via redundantie en een packet-switched network (in plaats van een circuit-switched network).
- **Scalability:** Een scalable network kan snel groeien en meer gebruikers ondersteunen zonder de prestaties van bestaande diensten te beïnvloeden.
- **Quality of Service (QoS):** Beheert de prioriteit van data. Cruciale data (zoals video of spraak) krijgt voorrang boven minder tijdgevoelige data (zoals e-mail) om haperingen te voorkomen.
- **Network Security:**
  - **Network Infrastructure Security:** Fysieke beveiliging van apparaten.
  - **Information Security:** Bescherming van de data zelf.
  - **Doelen:** Confidentiality, Integrity, en Availability.

## Network Security

### Security Threats
**External Threats:** Viruses, worms, Trojan horses, Spyware, Zero-day attacks, Denial of Service (DoS) attacks, en Identity theft.

**Internal Threats:** Verloren/gestolen apparaten of misbruik door medewerkers.

### Security Solutions
**Basisoplossingen:** Antivirus, antispyware en firewall filtering.

**Geavanceerde oplossingen:** Dedicated firewall systems, Access control lists (ACL), Intrusion prevention systems (IPS), en Virtual private networks (VPN).