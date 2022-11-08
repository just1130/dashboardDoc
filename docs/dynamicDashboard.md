# Dynamic Dashboard
Im Folgenden werden die einzelnen Unter-Ordner, Skripte und Dateien aus dem Ordner Frontend vorgestellt. 


## Helper
### auth.js
Dieses Modul verwaltet die Authentifizierung des Login und die Validierung der verschiedenenen User.

---
#### `signup(req,res)`
Diese Methode verwaltet den Login Prozess für eine Anfrage.

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
Diese Methode validiert einen Nutzer.

- **Parameter:**
    - **req** (Object): request body 

- **Returntype:** 
    - bool
---

### config.js
```
  module.exports = {
    secret: "dpenzuqq-iabutv-oyj"
 }
```

### dateParser.js
In diesem Modul wird das Format des Datums angepasst

---
#### `convertMonthDataToIsoFormat(dataset)`
Diese Methode bekommt ein Datenset mit Monatsdaten in String Format übergeben, um diese anschließend in ein ISO Format zu konvertieren und zurückzugeben.

- **Parameter:**
    - **dataset** (Object): Zeitreihen
- **Returntyp:**
    - dataset 
- **Returns:** 
    - konvertierter Datensatz
---
#### `convertQuarterDataToIsoFormat(dataset)`
Diese Methode bekommt ein Datenset mit Quartalsdaten in String Format übergeben, um diese anschließend in ein ISO Format zu konvertieren und zurückzugeben.

- **Parameter:**
    - **dataset** (Object): Zeitreihen
- **Returntyp:**
    - dataset 
- **Returns:** 
    - konvertierter Datensatz
---
#### `convertYearDataToIsoFormat(dataset)`
Diese Methode bekommt ein Datenset mit Jahresdaten in String Format übergeben, um diese anschließend in ein ISO Format zu konvertieren und zurückzugeben.

- **Parameter:**
    - **dataset** (Object): Zeitreihe
- **Returntyp:**
    - dataset 
- **Returns:** 
    - konvertierter Datensatz


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
---

## Middlewares    
TODO

### authJwt.js   
In diesem Modul wird geprüft, ob ein Nutzer die Adminrechte besitzt und authorisiert ist

---
#### `verifyToken = (req,res,next) =>`
Prüft ob ein Nutzer authorisiert ist und gibt falls nicht eine entsprechende Meldung aus.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body
    - **next** (TODO): express.NextFunction
---
#### `isAdmin = (req, res, next) =>`
Prüft ob ein Nutzer über die Adminrechte verfügt und gibt falls nicht eine entsprechende Meldung aus.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body
    - **next** (TODO): express.NextFunction



### verifySignUp.js     
In diesem Modul wird beim Erstellen eines neuen Nutzers geprüft, ob die angegebene E-mail Adresse schon im System existiert.

---
#### `checkDuplicateEmail = (req,res,next) => `
Diese Methode prüft, ob eine E-mail Adresse schon im System existiert.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body
    - **next** (TODO): express.NextFunction


## Mongoose  
TODO
### Role.js  


### Sites.js
### Table.js
### User.js

## Router  
TODO
### Routes  
TODO
#### auth.js   
TODO

---
##### `POST signUp`  
Diese Methode erstellt einen neuen Nutzer.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body
    - **next** (TODO): express.NextFunction
---
##### `POST signIn`  
Erstellt clientseitig einen Cookie, falls der User authorisiert ist.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body


#### db.js
TODO

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
Löscht einen bestimmten Nutzer.

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
##### `GET insertEntry`  
TODO

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body
---
##### `GET addSite`  
Erstellt eine Seite an.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body
---
##### `GET addSite`  
Erstellt eine neue Seite.

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
---
##### `GET deleteSiteNull`  
Löscht die null Seite.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body



### index.js  
TODO

---
##### `POST *`  
Prüft ob der Body im Json Format ist und routet alle POST Calls TODO.

- **Parameter:**
    - **req** (Object): Request Body
    - **res** (Object): Response Body



## app.js
TODO


