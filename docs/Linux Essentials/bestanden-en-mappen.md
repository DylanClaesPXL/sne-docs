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
  - Bestanden en mappen
---

# Hoofdstuk 4
Bij dit hoofdstuk ga je alles over bestanden en mappen zien ook ga je nieuwe commando's bij leren hoe je folders of bestanden aanmaakt, verplaatst, verwijderd.

## Theorie
Bij Windows start een absoluut pad met C:/... maar in Linux gebruiken we geen schijfletters. De C:/ is bij Linux de root directory. Deze map wordt aan het begin van een pad aangeduid als /.

![STRUCTUUR](https://vwgert.github.io/be-nl/images/04/Ch4_CleanInstall.png){ width=1000px }

Vorig hoofdstuk zag je de ~ teken dat was een afkorting voor de map /home/student. Dit wordt de homefolder genoemd.
Elke gebruiker op het besturingssysteem krijgt een eigen homefolder in /home. Een gebruiker heeft alle rechten (lezen, schrijven, uitvoeren) in zijn folder.
Buiten die map hebben ze vaak alleen les rechten.

### Absolute en relatieve paden
Bij het gebruik van commando moet je vaak paden naar mappen of bestanden gebruiken. Het commando cd vereist als voorbeeld een pad om naartoe te navigeren.

Paden wordt gebruikt om naar bestanden en mappen op het systeem te wijzen. Je hebt 2 soorten: Relatieve en absolute paden.

**Absoluut pad**

Absolute paden beginnen met een /. Dit betekent dat absoluut pad begint vanuit de rootmap en zich daarna een weg naar beneden gaat.

```
student@ubuntu-server:/tmp$ cd /home/student/
student@ubuntu-server:~/$ pwd
/home/student
```

Wist je dat Linux CLI commando- en pathcompletion heeft? Dit doe je met TAB te drukken wanneer je een deel van een commando, bestands- of mapnaam typt. Als een commando, bestand of map overeenkomt met het eerste deel wordt het woord automatisch voltooid!

Wanneer je tabcompletion op een directory gebruikt, eindigt deze met een /, bijvoorbeeld cd /home/student/. De laatste / is optioneel.

**Relatief pad**

Relatief pad begint altijd bij de huidige directory en verwijst van daaruit naar een ander bestand of map.

```
student@ubuntu-server:~$ cd Downloads/test
student@ubuntu-server:/Downloads/test$ pwd
/home/student/Downloads/test
```
Wanner je relatieve paden gebruikt kan je enkele afkortingen gebruiken.

| Afkorting | Omschrijving |
|-----------|--------------|
| . (één punt) | Verwijst naar de huidige map |
| .. (2 puntjes) | Verwijst naar de bovenliggende map |
| ~ (tilde) | Verwijst naar de thuismap van de gebruiker |

Een hekje # vertelt de shell dat alles erachter als een opmerking wordt beschouwd en niet als commando of argument.

## Commando's
1 **pwd**

Dit commando laat de huidige map zien.

```
student@ubuntu-server:~$ pwd
/home/student
```

De map student is de huidige werkmap. Deze map is een submap van de map home die ook een submap is van de root directory /.

2 **cd**

Dit commando laat je de huidige werkmap wijzigen. (change directory)

```
student@ubuntu-server:~$ cd /etc
student@ubuntu-server:/etc$ pwd
/etc

student@ubuntu-server:/etc$ cd ~
student@ubuntu-server:~$ pwd
/home/student
```

Dit commando neemt het pad als argument. Hierboven gaan we naar de map etc in de hoofdmap ook wel de root genoemd. Je kan dit zien door pwd uit te voeren. Bij het 2de deel kan je zien dat we het teken ~ gebruikt hebben om snel naar de homefolder van de gebruiker te gaan.

Je kan ook het commando cd zonder een argument, dit navigeert ook terug naar de homefolder.

3 **tree**

Dit commando laat een boomstructuur zijn van een map met zijn submappen.

```
student@ubuntu-server:~$ tree
.
└── emptyfile

0 directories, 1 file
```

Je kan ook de optie '-a' gebruiken om verborgen bestanden te bekijken (bestanden die beginnen met een punt)

```
student@ubuntu-server:~$ tree -a
.
├── .bash_history
├── .bash_logout
├── .bashrc
├── .cache
│   └── motd.legal-displayed
├── .lesshst
├── .local
│   └── share
│       └── nano
├── .profile
├── emptyfile
├── .ssh
│   └── authorized_keys
├── .sudo_as_admin_successful
└── .wget-hsts

5 directories, 10 files
```

Je kan ook alleen een pad als parameter opgeven om van een bepaalde map te krijgen.

```
student@ubuntu-server:~$ tree /etc/dhcp
/etc/dhcp
├── debug
├── dhclient.conf
├── dhclient-enter-hooks.d
│   └── debug -> ../debug
└── dhclient-exit-hooks.d
    ├── debug -> ../debug
    ├── hook-dhclient
    ├── resolved
    ├── rfc3442-classless-routes
    └── timesyncd
 
2 directories, 8 files
```

4 **ls**

Dit commando toont de inhoud van een map. Als je dit command zonder opties of argumenten gebruikt wordt de inhoud van de huidige map weergegeven.

```
student@ubuntu-server:~$ ls
Downloads
```

Je kan ook in een bepaalde map gaan voor inhoud ervan te zien.

```
student@ubuntu-server:~$ cd /
student@ubuntu-server:/$ ls
bin   dev  home  lib32  libx32      media  opt   root  sbin  srv  tmp  var
boot  etc  lib   lib64  lost+found  mnt    proc  run   snap  sys  usr
```

Het commando ls kan maar 1 argument gebruiken. Dit argument is een pad dat absoluut of relatief kan zijn.
Het commando ls heeft ook verschillende opties. Deze opties kan je vinden in de manpage.

```
student@ubuntu-server:~$ ls -alh
total 45M
drwxr-xr-x 5 student student 4.0K Mar 27 16:36 .
drwxr-xr-x 3 root    root    4.0K Oct  5 13:40 ..
-rw------- 1 student student 1.7K Mar 17 12:14 .bash_history
-rw-r--r-- 1 student student  220 Oct  5 13:40 .bash_logout
-rw-r--r-- 1 student student 3.7K Oct  5 13:40 .bashrc
drwxrwxr-x 2 student student 4.0K Oct  1 14:31 Downloads
-rw-r--r-- 1 student student  807 Oct  5 13:40 .profile
drwxr-xr-x 2 student student 4.0K Oct  5 13:40 .ssh
-rw-r--r-- 1 student student    0 Oct  6 08:20 .sudo_as_admin_successful
```
Je ziet dat we 3 opties hebben gecombineerd met het commando hierboven. Je kan de opties in elke volgorde zetten.
Je kan de opties vinden in de manpage maar hieronder vind je een overzicht van die gebruikt zijn.

- '-a' - Toont verborgen bestanden en folders. In linux beginnen die altijd met een .
- '-l' - Toont een long listing. Dit betekent dat die alle extra uitvoer toont en niet alleen de bestanden en mappen.
- '-h' - Verwijst naar human readable en zorgt ervoor dat bestandsgrootte zichtbaar is met de juiste eenheid in plaats van bytes.

* De eerste kolom verwijst naar de machtigingen voor dat specifiek bestand/map. De kolommen met student student verwijst naar eigenaar en groepseigenaar van dat specifiek bestand/map.
De 3.7K regel van .bashrc verwijst naar de grootte van het bestand en Oct 5 13:40 naar de tijd van laatste wijziging.

5 **mkdir**

Dit commando maakt mappen aan.

```
student@ubuntu-server:~$ mkdir backup
student@ubuntu-server:~$ ls
backup  Downloads
```

Hierboven zie je dat mkdir een map met naam backup aanmaakt in de hudige map (/home/student). De mapnaam hier is een relatief path.
Je kan ook paden met submappen doen. Bij het gebruik van relatieve of absolute paden kan je het volgende doen.

```
student@ubuntu-server:~$ mkdir backup/downloads/pxl
student@ubuntu-server:~$ ls
mkdir: cannot create directory ‘backup/downloads/pxl: No such file or directory
```
Deze fout komt door dat de map downloads nog niet in backup bestaand. Dit kan je oplossen door de optie -p.
```
student@ubuntu-server:~$ mkdir -p backup/downloads/pxl
student@ubuntu-server:~$ tree backups
backup
└── downloads
    └── pxl
 
2 directories, 0 files
```
Hierdoor maakt hij een downloads folder als deze nog niet bestaat.

6 **touch**

Dit commando maakt een leeg bestand aan.

```
student@ubuntu-server:~$ touch fileOne
student@ubuntu-server:~$ ls -l
total 0
drwxrwxr-x 3 student student 4096 Oct  1 14:34 backup
drwxrwxr-x 2 student student 4096 Oct  1 14:31 Downloads
-rw-r--r-- 1 student student 0 Feb 12 09:50 fileOne
```

Je kan zien aan de bestandsgrootte dat de bestand leeg is.
Wil je bestanden met spaties in de naam? Dit kan je doen door aanhalingtekens te doen.

```
student@ubuntu-server:~$ touch "File Two"
student@ubuntu-server:~$ ls -l
total 0
drwxrwxr-x 3 student student 4096 Oct  1 14:34 backup
drwxrwxr-x 2 student student 4096 Oct  1 14:31 Downloads
-rw-r--r-- 1 student student 0 Feb 12 09:50 'File Two'
```
Onthoud dat ook enkele aanhalingsteken kunnen gebruiken touch 'File Two' of een backslach om de spatie als string te lezen touch File\ Two.

7 **mv**

Dit commando laat je bestanden verplaatsen.

```
student@ubuntu-server:~$ mv FileOne backup/
student@ubuntu-server:~$ ls
backup  Downloads  fileOne  'File Two'
student@ubuntu-server:~$ ls backup
FileOne  downloads
```

Deze opdracht heeft 2 argumenten: Het bronbestand/bronmap en het doelbestand/doelmap.

8 **cp**

Dit commando laat je bestanden kopiëren.

```
student@ubuntu-server:~$ cp FileOne FileOne.backup
```
Beide argumenten zijn paden. Het eerste pad is oorspronkelijke bestand/map. Het 2de is de pad van de nieuwe locatie en nieuwe bestandsnaam/mapnaam.
Je kan dit commando gebruiken voor zowel bestanden als mappen naar dezelfde map of andere map te kopiëren.

- Je kan ook recursief kopiëren. Om volledige mappen met alle submappen en files in die map te kopiëren moet je de optie -r (recursief) gebruiken.
- Onthoud dat het commando standaard bestaanden bestanden overschrijft. We kunnen de optie -i (interactief) gebruiken om een prompt te krijgen waarbij we moeten bevestigen of we het bestand wel willen overschrijven.

Hier komen nog meer commando's!

## Quiz
Elk hoofdstuk heeft een quiz waar je een aantal vragen moet beantwoorden zodat je jezelf kan oefenen of je genoeg kennis hebt voor het hoofdstuk.

<quiz> 
### Vraag 1
Met welk symbool wordt de root directory aangeduid?
- [ ] ~
- [ ] C:/
- [x] /
- [ ] \

De forward slash aan het begin van een pad vertegenwoordigt het allerhoogste niveau.
</quiz>

<quiz> 
### Vraag 2
Je bevindt je in de map /home/student/Downloads. Welk commando brengt je direct naar de map /home/student met gebruik van een relatief pad?
- [x] cd ..
- [ ] cd ~
- [ ] cd /home/student
- [ ] cd .

De dubbele punt verwijst altijd naar de bovenliggende map.
</quiz>

<quiz> 
### Vraag 3
Je wilt een nieuwe mapstructuur maken: project/data/2024. De map project bestaat echter nog niet. Welk commando moet je gebruiken?
- [x] mkdir -p project/data/2024
- [ ] mkdir project/data/2024
- [ ] touch -p project/data/2024
- [ ] mkdir -a project/data/2024
</quiz>

<quiz> 
### Vraag 4
Wat is het resultaat van het commando ls -alh?
- [ ] Een boomstructuur van de huidige map inclusief alle submappen.
- [x] Een gedetailleerde lijst van alle bestanden, inclusief verborgen bestanden, met leesbare groottes (KB, MB).
- [ ] Een lijst van alleen de mappen in de root directory.
- [ ] Het aanmaken van een verborgen bestand met de naam 'alh'.
</quiz>

<quiz> 
### Vraag 5
Je wilt een bestand aanmaken met de naam Mijn Rapport.txt. Welk commando is correct om dit als één bestand aan te maken?
- [ ] touch Mijn Rapport.txt
- [ ] mv Mijn Rapport.txt
- [ ] mkdir "Mijn Rapport.txt"
- [x] touch "Mijn Rapport.txt"
- [x] touch 'Mijn Rapport.txt'
</quiz>

<quiz> 
### Vraag 6
Je wilt de grootte van een bestand zien in MB of GB in plaats van in bytes. Welke optie voeg je toe aan het ls commando?
- [ ] -m
- [ ] -s
- [x] -h
- [ ] -l

De optie -h staat voor 'human readable' en zet bytes om naar makkelijk leesbare eenheden.
</quiz>

<quiz> 
### Vraag 7
Wat gebeurt er als je het commando cd typt zonder extra argumenten of paden?
- [ ] De terminal wordt afgesloten.
- [x] Je keert direct terug naar je homefolder (/home/gebruiker).
- [ ] Je krijgt een foutmelding.
- [ ] Je gaat naar de root directory /.

In Linux is de standaardbestemming voor het cd-commando de thuismap van de actieve gebruiker.
</quiz>

<quiz> 
### Vraag 8
Bij de uitvoer van ls -l zie je de regel: -rw-r--r-- 1 student student 3.7K Oct 5 13:40 .bashrc. Wat vertelt de eerste letter (het streepje) je over dit object?
- [ ] Het bestand is beveiligd tegen lezen.
- [x] Het is een regulier bestand.
- [ ] Het is een map (directory).
- [ ] Het is een verborgen bestand.

Een streepje '-' aan het begin van de permissie-kolom duidt op een bestand, terwijl een 'd' op een directory duidt.
</quiz>

<quiz> 
### Vraag 9
Je wilt een bestand genaamd data.txt verplaatsen naar een map genaamd archief. Welk commando gebruik je?
- [x] mv data.txt archief/
- [ ] move data.txt to archief
- [ ] cp data.txt archief/
- [ ] mkdir data.txt archief/

Het mv-commando neemt de bron als eerste argument en de bestemming als tweede.
</quiz>

<quiz> 
### Vraag 10
Je wilt een bestand genaamd data.txt verplaatsen naar een map genaamd archief. Welk commando gebruik je?
- [ ] De persoon die het bestand het laatst heeft geopend.
- [ ] De eigenaar van het bestand.
- [ ] De map waarin het bestand staat.
- [ ] De naam van de server waarop je werkt.
- [x] De groepseigenaar van het bestand.

De eerste naam is de eigenaar, de tweede naam is de groep die rechten heeft op het bestand.
</quiz>

<quiz> 
### Vraag 11
Hoe kun je een spatie in een bestandsnaam invoeren zonder aanhalingstekens te gebruiken?
- [ ] Dit is onmogelijk; spaties MOETEN altijd tussen aanhalingstekens.
- [ ] Door twee spaties te typen in plaats van één.
- [ ] De map waarin het bestand staat.
- [ ] Door een underscore te gebruiken: File_One
- [x] Door een backslash te gebruiken voor de spatie: File\ One

De backslash fungeert als een 'escape' karakter dat de shell vertelt de spatie letterlijk te nemen.
</quiz>

<quiz> 
### Vraag 12
Welk symbool gebruik je in een pad om specifiek naar de huidige werkmap te verwijzen?
- [x] .
- [ ] ~
- [ ] /

Een enkele punt wordt vaak gebruikt in commando's om 'hier' aan te duiden.
</quiz>

<quiz> 
### Vraag 13
In de CLI zie je student@ubuntu-server:~/Downloads$. Wat is je huidige werkmap?
- [ ] /Downloads
- [x] /home/student/Downloads
- [ ] /home/Downloads

De tilde (~) staat voor /home/student, dus de volledige map is /home/student/Downloads.
</quiz>

<quiz> 
### Vraag 14
Wat doet het commando rm?
- [x] Het verwijderdt een bestand.
- [ ] Veranderd de naam van een bestand.
- [ ] Maakt een nieuwe map aan.
- [ ] Maakt een kopie van een bestand.

Het command rm verwijderdt een bestand.
</quiz>

<quiz> 
### Vraag 15
Je kan met 'sudo rm' bestanden uit de homefolder van andere gebruikers verwijderen.
- [x] Waar
- [ ] Niet Waar

Je kan met sudo rm een bestand uit de homefolder van andere verwijderen.
</quiz>