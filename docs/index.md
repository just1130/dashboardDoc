

# Dashboard Bauindustrie Deutschland


Diese ReadMe enthält eine ausführliche Anleitung zur Installation des Projekts. Des Weiteren ermöglicht sie dem Leser einen ersten Überblick über den Aufbau des Projekts, welches hauptsächlich aus 3 verschiedenen Unterordnern besteht:

- [dashboard Frontend]()
- [dashboard Backend]() 
- [Prognose und Scraping Backend]()

Eine genauere Dokumentation über die jeweiligen Unterordnern finden Sie in der dazugehörigen Seite. 

## Problemstellung des Projekts
Die Erstellung von Konjunktur-, Struktur- und Marktanalysen sind für Bauunternehmen Grundlage für wichtige Unternehmensentscheidungen, betreffend Einkauf, über Investitionen und Projekte. Viele Kennzahlen in diesen Bereichen werden schon öffentlich erfasst und von den Unternehmen auch abgefragt. Die Interpretation und Darstellung gestalteten sich allerdings, vor allem über viele Quellen hinweg, bisher schwierig.
So auch beim Hauptverband der deutschen Bauindustrie, dem Kooperationspartner dieses Projekts. Dieser erstellt bisher händisch Berichte zu aktuellen Zahlen und Fakten aus der Bauindustrie. Zum Beispiel zur Baukonjunktur, zur Bauwirtschaft oder zum Arbeitsmarkt. Die Zielgruppe sind dabei Manager deutscher Bauunternehmen & die Mitglieder des Verbandes. 
An diese werden Berichte, zum einen unregelmäßig, in Form eines E-Mail Newsletters und zum anderen regelmäßig, in Form von Präsentationen auf der eigenen Homepage veröffentlicht. Zu bemerken ist hierbei, dass die Homepage nicht vom Verband, sondern einer Agentur verwaltet wird und der Verband keine Möglichkeit hat, selbst Dokumente zu veröffentlichen.
Das Erstellen der Berichte stellt dementsprechend aktuell einen hohen manuellen Aufwand dar, da sich die Daten mühsam aus der eigenen ELVIRA-Datenbank zusammengeklickt werden müssen.

![alternativer text](link)

Außerdem sind diese Berichte nicht dynamisch anpassbar. Das bedeutet für deren Empfänger, dass Daten unter Umständen nicht in den Kontext gesetzt werden können, wie es zur Erkenntnisgewinnung nötig wäre.


## Ziel des Projekts
Auf Grund der im vorherigen Absatz beschriebenen Probleme haben wir mit dem Bauverband folgendes Ziel für unser Projekt festgelegt:
Die Entwicklung eines Dashboards für Baustatistiken aus verschiedenen Blickwinkeln. 
Außerdem haben wir einige Rahmenbedingen und Kriterien definiert, um dieses Ziel zu erreichen:

- Möglichkeit zur flexiblen Einbindung unterschiedlichster Datenquellen, jedoch mindestens der ELVIRA-Datenbank des Verbandes
- Möglichkeit zum schnellen & einfachen Zugriff auf eingebundenen Daten
- Möglichkeit zur dynamischen Anpassung des Dashboards
- Möglichkeit zur Erstellung von Zeitreihen Prognosen, auf Basis der eingebundenen Daten
- Möglichkeit zur Veröffentlichung von Seiten durch Administratoren

## Installation

### 1. Einrichtung von Docker
so richten sie sich die Docker ein

`Terminal Befehle hier einsetzen ` 


### 2. Klonen des Git Repos
So richten sie die Git Repos ein: 

`Terminal Befehle hier einsetzen ` 

### 3. Downloaden von bereits gescrapte Daten
Da die Verwendung des Dashboards Daten benötigt, und der Bauverband leider keine API benutzt wurde ein Scraper verwendet mit welchem die Daten auf der 

`Terminal Befehle hier einsetzen ` 

### 
## Usage

```python
import foobar

# returns 'words'
foobar.pluralize('word')

```

