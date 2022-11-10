# Frontend 
Im Folgenden werden die einzelnen Unter-Ordner, Skripte und Dateien aus dem Ordner Frontend vorgestellt. 

## public

-> dashboardFrontend -> dashboard -> src 

## Components
### Charts
In diesem Ordner sind die Components für die verschiedenen Diagramme hinterlegt. 


#### AcfandPacf.jsx
---
##### `getData(data)`
Ruft die Datenreihen gefiltert nach Name, Anfang und Ende ab.

- **Parameter:**
  - **data (Object):** Datenreihen des Modells.
<br>

#### AreaChart.jsx
---
##### `getData(data)`
Ruft die Datenreihen gefiltert nach Name, Anfang und Ende ab.

- **Parameter:**
    - **data (Object):** Datenreihen des Modells.
<br>

#### BarChart.jsx
---
##### `getData(data)`
Ruft die Datenreihen gefiltert nach Name, Anfang und Ende ab.

- **Parameter:**
    - **data (Object):** Datenreihen des Modells.
<br>

#### LineChart.jsx
---
##### `getData(data)`
Ruft die Datenreihen gefiltert nach Name, Anfang und Ende ab.

- **Parameter:**
    - **data (Object):** Datenreihen des Modells.
<br>

#### ScatterChart.jsx
---
##### `getData(data)`
Ruft die Datenreihen gefiltert nach Name, Anfang und Ende ab.

- **Parameter:**
    - **data (Object):** Datenreihen des Modells.
<br>

### WizardSteps
#### Drop.jsx 
---
##### `getTables()`  
Ruft die Tabellennamen ab.      

---
##### `onFiltering(e)`  
Filtert die Dropdown-Einträge.

- **Parameter:**
    - **e (Object):** Suchanfrage.
    
---
##### `onClose()`
Aktualisieren und in den State einfügen.

<br>
   
#### StepOne.jsx
Im ersten Schritt wird die Zeitreihe und der Titel des zu erstellenden Elements übergeben.

---
##### `goToStepTwo()`
Validierung und Übergang zu Schritt zwei.

<br>

#### StepTwo.jsx
Im zweiten Schritt wird entschieden, ob ein Diagramm-, Freitext- oder Kennzahl-Element erstellt wird.

---
##### `goToStepThree()`
Gehe zu Schritt drei und füge Datum zu ElementBody hinzu.

<br>

#### StepThree.jsx
Im dritten Schritt gibt es 3 Fälle:   
- Freitext: Text wird eingegeben und Wizard wird geschlossen
- Kennzahl: Kennzahl-Art wird ausgesucht und es geht zu Schritt 4
- Diagramm: Diagramm-Art wird ausgesucht und es geht zu Schritt 4

---
##### `goToStepFour()`
Gehe zu Schritt drei und füge Datum zu ElementBody hinzu.

---
##### `closeWizard()`
Wenn 'Text' gewählt wurde, wird der Wizard an dieser Stelle beendet.

---
##### `saveElements()`
Neue Elemente nach Texteingabe speichern.

<br>

#### StepFour.jsx
Im vierten Schritt werden die Datenreihen ausgesucht, Kurzbeschreibung beigefügt,  Zeitfilter angepasst (optinal) und entschieden ob die Datenreihe prognostiziert werden soll.

---
##### `onBeforeRender()`
Renderfunktion für die Tooltip-Komponente.

---
##### `triggerRefresh()`
Tooltip nach Schließen des Dropdowns aktualisieren.

---
##### `changeFilterStatus(key, filter)`
Ändert das Date-Objekt für Start und Ende.

- **Parameter:**
    - **key (Number):** Aktuelle Position im Array.
    - **key (Number):** Markierung, wenn Anfang oder Ende geändert wird.
    
---
##### `getTables()`
Ruft alle Tabellennamen aus der Datenbank ab.

---
##### `addRow(key)`
Wird verwendet, nachdem der Benutzer auf der Schaltfläche 'add' geklickt hat, um eine neue Datenreihe hinzuzufügen.

