# Starten der Applikation
Unser Softwaresystem wird aktuell über Github verwaltet und setzt auf eine Microservicearchitektur. Aufgrund dieser Architekturentscheidung setzten wir zudem auf eine Containerisierung der Module. Dies geschieht durch den Einsatz von Docker. Aus diesen Gründen ergeben sich die nachfolgenden notwendigen Schritte, um die Applikation zu starten.

## **Vorraussetzungen**

Für die Ausführung des Programms ist es notwendig, Dockerdesktop (bzw. Docker) zu installieren. Der Link zur Anwendung: _https://www.docker.com/products/docker-desktop/_

## **Download des Projekts**

1. Clonen des Repositories (**git clone https://github.com/just1130/DashboardBauindustrieDeutschland.git **)
    - In dem Ordner DashboardBauindustrieDeutschland liegt eine .env Datei hier können das PW und die Email für die Elvira hinterlegt werden (optional)
    - Der Scraper läuft jede Nacht um 3 Uhr MEZ, das System läuft zunächst mit Initialdaten(siehe unten)
    - Solltet ihr den Scraper testen wollen, meldet euch bitte in Slack, dann senden wir euch das PW und die Email privat zu

## **Start des Systems**

2. Per Terminal in den Ordner **DashboardBauindustrieDeutschland** navigieren
    - hier liegt eine Docker-Compose Datei
3. Im Terminal den Befehl **docker-compose up --build** eingeben
    - Der Prozess wird gestartet und kann je nach System bis zu 10 Minuten in Anspruch nehmen
4. Nachdem alle Server gestartet wurden, kann über die folgende URL der Prozess für eine initiale Beladung gestartet werden _http://localhost:8000/loadInitData_
    - Durch den Aufruf der Route werden initiale Daten geladen, verarbeitet und Prognosemodelle für diese abgelegt.
    - Der Prozess kann im Hintergrund weiterlaufen und das System kann sofort genutzt werden.

## **Nutzung des Systems**

- Das Userinterface ist über die folgende URL erreichbar _http://localhost:3001_
- Beim ersten Start des Systems wird ein default User angelegt 
    - Email: admin@bauverband.de
    - Password: admin
    - Der Nutzer kann nach dem ersten Login gelöscht werden und durch einen neuen Nutzer ersetzt werden (Siehe Handbuch)
