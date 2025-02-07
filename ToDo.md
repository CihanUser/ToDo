# 1. Die Vorbereitung: Was soll die App können?

Zu Beginn musste ich mir überlegen, welche Funktionen die To-Do-App bieten soll. Die Aufgabe war klar definiert, aber ich musste herausfinden, wie man es technisch umsetzt. Die grundlegenden Funktionen waren:

- Aufgaben hinzufügen  
- Aufgaben als erledigt markieren  
- Aufgaben löschen  
- Alle Aufgaben auf einmal auswählen oder löschen  
- Die Aufgaben sollten auch nach einem Seitenneuladen im LocalStorage gespeichert bleiben  

---

## 2. Der Aufbau des Grundgerüsts in HTML  

Als ersten Schritt habe ich mit der HTML-Datei begonnen, um das Grundgerüst der App zu erstellen.  
Zuerst habe ich die grundlegenden HTML-Elemente aufgesetzt:

- Ein Textfeld, in das der Benutzer eine neue Aufgabe eingeben kann  
- Ein Button, um diese Aufgabe der Liste hinzuzufügen  
- Eine Liste (`<ul>`), in der alle hinzugefügten Aufgaben angezeigt werden  
- Zwei zusätzliche Buttons:  
  - Einer, um alle Aufgaben auszuwählen (als erledigt zu markieren)  
  - Einer, um alle Aufgaben zu löschen  

Dafür habe ich die Struktur festgelegt und mit Bootstrap gearbeitet, um die Gestaltung zu erleichtern und die App responsiv zu machen.  

---

## 3. Das Design mit CSS  

Nachdem das Grundgerüst mit HTML fertig war, habe ich mich dem Design der App gewidmet, um sicherzustellen, dass sie gut aussieht und benutzerfreundlich ist.  
Dafür habe ich eine separate CSS-Datei verwendet:

- Der Hintergrund der Seite wurde mit einem hellen Farbton gesetzt, um eine angenehme Atmosphäre zu schaffen.  
- Die To-Do-Liste wurde auf eine bestimmte Breite begrenzt und zentriert, damit sie ordentlich auf der Seite aussieht.  
- Aufgaben, die als erledigt markiert sind, habe ich durchgestrichen und in grau gefärbt, damit sie visuell hervorgehoben werden.  
- Es gab auch Fehlermeldungen für den Fall, dass das Eingabefeld leer war oder eine Aufgabe doppelt hinzugefügt wurde.  

---

## 4. Die App mit JavaScript zum Leben erwecken  

Nachdem HTML und CSS fertig waren, habe ich mit JavaScript die Funktionen eingebaut, die die App interaktiv machen.  

### 4.1. Aufgaben hinzufügen (`addTask`)  

Ich habe als erstes die Funktion zum Hinzufügen von Aufgaben erstellt:  

1. Wenn der Benutzer eine Aufgabe eingibt und auf den „Hinzufügen“-Button klickt, wird die Aufgabe zunächst auf Leerzeichen überprüft.  
2. Dann habe ich sichergestellt, dass keine doppelte Aufgabe hinzukommt.  
3. Wenn die Aufgabe korrekt ist, wurde sie mit einer einzigartigen ID versehen und in einem Array gespeichert, das später im LocalStorage abgelegt wird.  

Ich musste dabei sicherstellen, dass die Liste nach dem Hinzufügen der Aufgabe immer aktualisiert wird.  

---

### 4.2. Aufgaben anzeigen (`loadTasks`)  

Um sicherzustellen, dass die Aufgaben auch nach dem Neuladen der Seite angezeigt werden, habe ich eine Funktion (`loadTasks`) programmiert:  

- Diese Funktion holt alle gespeicherten Aufgaben aus dem LocalStorage.  
- Ich habe dann für jede Aufgabe ein neues Listenelement erstellt und es der To-Do-Liste hinzugefügt.  

Damit war die App in der Lage, die Aufgaben anzuzeigen und auch nach einem Seitenneuladen beizubehalten.  

---

### 4.3. Aufgaben als erledigt markieren (`toggleTask`)  

Ein wichtiger Schritt war, die Funktion zum Markieren von Aufgaben als erledigt zu erstellen:  

1. Jede Aufgabe hat nun einen „Erledigt“-Button, der beim Klicken den Status der Aufgabe ändert.  
2. Wenn der Benutzer auf den Button klickt, wird der Status der Aufgabe umgeschaltet (von „erledigt“ auf „nicht erledigt“ und umgekehrt).  
3. Danach wird die Liste im LocalStorage aktualisiert, und die Seite zeigt die Änderungen an.  

Ich habe auch dafür gesorgt, dass die erledigten Aufgaben visuell anders aussehen, also durchgestrichen und grau gefärbt.  

---

### 4.4. Aufgaben löschen (`deleteTask`)  

Ich habe ebenfalls eine Funktion programmiert, um Einzelaufgaben zu löschen:  

- Der Benutzer kann auf einen „Löschen“-Button klicken, um eine Aufgabe aus der Liste zu entfernen.  
- Die Aufgaben werden sowohl aus der Anzeige als auch aus dem LocalStorage entfernt.  

---

### 4.5. Alle Aufgaben auswählen oder löschen (`selectAllTasks`, `deleteAllTasks`)  

Für den Abschluss der App wollte ich Funktionen zum Auswählen oder Löschen aller Aufgaben hinzufügen:  

- Wenn der Benutzer auf „Alle auswählen“ klickt, wird der Status aller Aufgaben auf „erledigt“ oder „zurückgesetzt“ geändert, je nachdem, ob sie alle schon erledigt sind.  
- Der „Alle löschen“-Button entfernt alle Aufgaben aus dem LocalStorage.  

---

## 5. Das Testen und Optimieren  

Nachdem alle Funktionen eingebaut waren, habe ich die App gründlich getestet:  

- Ich habe das Hinzufügen, Markieren und Löschen von Aufgaben ausprobiert, um sicherzustellen, dass alles funktioniert.  
- Außerdem habe ich überprüft, ob die Aufgaben auch nach dem Neuladen der Seite gespeichert sind.  

---

## 6. Fazit und Ausblick  

Die Aufgabe, diese To-Do-App zu entwickeln, war eine sehr gute Übung, um mehr über HTML, CSS und JavaScript zu lernen, insbesondere im Umgang mit LocalStorage. Ich habe gelernt, wie man mit JavaScript interaktive Elemente erstellt und wie man Daten speichert, damit sie auch nach einem Neustart der Seite erhalten bleiben.  

Für die Zukunft könnte ich die App noch erweitern, zum Beispiel:  

- Eine Funktion, um Aufgaben zu bearbeiten  
- Ein schöneres Design oder zusätzliche Funktionen wie Dark Mode  
