## Aufgabe 1: Der Datenbank-Architekt (Datenmodellierung)
Entwirf und erstelle zwei Datenbanktabellen. Überlege selbst, welche Datentypen sinnvoll sind.
- Fächer (Subjects): Sollte den Namen des Fachs speichern (z.B. „Mathe“).
- Hausaufgaben (Homework):
    - Muss Titel und Beschreibung enthalten.
    - Muss ein Fälligkeitsdatum haben.
    - Muss speichern können, ob die Aufgabe „erledigt“ ist oder nicht.
    - Wichtig: Stelle eine Verknüpfung her! Eine Hausaufgabe gehört immer zu einem Fach (1:n Beziehung).
   
## Aufgabe 2: Der schnelle Start (Prototyping)
Niemand schreibt heute mehr Standard-Code von Hand.
- Nutze das Gii-Tool, um für beide Tabellen Models und CRUD-Controller zu generieren.
- Ziel: Du solltest danach im Browser Fächer und Hausaufgaben anlegen, bearbeiten und löschen können.

## Aufgabe 3: Die Geschäftslogik (Das Herzstück)
Jetzt musst du programmieren. Die generierten Models sind „dumm“ – mach sie schlau!
- Beziehungen: Bringe dem Hausaufgaben-Model bei, wer sein „Fach“ ist. Nutze dazu eine hasOne-Beziehung in der Model-Klasse.
- Warnsystem: Schreibe eine Funktion im Model, die prüft, ob eine Hausaufgabe überfällig ist (Datum in der Vergangenheit UND noch nicht erledigt).

## Aufgabe 4: Das Dashboard (Controller & View)
Der Kunde möchte nicht in Tabellen suchen. Er will eine Übersicht unter /index.php?r=homework/dashboard.
- Controller: Erstelle eine neue Action im HomeworkController.
- Datenbeschaffung: Lade dort nur die Hausaufgaben, die noch nicht erledigt sind. Sortiere sie so, dass die dringendsten oben stehen.
    - Tipp: Nutze find(), where() und orderBy().
- Anzeige (View): Gib die Daten in einer HTML-Liste oder Tabelle aus.
    - Zeige den Fach-Namen an (nicht die ID!).
    - Wenn eine Aufgabe überfällig ist, soll sie rot markiert werden (nutze deine Funktion aus Aufgabe 3).