- **Parameter:**
    - **key (Number):** Position.
    
---
##### `prognosisChecked(key)`
Ändert den Status der Prognose-Checkox.

- **Parameter:**
    - **key (Integer):** Status.


---
##### `closeStepWizard()`
Schließt den Assistenten und fügt Daten zum Elementbody hinzu.

---
##### `validated()`
Wird vor dem Speichern aufgerufen, um die Benutzereingaben zu überprüfen.

---
##### `saveElements()`
Neue Elemente speichern.

---
##### `deleteDataEntry(key)`
Löschen einer Zeitreihe.

- **Parameter:**
    - **key (Integer):** Zeitreihe.
<br>

#### StepFive.jsx
Letzter Schritt im StepWizard. Hier wird dem Element optional ein Textfeld hinzugefügt.
Ist das zu erstellende Element ein Diagramm, so wird hier zusätzlich die Achsenbeschriftung hinzugefügt.

---
##### `closeStepWizard()`
Schließt den Assistenten und fügt Daten zum Elementbody hinzu.

---
##### `validated()`
Wird vor dem Speichern aufgerufen, um die Benutzereingaben zu überprüfen.

---
##### `saveElements()`
Neue Elemente speichern.

<br>

### AddNewUser.jsx  
Legt neue Benutzer an.

---
#### `saveNewUser()`
Sendet den neuen Benutzer an das NodeJS Backend.

---
#### `validatedEmail()`
Validiert die E-Mail Adresse. 

---
#### `validatedPw()`
Validiert das Passwort.
<br>

### AddNewAdminPage.jsx  
In diesem Component wird eine neue Admin Seite angelegt.

---
#### `saveNewPage()`
Sendet eine bestimmte Seite an das Backend und die Variablen werden geupdatet. 

---
#### `duplicate(siteName)`
In dieser Methode wird geprüft, ob schon eine Seite mit dem übergebenem Seitennamen existiert.

- **Parameter:**
    - **siteName** (String): Seitenname
- **Returntyp:**
    - Bool
- **Returns:** 
    - Gibt zurück ob eine Seite mit diesem Namen schon existiert

<br>

### CreateNewModel.jsx
TODO 

---
#### `calculateNewModel()`
TODO 
   
---
#### `saveModel()`
TODO 

<br>

### DeleteAdminPage.jsx
Startet den Löschvorgang von Adminseiten.

---
#### `deletePage ()`
Übergibt den Seitennamen, der zu löschenden Seite an das Backend und alle Variablen werden geupdatet.

<br>

### DeleteElementDialog.jsx
Startet den Löschvorgang von einer Kachel einer Adminseite.

---
#### `deleteElement()`
Übergibt eine zu löschende Kachel an das Backend und alle Variablen werden geupdatet.

<br>

### DeleteUser.jsx
Startet den Löschvorgang eines Nutzers.

---
#### `deleteUser()`
Übergibt einen zu löschenden Nutzer an das Backend und alle Variablen werden geupdatet.

<br>

### DropdownPrognosis.jsx
Enthält die Logik für die Dropdownliste der Zeitreihen auf der Prognose Seite.

---
#### `getTables()`
Liefert alle Tabellennamen zurück.

---
#### `onFiltering(e)`
Filtert die Dropdown-Einträge.

- **Parameter:**
    - **e:(Object)** Suchanfrage.

---
#### `onBeforeRender()`
Renderfunktion für die Tooltip-Komponente.

---
#### `onClose()`
Aktualisieren und in den State einfügen.

<br>

### EditAdminPageName.jsx
Ändert den Seitennamen.



---
#### `editPage(newName)`
Prüft, ob schon eine Seite mit dem übergebenem Seitennamen existiert.

- **Parameter:**
    - **newName** (String): neuer Seitenname

---
#### `duplicate(siteName)`
Prüft, ob schon eine Seite mit dem übergebenem Seitennamen existiert.

- **Parameter:**
    - **siteName** (String): Seitenname
- **Returntyp:**
    - Bool
- **Returns:** 
    - Gibt zurück ob eine Seite mit diesem Namen schon existiert

