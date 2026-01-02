---
tags:
  - Basic Switch and End Device Configuration
---

# Hoofstuk 2
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

**Privilged EXEC Mode** 

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

Er wordt hier nog toegevoegd!