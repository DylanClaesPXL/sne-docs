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
  - Basic Switch and End Device Configuration
---

# Hoofdstuk 2
Bij dit hoofdstuk ga je alles over het instellen van passwords, IP addressing en default gateway parameters op een netwerk switch en end devices hebben.

## Cisco IOS Access

### Operating Systems
Elk apparaat heeft een Operating System (OS) nodig. Bij Cisco-apparaten is dit de Cisco IOS.

- **Shell:** De gebruikersinterface die de gebruiker toestaat om specifieke taken aan te vragen via de CLI of GUI.
- **Kernel:** Communiceert rechtstreeks met de hardware en software van de computer.
- **Hardware:** De fysieke onderdelen van een apparaat.

### Access Methods
Er zijn drie veelvoorkomende manieren om toegang te krijgen tot de CLI:

- **Console:** Een fysieke managementpoort voor toegang (toegang zonder netwerkverbinding).
- **Secure Shell (SHH):** Een methode voor het op afstand via een virtuel interface tot stand brengen van een beveiligde CLI-verbinding via een netwerk.
- **Telnet:** Een onveilige methode voor externe toegang; gegevens worden in platte tekst verzonden.

### Terminal Emulation Programs
Om verbinding te maken via de console of SSH worden programma's gebruikt zoals:

- PuTTY
- Tera Term
- SecureCRT

## IOS Navigation

### Primary Command Modes
**User EXEC Mode** 

Heeft beperkte mogelijkheden. Laat alleen een klein aantal basiscommando's toe voor monitoring. Herkenbaar aan het symbool `>`

```
Router>

Switch>
```

**Privileged EXEC Mode** 

Geeft toegang tot alle commando's en configuraties. Herkenbaar aan het symbool `#`.

```
Router#

Switch#
```

### Configuration Mod and Subconfiguration Modes
**Global Configuration Mode** 

Gebruikt om algemene instellingen op het apparaat te configureren.

```
Switch(config)#
```

**Line Configuration Mode**

Om toegang via console, SHH of Telnet te configureren.

```
Switch(config-line)#
```

**Interface Configuration Mode**

Om een specifieke netwerkport te configureren.

```
Switch(config-if)#
```

### Navigation Between IOS Modes

**Privileged EXEC Mode**

Om van user EXEC mode naar Privileged EXEC mode te gaan gebruik je het commando `enable`.

```
Switch> enable
Switch#
```

**Global Configuration Mode**

Om in en uit te gaan van global configuration mode, gebruik je het commando `configure terminal`. Om terug naar privileged EXEC mode te gaan gebruik je het commando `exit`.

```
Switch(config)#
Switch(config)#exit
Switch#
```

**Line Configuration Mode**

Om in en uit te gaan van line configuration mode, gebruik je het commando `line` gevolgd met het management line type. Om terug te gaan naar global configuration mode gebruik je het commando `exit`.

```
Switch(config)#line console 0
Switch(config-line)#exit
Switch(config)#
```

## The Command Structure

### Basic IOS Command Structure
Een commando bestaat uit meerdere delen zoals: Prompt, Command, Space, Keyword of argument.

- **Keyword:** Een specifiek parameter gedefinieerd in het OS (ip protocols)
- **Argument:** Een waarde die door de gebruiker wordt opgegeven. (Bijvoorbeeld een IP-address)

## Basic Device Configuration

### Device Names
Als eerste configuratie command op elk apparaat zou je een unieke hostname moeten geven.

Een hostname moet beginnen met een letter en mag geen spaties bevatten. Hieronder vind je een voorbeeld van het commando:

```
Switch#conf t
Switch(config)#hostname Sw-Floor-1
Sw-Floor-1(config)#
```

### Configure Passwords

**Securing User EXEC mode access:**

- Eerst ga je naar line console configuration mode met gebruik van `line console 0` command in global configuration mode.
- Hierna, ga je user EXEC mode wachtword instellen met gebruik van `password (password)` command.
- Uiteindelijk enable user EXEC access met gebruik van `login` command.

