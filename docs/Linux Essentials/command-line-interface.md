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
  - Command Line Interface (CLI)
---

# Hoofdstuk 3
Bij dit hoofdstuk ga je alles over de prompt hebben en over commando's. Ook ga je het hebben over sudo, manpages, shell history.

## Theorie

![CLI](https://vwgert.github.io/be-nl/images/03/CLI_Login_And_Welcome.png){ align=right width=300px }

Deze omgeving wordt een command line interface (CLI) genoemd. Er is geen graphical user interface (GUI) aanwezig in een Ubuntu Server, bij een Ubuntu Desktop wel. CLI zal beter bij het deel automatisering zijn en bij de Ubuntu Desktop iets mogelijker bij het gebruik van een GUI.

Als je bent ingelogd krijg je de volgende regel in de CLI:
![PROMPT](https://vwgert.github.io/be-nl/images/03/prompt.png){ width=500px }

De prompt bestaat uit meerdere onderdelen die informatie laat zien zoals onze gebruiker, hostnaam van de server waarop we zijn ingelogd.

Het ~ symbool is een afkorting van de homefolder van de ingelogde gebruiker wat in dit geval de map /home/student is, dit valt te vergelijken zoals bij Windows met C:Users/student. 
Dus wat je ziet tussen de : en de $ teken is het pad dat verwijst naar de map waar je in zit te werken.

Om het besturingssysteem te gebruiken met behulp van een CLI moet je commando's gaan gebruiken.

Onthoud dat in Linux alles hoofdlettergevoelig is dat betekent dus de commando's, opties, argumenten, bestands- en mapnamen, ...

## Commando's
1 **echo**

Dit commando zegt wat het argument is.
```
student@ubuntu-server:~$ echo hello world
hello world
```

De string *hello world* wordt gezien als een argument van het echo commando.

2 **shutdown**

Dit commando zorgt ervoor dat de Ubuntu-server afgesloten wordt.
```
student@ubuntu-server:~$ sudo shutdown now
```

Het sudo commando staat voor *super user do*. Voor sommige commando's zijn er beheerdersrechten vereist. 
Door het commando sudo ervoor te plaatsen, voer je het commando uit als super user ook wel in Linux *root* genoemd. 
Het voorbeeld bestaat uit 2 commando's: Het sudo commando gevolgd met het shutdown commando met daarna *de parameter* now.

3 **man**

Commando's hebben vaak opties, maar hoe kan je deze bekijken?

Als voorbeeld bij de shutdown commando kan je kiezen wanneer de server moet worden afgesloten. Als er geen waarde wordt gegeven, wordt dit automatisch 1 minuut na het uitvoeren gepland. Je kan deze opties bekijken via de *manpage*.

Ubuntu heeft allerlei ingebouwde commando's. Wil je graag alle opties van een bepaalde commando uitvoeren moet je naar de manuel pages oftewel de afkorting man pages.
```
student@ubuntu-server:~$ man shutdown
```

Niet alleen commando's hebben een eigen manpages maar ook configuratie-/systeembestanden kunnen ook een manpage bevatten. Hieronder kan je een voorbeeld zien.
```
student@ubuntu-server:~$ man sudo.conf
```

Manpages kunnen heel groot zijn en bestaan uit meerdere pagina's of secties. Om de volgende pagina te bekijken druk je op de spatiebalk of je kan de pijltjestoetsen gebruiken.

Wil je graag iets opzoeken? Dit kan je doet met een / te typen en gevolgd met een zoekwoord, de manpage markeert het eerst wat voorkomt van het zoekwoord.
Je kan ook de sneltoets N (Next) gebruiken om naar de volgende instantie te gaan van het zoekwoord.

Je kan de manpage verlaten met de sneltoets Q (Quit). Ook kan je door g te typen naar de eerste regel gaan maar wil je naar de laatste dan moet je hoofdletter G indrukken.

4 **whereis & whatis**

Wil je snel de beschrijving van een commando bekijken zonder de manpage te openen?
```
student@ubuntu-server:~$ whatis route
route (8) - show / manipulate the IP routing table
```

Om de locatie van de manpage zelf te bekijken kan je het commando whereis gebruiken:
```
student@ubuntu-server:~$ whereis -m ls
ls: /usr/share/man/man1/ls.1.gz
```

De manpages worden ook opgeslagen in archieven met .gz ook wel vergelijkbaar als een zip bestand. Bij het typen van het commando man ls opent het een tekstbestand in het archief /usr/share/man/man1/ls.1.gz.



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
Kan je zien wat je typt van wachtwoord?
- [ ] Ja
- [x] Nee

Je kan niet zien wat je hebt getyped als voor wachtwoord.
</quiz>

<quiz> 
### Vraag 3
Waar staat het symbool ~ voor?
- [x] De homefolder van de momenteel ingelogde gebruiker.
- [ ] De tijdelijke homefolder voor commando's.
- [ ] De root voor het hele systeem.

Het symbool ~ is een snelkoppeling naar ```/home/gebruikersnaam```, vergelijkbaar met ```C:\Users``` in Windows.
</quiz>

<quiz> 
### Vraag 4
Je probeert een bestand te openen met de naam ```Document.txt```, maar je typt ```document.txt```. Waarom werkt dit waarschijnlijk niet in Linux?
- [ ] Omdat Linux geen bestandsextensies zoals .txt herkent.
- [ ] Omdat je altijd sudo moet gebruiken.
- [x] Omdat alles in Linux hoofdlettergevoelig is.

In Linux worden 'Document.txt' en 'document.txt' als twee totaal verschillende bestanden gezien.
</quiz>

<quiz> 
### Vraag 5
Je bent in een 'manpage' aan het lezen en je wilt zoeken naar een specifiek trefwoord. Welk teken gebruik je hiervoor?
- [x] De slash (/)
- [ ] De letter S (Search)
- [ ] Het vraagteken (?)
- [ ] Het dollarteken ($)

Door een slash te typen gevolgd door een zoekwoord, kun je binnen de manpage zoeken.
</quiz>

<quiz> 
### Vraag 6
Je bevindt je in de map ```/var/log```. Welk commando brengt je direct terug naar de map die in de prompt wordt aangeduid met ~?
- [x] cd /home/student
- [ ] cd /root
- [ ] echo ~
- [ ] cd .
- [x] cd

Hoewel dit technisch naar dezelfde locatie leidt voor de student-gebruiker, is de tilde een universele snelkoppeling voor de persoonlijke map van de actieve gebruiker.
</quiz>

<quiz> 
### Vraag 7
In de man-pagina van shutdown zie je dat de tijd parameter optioneel is. Wat gebeurt er specifiek als je het argument now weglaat?
- [ ] Het commando wordt genegeerd omdat er geen tijd is opgegeven.
- [ ] De server sluit onmiddellijk af.
- [x] De afsluiting wordt automatisch gepland voor 1 minuut later.
- [ ] De server vraagt om een wachtwoord via een pop-up venster.

De man-pagina specificeert dat 1 minuut de standaard wachttijd is als er geen specifiek tijdstip wordt meegegeven.
</quiz>

<quiz> 
### Vraag 8
Je voert man route uit en ziet de tekst route (8). Wat geeft het getal 8 tussen de haakjes aan?
- [x] Dat dit commando tot de sectie voor systeembeheer behoort.
- [ ] Dat er 8 verschillende versies van het commando zijn.
- [ ] Dat het commando 8 seconden nodig heeft om te laden.
- [ ] Dat de handleiding uit precies 8 pagina's bestaat.

Sectie 8 van de man-pagina's is gereserveerd voor commando's die meestal door beheerders (root) worden gebruikt.
</quiz>

<quiz> 
### Vraag 9
Stel dat je het commando echo ```$USER``` typt. Wat is in dit geval het argument voor het echo commando?
- [ ] echo
- [ ] student@ubuntu-server
- [x] $USER
- [ ] De spatie tussen echo en $USER.

Alles wat na de commandonaam komt en aangeeft waar het commando op moet werken, is een argument.
</quiz>

<quiz> 
### Vraag 10
Wat gebeurt er als je in een man-pagina op de 'N' toets drukt zonder dat je eerst een zoekterm met '/' hebt ingevoerd?
- [x] Er gebeurt niets of je krijgt een foutmelding.
- [ ] De tekst wordt in kleur weergegeven.
- [ ] Je gaat direct naar de laatste pagina.
- [ ] De man-pagina sluit af.

De 'N' staat voor 'Next' (volgende zoekresultaat), dus zonder zoekopdracht is er geen 'volgende'.
</quiz>

<quiz> 
### Vraag 11
In het pad ```/home/student```, wat is de betekenis van de eerste slash (/) aan het begin?
- [ ] Het is een typefout die Linux automatisch negeert.
- [x] Het vertegenwoordigt de 'root' map, het allerhoogste niveau van het systeem.
- [ ] Het geeft aan dat het pad relatief is aan je huidige map.
- [ ] Het is een teken dat aangeeft dat het om een map gaat.

Alle paden in Linux beginnen vanuit de root-map, aangegeven met een enkele slash.
</quiz>

<quiz> 
### Vraag 12
Welk commando uit de tekst helpt je om te achterhalen WAAR de documentatie van een specifiek commando op de harde schijf staat?
- [ ] whatis
- [ ] man
- [ ] echo
- [x] whereis

Dit commando zoekt specifiek naar de locaties van binaire bestanden, broncodes en man-pagina's.
</quiz>

<quiz> 
### Vraag 13
Je typt ```SUDO SHUTDOWN NOW``` in plaats van ```sudo shutdown now```. Wat zal de CLI doen?
- [x] Een foutmelding geven zoals 'command not found'.
- [ ] De server direct afsluiten zonder sudo te controleren.
- [ ] Het commando uitvoeren omdat Linux slim genoeg is om het te begrijpen.
- [ ] Vragen of je bedoelde 'sudo shutdown now'.

Omdat Linux hoofdlettergevoelig is, herkent hij het niet als een officiële commando.
</quiz>

<quiz> 
### Vraag 14
Met !! wordt er gerefereerd naar het vorig commando.
- [x] Waar
- [ ] Niet Waar
</quiz>

<quiz> 
### Vraag 15
Je kunt geen verborgen bestanden zien zonder extra opties in het 'ls' commando.
- [x] Waar
- [ ] Niet Waar
</quiz>