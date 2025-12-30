---
tags:
  - Command Line Interface (CLI)
---

# Hoofdstuk 3
Bij dit hoofdstuk ga je alles ...

## Theorie

![CLI](https://vwgert.github.io/be-nl/images/03/CLI_Login_And_Welcome.png){ align=right width=300px }

Deze omgeving wordt een command line interface (CLI) genoemd. Er is geen graphical user interface (GUI) aanwezig in een Ubuntu Server, bij een Ubuntu Desktop wel. CLI zal beter bij het deel automatisering zijn en bij de Ubuntu Desktop iets mogelijker bij het gebruik van een GUI.

Als je bent ingelogd krijg je de volgende regel in de CLI:
![PROMPT](https://vwgert.github.io/be-nl/images/03/prompt.png){ width=500px }

De prompt bestaat uit meerdere onderdelen die informatie laat zien zoals onze gebruiker, hostnaam van de server waarop we zijn ingelogd.

Het ~ symbool is een afkorting van de homefolder van de ingelogde gebruiker wat in dit geval de map /home/student is, dit valt te vergelijken zoals bij Windows met C:Users/student. 
Dus wat je ziet tussen de : en de $ teken is het pad dat verwijst naar de map waar je in zit te werken.

Om het besturingssysteem te gebruiken met behulp van een CLI moet je commando's gaan gebruiken.

### Commando's
1. **Echo**
Deze commando zegt gewoon wat het argument is.
```
student@ubuntu-server:~$ echo hello world
hello world

```
De string *hello world* wordt gezien als een argument van het echo commando.

2. **Shutdown**
```
student@ubuntu-server:~$ sudo shutdown now
```

## Quiz
Elk hoofdstuk heeft een quiz waar je een aantal vragen moet beantwoorden zodat je jezelf kan oefenen of je genoeg kennis hebt voor het hoofdstuk.

<quiz> 
### Vraag 1
Is er een Graphical User Interface (GUI) bij een Ubuntu Server?
- [ ] Ja
- [x] Nee

Er is geen Graphical User Interface (GUI) aanwezig in Ubuntu Server, maar wel bij Ubuntu Desktop.
</quiz>

<quiz> 
### Vraag 2
Kan je zien wat je typt voor het wachtwoord?
- [ ] Ja
- [x] Nee

Je kan niet zien wat je hebt getyped als voor wachtwoord.
</quiz>