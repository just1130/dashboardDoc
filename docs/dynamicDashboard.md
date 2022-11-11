# Dynamic Dashboard
Dieses NodeJS Backend bietet über REST Schnittstellen Funktionen an, um Nutzer zu verwalten, Login-Prozesse zu authentifizieren. Desweiteren findet hier die Dateninteraktion mit dem Frontend statt. Im Folgenden werden die einzelnen Unter-Ordner, Module und Dateien in diesem Zusammenhang vorgestellt. 


## Helper
### auth.js
Dieses Modul verwaltet die Authentifizierung des Logins und die Validierung der verschiedenen User.

---
#### `signup(req,res)`
Diese Methode verwaltet den Prozess für die Erstellung eines Nutzers.

- **Parameter:**
    - **req** (Object):  request body 
    - **res** (Object):  response body

---
#### `signin(req,res) `
In dieser Methode wird der Login Prozess verwaltet.

- **Parameter:**
    - **req** (Object):  request body  
    - **res** (Object):  response body
---

#### `proofToken(req) `
Diese Methode validiert den Token eines Nutzers.

- **Parameter:**
    - **req** (Object): request body 

- **Returntype:** 
    - bool

<br>

### dateParser.js
In diesem Modul wird das Format des Datums angepasst.

---
#### `convertMonthDataToIsoFormat(dataset)`
Diese Methode bekommt ein Datenset mit invaliden Monatsdaten übergeben, um diese anschließend in ein ISO Format zu konvertieren und zurückzugeben.

- **Parameter:**
    - **dataset** (Object): Zeitreihen
- **Returntyp:**
    - dataset 
- **Returns:** 
    - konvertierter Datensatz

---
#### `convertQuarterDataToIsoFormat(dataset)`
Diese Methode bekommt ein Datenset mit invalden Quartalsdaten übergeben, um diese anschließend in ein ISO Format zu konvertieren und zurückzugeben.

- **Parameter:**
    - **dataset** (Object): Zeitreihen
- **Returntyp:**
    - dataset 
- **Returns:** 
    - konvertierter Datensatz

---
#### `convertYearDataToIsoFormat(dataset)`
Diese Methode bekommt ein Datenset mit invaliden Jahresdaten übergeben, um diese anschließend in ein ISO Format zu konvertieren und zurückzugeben.

- **Parameter:**
    - **dataset** (Object): Zeitreihe
- **Returntyp:**
    - dataset 
- **Returns:** 
    - konvertierter Datensatz

<br>

### kpiCalculation.js  
---
#### `kpiCalculation(req,entry)`
Diese Methode berechnet für eine übergebene Zeitreihe eine Kennzahl, die entweder Summe, Mittelwert, Median, Höchst- oder Tiefstwert sein kann.

- **Parameter:**
    - **req** (Object): Request Body
    - **entry** (Object): Zeitreihe
- **Returntyp:**
    - double 
- **Returns:** 
    - berechnete Kennzahl

<br>

## Middlewares    
Spezifische Middleware Komponenten für die Authentifizierung und Erstellung von Nutzern.

### authJwt.js   
In diesem Modul wird geprüft, ob ein Nutzer die Adminrechte besitzt und authorisiert ist.

---
#### `verifyToken(req,res,next)`
Prüft ob ein Nutzer authorisiert ist und gibt falls nicht eine entsprechende Meldung aus.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body
    - **next** (TODO): express.NextFunction
---
#### `isAdmin(req, res, next)`
Prüft ob ein Nutzer über die Adminrechte verfügt und gibt falls nicht eine entsprechende Meldung aus.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body
    - **next** (TODO): express.NextFunction

<br>

### verifySignUp.js     
In diesem Modul wird beim Erstellen eines neuen Nutzers geprüft, ob die angegebene E-mail Adresse schon im System existiert.

---
#### `checkDuplicateEmail(req,res,next)`
Diese Methode prüft, ob eine E-mail Adresse schon im System existiert.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body
    - **next** (TODO): express.NextFunction

<br>

## Mongoose  
Enthält alle Schemas Definitionen für die MongoDB.
### Role.js  
Beschreibt das Schema der Rollen für die MongoDB.
### Sites.js  
Beschreibt das Schema der Seiten für die MongoDB.
### Table.js  
Beschreibt das Schema der Tabellen für die MongoDB.
### User.js   
Beschreibt das Schema der Nutzer für die MongoDB.

<br>

## Router  

### Routes  

#### auth.js   
Konfiguration der Schnittstellen für die Athentifizierung.

---
##### `POST signUp`  
Diese Methode erstellt einen neuen Nutzer.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body
---
##### `POST signIn`  
Erstellt clientseitig einen Cookie, falls der User authorisiert ist.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

<br>

#### db.js
Konfiguration der Schnittstellen für die Dateninteraktion.

---
##### `GET isAuth`  
Prüft, ob der Nutzer authorisiert ist.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `GET getEntries`  
Gibt alle Tabellen zurück.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `GET getUsers`  
Gibt alle Nutzer zurück.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `GET deleteUser`  
Löscht einen übergebenen Nutzer.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `GET getEntry`  
Liefert eine Zeitreihe oder eine Kennzahl zu einem bestimmten Tabellennamen zurück.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `GET getLastTimestamp`  
Liefert den jüngsten Zeitstempel einer Tabelle zu einem bestimmten Tabellennamen zurück.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `GET getAllTableNames`  
Liefert die Tabellennamen von allen Tabellen zurück.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `GET getTableNamesByTimeRange`  
Liefert die Tabellennamen von allen Tabellen nach Zeitraum (Monat, Quartal, Jahr) gefiltert zurück.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `POST insertEntry`  
Let eine Zeitreihe und ihre PArameter an.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `POST addSite`  
Erstellt eine Seite an.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `GET getSite`  
Gibt alle Seiten zurück. Falls ein Seitenname übergeben wurde, nur eine bestimmte Seite.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `GET getSite`  
Gibt alle Seiten zurück. Falls ein Seitenname übergeben wurde, nur eine bestimmte Seite.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `GET editSite`  
Ersetzt bisherigen Seitenname einer Seite mit einem neuen Seitenname.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

---
##### `GET deleteSite`  
Löscht alle Seiten. Falls ein Seitenname übergeben wurde, wird nur die letzte Seite gelöscht.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body

<br>

### index.js  
Deckt allgemeine Middleware Funktionen ab.

<br>

#### app.js
Initialer Start des Servers und Einstellung aller notwendigen Parameter.


