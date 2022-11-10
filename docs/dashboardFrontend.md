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

#### AreaChart.jsx
---
##### `getData(data)`
Ruft die Datenreihen gefiltert nach Name, Anfang und Ende ab.

- **Parameter:**
    - **data (Object):** Datenreihen des Modells.

#### BarChart.jsx
---
##### `getData(data)`
Ruft die Datenreihen gefiltert nach Name, Anfang und Ende ab.

- **Parameter:**
    - **data (Object):** Datenreihen des Modells.

#### LineChart.jsx
---
##### `getData(data)`
Ruft die Datenreihen gefiltert nach Name, Anfang und Ende ab.

- **Parameter:**
    - **data (Object):** Datenreihen des Modells.


#### ScatterChart.jsx
---
##### `getData(data)`
Ruft die Datenreihen gefiltert nach Name, Anfang und Ende ab.

- **Parameter:**
    - **data (Object):** Datenreihen des Modells.


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


#### StepOne.jsx
Im ersten Schritt wird die Zeitreihe und der Titel des zu erstellenden Elements übergeben.

---
##### `goToStepTwo()`
Validierung und Übergang zu Schritt zwei.


#### StepTwo.jsx
Im zweiten Schritt wird entschieden, ob ein Diagramm-, Freitext- oder Kennzahl-Element erstellt wird.

---
##### `goToStepThree()`
Gehe zu Schritt drei und füge Datum zu ElementBody hinzu.


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
Neue Elemente nach Texteingabe speichern.





### AddNewUser.jsx  
### AddNewAdminPage.jsx  
### CreateNewModel.jsx
### DeleteAdminPage.jsx
### DeleteElementDialog.jsx
### DeleteUser.jsx
### DropdownPrognosis.jsx
### EditAdminPageName.jsx
### index.jsx
### KPIContainer.jsx 
### LoginButton.jsx
### LogoutButton.jsx
### Navbar.jsx
### Sidebar.jsx
### Text.jsx
### Wizard.jsx

## Contexts
### contextProvider.js

## Pages
### Admin.jsx
### CustomPrognosis.jsx
### Dashboard.jsx
### Login.jsx
### Useradministration.jsx

## App.js






#### WizardSteps

##### Drop

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
---
