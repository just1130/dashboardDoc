# Forecast and Scraping
Das Softwaremodul Forecast_And_Scraping setzt sich aus einem Pythonserver und einer MongoDB zusammen. Die Hauptaufgaben dieses Moduls liegen in der Datenbeschaffung und der Prognose von Zeitreihen. Die Datenbeschaffung setzt sich aus zwei Teilen zusammen. Zum einen werden Daten aus der Elvira Datenbank per Webscraper abgerufen und zum anderen werden Daten der Bundesbank per REST-Schnittstellen eingebunden. Diese Datenabrufe geschehen immer nachts um eins(UTC). Der Prozess des Scraper kann bis zu drei Stunden betragen, weshalb die Anfragen gleichmäßig über die Woche verteilt werden.Um für jede Zeitreihe, die im System liegt, eine Prognosemöglichkeit zu haben, wird direkt beim Abruf der Daten ein neues Sarima Modell berechnet. Dieses Modell wird anschließend als binärer String (Base64) in der MongoDB persistent gespeichert. Hierdurch gehen keinerlei Moellinformationen verloren, auch wenn Änderungen am Server vorgenommen werden müssen. Für die Erstellung des Servers beziehungsweise der Schnittstellen verwenden wir FastAPI und Uvicorn.

## App

### DB
#### MongoDB.py

---
#### `add_model(name,model,last_timestamp,params)`
Fügt ein Sarima-Modell zur MongoDB hinzu.

- **Parameter:**
    - **name (String):** Der Name des angegebenen Modells.
    - **model (String):** Das in eine Zeichenkette umgewandelte Sarima-Modell.

---
#### `get_model(name)`
Ruft das Modell aus der Datenbank ab.

- **Parameter:**
    - **name (String):** Das Modell, das aus der Datenbank abgerufen werden soll.
- **Returntype:**     
    - **Object**

<br>

### Forecast
#### DateHandler.py
---
#### `getTimeLine(model_name)`
Rückgabe der Zeitleiste für die Prdicion-Struktur.

- **Parameter:**
    - **start_date (String):** Beginn der Zeitleiste.
    - **end_date (String):** Ende der Zeitleiste.

    - **time_range (String):** Intervall der Einträge.

    - **model_name (String):** Name des Modells, das zum Abrufen von Informationen verwendet wird.

- **Returntype:**     
    - **List**
    - **Integer**

<br>

#### Sarima.py
---
#### `calculate_sarima_modell(time_range,y_data,model_name,custom=False,params={})`  
Name of the model used to retrieve information.

- **Parameter:**
    - **time_range (String):** Zeitintervall.
    - **y_data (Array):** Die y-Daten zur Berechnung des Modells.

    - **model_name (String):** Der Modellname (alter Spaltenname).

    - **custom (Boolean):** Entscheidet, ob das Modell im Cache gespeichert werden soll.
    - **params (Object):** Wenn params nicht leer ist, wird ein benutzerdefiniertes Modell berechnet.


- **Returntype:**     
    - **Boolean**
    
---

#### `save_model(model,model_name,model_params,mae)`
Konvertiert das Modell in einen base64 String.

- **Parameter:**
    - **model (Object):** Das Sarima-Modell.
    - **model_name (String):** Der Name des Modells, um es in der MongoDB zu finden.
    - **model_params (Object):** Die Parameter, die zur Berechnung des Modells verwendet wurden.
    - **mae (double):** Der berechnete Mae.

---
#### `predict(model_name,steps,model)`
   Laden des Sarima-Modells und Verwendung für Vorhersagen.

- **Parameter:**
    - **model_name (String):** Das Modell, das geladen werden soll.
    - **steps (integer):** Die Anzahl der zu prognostizierenden Schritte.
    - **model (Object):** Das berechnete Sarima/Arima-Modell.

---
#### `predict_for_ui(table_name,start_date,end_date,time_interval,kpi_selection,model={})`
   Zeitreihenvorhersage für die Benutzeroberfläche.