```
Sw-Floor-1#configure terminal
Sw-Floor-1(config)#line console 0
Sw-Floor-1(config-line)#password wachtwoord
Sw-Floor-1(config-line)#login
Sw-Floor-1(config-line)#end
Sw-Floor-1#
```

**Securing Privileged EXEC mode access:**

- Eerst ga je naar global configuration mode.
- Hierna, gebruik je `enable secret (password)` command.

```
Sw-Floor-1#configure terminal
Sw-Floor-1(config)#enable secret wachtwoord
Sw-Floor-1(config)#exit
Sw-Floor-1#
```

**Securing VTY (Virtuel Teletype) line access:**

- Eerst ga je naar VTY configuration mode met gebruik van het commando `line vty 0 15` in global configuration mode.
- Hierna ga je het VTY password instellen met het commando `password (password)`.
- Uiteindelijk ga je VTY access enable uitvoeren met `login` command.

```
Sw-Floor-1#configure terminal
Sw-Floor-1(config)#line vty 0 15
Sw-Floor-1(config-line)#password wachtwoord
Sw-Floor-1(config-line)#login
Sw-Floor-1(config-line)#end
Sw-Floor-1#
```

### Encrypt Passwords
In startup-config en running-config zullen de meeste wachtwoorden gezien worden in plaintext. Dit los je op met het encrypteren.

Gebruik het commando `show running-config` command om te bekijken.

```
Sw-Floor-1#show running-config
```

Om je wachtwoorden te encrypten gebruik je het commando `service password-encryption`.

```
Sw-Floor-1#configure terminal
Sw-Floor-1(config)#service password-encryption
Sw-Floor-1(config)#exit
Sw-Floor-1#
```

### Banner Messages
Om een banner message of the day aan te maken gebruik je het commando `banner motd # the message of the day #`.

```
Sw-Floor-1#configure terminal
Sw-Floor-1(config)#banner motd #Authorized Access Only!#
```

## Save Configurations

### Configuration Files
Er zijn twee betanden waarin instellingen worden opgeslagen:

- startup-config: Opgeslagen in NVRAM.
- running-config: Opgeslage in RAM. Alle wijzigingen die je maakt, komen hierin. Als het apparaat uit wordt gezet gaat alle wijzigingen verloren daarom moet je deze opslaan naar de startup-config.

Om je running-config naar je startup-config te doen gebruik je het commando `copy running-config startup-config`.

## Ports And Addresses

### IP Addresses
- **IPv4 Address:** Bestaat uit vier cijfers van 0 tot 255 gescheiden door punten (bijv. 192.168.1.1).
- **Subnet Mask:** Is een 32-bit value. Gekoppeld met een IPv4 address. 

### Interfaces and Ports
Netwerkcommunicatie is afhankelijk van de gebruikte Medium (kabels of draadloos). Verschillende types netwerkpoorten hebben verschillende snelheden (bijv. Ethernet, FastEthernet, GigabitEthernet).


## Configure IP Addressing
Een computer kan handmatig (Static) een IP-adres krijgen of automatisch via DHCP. Maar elk end devices op een netwerk moet een IP address hebben om te kunnen communiceren.

### Switch Virtual Interface Configuration
Om een switch remotely access te krijgen moet dit geconfigureerd zijn bij de SVI (Switch Virtual Interface).

Om dit te configureren volg je de stappen hieronder:

- Gebruikt het commando `interface vlan 1` in global configuration mode. Standaard is dit VLAN 1.
- Daarna ga je een IP-adres toevoegen met het commando `ip address ip-address subnet-mask`.
- Uiteindelijk ga je de virtual interface enable doen met het commando `no shutdown`.

```
Sw-Floor-1#configure terminal
Sw-Floor-1(config)#interface vlan 1
Sw-Floor-1(config-if)#ip address 192.168.1.20 255.255.255.0
Sw-Floor-1(config-if)#no shutdown
```

## Quiz
Elk hoofdstuk heeft een quiz waar je een aantal vragen moet beantwoorden zodat je jezelf kan oefenen of je genoeg kennis hebt voor het hoofdstuk.

