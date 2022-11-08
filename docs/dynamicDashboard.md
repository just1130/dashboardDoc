# Dynamic Dashboard
Im Folgenden werden die einzelnen Unter-Ordner, Skripte und Dateien aus dem Ordner Frontend vorgestellt. 

ignorierte Ordner:  
.vscode  
Dockerfile  
package-lock.json  
package.json  




## helper
### auth
Dieses Modul verwaltet die Authentifizierung des Login und die Validierung der verschiednenen User.

---
#### `signup(req,res)`
Diese Methode verwaltet den Login Prozess für eine Anfrage

- **Parameter:**
    - **req** (Object): The request body 
    - **res** (Object): The response body
---

#### `signin(req, res) `
In dieser Methode wird der Login Prozess verwaltet.

- **Parameter:**
    - **req** (Object): The request body  
    - **res** (Object): The response body
---

#### `proofToken(req) `
Diese Methode Validiert einen Nutzer.

- **Parameter:**
    - **req** (Object): The request body 

- **Returntype:** 
    - bool
---

### config
```
  module.exports = {
    secret: "dpenzuqq-iabutv-oyj"
 }
```

### dateParser
In diesem Modul wird das Format des Datums angepasst

---
#### `convertMonthDataToIsoFormat(dataset)`
Diese Methode bekommt ein Datenset mit Monatsdaten in String Format übergeben, um diese anschließend  in ein ISO Format zu konvertieren und zurückzugeben.

- **Parameter:**
    - **dataset** (Object): The request body 

- **Returntype:** 
    - bool
---
#### `convertQuarterDataToIsoFormat(dataset)`
Diese Methode konvertiert ein Quartalsdatum als String in ein ISO Format.

- **Parameter:**
    - **dataset** (Object): The request body 

- **Returntype:** 
    - bool
---

### kpiCalculation




## middlewares


## mongoose


## router
### routes
#### auth 
#### db
### index

## app.js