<br>

### KPIContainer.jsx 
TODO

---
#### `getData(data)`
Gibt alle Kennzahlen nach Namen, Start und Enddatum gefiltert zurück.
TODO Passt das so?

- **Parameter:**
    - **data** (Object[]): Metadaten aller Tabellen 
- **Returntyp:**
    - 
- **Returns:** 
   
<br>

### LoginButton.jsx
Logik und Design des LoginButtons.

<br>

### LogoutButton.jsx
Logik und Design des LogoutButtons.

---
#### `logout()`
Meldet einen angemeldeten Nutzer ab.

<br>

### Navbar.jsx
Design der Navbar.

<br>

### Sidebar.jsx
Design und Interaktion der Sidebar.

<br>

---
#### `handleCloseSideBar ()`
Klappt die Sidebar ein.

---
#### `changeSite ()`
Wechselt die Ansicht des Dashboards auf eine übergebene Seite und aktualisert die Elemente. 

- **Parameter:**
    - **siteName** (String): Seitenname 

---
#### `sideBarClick(siteName)`
TODO

- **Parameter:**
    - **siteName** (String): TODO 

<br>

### Text.jsx
TODO

### Wizard.jsx
Dialog zum Erstellen und Bearbeiten von Kacheln. Ruft Components aus WizardSteps auf.

---
#### `closeTheWizard()`
Schließt den Dialog und aktualisiert die Elemente.

## Contexts
TODO

<br>

### contextProvider.js
TODO

---
#### `updateSidebarElements()`
Aktualisiert die Seiten der der Sidebar.


---
#### `updateAdminElements(siteName)`
Ruft die Daten der einzelnen Kachlen der zu ladenden Seite ab.

- **Parameter:**
    - **siteName**(String):  Name der zu ladenden Seite


## Pages
Enthält die Components für die einzelnen Seiten in der Navbar und des Logins.

### Admin.jsx
Logik und Design der Adminseite.

---
#### `checkAdminSite(body)`
TODO

- **Parameter:**
    - **body** (TODO):TODO 
    
---
#### `addNewElement()`
Startet Prozess zum Erstellen einer Kachel.

---
#### `edit(item, key)`
Startet Prozesse zum Bearbeiten einer Kachel.

- **Parameter:**
    - **item** (TODO):TODO 
    - **key** (TODO):TODO  

<br>

### CustomPrognosis.jsx
Ermöglicht es Prognosen detaillierter zu betrachten und Parameter manuell anzupassen.

---
#### `getModelInfos(name)`
TODO

- **Parameter:**
    - **name** (String): TODO

---
#### `setSelectedValue(name, timeInterval)()`
TODO

- **Parameter:**
    - **name** (String):  TODO
    - **timeInterval** (TODO): TODO  
    
---
#### `calculateNewModel()`
TODO

---
#### `saveModel()`
Speichert das neu erstellte Model. TODO

---
#### `updateSelectedName (name)`
TODO

- **Parameter:**
    - **name** (String):  TODO

<br>

### Dashboard.jsx
Zeigt die erstellten Kacheln.

---
#### `checkAdminSite(adminSite)`
Prüft, ob Änderungen an der übergebenen Seite vorgenommen wurden und aktualisiert die Seite im Dashboard anschließend.

- **Parameter:**
    - **adminSite** (TODO): TODO

<br>

### Login.jsx
Verwaltet und designt die Anmelde Seite.

---
#### `sendLoginRequest()`
TODO

---
#### `validated()`
Überprüft das Format der E-Mail Adresse.

- **Returntyp:**
    - Bool
- **Returns:*
    - Gibt zurück, ob das Format der E-Mail Adresse gültig ist.
    - 
---
#### `closeDialog()`
Schließt den Dialog und aktualisiert entsprechende Elemente.

<br>

### Useradministration.jsx
Verwaltung der Nutzer.

---
#### `updateUsers ()`
TODO

---
#### `closeWindow ()`
TODO

---
#### `getUsers()`
Ruft alle Nutzer aus der Datenbank ab.

<br>



