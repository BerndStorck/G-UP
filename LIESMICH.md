# g-up - Aktualisierungsprogramm für Debian / Ubuntu

**g-up vereinfacht es für den Anwender von der Kommandozeile aus ein Debian-basiertes Linux-System wie Ubuntu oder Linux Lite zu aktualisieren, wenn ihr System das Programm `apt-get` benutzt.**

## Lizenz

g-up ist freie Software. Das Skript kann unter Einhaltung der Vorgaben der GNU General Public License Version 2.0 der Free Software Foundation genutzt, weitergegeben oder verändert werden. Eine Kopie der  GNU GPL 2.0 gehört zu der Archivdatei, mir der g-up bei Github heruntergeladen werden kann. Eine deutsche Übersetzung der Lizenz findet man unter http://www.gnu.de/documents/gpl-2.0.de.html

## Installation

Entpacken Sie das "g-up"-Bash-Skript aus dem Zip-Archiv und verschieben Sie es entweder in eines der Verzeichnisse `/usr/local/bin` oder `~/bin`.

Hinweis: Skripte, die aus dem Verzeichnis `~/bin` ausgeführt werden, können nicht mit dem Präfix '`sudo`' gestartet werden, da das System sie nicht finden würde. Wer dieses Skript aus einem Skript für cron-, anacron- oder systemd-Timer aufrufen möchte, sollte es in `/usr/local/bin` ablegen. Dies ist auch die beste Vorgehensweise, wenn es mehr als ein Administratorenkonto auf dem Rechner gibt.

## Bedienung

### Aufrufsyntax

    g-up [--clean|--remove|--clean-only|--help]

### Aufrufvarianten

#### Ohne Option

Den Paket-Cache aktualisieren und ein komplettes Upgrade starten:

```bash
g-up
```

#### --clean

Das System komplett aktualisieren, danach aus dem lokalen Cache
Pakete entfernt, die nicht mehr in den Repositories vorkommen,
außerdem verwaiste, von keinem Programm benötigte Pakete entfernt:

```bash
g-up --clean  # Oder kürzer "-c"
```

#### --remove

Das System komplett aktualisieren und danach verwaiste Pakete
entfernen, ohne den Apt-Cache zu verändern: 

```bash
g-up --remove # Oder kürzer: "-r"
```

#### --clean-only

Kein Programm herunterladen und installieren, nur überflüssige Pakete entfernen, wie es auch `--clean` tut:

```bash
g-up --clean-only
```

#### --hilf

Die Hilfe anzeigen:

```bash
g-up --hilf
```

#### --version

Versionsinfo anzeigen:

```bash
g-up --version  
```

#### -#

Nur die Versionsnummer ausgeben:

```bash
g-up -#
```

## Entstehungsgeschichte

`g-up` habe ich ausgehend von den Versionen 1.0 und 1.2 des Bash-Skripts `up` von Joe Collins (ezeelinux.com) entwickelt. 

Collins hat die Version 1.0 gegen Ende seines Youtube-Videos *"A Beginner's Introduction to BASH Shell Scripting"* erläutert:  https://www.youtube.com/watch?v=_n5ZegzieSQ (2018-08-09). Version 1.2 kann von Github heruntergeladen werden: https://codeload.github.com/EzeeLinux/up-debian_ubuntu_update_tool/zip/master 

Kodiert von Bernd Storck, https://facebook.com/BStLinux/.

### Unterschiede von g-up und up

`g-up` ist eine weitgehende Reimplementierung oder mindestens ein umfassender Code-Review und eine mehrfache Verbesserung von `up`.  Ein wesentlicher Unterschied ist, dass das Skript nun zusätzlich auf Deutsch mit dem Anwender kommuniziert: deutscher Hilfetext und deutsche Bildschirmmeldungen. g-up soll dadurch dazu beitragen deutschsprachigen Anwendern den Einstieg in Linux und das Verständnis zu erleichtern.  

- Mehrsprachigkeit: Bildschirmmeldungen und Hilfe in Deutsch oder Englisch.
- Zusätzliche Aufrufoption `--hilf` für einen schnellen systemsprachenunabhängigen Aufruf der deutschen Hilfe.
- Pager-Aufruf in Abhängigkeit von Terminalhöhe und Zeilenzahl des auszugebenden Hilfe-Textes.
- Zusätzliche Option, um nur den Apt-Cache zu bereinigen.
- Zusätzliche kurze Aufrufoptionen `-h` für `--help `,  `-c` für `--clean` und  `-r` für `--remove`.
- Zusätzliche Optionen zur Abfrage der Skript-Version.
- Komplette Veränderung der zentralen Ablaufsteuerung.
- Bemühungen, das Skript ein wenig schneller zu machen: Ein Funktionsaufruf wurde entfernt, geringfügige Code-Redundanz zugunsten der Ausführungsgeschwindigkeit, Verminderung der Bildschirmausgaben von apt-get.
- Bug fix: Fehlerhafte Prüfung, ob der Pager less installiert ist, durch eine eigene Funktion ersetzt, die überprüft, ob ein bekannter Pager installiert ist.

## Haftungsauschluß
Kurz und knapp: Ich hafte für nichts; ob und wie Sie das Programm benutzten ist Ihre Sache. Das Programm beantwortet insbesonere alle Rückfragen automatisch mit "Ja". 