- **Parameter:**
   - **table_name (String):** Name der Zeitreihe.
    - **start_date (String):** Der angegebene Start.
    - **end_date (String):** Das angegebene Ende.
    - **time_interval (String):** Intervall der Datenreihe.
    - **kpi_selection (String):** Wenn nicht "", dann Vorhersage für KPI.
    - **model (Object):** Ausgewähltes Modell.

- **Returntype:**     
    - **Object**

---
#### `kpi_calculation(kpi_selection, predictions)`
   Berechnung der KPIs.

- **Parameter:**
    - **kpi_selection (String):** Auswahl der KPI.
    - **predictions (Object):** Vorhersagen.

- **Returntype:**     
    - **Double**

---
#### `calculate_custom_model(data,y_data)`
Berechnung des benutzerdefinierten Modells.

- **Parameter:**
    - **k data (Object):** Informationen zur Erstellung eines neuen Modells.
    - **y_data ([])** Zeitreihen.

- **Returntype:**     
    - **Object**

---
#### `save_cache()`
Zwischengespeichertes Modell speichern.

<br>

## Helper
### Bundesbank.py
---

#### `get_selected_data_from_bundesbank()`

<br>

### CalculateStats.py

---
#### `calculate_acf_and_pacf(data)`
Berechnung von acf und pacf

- **Parameter:**
    - **data (Object):** Zeitreihe.
- **Returntype:**     
    - **Object**
    - **Object**

<br>

### Bundesbank.py
#### `parsing_csv(path)`
Wandelt csv-Daten in eine Json-Datei um. Löst auch das Senden der Daten und die Berechnung der Sarima-Modelle aus.

- **Parameter:**
   - **path (string):** Der Pfad zu einer gegebenen csv-Datei.

---
#### `send_data_to_nodejs(data, not_init=True)`
Senden von Daten an das NodeJS-Backend.

- **Parameter:**
    - **data (dict):** Das dictionary, das an das NodeJS-Backend gesendet werden soll.
    - **data (dict):** Speichert die Einträge als json, um sie als Init-Daten zu verwenden.

---
#### `get_y_data(table_name,start_date)`
Senden von Daten an das NodeJS-Backend.

- **Parameter:**
    - **table_name (String):** Tabellenname.
    - **start_date (String):** Zeitstempel als IsoString.

- **Returntype:**     
    - **Object**

---
#### `load_initial_data()`
Ausgangsdaten laden.

<br>

### Server.py
#### `GET loadInitData`  
Ausgangsdaten laden.

- **Returntype:**     
    - **Object**

---
#### `GET getPrediction`  
Liefert ein Vorhersageergebnis für eine Zeitreihe.

- **Parameter:**
    - **prediction_request (String):** Request body

- **Returntype:**     
    - **Object**

---
#### `GET getbundesbankData`  
Startet den Bundesbank-Scraper.

- **Returntype:**     
    - **Object**

---
#### `GET getPredictionForUI`  
Liefert eine Vorhersage für eine Zeitreihe im Dictonary Format.

- **Parameter:**
    - **prediction_request (String):** Request body

- **Returntype:**     
    - **Object**

---
#### `GET calculateAcfPacf`  
Berechnet acf & pacf für Insights.

- **Parameter:**
    - **prediction_request (String):** Request body
    
- **Returntype:**     
    - **Object**

---
#### `GET getModelParams`  
Liefert alle Modell-Parameter.

- **Parameter:**
    - **prediction_request (String):** Request body
    
- **Returntype:**     
    - **Object**

---
#### `GET CalculateModelForAdmin`  
Neuberechnung des Prognose-Modells.

- **Parameter:**
    - **prediction_request (String):** Request body
    
- **Returntype:**     
    - **Object**

---
#### `GET saveCachedModel`  
Überschreibt das Modell durch den Admin.
