---
quiz:
  enabled: true
  auto_number: false
  show_correct: true
  auto_submit: false
  disable_after_submit: true
  shuffle_answers: true
  show_progress: true
  language: en
  
tags:
  - Networking Today
---

# Hoofdstuk 1


```Dit is heel de blok```
`Dit is een klein beetje`
**
*

## Network Components

### Host Roles
Elke computer op een netwerk wordt een **host of een end device** genoemd.

**Servers** zijn computers die informatie aanbieden naar de end devices.

- Email servers
- Web servers
- File servers

**Clients zijn computers die requests versturen naar de server om informatie te verkrijgen.**

- Web pagina van de web server
- Email van een email server.

![Host Roles](/assets/host-roles.png){ width=1000px }

| Server Type | Omschrijving |
|-----------|--------------|
| Email | Email server runt email server software. Clients gebruiken client software om toegang te krijgen naar mail. |
| Web | Web server runt web server software. Clients gebruiken browser software om toegang te krijgen naar de webpagina. |
| File | File server slaagt corporate en user bestanden. De client devices hebben toegang tot die bestanden. |

### Peer-to-Peer
Het is mogelijk om je **device een client en een server te hebben in een Peer-to-Peer Netwerk**. Deze type van netwerk design is alleen aanbevolen voor **heel kleine netwerken**.

![Peer-to-Peer](/assets/peer-to-peer.png){ width=1000px }

| Voordelen | Nadelen |
|-----------|--------------|
| Makkelijk om op te zetten | Geen centrale administratie. |
| Minder complex | Niet zo veilig. |
| Lagere kosten | Niet schaalbaar. |
| Gebruikt voor simpele taken: bestanden overschrijven en delen van printers | Slechtere performance. |

### End Devices
Een end device is waar het bericht **vandaan** komt of van waar het **verzonden** wordt. 

### Intermediary Network Devices
Een intermediary device zorgt voor de verbinding met de end devices. Voorbeelden inclusief switches, wireless access points, routers en firewalls.

**Management of data** dat door je netwerk stroomt is ook de rol van een intermediary device.

- Regenereren en opnieuw verzenden van data signals.
- Informatie bijhouden over welke paden er in het netwerk bestaan.
- Andere apparaten op de hoogte brengen van fouten en communicatie storingen.

![Peer-to-Peer](/assets/intermediary-network-devices.png){ width=1000px }

### Network Media
Communicatie via een netwerk **verloopt via een medium** waarmee een bericht van bron naar bestemming kan worden verzonden.

![Network Media](/assets/network-media.png){ width=1000px }

| Media Types | Omschrijving |
|-----------|--------------|
| Metalen draden in kabels | Gebruikt elektrische pulsen. |
| Glas- of kuntstofvezels in kabels (glasvezelkabel) | Maakt gebruik van lichtpulsen. |
| Draadloze transmissie | Maakt gebruik van modulation van specifieke frequenties van elektromagnetische golven. |

## Network Representations and Topologies

### Network Representations
**Netwerkdiagrammen, vaak topologiediagrammen genoemd**, gebruiken symbolen om apparaten binnen het netwerk weer te geven

Belangrijke termen om te weten:

- Network Interface Card (NIC)
- Physical Port
- Interface

**Opmerking:** Vaak worden de termen port en interface door elkaar gebruikt.

### Topolgy Diagrams
**Physical topology** diagram illustreerdt de fysieke **locatie** van tussenliggende apparaten en kabels installaties.

![Physical Topology](/assets/physical-topology.png){ width=1000px }

**Logicol Topology** diagram illustreerdt **devices, ports, en de addressing** schema van het netwerk.

![Logical Topology](/assets/logical-topology.png){ width=1000px }

## Common Types of Networks

### Networks of Many Sizes
- **Small Home Networks:** Verbindt een paar computers met elkaar en met het internet.
- **Small Office/Home Office:** Maakt het mogelijk om een computer thuis of op een extern kantoor verbinding te laten maken met een bedrijfsnetwerk.
- **Medium to Large Networks:** Veel locaties met honderden of duizenden onderling verbonden computers.
- **World Wide Networks:** Verbindt honderden miljoenen computers wereldwijd, zoals het internet.

### LANs and WANs
Netwerkinfrastructuren variëren sterk in termen van:

- Omvang van het gebied dat wordt bestreken.
- Aantal aangesloten gebruikers.
- Aantal en soorten beschikbare diensten.
- Verantwoordelijkheidsgebied

2 meest voorkomende types van netwerken:

- **Local Area Network (LAN)**
- **Wide Area Network (WAN)**

![LANs and WANs](/assets/lans-and-wans.png){ width=800px }

Een LAN is een netwerk infrastructuur die zich uitstrekt over een **klein geografisch gebied**.

![LAN](/assets/lan.png){ width=500px }


Een WAN is een netwerk infrastructuur die zich uitstrekt over een **groot geografisch gebied**.

![WAN](/assets/wan.png){ width=500px }

| LAN | WAN |
|-----------|--------------|
| Verbind eindapparaten in een beperkt gebied met elkaar. | LAN's over grote geografische gebieden met elkaar verbinden. |
| Beheerd door één enkele organisatie of persoon. | Wordt beheerd door een of meer service providers. |
| Zorgt voor hoge snelheid bandbreedte naar interne apparaten. | Zorgt voor langzamere verbindingen tussen LAN's. |

### The Internet
De internet is een **wereldwijde verzameling van onderling verbonden LAN's en WAN's**.

- LAN's zijn met elkaar verbonden via WAN's
-  WAN's kunnen gebruik maken van kopere draden, glasvezel kabels en draadloze transmissies.

Het internet is **geen eigendom van een individu of groep**. De volgende groepen zijn opgericht om de structuur van het internet te helpen handhaven.

- IETF
- ICANN
- IAB

### Intranets and Extranets

Een intranet is een privé verzameling van LANs en WANs binnen een organisatie die alleen toegankelijk is voor leden van de organisatie of andere met autorisatie.

Een organisatie kan een extranet gebruiken om veilige toegang tot haar netwerk te bieden aan personen die voor een andere organisatie werken en toegang nodig hebben tot gegevens op haar netwerk.

## Internet Connections

### Internet Access Technologies
Er zijn veel manieren om gebruikers en organisaties te verbinden met het internet:

- Populaire diensten voor thuisgebruikers en kleine kantoren zijn onder meer breedbandkabel, breedband digitale abonneelijnen (DSL), draadloze WAN's en mobiele diensten.
- Organisaties hebben snellere verbindingen nodig om IP-telefoons, videoconferenties en datacenteropslag te ondersteunen.
- Interconnecties van business-class worden meestal geleverd door serviceproviders (SP) en kunnen het volgende omvatten:  business DSL, huurlijnen en Metro Ethernet.

### Home and Small Office Internet Connections


| Connectie | Omschrijving |
|-----------|--------------|
| Kabel | LAN's over grote geografische gebieden met elkaar verbinden. |
| Beheerd door één enkele organisatie of persoon. | Wordt beheerd door een of meer service providers. |
| Zorgt voor hoge snelheid bandbreedte naar interne apparaten. | Zorgt voor langzamere verbindingen tussen LAN's. |

Stop gezet wegens het te lang was.