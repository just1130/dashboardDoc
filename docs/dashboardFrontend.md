# Frontend 
Im Folgenden werden die einzelnen Unter-Ordner, Skripte und Dateien aus dem Ordner Frontend vorgestellt. 

## public
Hier sind die installierten Module abgelegt.

## src

### components

#### Charts

---
##### `getData(data)`
Ruft die Datenreihen gefiltert nach Name, Anfang und Ende ab.

- **Parameter:**
    - **data (Object):** Datenreihen des Modells.
---

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

##### StepOne

---
##### `goToStepTwo()`
Validierung und Übergang zu Schritt zwei.
---

##### StepTwo

---
##### `goToStepThree()`
Gehe zu Schritt drei und füge Datum zu ElementBody hinzu.
---

##### StepThree

---
##### `goToStepFour()`
Gehe zu Schritt drei und füge Datum zu ElementBody hinzu.
---

##### `closeWizard()`
Wenn 'Text' gewählt wurde, wird der Wizard an dieser Stelle beendet.
---

##### `saveElements()`
Neue Elemente nach Texteingabe speichern.
---

##### StepFour

---
##### `onBeforeRender()`
GRenderfunktion für die Tooltip-Komponente.
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
Wird verwendet, nachdem der Benutzer auf die Schaltfläche add geklickt hat, um eine neue Datenreihe hinzuzufügen..

- **Parameter:**
    - **key (Number):** Position.
---

##### `prognosisChecked(key)`
Ändert den Status der Prognose-Checkox.

- **Parameter:**
    - **key (Integer):** Status.
---

---
##### `closeStepWizard()`
Schließt den Assistenten und fügt Daten zum Elementbody hinzu.
---

---
##### `validated()`
Wird vor dem Speichern aufgerufen, um die Benutzereingaben zu überprüfen.
---

##### `deleteDataEntry(key)`
Löschen einer Zeitreihe.

- **Parameter:**
    - **key (Integer):** Zeitreihe.
---

##### StepFive

---
##### `closeStepWizard()`
Ruft die Tabellennamen ab.

- **Parameter:**
    - **data (Object):** Datenreihen des Modells.
---