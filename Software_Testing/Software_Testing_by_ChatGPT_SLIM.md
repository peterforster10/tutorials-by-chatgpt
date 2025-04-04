# Software Testing – Grundlagen, Methoden und moderne Praxis

## Inhalt

### **Einleitung**
- Zielsetzung und Zielgruppe des Buches
- Bedeutung von Softwarequalität
- Rolle des Software Testings im Entwicklungsprozess
- Überblick über die Kapitel

---

### **Teil I: Grundlagen des Software Testings**

#### Kapitel 1: Einführung in das Software Testing
- Was ist Software Testing?
- Fehler, Bugs und Defekte: Begriffserklärungen
- Qualitätssicherung vs. Testing
- Testziele und -prinzipien

#### Kapitel 2: Testprozess und Testlebenszyklus
- Testplanung
- Testanalyse und -design
- Testimplementierung
- Testdurchführung
- Testauswertung und Abschluss

#### Kapitel 3: Teststufen
- Unit Testing (Modultest)
- Integrationstest
- Systemtest
- Abnahmetest

#### Kapitel 4: Testarten
- Funktionales vs. nicht-funktionales Testing
- Regressionstests
- Smoke & Sanity Tests
- Exploratives Testing
- Ad-hoc Testing

---

### **Teil II: Testmethoden und -techniken**

#### Kapitel 5: Statische und dynamische Testverfahren
- Code Reviews, Walkthroughs, Inspektionen
- Statische Codeanalyse
- Dynamisches Testen im Vergleich

#### Kapitel 6: White-Box-Testing
- Kontrollflussanalyse
- Pfadüberdeckung, Anweisungsüberdeckung
- Werkzeuge für White-Box-Tests

#### Kapitel 7: Black-Box-Testing
- Äquivalenzklassenbildung
- Grenzwertanalyse
- Entscheidungstabellen
- Zustandsbasierte Tests

#### Kapitel 8: Testentwurfsverfahren
- Erfahrungsbasierte Verfahren
- Strukturbasierte Verfahren
- Spezifikationsbasierte Verfahren

---

### **Teil III: Testmanagement und -automatisierung**

#### Kapitel 9: Testmanagement
- Teststrategie und Testkonzept
- Risikobasiertes Testen
- Metriken und Kennzahlen
- Testberichte und Kommunikation

#### Kapitel 10: Testwerkzeuge
- Auswahlkriterien für Tools
- Übersicht wichtiger Tools (JUnit, Selenium, Postman etc.)
- Open-Source vs. kommerzielle Lösungen

#### Kapitel 11: Testautomatisierung
- Was automatisieren – und was nicht?
- Architektur automatisierter Tests
- Frameworks und Best Practices
- Continuous Integration & Testing

---

### **Teil IV: Agile und moderne Testansätze**

#### Kapitel 12: Testing in agilen Projekten
- Testgetriebene Entwicklung (TDD)
- Behavior Driven Development (BDD)
- Rolle des Testers im Scrum-Team

#### Kapitel 13: DevOps und Continuous Testing
- Integration von Testing in DevOps
- Shift-Left- und Shift-Right-Testing
- Test in CI/CD-Pipelines

#### Kapitel 14: Testen von modernen Architekturen
- Testing in Microservices-Umgebungen
- API-Tests
- Cloud-Testing
- Container- und Infrastrukturtests

---

### **Teil V: Qualität, Ethik und Zukunft**

#### Kapitel 15: Softwarequalität ganzheitlich verstehen
- ISO/IEC-25010 Qualitätsmodell
- Usability, Performance, Sicherheit

#### Kapitel 16: Ethik im Software Testing
- Verantwortung des Testers
- Testdaten und Datenschutz
- Manipulation von Testergebnissen

#### Kapitel 17: Zukunft des Software Testings
- KI im Testing
- Self-healing Tests
- No-Code-/Low-Code-Testing-Plattformen
- Trends und Ausblick

  
# **Einleitung**

Software ist aus unserem Leben nicht mehr wegzudenken. Ob beim Online-Banking, im Gesundheitswesen, in Fahrzeugen oder bei der Steuerung industrieller Anlagen – überall spielen digitale Systeme eine zentrale Rolle. Mit dieser zunehmenden Durchdringung wächst auch die Verantwortung der Entwicklerteams, qualitativ hochwertige und verlässliche Software bereitzustellen.

Doch perfekte Software gibt es nicht. Fehler entstehen zwangsläufig – durch Missverständnisse, Zeitdruck, technische Komplexität oder unvollständige Anforderungen. Umso wichtiger ist es, systematisch vorzugehen: durch professionelles **Software Testing**, also das gezielte Planen, Durchführen und Auswerten von Tests, um Qualität messbar und steuerbar zu machen.

## Ziel dieses Buches

Dieses Buch richtet sich an alle, die sich fundiert mit dem Thema Software Testing auseinandersetzen wollen – unabhängig davon, ob sie am Anfang stehen oder bereits praktische Erfahrung gesammelt haben. Es vermittelt:

- **Grundlagenwissen**, das für ein solides Verständnis der Testdisziplin unerlässlich ist
- **Methoden und Techniken**, die in Projekten direkt anwendbar sind
- **Einblicke in moderne Testansätze**, wie sie in agilen und DevOps-orientierten Umgebungen zum Einsatz kommen
- **Werkzeuge, Best Practices und Fallbeispiele**, die helfen, Theorie in die Praxis zu überführen

## Für wen ist dieses Buch?

Dieses Buch ist geschrieben für:

- **Softwaretester:innen**, die ihre Kenntnisse systematisieren oder vertiefen möchten
- **Entwickler:innen**, die Testing als festen Bestandteil ihrer Arbeit verstehen
- **Testmanager:innen**, die Prozesse gestalten und verantworten
- **Studierende**, die sich auf Prüfungen oder den Berufseinstieg vorbereiten
- **IT-Projektverantwortliche**, die Qualität strategisch absichern wollen

Unabhängig von der Rolle ist die zentrale Botschaft: **Testing ist kein lästiges Anhängsel**, sondern ein **essentieller Erfolgsfaktor** für jedes Softwareprojekt.

## Aufbau des Buches

Das Buch ist in fünf Teile gegliedert, die sich inhaltlich logisch aufeinander aufbauen:

1. **Grundlagen des Software Testings** – Begriffsklärungen, Testarten und -stufen, zentrale Prinzipien  
2. **Testmethoden und -techniken** – von klassischen Verfahren bis hin zu strukturierten Entwurfsverfahren  
3. **Testmanagement und -automatisierung** – Planung, Steuerung und technische Umsetzung  
4. **Agile und moderne Testansätze** – TDD, BDD, Continuous Testing und Testen in Microservices  
5. **Qualität, Ethik und Zukunft** – über ISO-Standards, Verantwortung und neue Trends wie KI im Testing

Jedes Kapitel enthält praxisnahe Beispiele, Abbildungen und – sofern sinnvoll – Checklisten oder Übungen, um den Wissenstransfer zu fördern.

---

**Software zu testen heißt, Verantwortung zu übernehmen.** Dieses Buch möchte Sie dabei unterstützen – mit dem nötigen Handwerkszeug, mit Erfahrungswissen und mit einem systematischen Blick auf Qualität.



# **Kapitel 1: Einführung in das Software Testing**

## 1.1 Was ist Software Testing?

Software Testing ist ein zentraler Bestandteil der Qualitätssicherung in der Softwareentwicklung. Es umfasst alle Aktivitäten, die zum Ziel haben, Fehler (auch „Bugs“ oder „Defekte“ genannt) in Softwareprodukten frühzeitig zu erkennen und deren Auswirkungen zu minimieren.

Der Zweck von Tests ist jedoch nicht nur das Finden von Fehlern. Ebenso wichtig ist es, **Vertrauen in die Qualität eines Systems aufzubauen**. Tests liefern die Grundlage für fundierte Entscheidungen – etwa, ob eine Software in Produktion gehen kann oder ob sie überarbeitet werden muss.

**Definition (nach ISTQB):**  
*Software Testing ist der Prozess, bestehend aus allen Lebenszyklusaktivitäten – sowohl statisch als auch dynamisch –, die zur Planung, Vorbereitung und Bewertung von Softwareprodukten dienen und darauf abzielen, sicherzustellen, dass sie bestimmten Anforderungen entsprechen.*

## 1.2 Warum ist Testing notwendig?

Software steht im Zentrum unseres Alltags: von Bankensystemen über medizinische Geräte bis zu Mobiltelefonen. Ein Fehler in einem dieser Systeme kann schwerwiegende Folgen haben – von wirtschaftlichen Schäden bis hin zu Gefährdung von Menschenleben.

**Gründe für systematisches Testing:**
- Frühzeitige Erkennung von Fehlern
- Reduzierung von Risiken
- Sicherstellung der Erfüllung von Anforderungen
- Verbesserung der Benutzerfreundlichkeit
- Unterstützung von Wartbarkeit und Weiterentwicklung

Ein nicht entdeckter Fehler im Produktionsbetrieb ist in der Regel **teurer und aufwändiger** zu beheben als ein frühzeitig identifizierter Fehler.

## 1.3 Fehler, Bugs und Defekte: Begriffsklärung

In der Literatur und Praxis werden verschiedene Begriffe verwendet, um Unstimmigkeiten in Software zu beschreiben:

| Begriff      | Bedeutung |
|--------------|-----------|
| **Fehler (Error)** | Eine menschliche Handlung, die zu einem Problem im Code führt (z. B. ein Tippfehler oder ein Denkfehler beim Design). |
| **Defekt (Defect/Fault)** | Eine konkrete Anomalie im Code oder Design, die durch einen Fehler verursacht wurde. |
| **Fehlverhalten (Failure)** | Ein beobachtbares falsches Verhalten der Software zur Laufzeit, das durch einen Defekt verursacht wird. |

## 1.4 Testziele

Je nach Projektphase, Kontext und Zielgruppe variieren die Ziele des Testens:

- **Fehleraufdeckung:** Finden möglichst vieler Fehler vor dem Release.
- **Qualitätssicherung:** Sicherstellen, dass Anforderungen erfüllt werden.
- **Verifikation und Validierung:**  
   - *Verifikation*: „Bauen wir das Produkt richtig?“  
   - *Validierung*: „Bauen wir das richtige Produkt?“
- **Vertrauensbildung:** Nachweis, dass das System zuverlässig funktioniert.
- **Wissensgewinn:** Verständnis über das Verhalten des Systems unter verschiedenen Bedingungen.

## 1.5 Testprinzipien

Die folgenden Prinzipien gelten als grundlegende Leitlinien im Software Testing:

1. **Testing zeigt die Präsenz von Fehlern, nicht deren Abwesenheit.**  
   Auch wenn keine Fehler gefunden werden, kann man nicht garantieren, dass das System fehlerfrei ist.

2. **Ausgiebiges Testen ist nicht möglich.**  
   Die Anzahl möglicher Eingaben, Abläufe und Zustände ist meist zu groß – deshalb ist gezielte Auswahl entscheidend.

3. **Frühes Testen spart Zeit und Geld.**  
   Fehler, die früh entdeckt werden, sind günstiger zu beheben.

4. **Häufung von Fehlern (Fehlercluster).**  
   Fehler treten oft in bestimmten Modulen oder Funktionen gehäuft auf.

5. **Pestizid-Paradoxon.**  
   Immer gleiche Tests finden irgendwann keine neuen Fehler – Tests müssen regelmäßig überprüft und angepasst werden.

6. **Testen ist kontextabhängig.**  
   Sicherheitskritische Systeme erfordern andere Teststrategien als etwa Webshops.

7. **Irrtum des Fehlens.**  
   Ein fehlerfreies System, das jedoch die Anforderungen nicht erfüllt, ist ebenfalls mangelhaft.



# **Kapitel 2: Testprozess und Testlebenszyklus**

## 2.1 Überblick über den Testprozess

Der Testprozess ist ein strukturierter Ablauf von Aktivitäten, die sicherstellen sollen, dass ein Softwareprodukt den definierten Anforderungen entspricht und erwartungsgemäß funktioniert. Ein klar definierter Testprozess erhöht die Effizienz, Wiederholbarkeit und Nachvollziehbarkeit von Tests – und trägt somit maßgeblich zur Qualitätssicherung bei.

Der Standard-Testprozess umfasst typischerweise folgende Phasen:

1. **Testplanung und Steuerung**
2. **Testanalyse und Testentwurf**
3. **Testrealisierung und -implementierung**
4. **Testdurchführung**
5. **Testabschluss**

Diese Phasen bilden gemeinsam den sogenannten **Testlebenszyklus**.

## 2.2 Testplanung und Steuerung

In der Planungsphase werden die Grundlagen für die Testaktivitäten gelegt. Ziel ist es, die Teststrategie zu definieren, Ressourcen einzuplanen und die Qualitätssicherungsziele des Projekts zu unterstützen.

**Typische Inhalte der Testplanung:**

- Testziele und Testumfang
- Auswahl der Testmethoden und -werkzeuge
- Risikobewertung und Priorisierung
- Zeit- und Ressourcenplanung
- Definition von Ein- und Austrittskriterien (Entry/Exit Criteria)
- Zuweisung von Rollen und Verantwortlichkeiten

**Teststeuerung** ist ein fortlaufender Prozess während des gesamten Projekts. Hier wird regelmäßig geprüft, ob der Testfortschritt mit der Planung übereinstimmt. Bei Abweichungen erfolgt eine Anpassung der Planung.

## 2.3 Testanalyse und Testentwurf

In dieser Phase werden die Testbasis (z. B. Anforderungen, Designspezifikationen) analysiert und daraus konkrete Testbedingungen, Testfälle und Testdaten abgeleitet.

**Ziele der Testanalyse:**

- Verstehen, was getestet werden soll
- Ableitung von Testbedingungen aus der Testbasis
- Ermittlung von Testabdeckung und Risiken

**Testentwurf:**  
Basierend auf den Testbedingungen werden konkrete Testfälle erstellt. Dabei werden auch Eingabedaten, erwartete Ergebnisse und Abdeckungsgrade definiert.

## 2.4 Testimplementierung und -realisierung

In dieser Phase werden die Testfälle technisch umgesetzt, Testsuiten organisiert und die Testumgebung vorbereitet.

**Typische Aktivitäten:**

- Detaillierte Ausformulierung der Testfälle
- Vorbereitung oder Generierung von Testdaten
- Aufbau bzw. Konfiguration der Testumgebung
- Automatisierung von Testfällen (wo sinnvoll)
- Pflege der Rückverfolgbarkeit (Traceability) zu Anforderungen

Ein strukturierter Aufbau der Testartefakte erleichtert spätere Wiederverwendung und Wartung der Tests.

## 2.5 Testdurchführung

Die eigentliche Testausführung beginnt, sobald die Testumgebung bereit ist und alle Voraussetzungen erfüllt sind.

**Ablauf der Testdurchführung:**

- Ausführung der vorbereiteten Testfälle
- Protokollierung der Testergebnisse
- Vergleich der tatsächlichen mit den erwarteten Ergebnissen
- Identifikation und Dokumentation von Abweichungen (Fehlverhalten)
- Meldung von Defekten an das Entwicklungsteam

Ein gutes Defektmanagement ist entscheidend für eine effiziente Fehlerbehebung und Kommunikation zwischen Test und Entwicklung.

## 2.6 Testabschluss

Nach der Durchführung der geplanten Tests wird der Testprozess abgeschlossen und die Ergebnisse ausgewertet.

**Abschlussaktivitäten:**

- Bewertung des erreichten Testabdeckungsgrads
- Überprüfung, ob alle Ein-/Austrittskriterien erfüllt wurden
- Erstellung von Abschlussberichten
- Archivierung von Testartefakten
- Lessons Learned und Verbesserungsvorschläge für zukünftige Projekte

Der Testabschluss markiert nicht nur das Ende einer Phase, sondern liefert auch wertvolle Erkenntnisse zur kontinuierlichen Prozessverbesserung.

## 2.7 Iterativer Testprozess in der Praxis

In klassischen Wasserfallprojekten erfolgt der Testprozess sequenziell. In agilen Projekten hingegen ist der Testlebenszyklus **inkrementell und iterativ**: Testplanung, Testentwurf und Testdurchführung finden kontinuierlich und parallel zur Entwicklung statt. Dabei gewinnen frühe Rückmeldung und schnelles Reagieren auf Änderungen an Bedeutung.

Ein agiler Testprozess folgt dem Prinzip: **„Testen ist integraler Bestandteil der Entwicklung“**, nicht ein nachgelagerter Schritt.

## 2.8 Rollen im Testprozess

Im professionellen Testprozess wirken verschiedene Rollen zusammen:

- **Tester:innen**: Erstellung, Durchführung und Auswertung von Tests
- **Testmanager:innen**: Planung, Steuerung und Berichterstattung
- **Entwickler:innen**: Durchführung von Unit-Tests, Analyse von Defekten
- **Produktverantwortliche**: Definition von Testakzeptanzkriterien
- **Automatisierungsspezialist:innen**: Umsetzung und Wartung von Testskripten

Eine klare Rollendefinition fördert reibungslose Abläufe und unterstützt die Zusammenarbeit im Team.

---

**Zusammenfassung:**  
Ein systematischer Testprozess bildet das Rückgrat effektiver Qualitätssicherung. Er schafft Struktur, Transparenz und ermöglicht fundierte Entscheidungen. Gleichzeitig muss er flexibel genug sein, um sich an verschiedene Projektmethoden und Technologien anpassen zu lassen.



# **Kapitel 3: Teststufen**

## 3.1 Einführung in die Teststufen

Ein professionelles Testvorgehen gliedert sich in verschiedene Ebenen, sogenannte **Teststufen**. Jede dieser Stufen fokussiert auf einen spezifischen Ausschnitt des Gesamtsystems – von einzelnen Programmteilen bis hin zum fertigen Produkt im Einsatzkontext. Die Unterteilung ermöglicht eine gezielte Fehlererkennung und unterstützt die Modularität des Testens.

Die klassischen Teststufen sind:

1. **Modultest (Unit Test)**
2. **Integrationstest**
3. **Systemtest**
4. **Abnahmetest (Acceptance Test)**

Je nach Projektkontext – z. B. bei agilen Methoden oder bei Microservices – können zusätzliche, angepasste Stufen definiert werden.

## 3.2 Modultest (Unit Testing)

Der Modultest prüft **einzelne Komponenten oder Funktionen** des Codes in Isolation. Ziel ist es, sicherzustellen, dass jede einzelne Einheit wie erwartet funktioniert.

**Typische Merkmale:**

- Fokus auf einzelne Methoden oder Klassen
- Verwendung von Mocks/Stubs zur Isolierung
- Hoher Automatisierungsgrad
- Sehr schnelle Ausführung

**Beispiel:**  
Eine Methode zur Berechnung von Mehrwertsteuer wird mit verschiedenen Eingabewerten getestet.

**Werkzeuge:**  
JUnit (Java), NUnit (.NET), PyTest (Python), Jest (JavaScript)

Modultests werden in der Regel **vom Entwicklungsteam selbst geschrieben und ausgeführt**.

## 3.3 Integrationstest

Im Integrationstest wird überprüft, **wie mehrere Komponenten miteinander interagieren**. Es geht um Schnittstellen, Datenflüsse und die Kommunikation zwischen Modulen.

**Typische Ansätze:**

- **Big Bang**: Alle Komponenten werden gleichzeitig integriert
- **Inkrementell**: Schrittweise Integration (top-down, bottom-up oder sandwich)

**Ziele:**

- Aufdecken von Schnittstellenproblemen
- Sicherstellen von korrekter Datenweitergabe
- Überprüfung von Protokollen und API-Aufrufen

**Beispiel:**  
Ein Login-Modul wird zusammen mit der Benutzerverwaltung getestet, um sicherzustellen, dass Nutzer korrekt authentifiziert und autorisiert werden.

Integrationstests können **teilweise automatisiert** durchgeführt werden, erfordern jedoch meist mehr Aufwand als Unit-Tests.

## 3.4 Systemtest

Der Systemtest betrachtet die **Software als Ganzes**, inklusive aller Komponenten und externen Schnittstellen, in einer möglichst realitätsnahen Umgebung.

**Ziel:**  
Feststellen, ob das Gesamtsystem die spezifizierten funktionalen und nicht-funktionalen Anforderungen erfüllt.

**Typische Inhalte:**

- Funktionale Testszenarien
- Last- und Performancetests
- Sicherheitsüberprüfungen
- Usability-Tests

**Beispiel:**  
Ein Onlineshop wird als komplette Anwendung getestet – vom Warenkorb über die Zahlungsabwicklung bis zur Bestellbestätigung per E-Mail.

Systemtests sind häufig **nicht durch Entwickler:innen**, sondern durch spezialisierte **Tester:innen oder QA-Teams** durchzuführen.

## 3.5 Abnahmetest (Acceptance Testing)

Der Abnahmetest ist die **letzte Stufe vor der Produktivsetzung**. Hier prüft der Kunde oder ein Stellvertreter, ob die Software den **geschäftlichen Anforderungen** entspricht und einsatzbereit ist.

**Ziele:**

- Bestätigung, dass das System „das Richtige“ liefert
- Identifikation von Abweichungen zur Erwartung
- Grundlage für die Freigabe

**Typen von Abnahmetests:**

- **Benutzerakzeptanztest (UAT)**: Durchführung durch Endnutzer
- **Vertraglicher Abnahmetest**: Gegen vertraglich definierte Anforderungen
- **Regulatorischer Test**: Für sicherheitskritische oder regulierte Umgebungen

**Beispiel:**  
Ein Kunde prüft, ob ein neues Abrechnungssystem alle Geschäftsprozesse korrekt unterstützt und Reports wie erwartet erzeugt werden.

## 3.6 Teststufen in agilen Projekten

In agilen Projekten werden die Teststufen nicht strikt sequentiell durchgeführt, sondern **kontinuierlich integriert**. Besonders betont wird dabei:

- **Automatisiertes Unit-Testing** durch die Entwickler
- **Kontinuierliches Integrationstesten** mit jeder Codeänderung
- **Systemnahe Tests im Sprint** (manuell oder automatisiert)
- **Regelmäßige Akzeptanztests mit dem Product Owner**

Agile Teams nutzen oft das Prinzip **„Test early, test often“**, um Fehler möglichst frühzeitig zu identifizieren.

## 3.7 Zusammenwirken der Teststufen

Die Teststufen bauen logisch aufeinander auf, überlappen sich aber häufig in der Praxis. Wichtig ist, dass **jede Stufe eigene Fehlerarten adressiert**:

| Teststufe       | Ziel                                        | Fehlerarten                         |
|------------------|---------------------------------------------|--------------------------------------|
| **Modultest**     | Funktion einzelner Methoden/Komponenten     | Logikfehler, Syntaxfehler            |
| **Integrationstest** | Zusammenspiel von Komponenten            | Schnittstellenfehler, Datenfehler    |
| **Systemtest**    | Gesamtverhalten der Anwendung               | Anforderungsfehler, Performanceprobleme |
| **Abnahmetest**   | Erfüllung von Geschäftszielen               | Anwendungsfehler, Usabilityprobleme  |

Ein **fehlender Fokus auf eine Teststufe** führt häufig dazu, dass Fehler später und teurer entdeckt werden.

---

**Zusammenfassung:**  
Teststufen strukturieren den Testprozess und sorgen dafür, dass Fehler frühzeitig, systematisch und kontextgerecht erkannt werden. Durch die Kombination der verschiedenen Ebenen entsteht ein vollständiges Bild der Softwarequalität – von der technischen Funktion bis zur Nutzererfahrung.



# **Kapitel 4: Testarten**

## 4.1 Einführung

Testarten beschreiben unterschiedliche **Zielsetzungen und Schwerpunkte** innerhalb des Software Testings. Während Teststufen sich auf die **Struktur der Softwareebene** beziehen (z. B. Modul, System), konzentrieren sich Testarten auf den **Testzweck** – also auf das *„Was“* und *„Warum“* getestet wird.

Eine Kombination verschiedener Testarten ist notwendig, um ein umfassendes Bild der Softwarequalität zu erhalten. Sie lassen sich grundsätzlich in zwei große Kategorien unterteilen:

- **Funktionale Tests**
- **Nicht-funktionale Tests**

## 4.2 Funktionale Tests

Funktionale Tests überprüfen, **ob das System das tut, was es tun soll** – also ob es sich entsprechend der funktionalen Anforderungen verhält. Diese Anforderungen stammen in der Regel aus Spezifikationen, User Stories oder Use Cases.

**Typische Schwerpunkte:**

- Korrektheit der Funktionen
- Datenverarbeitung und -validierung
- Benutzerinteraktionen
- Geschäftslogik

**Beispiele:**

- Wird ein Rabatt korrekt berechnet?
- Kann sich ein Nutzer mit gültigen Anmeldedaten einloggen?
- Wird eine Fehlermeldung angezeigt, wenn ein Pflichtfeld leer bleibt?

Funktionale Tests bilden das Rückgrat der Qualitätssicherung, da sie direkt prüfen, ob die Kernfunktionen wie gewünscht arbeiten.

## 4.3 Nicht-funktionale Tests

Nicht-funktionale Tests konzentrieren sich auf **Eigenschaften und Qualitätsmerkmale** der Software, die über die reine Funktionalität hinausgehen. Diese Aspekte sind oft schwerer messbar, aber für die Benutzerzufriedenheit und Betriebssicherheit entscheidend.

**Wichtige nicht-funktionale Testarten:**

- **Leistungstests (Performance Testing):** Antwortzeiten, Durchsatz, Ressourcenverbrauch
- **Sicherheitstests (Security Testing):** Zugriffskontrollen, Schutz vor Angriffen
- **Benutzbarkeitstests (Usability Testing):** Verständlichkeit, Bedienbarkeit
- **Kompatibilitätstests:** Browser, Betriebssysteme, Geräte
- **Zuverlässigkeitstests (Reliability Testing):** Stabilität über längere Zeiträume
- **Wartbarkeitstests:** Verständlichkeit und Änderbarkeit des Codes

**Beispiel:**  
Ein Lasttest stellt sicher, dass eine Webanwendung auch bei 1.000 gleichzeitigen Nutzern stabil bleibt.

## 4.4 Regressionstests

Regressionstests überprüfen, ob **neue Änderungen bestehende Funktionen unbeabsichtigt beeinträchtigt haben**. Sie werden typischerweise nach Codeänderungen, Bugfixes oder neuen Releases durchgeführt.

**Merkmale:**

- Wiederverwendung vorhandener Testfälle
- Hoher Automatisierungsgrad empfehlenswert
- Bestandteil jeder CI/CD-Pipeline

**Beispiel:**  
Nach dem Update des Warenkorbsystems wird überprüft, ob der Bestellvorgang weiterhin fehlerfrei funktioniert.

Regressionstests sind ein wesentliches Mittel zur Qualitätssicherung bei **kontinuierlicher Entwicklung**.

## 4.5 Smoke- und Sanity-Tests

Diese beiden Testarten dienen einer **schnellen Erstbewertung** des Systems, z. B. nach einem neuen Build.

- **Smoke-Test:**  
  Oberflächlicher Test der wichtigsten Funktionen („funktioniert das System grundsätzlich?“).  
  → Wird typischerweise automatisiert nach jedem Build ausgeführt.

- **Sanity-Test:**  
  Schnelle Prüfung nach einer Änderung oder einem Bugfix, ob die Änderung wie erwartet wirkt.  
  → Eingeschränkter Test mit Fokus auf die betroffenen Bereiche.

Beide Testarten helfen, frühzeitig schwere Fehler zu erkennen und unnötige Testaufwände zu vermeiden.

## 4.6 Exploratives Testing

Beim explorativen Testing werden Tests **ohne vorher festgelegte Testfälle** durchgeführt. Tester:innen erkunden das System intuitiv, basierend auf Erfahrung und Beobachtung.

**Vorteile:**

- Sehr flexibel
- Effektiv beim Aufdecken unerwarteter Fehler
- Fördert Kreativität und Systemverständnis

**Nachteile:**

- Schwer nachvollziehbar oder wiederholbar
- Stark abhängig von der Kompetenz der Tester:innen

Exploratives Testing eignet sich besonders gut für **neue oder instabile Systeme**, bei denen strukturierte Tests noch nicht möglich oder zielführend sind.

## 4.7 Ad-hoc Testing

Ad-hoc Testing ist eine **noch weniger strukturierte Form** des explorativen Testens. Es gibt keine Dokumentation, keine Regeln, keine Vorbereitung – nur spontane Tests auf Basis von Intuition und Erfahrung.

**Typisch für Ad-hoc Tests:**

- Schnelle Durchführung
- Unsystematisch, aber manchmal sehr effektiv
- Kein Anspruch auf Vollständigkeit

Ad-hoc Tests sollten **nicht als Ersatz**, sondern nur als Ergänzung zu strukturierten Tests verwendet werden.

## 4.8 Weitere Testarten

Neben den klassischen Kategorien gibt es eine Vielzahl weiterer spezialisierter Testarten:

- **Installationstests:** Überprüfung der Installierbarkeit und Konfigurierbarkeit
- **Recovery-Tests:** Verhalten bei Systemabstürzen und Wiederherstellungen
- **Internationalisierungstests (i18n):** Mehrsprachigkeit, Zeichensätze, Datumsformate
- **Accessibility-Tests:** Barrierefreiheit gemäß WCAG-Standards
- **A/B-Tests:** Vergleich verschiedener Versionen einer Funktion im Livebetrieb

Je nach Projekttyp, Branche und Zielgruppe müssen passende Testarten ausgewählt und kombiniert werden.

---

**Zusammenfassung:**  
Testarten geben dem Testprozess Richtung und Schwerpunkt. Durch das gezielte Kombinieren funktionaler, nicht-funktionaler, strukturierter und erfahrungsbasierter Tests entsteht ein vollständiges Testbild. Der Schlüssel liegt in der richtigen Auswahl und Integration – passend zur Projektphase, zum System und zum Risiko.


# **Kapitel 5: Statische und dynamische Testverfahren**

## 5.1 Einführung

Testverfahren lassen sich grundsätzlich in zwei Hauptkategorien einteilen:

- **Statische Testverfahren**: Die Software wird **nicht ausgeführt**, sondern anhand von Dokumenten oder Quellcode analysiert.
- **Dynamische Testverfahren**: Die Software wird **ausgeführt**, um ihr Verhalten bei bestimmten Eingaben zu beobachten und zu bewerten.

Beide Ansätze ergänzen sich sinnvoll: Statische Verfahren sind besonders früh im Entwicklungsprozess einsetzbar, dynamische Verfahren liefern direktes Feedback zum Laufzeitverhalten.

## 5.2 Statische Testverfahren

Statische Testverfahren zielen darauf ab, **Fehler bereits vor der Ausführung** der Software zu identifizieren. Sie eignen sich hervorragend für die frühzeitige Qualitätssicherung, insbesondere bei Dokumentation, Quellcode und Architektur.

### 5.2.1 Review-Techniken

**Reviews** sind systematische Überprüfungen von Artefakten wie Spezifikationen, Quellcode oder Testfällen durch Personen.

**Arten von Reviews:**

- **Informelles Review**  
  Spontanes Feedback unter Kollegen, z. B. per Pair Programming oder Peer Review

- **Walkthrough**  
  Der Autor stellt sein Artefakt einem kleinen Kreis vor; Ziel ist das gemeinsame Verständnis

- **Technisches Review**  
  Strukturierte Diskussion mit Fokus auf technische Qualität, z. B. bei Architekturentscheidungen

- **Inspektion**  
  Formeller, dokumentierter Prozess mit Rollen (Moderator, Protokollführer, Leser); sehr effektiv zur Fehlerentdeckung

**Vorteile von Reviews:**

- Frühe Fehlererkennung (auch bei Anforderungen)
- Verbesserte Kommunikation im Team
- Know-how-Transfer
- Reduktion von Nachbesserungskosten

### 5.2.2 Statische Codeanalyse

Die statische Codeanalyse untersucht den **Quellcode automatisiert** auf potenzielle Fehler, Sicherheitsrisiken oder Verstöße gegen Programmierstandards – **ohne den Code auszuführen**.

**Beispiele für Prüfungen:**

- Ungenutzte Variablen
- Nicht behandelte Ausnahmen
- Sicherheitslücken (z. B. SQL-Injection)
- Komplexität und Wartbarkeit

**Werkzeuge:**

- SonarQube
- ESLint (JavaScript)
- PMD (Java)
- Pylint (Python)

**Einsatzgebiet:**  
Besonders wertvoll in CI/CD-Pipelines, um automatisch die Codequalität zu sichern.

## 5.3 Dynamische Testverfahren

Dynamisches Testen bedeutet, dass die Software **in einem echten oder simulierten Ausführungskontext** getestet wird. Ziel ist es, durch Ausführen von Testfällen reale Reaktionen des Systems zu beobachten.

### 5.3.1 Ablauf

Ein typischer dynamischer Test folgt diesem Schema:

1. Auswahl und Vorbereitung von Testdaten
2. Ausführung des Testfalls im System
3. Beobachtung des tatsächlichen Ergebnisses
4. Vergleich mit dem erwarteten Ergebnis
5. Protokollierung von Abweichungen (Defekte)

**Beispiele:**

- Ein Benutzer registriert sich mit ungültigen Daten → das System gibt eine Fehlermeldung aus
- Ein Algorithmus wird mit Grenzwerten getestet → das Ergebnis muss exakt stimmen

### 5.3.2 Arten dynamischer Tests

Dynamische Tests lassen sich nach mehreren Kriterien unterscheiden:

- **Funktional vs. nicht-funktional**
- **Automatisiert vs. manuell**
- **Strukturiert vs. explorativ**
- **White-Box vs. Black-Box**

Sie werden in verschiedenen **Teststufen** (siehe Kapitel 3) durchgeführt – vom Unit-Test bis zum Abnahmetest.

### 5.3.3 Automatisierte Tests

Automatisierung ist eine Schlüsseldisziplin im dynamischen Testen. Besonders bei **Regressionstests**, **Smoke-Tests** und in **agilen Projekten** mit häufiger Ausführung zahlt sich der initiale Aufwand aus.

**Typische Werkzeuge:**

- Selenium (UI-Tests)
- JUnit/TestNG (Unit-Tests)
- Cypress (Webanwendungen)
- Postman/Newman (API-Tests)

**Vorteile:**

- Wiederholbarkeit
- Schnelligkeit
- Integrierbarkeit in CI/CD-Prozesse

## 5.4 Kombination statischer und dynamischer Verfahren

Ein effektiver Testprozess nutzt beide Verfahren **komplementär**:

| Verfahren         | Zeitpunkt im Projekt     | Erkenntnisgewinn                      |
|-------------------|--------------------------|----------------------------------------|
| **Statisch**       | Früh (vor Implementierung) | Logikfehler, Verständlichkeit, Stil   |
| **Dynamisch**      | Später (nach Implementierung) | Verhalten zur Laufzeit, Systemreaktionen |

**Beispiel:**  
Ein Fehler in der Anforderungsbeschreibung kann durch ein Review früh erkannt werden – bevor er in den Code gelangt und dort mühsam getestet werden muss.

## 5.5 Wirtschaftlichkeit

Statische Verfahren gelten als **besonders wirtschaftlich**, da sie Fehler früh und mit relativ geringem Aufwand erkennen. Dynamische Tests sind hingegen **unverzichtbar**, um das reale Systemverhalten zu prüfen – insbesondere bei Interaktion, Performance und Komplexität.

Die richtige Balance aus beidem ist entscheidend für:

- Qualitätssicherung
- Risikominimierung
- Budgeteffizienz

---

**Zusammenfassung:**  
Statische und dynamische Testverfahren bilden die methodische Basis des Software-Testings. Während statische Verfahren früh und präventiv wirken, liefern dynamische Verfahren valide Aussagen über das Verhalten eines Systems in Aktion. Die Kombination beider Ansätze schafft ein belastbares Fundament für eine nachhaltige Softwarequalität.



# **Kapitel 6: White-Box-Testing**

## 6.1 Einführung

White-Box-Testing (auch **strukturbezogenes Testen**) ist ein Testverfahren, bei dem der Tester **Einblick in den internen Aufbau und die Logik der Software** hat. Anders als beim Black-Box-Testing wird hier nicht nur die Funktionalität von außen überprüft, sondern gezielt das **Innenleben des Codes analysiert und getestet**.

Ziel ist es, sicherzustellen, dass **alle relevanten Codepfade, Verzweigungen und logischen Bedingungen** korrekt umgesetzt und getestet sind.

## 6.2 Einsatzgebiete

White-Box-Tests eignen sich insbesondere für:

- **Modultests (Unit Testing)**, bei denen einzelne Funktionen oder Methoden getestet werden
- **Code Reviews und statische Analysen**, zur Verbesserung von Codequalität
- **Sicherheitskritische Komponenten**, bei denen vollständige Kontrollflussabdeckung notwendig ist

Typischerweise wird White-Box-Testing **von Entwickler:innen durchgeführt**, da fundierte Programmierkenntnisse erforderlich sind.

## 6.3 Techniken des White-Box-Testing

Es gibt verschiedene Techniken, um sicherzustellen, dass bestimmte Teile oder Strukturen des Codes getestet wurden. Diese Techniken zielen auf eine **möglichst hohe Abdeckung (Coverage)** des Quellcodes.

### 6.3.1 Anweisungsüberdeckung (Statement Coverage)

Hier wird geprüft, ob **jede einzelne Anweisung** im Code mindestens einmal ausgeführt wurde.

**Beispiel:**

```python
if x > 10:
    print("Größer als 10")
print("Ende")
```

Ein Test mit `x = 15` erreicht 100 % Anweisungsüberdeckung. Wird jedoch `x = 5` getestet, wird die erste Anweisung übersprungen – die Abdeckung sinkt.

**Ziel:**  
Einfacher Einstieg in strukturbasiertes Testen, aber **geringe Aussagekraft**, da Verzweigungen unberücksichtigt bleiben.

### 6.3.2 Zweigüberdeckung (Branch Coverage)

Hier wird geprüft, ob **jeder mögliche Ausgang** einer Entscheidung (true/false) mindestens einmal getestet wurde.

**Beispiel:**

```python
if x > 10:
    print("Größer")
else:
    print("Kleiner oder gleich")
```

Ein Test mit `x = 15` und `x = 5` führt zu 100 % Zweigüberdeckung.

**Vorteil:**  
Bessere Fehlererkennung in Entscheidungsstrukturen als bei reiner Anweisungsüberdeckung.

### 6.3.3 Pfadüberdeckung (Path Coverage)

Diese Technik zielt darauf ab, **alle möglichen Ausführungspfade** durch den Code zu testen – inklusive verschachtelter Bedingungen und Schleifen.

**Herausforderung:**  
Die Anzahl möglicher Pfade steigt **exponentiell** mit der Komplexität – vollständige Abdeckung ist daher oft **nicht praktikabel**.

**Ziel:**  
Auswahl **repräsentativer Pfade**, insbesondere risikobehafteter oder besonders komplexer Pfade.

### 6.3.4 Bedingungsüberdeckung (Condition Coverage)

Bei komplexen Bedingungen wie `if (a > 5 && b < 3)` wird überprüft, ob **jede Teilbedingung separat** sowohl `true` als auch `false` ergibt – unabhängig davon, ob die Gesamtbedingung wahr ist.

**Varianten:**

- **Einfache Bedingungsüberdeckung:** Jede atomare Bedingung wird einzeln getestet
- **Multiple Condition Coverage:** Alle möglichen Kombinationen von Bedingungen werden getestet

Diese Technik ist besonders wichtig bei **sicherheitskritischen Systemen**, in denen versteckte Fehler in Bedingungen fatale Folgen haben können.

## 6.4 Kontrollflussanalyse

Die Kontrollflussanalyse ist eine Methode zur **graphischen Darstellung und Untersuchung von Programmabläufen**. Sie unterstützt die Auswahl geeigneter Testfälle und die Identifikation kritischer Pfade.

**Elemente eines Kontrollflussdiagramms:**

- Start- und Endpunkte
- Anweisungen (Knoten)
- Verzweigungen (Entscheidungspunkte)
- Pfade (Verbindungen zwischen Knoten)

**Ziel:**  
Übersicht über logische Abläufe und systematische Abdeckung aller Pfade.

**Beispielhafte Anwendung:**  
Analyse eines Algorithmus zur Berechnung von Rabatten: Sind alle Rabattstufen getestet? Werden auch Sonderfälle wie negative Eingaben korrekt behandelt?

## 6.5 White-Box-Testing in der Praxis

**Typische Einsatzbereiche:**

- **Unit-Tests** bei neuen Funktionen
- **Sicherheitsprüfungen** (z. B. Prüfung auf Logikfehler in Authentifizierungsmechanismen)
- **Code-Metriken** zur Überwachung der Komplexität und Testbarkeit

**Automatisierungstools:**

- **Coverage-Tools**: z. B. JaCoCo (Java), Coverage.py (Python), Istanbul (JavaScript)
- **Unit-Test-Frameworks**: JUnit, NUnit, xUnit, PyTest
- **CI/CD-Integration**: Code Coverage Reports in Build-Prozesse integrieren

**Vorteile:**

- Tiefgehende Analyse des Codes
- Frühe Fehlererkennung
- Aussagekräftige Metriken (Coverage, Komplexität)

**Nachteile:**

- Hoher technischer Aufwand
- Keine Prüfung auf fehlende Anforderungen („Bauen wir das richtige System?“)
- Begrenzte Aussage über das Gesamtsystem

## 6.6 Vergleich zu Black-Box-Testing

| Aspekt             | White-Box-Testing                  | Black-Box-Testing                  |
|--------------------|------------------------------------|------------------------------------|
| Kenntnis des Codes | Erforderlich                       | Nicht erforderlich                 |
| Testbasis          | Quellcode, Kontrollfluss           | Spezifikation, Anforderungen       |
| Ziel               | Abdeckung interner Strukturen      | Prüfung des funktionalen Verhaltens|
| Durchführung       | Häufig durch Entwickler:innen      | Häufig durch QA-Teams              |
| Fehlerarten        | Logikfehler, nicht erreichte Pfade | Fehlende oder falsche Funktion     |

In der Praxis werden **beide Ansätze kombiniert**, um sowohl die innere Logik als auch das äußere Verhalten des Systems zu prüfen.

---

**Zusammenfassung:**  
White-Box-Testing ist ein mächtiges Werkzeug zur Qualitätssicherung auf Codeebene. Es ermöglicht eine gezielte Überprüfung logischer Abläufe und eine transparente Messung der Testabdeckung. In Kombination mit anderen Testmethoden bildet es die Grundlage für robuste, wartbare und verlässliche Software.



# **Kapitel 7: Black-Box-Testing**

## 7.1 Einführung

Black-Box-Testing (auch **verhaltensbasiertes oder spezifikationsbasiertes Testen**) ist ein Testansatz, bei dem die **interne Struktur oder der Quellcode der Software nicht bekannt** oder nicht relevant ist. Der Fokus liegt ausschließlich auf dem **Input-Output-Verhalten** eines Systems – also darauf, ob es bei bestimmten Eingaben die erwarteten Ausgaben liefert.

Dieser Ansatz eignet sich besonders gut, um zu prüfen, ob das System die **funktionalen Anforderungen erfüllt**, unabhängig davon, wie es intern realisiert wurde.

## 7.2 Merkmale des Black-Box-Testings

- Test basiert auf **Spezifikationen, Anforderungen oder User Stories**
- Keine Kenntnisse über den Quellcode notwendig
- Tester:innen agieren wie Endbenutzer oder Kund:innen
- Anwendung in allen Teststufen, insbesondere **System- und Abnahmetests**
- Eignet sich für **funktionale und nicht-funktionale Tests**

**Beispiel:**  
Ein Login-Formular wird mit gültigen und ungültigen Benutzerdaten getestet – ohne Kenntnis der dahinterliegenden Authentifizierungslogik.

## 7.3 Vorteile und Grenzen

**Vorteile:**

- Realitätsnah: Tests aus Sicht der Nutzer:innen
- Unabhängigkeit vom Code: auch von externen Teams durchführbar
- Geeignet für Tests auf verschiedenen Ebenen (System, Integration, Abnahme)
- Guter Schutz gegen **Fehlinterpretationen der Anforderungen**

**Grenzen:**

- Keine Prüfung interner Logik oder nicht erreichter Codeteile
- Hoher Aufwand zur vollständigen Testabdeckung (wegen unendlicher Eingabemöglichkeiten)
- Weniger präzise bei Ursachenanalyse von Fehlern

## 7.4 Testentwurfsverfahren im Black-Box-Testing

Um den Testumfang effizient zu begrenzen und systematisch zu testen, kommen verschiedene **Testentwurfsverfahren** zum Einsatz. Diese helfen, aussagekräftige Testfälle auf Basis der Anforderungen zu definieren.

### 7.4.1 Äquivalenzklassenbildung

Dieses Verfahren teilt den Eingabebereich in **gleichwertige Klassen** ein, bei denen angenommen wird, dass sie vom System gleich behandelt werden. Für jede Klasse wird ein **repräsentativer Testfall** gewählt.

**Beispiel:**

Ein Altersfeld akzeptiert nur Werte zwischen 18 und 65:

- Gültige Äquivalenzklasse: 18–65 → z. B. Test mit 30
- Ungültige Klassen: <18, >65 → z. B. Test mit 17 und 70

**Vorteil:** Reduktion der Testanzahl bei gleichbleibender Aussagekraft

### 7.4.2 Grenzwertanalyse

Fehler treten besonders häufig an den **Grenzen von Wertebereichen** auf. Deshalb werden Testfälle gezielt an diesen Grenzen platziert.

**Beispiel (wie oben):**

- Untere Grenze: 17 (ungültig), 18 (gültig)
- Obere Grenze: 65 (gültig), 66 (ungültig)

**Vorteil:** Erkennung typischer Off-by-One-Fehler oder falscher Vergleichsoperatoren

### 7.4.3 Entscheidungstabellen

Entscheidungstabellen eignen sich für Systeme mit **komplexen Regeln oder Abhängigkeiten** zwischen Eingaben. Sie stellen verschiedene Bedingungen und deren zugehörige Aktionen tabellarisch dar.

**Beispiel:** Kreditvergabe hängt ab von Einkommen, Alter und Schuldenstatus

| Einkommen | Alter | Schuldenfrei | Entscheidung |
|-----------|-------|--------------|--------------|
| Hoch      | > 25  | Ja           | Genehmigt    |
| Niedrig   | < 25  | Nein         | Abgelehnt    |
| ...       | ...   | ...          | ...          |

**Vorteil:** Übersicht und Vollständigkeit bei regelbasierten Systemen

### 7.4.4 Zustandsbasierte Tests

Diese Technik wird verwendet, wenn das System **intern verschiedene Zustände einnimmt**, z. B. bei Zustandsautomaten, Workflows oder Benutzerinteraktionen.

**Beispiel:**  
Ein Benutzerkonto kann den Zustand *aktiv*, *gesperrt* oder *gelöscht* haben. Die erlaubten Aktionen hängen vom aktuellen Zustand ab.

**Testschritte:**

- Modellierung der Zustände und Übergänge
- Definition von Testfällen für zulässige und unzulässige Übergänge

**Werkzeuge:** Zustandsdiagramme (z. B. UML)

### 7.4.5 Use Case-basierte Tests

Testfälle werden aus **Anwendungsfällen (Use Cases)** oder Benutzerstories abgeleitet. Ziel ist es, **reale Nutzungsszenarien** möglichst vollständig abzudecken.

**Beispiel:**  
Ein Kunde bestellt ein Produkt, erhält eine Rechnung und storniert die Bestellung → mehrere Schritte und Systeme werden abgebildet.

**Vorteil:** Gute Nachvollziehbarkeit für Stakeholder, ideal für Abnahmetests

## 7.5 Anwendung in der Praxis

Black-Box-Tests kommen in zahlreichen Kontexten zum Einsatz:

- **Systemtests:** Funktionale Überprüfung der Gesamtanwendung
- **Abnahmetests:** Prüfung durch Kund:innen anhand von Anforderungen
- **Explorative Tests:** Spontanes Erkunden der Anwendung
- **Nicht-funktionale Tests:** z. B. Performance, Kompatibilität, Sicherheit

Sie werden häufig **von unabhängigen Testteams**, Qualitätssicherungsabteilungen oder auch **durch automatisierte Testwerkzeuge** durchgeführt.

**Werkzeuge für automatisierte Black-Box-Tests:**

- Selenium (Web-UI)
- Postman (APIs)
- Cypress (Browseranwendungen)
- Robot Framework (Keyword-Driven Testing)

## 7.6 Kombination mit anderen Testarten

In der Praxis wird Black-Box-Testing mit anderen Methoden kombiniert:

| Kombination mit         | Ziel                                        |
|-------------------------|---------------------------------------------|
| **White-Box-Testing**   | Innen- und Außenansicht kombinieren         |
| **Erfahrungsbasierten Tests** | Kreative Fehlerfindung ergänzen        |
| **Nicht-funktionalen Tests** | Performanz, Usability, Sicherheit testen |

Eine **ganzheitliche Teststrategie** entsteht durch die Verknüpfung verschiedener Perspektiven – insbesondere bei komplexen Systemen mit hohen Anforderungen an Sicherheit oder Benutzerfreundlichkeit.

---

**Zusammenfassung:**  
Black-Box-Testing ist eine zentrale Methode zur Überprüfung des sichtbaren Systemverhaltens. Es ist besonders geeignet für funktionale Tests, systemnahe Prüfungen und Abnahmen. Durch strukturierte Verfahren wie Äquivalenzklassenbildung, Grenzwertanalyse oder Entscheidungstabellen können auch große Eingabemengen gezielt und effizient getestet werden – ganz ohne Kenntnis des Codes.



# **Kapitel 8: Testentwurfsverfahren**

## 8.1 Einführung

Testentwurfsverfahren (auch **Testdesigntechniken** genannt) sind systematische Methoden zur **Ableitung von Testfällen** aus einer gegebenen Basis – etwa aus Anforderungen, Spezifikationen, Modellen oder dem Quellcode. Sie helfen dabei, relevante Tests gezielt auszuwählen, Lücken zu vermeiden und die Testabdeckung zu maximieren.

Ein gezielter Testentwurf spart Zeit, reduziert Redundanzen und erhöht die Wirksamkeit der Tests. Testentwurfsverfahren lassen sich grob in drei Hauptkategorien unterteilen:

1. **Spezifikationsbasierte Verfahren (Black-Box)**
2. **Strukturbasierte Verfahren (White-Box)**
3. **Erfahrungsbasierte Verfahren**

Je nach Projektphase, Kontext und Risikoprofil können diese Verfahren einzeln oder in Kombination verwendet werden.

---

## 8.2 Spezifikationsbasierte Verfahren (Black-Box)

Diese Verfahren basieren auf **Anforderungen, Use Cases oder funktionalen Beschreibungen** des Systems. Die interne Struktur des Codes wird nicht betrachtet.

### 8.2.1 Äquivalenzklassenbildung

→ Siehe Kapitel 7.  
Eingabebereiche werden in gültige und ungültige Klassen aufgeteilt, um repräsentative Testfälle pro Klasse zu definieren.

### 8.2.2 Grenzwertanalyse

→ Siehe Kapitel 7.  
Besondere Aufmerksamkeit gilt den Werten an den Rändern von gültigen und ungültigen Bereichen.

### 8.2.3 Entscheidungstabellen

→ Siehe Kapitel 7.  
Kombination verschiedener Eingabebedingungen und deren Auswirkungen werden in Tabellenform dargestellt.

### 8.2.4 Zustandsbasierter Test

→ Siehe Kapitel 7.  
Geeignet für Systeme mit Zustandsautomaten oder komplexen Zustandsübergängen.

### 8.2.5 Use Case-basierter Test

→ Siehe Kapitel 7.  
Abgeleitet aus Benutzerinteraktionen oder Geschäftsprozessen.

**Vorteile der spezifikationsbasierten Verfahren:**

- Hohe Realitätsnähe
- Fokus auf Anforderungsabdeckung
- Gute Kommunikation mit Stakeholdern

---

## 8.3 Strukturbasierte Verfahren (White-Box)

Diese Verfahren orientieren sich an der **internen Struktur des Programmcodes**. Ziel ist es, durch gezielte Testfälle **eine möglichst hohe Abdeckung des Codes** zu erreichen.

### 8.3.1 Anweisungsüberdeckung  
Alle Anweisungen im Code werden mindestens einmal durchlaufen.

### 8.3.2 Zweigüberdeckung  
Alle möglichen Ausgänge (true/false) einer Bedingung werden getestet.

### 8.3.3 Pfadüberdeckung  
Alle möglichen Kontrollflusswege durch den Code werden betrachtet.

### 8.3.4 Bedingungsüberdeckung  
Jede atomare Bedingung wird unabhängig voneinander auf true und false getestet.

Diese Verfahren sind besonders hilfreich, um **Logikfehler** zu identifizieren, die durch rein verhaltensbasiertes Testen unentdeckt bleiben könnten.

**Vorteile strukturbasierter Verfahren:**

- Messbarkeit durch Codeabdeckung
- Frühzeitige Fehlererkennung
- Objektive Analyse komplexer Kontrollflüsse

---

## 8.4 Erfahrungsbasierte Verfahren

Diese Verfahren beruhen auf **Intuition, Erfahrung und Kreativität** der Tester:innen. Sie sind besonders nützlich, wenn keine vollständigen Spezifikationen vorliegen oder wenn ergänzend zu strukturierten Verfahren getestet werden soll.

### 8.4.1 Fehlerratenbasierter Test  
Testfälle werden basierend auf bekannten Schwachstellen aus früheren Projekten erstellt.

### 8.4.2 Exploratives Testen  
Tester:innen erkunden das System interaktiv und reagieren flexibel auf Beobachtungen.

### 8.4.3 Fehler- und Angriffsbasierter Test  
Gezielte Tests auf typische Fehlermuster oder potenzielle Angriffsvektoren (z. B. SQL-Injection).

**Vorteile erfahrungsbasierter Verfahren:**

- Schnell und flexibel einsetzbar
- Hoher Nutzen bei schwacher Spezifikation
- Gut geeignet zur Ergänzung formaler Verfahren

---

## 8.5 Auswahl geeigneter Verfahren

Die Wahl des passenden Testentwurfsverfahrens hängt ab von:

- **Testziel**: Funktionalität, Struktur, Sicherheit, Benutzerfreundlichkeit
- **Projektphase**: Frühe Phasen eignen sich für Reviews und White-Box-Methoden
- **Verfügbarkeit von Artefakten**: Spezifikationen, Code, Modelle
- **Komplexität des Systems**: Je komplexer, desto wertvoller sind strukturierte Verfahren
- **Risikobewertung**: Kritische Bereiche benötigen intensivere Testmethodik

**Kombination ist oft der Schlüssel:**  
Ein sicherheitskritisches System könnte z. B. explorativ, zustandsbasiert und codeabdeckend getestet werden.

---

## 8.6 Werkzeugunterstützung

Viele Testentwurfsverfahren lassen sich mit Tools unterstützen oder teilautomatisieren:

- **Testmanagement-Tools**: z. B. TestRail, Xray
- **Modellbasierte Testtools**: z. B. GraphWalker, TOSCA
- **Testdatengeneratoren**: z. B. Equivalence Partitioning Tools
- **Codeabdeckungstools**: z. B. JaCoCo, Istanbul

Solche Werkzeuge helfen bei der Verwaltung großer Testmengen, der Reproduzierbarkeit und der Nachvollziehbarkeit von Testdesigns.

---

**Zusammenfassung:**  
Testentwurfsverfahren bilden das methodische Herzstück des Software-Testings. Sie ermöglichen strukturierte, effiziente und gezielte Tests. In der Praxis ist eine Kombination aus Black-Box-, White-Box- und erfahrungsbasierten Verfahren ideal, um die Stärken aller Ansätze zu vereinen und Risiken umfassend zu adressieren.




# **Kapitel 9: Testmanagement**

## 9.1 Einführung

Testmanagement umfasst die **strategische Planung, Organisation, Steuerung und Kontrolle aller Testaktivitäten** in einem Softwareprojekt. Es stellt sicher, dass Testziele effizient erreicht werden, Risiken angemessen berücksichtigt sind und die Qualität des Produktes transparent bewertet werden kann.

Professionelles Testmanagement verbindet **technische Kompetenz mit organisatorischem Geschick** – insbesondere in Projekten mit hohem Zeitdruck, komplexen Anforderungen oder verteilter Teamstruktur.

---

## 9.2 Aufgaben des Testmanagements

Die Hauptaufgaben des Testmanagements lassen sich in folgende Kernbereiche unterteilen:

1. **Testplanung**: Festlegung von Strategie, Umfang, Ressourcen und Zeitrahmen
2. **Teststeuerung**: Laufende Überwachung und Anpassung des Testprozesses
3. **Testüberwachung und -berichterstattung**: Erfassung von Kennzahlen, Fortschritt und Qualität
4. **Fehlermanagement**: Systematische Behandlung von Defekten
5. **Testabschluss**: Bewertung der Zielerreichung und Lessons Learned

---

## 9.3 Teststrategie und Testkonzept

Die **Teststrategie** beschreibt den grundsätzlichen Ansatz für das Testen im Projekt. Sie beantwortet Fragen wie:

- Was soll wie intensiv getestet werden?
- Welche Teststufen und -arten kommen zum Einsatz?
- Wie wird mit Risiken und Abhängigkeiten umgegangen?
- Wie hoch ist der Automatisierungsgrad?

Das **Testkonzept** (auch Testplan genannt) konkretisiert diese Strategie und enthält unter anderem:

- Testziele
- Testumfang und -grenzen
- Rollen und Verantwortlichkeiten
- Testumgebung und -werkzeuge
- Ein- und Austrittskriterien
- Zeitplan und Meilensteine

Ein gut dokumentiertes Testkonzept ist **entscheidend für Transparenz und Nachvollziehbarkeit**, besonders in regulierten oder sicherheitskritischen Projekten.

---

## 9.4 Risikobasiertes Testen

Da Ressourcen (Zeit, Budget, Personal) begrenzt sind, müssen Testaktivitäten **priorisiert** werden. Das risikobasierte Testen fokussiert die Tests auf jene Komponenten, die potenziell **die gravierendsten Auswirkungen bei Fehlern** haben.

**Typische Risikokriterien:**

- Komplexität
- Änderungshäufigkeit
- Sicherheitsrelevanz
- Benutzerfrequenz
- Historie von Fehlern

**Vorgehen:**

1. Identifikation möglicher Risiken
2. Bewertung von Eintrittswahrscheinlichkeit und Schadensausmaß
3. Priorisierung von Testfällen
4. Dokumentation und Überwachung der Risiken

**Vorteil:**  
Maximale Wirkung bei begrenztem Aufwand – besonders wichtig in agilen, iterativen Umgebungen.

---

## 9.5 Testmetriken und Kennzahlen

Testmetriken helfen, **objektive Aussagen über Fortschritt und Qualität** zu treffen. Sie dienen der Steuerung, Kommunikation und Entscheidung im Projekt.

**Wichtige Metriken:**

| Metrik                       | Aussage                                                  |
|-----------------------------|-----------------------------------------------------------|
| Anzahl ausgeführter Tests   | Fortschritt im Vergleich zum Plan                         |
| Fehlerrate (Defects/Test)   | Fehlerdichte, Hinweis auf Qualität oder Instabilität      |
| Testabdeckung (Coverage)    | Anteil getesteter Funktionen oder Codeteile              |
| Defect Fix Rate             | Geschwindigkeit der Fehlerbehebung                       |
| Testautomatisierungsgrad    | Anteil der automatisierten Tests                         |

**Achtung:** Metriken sollten **nicht isoliert bewertet** werden, sondern im Kontext interpretiert werden.

---

## 9.6 Testberichte und Kommunikation

Ein professioneller Testprozess endet nicht mit der Ausführung der Testfälle, sondern mit deren **Dokumentation und Kommunikation**. Testberichte sind entscheidend für:

- Nachvollziehbarkeit von Entscheidungen
- Stakeholder-Information (z. B. Management, Kunden)
- Vorbereitung der Abnahme

**Inhalte eines Testberichts:**

- Überblick über durchgeführte Tests
- Ergebnisse und Abdeckungsgrade
- Aufgetretene Defekte und deren Status
- Risiken und offene Punkte
- Empfehlung zur Freigabe oder weiteren Maßnahmen

**Tipp:**  
Testberichte sollten **zielgruppengerecht aufbereitet** werden – technisches Detail für Entwickler:innen, klare Zusammenfassungen für Projektleiter:innen.

---

## 9.7 Rollen im Testmanagement

Ein strukturiertes Testteam besteht typischerweise aus mehreren Rollen:

- **Testmanager:in**: Verantwortlich für Planung, Koordination, Berichterstattung
- **Tester:in**: Erstellung und Durchführung von Testfällen, Dokumentation von Ergebnissen
- **Automatisierungsspezialist:in**: Aufbau und Pflege automatisierter Tests
- **Fachliche:r Tester:in**: Prüfung aus Sicht der Anwender:innen (z. B. beim Abnahmetest)
- **Entwickler:in**: Durchführung von Unit-Tests, Analyse von Defekten

In agilen Teams werden diese Rollen häufig flexibler gelebt – der Fokus liegt dann auf **gemeinsamer Verantwortung für Qualität**.

---

## 9.8 Testmanagement in agilen Projekten

In agilen Projekten (z. B. Scrum, Kanban) gelten andere Rahmenbedingungen für das Testmanagement:

- Tests werden **inkrementell und kontinuierlich** geplant
- Verantwortung ist oft **im Team verteilt**
- Dokumentation ist **leichtgewichtig**, z. B. in Form von Checklisten oder Test-Tasks
- Die Kommunikation ist **direkter** und iterativer

Trotzdem sind auch hier **klare Testziele, Priorisierung und Risikobewusstsein** essenziell. Agile Testmanagement-Tools wie **Xray, Zephyr oder Testmo** integrieren sich nahtlos in Jira & Co.

---

**Zusammenfassung:**  
Testmanagement ist weit mehr als nur Administration. Es ist ein entscheidender Erfolgsfaktor für Softwareprojekte – durch Planung, Steuerung und Kommunikation wird sichergestellt, dass Qualität messbar, steuerbar und nachhaltig erreicht werden kann. Gute Testmanager:innen verbinden strategisches Denken mit technischer Tiefe und einem sicheren Gespür für Risiken und Ressourcen.




# **Kapitel 10: Testwerkzeuge**

## 10.1 Einführung

Softwaretests effizient und effektiv durchzuführen, ist ohne geeignete **Testwerkzeuge** kaum möglich. Sie unterstützen die Testaktivitäten über den gesamten Testprozess hinweg – von der Planung über die Testfallerstellung bis hin zur Ausführung, Automatisierung und Auswertung.

Ein gezielter Einsatz von Tools kann:

- **Aufwände reduzieren**
- **Fehler vermeiden**
- **Transparenz und Nachvollziehbarkeit** erhöhen
- **Zusammenarbeit und Wiederverwendbarkeit** fördern

Die Auswahl geeigneter Testwerkzeuge erfordert jedoch klare Anforderungen, denn **nicht jedes Tool passt zu jedem Projektkontext**.

---

## 10.2 Kategorien von Testwerkzeugen

Testwerkzeuge lassen sich in funktionale Kategorien unterteilen, abhängig davon, **welchen Teil des Testprozesses** sie unterstützen:

| Kategorie                        | Zweck                                                                 |
|----------------------------------|-----------------------------------------------------------------------|
| **Testmanagement-Tools**         | Planung, Dokumentation, Organisation und Auswertung von Tests        |
| **Testfallerstellungstools**     | Unterstützung bei der Erstellung und Verwaltung von Testfällen       |
| **Automatisierungswerkzeuge**    | Automatisierte Ausführung von Tests (UI, API, Unit)                  |
| **Fehlermanagement-Tools**       | Erfassung, Nachverfolgung und Auswertung von Defekten                |
| **Testdatenmanagement-Tools**    | Erstellung, Pflege und Anonymisierung von Testdaten                  |
| **Last- und Performancetesttools**| Simulation vieler Benutzer, Messung von Antwortzeiten und Verhalten |
| **Codeanalyse-Tools**            | Statische Analyse, Stylechecks, Sicherheitslücken                    |
| **Reporting-/Dashboard-Tools**   | Visualisierung von Testmetriken und Ergebnissen                      |

In der Praxis werden oft mehrere Tools **integriert in Toolchains** oder CI/CD-Pipelines genutzt.

---

## 10.3 Auswahlkriterien für Testwerkzeuge

Die Einführung eines neuen Testtools sollte wohlüberlegt erfolgen. Wichtige Auswahlkriterien sind:

- **Projektgröße und Teamstruktur**
- **Technologie-Stack der Software**
- **Anforderungen an Automatisierung und Reporting**
- **Kompatibilität mit bestehenden Systemen (z. B. Jira, Git, CI/CD)**
- **Benutzerfreundlichkeit und Lernkurve**
- **Lizenzmodell (Open Source, kommerziell, Cloud-basiert)**
- **Skalierbarkeit und Wartungsaufwand**

Ein erfolgreich eingeführtes Tool ist **nicht nur technisch geeignet**, sondern wird **vom Team akzeptiert und aktiv genutzt**.

---

## 10.4 Überblick wichtiger Testwerkzeuge

### 10.4.1 Testmanagement

- **TestRail** – Beliebtes Tool zur Verwaltung von Testplänen und -fällen  
- **Xray** – Testmanagement-Plugin für Jira  
- **Zephyr** – Weitere Jira-Erweiterung mit guter Integration  
- **qTest** – Umfassende Enterprise-Lösung mit API-Anbindung

### 10.4.2 Testautomatisierung

- **Selenium** – Automatisierung von Webanwendungen, unterstützt viele Sprachen  
- **Cypress** – Moderne UI-Testlösung für JavaScript/Frontend  
- **Playwright** – Mächtige Automatisierungslösung für Browser-Tests  
- **Appium** – Automatisierung mobiler Apps (Android/iOS)  
- **Robot Framework** – Keyword-Driven Testing für verschiedene Anwendungstypen

### 10.4.3 Unit-Test-Frameworks

- **JUnit** (Java)  
- **NUnit** (.NET)  
- **PyTest** (Python)  
- **Jest** (JavaScript/React)  
- **xUnit** (plattformübergreifend)

### 10.4.4 API-Tests

- **Postman** – GUI-Tool für REST- und SOAP-APIs  
- **Newman** – CLI für automatisierte Postman-Tests  
- **RestAssured** – Java-basierte API-Testbibliothek  
- **SoapUI** – Speziell für Webservices geeignet

### 10.4.5 Performance-Tests

- **JMeter** – Last- und Performancetests für Web, Datenbanken etc.  
- **Gatling** – Hochperformante Simulation für HTTP-Services  
- **k6** – Modernes Open-Source-Tool, Skripte in JavaScript

### 10.4.6 Statische Codeanalyse

- **SonarQube** – Führende Plattform zur Codequalitätsbewertung  
- **ESLint, Pylint, Checkstyle** – Sprachspezifische Analysewerkzeuge  
- **Dependabot** – Überwachung veralteter oder unsicherer Abhängigkeiten

---

## 10.5 Open Source vs. kommerzielle Lösungen

Beide Modelle haben ihre Vor- und Nachteile:

| Kriterium         | Open Source                            | Kommerziell                              |
|-------------------|-----------------------------------------|-------------------------------------------|
| **Kosten**        | Kostenlos, aber ggf. hohe Einarbeitung  | Lizenzkosten, oft mit Support             |
| **Anpassbarkeit** | Sehr hoch, offen für Erweiterungen      | Eingeschränkter Zugriff auf Quellcode     |
| **Support**       | Community-basiert                       | Hersteller-Support, SLA möglich           |
| **Integration**   | Oft flexibel, ggf. Handarbeit           | Standardisierte Integrationen vorhanden   |

In vielen Unternehmen werden **hybride Strategien** verfolgt: Open-Source-Tools im Entwicklerteam, kommerzielle Tools im Enterprise-Umfeld.

---

## 10.6 Integration in CI/CD-Pipelines

Testwerkzeuge entfalten ihre volle Wirkung, wenn sie **nahtlos in den Entwicklungsprozess integriert** sind. Typische Tools der CI/CD-Kette:

- **Build-Systeme**: Jenkins, GitLab CI, GitHub Actions, Azure DevOps  
- **Quellcodeverwaltung**: Git, Bitbucket  
- **Testautomation**: Unit-Tests, API-/UI-Tests  
- **Analyse/Reporting**: SonarQube, Allure, HTML-Reports  
- **Benachrichtigung**: Slack, E-Mail, Dashboard

Eine automatisierte Testpipeline steigert die **Reaktionsgeschwindigkeit auf Fehler**, unterstützt **kontinuierliche Qualitätssicherung** und fördert das Vertrauen in neue Releases.

---

## 10.7 Herausforderungen bei der Toolnutzung

Trotz aller Vorteile können Testwerkzeuge auch neue Probleme mit sich bringen:

- Komplexität bei der Einführung und Wartung
- Mangelnde Schulung oder Akzeptanz im Team
- Tool-Abhängigkeiten oder Vendor Lock-in
- Überautomatisierung ohne klare Teststrategie
- Technische Schulden durch veraltete Skripte

**Empfehlung:**  
Werkzeuge sind **Mittel zum Zweck**, keine Selbstzweck. Der Fokus sollte immer auf dem Testziel und dem Mehrwert für das Projekt liegen.

---

**Zusammenfassung:**  
Testwerkzeuge sind unverzichtbar für moderne, skalierbare und effiziente Qualitätssicherung. Die passende Toolauswahl, eine durchdachte Integration und die richtige Kombination aus Mensch, Methode und Maschine machen den Unterschied zwischen technischer Spielerei und echtem Qualitätsgewinn.



# **Kapitel 11: Testautomatisierung**

## 11.1 Einführung

Testautomatisierung ist ein zentraler Bestandteil moderner Softwareentwicklung. Sie ermöglicht das **wiederholbare, schnelle und zuverlässige Ausführen von Tests**, reduziert den manuellen Aufwand und unterstützt Continuous Integration und Continuous Delivery (CI/CD).

Durch Automatisierung lassen sich Regressionstests effizient durchführen, Fehler frühzeitig erkennen und der Entwicklungszyklus beschleunigen. Gleichzeitig erfordert Testautomatisierung jedoch Planung, Wartung und eine klare Strategie – sie ist kein Selbstläufer.

---

## 11.2 Ziele und Vorteile der Testautomatisierung

**Hauptziele:**

- Reduktion manueller Testaufwände
- Erhöhung der Testabdeckung
- Frühzeitige Fehlererkennung
- Verbesserung der Wiederholbarkeit und Nachvollziehbarkeit
- Unterstützung kontinuierlicher Entwicklungsprozesse

**Vorteile:**

| Vorteil                         | Wirkung                                                         |
|----------------------------------|------------------------------------------------------------------|
| Schnelle Ausführung              | Tests können jederzeit und häufig ausgeführt werden             |
| Wiederverwendbarkeit             | Testskripte können mehrfach verwendet und angepasst werden      |
| Fehlerreduktion                  | Menschliche Flüchtigkeitsfehler werden minimiert                |
| Skalierbarkeit                   | Große Testmengen lassen sich effizient verwalten                |
| Dokumentation und Reporting     | Automatisierte Ergebnisse sind reproduzierbar und auswertbar    |

---

## 11.3 Grenzen und Herausforderungen

Trotz aller Vorteile ist Testautomatisierung **kein Allheilmittel**. Herausforderungen sind u. a.:

- **Hohe Anfangsinvestition**: Zeit und Know-how für Aufbau und Toolauswahl
- **Wartungsaufwand**: Änderungen im System erfordern Pflege der Tests
- **Falsche Erwartungen**: Automatisierung ersetzt keine vollständige Teststrategie
- **Ungeeignete Tests**: Explorative oder Usability-Tests sind nur schwer automatisierbar

**Fazit:** Nicht alles, was automatisiert werden kann, **sollte** auch automatisiert werden.

---

## 11.4 Was sollte automatisiert werden – und was nicht?

**Geeignet zur Automatisierung:**

- Regressionstests
- Smoke-Tests
- Rechenlogiken mit stabilen Eingaben/Ausgaben
- API-Tests
- Datenbanktests
- Unit-Tests

**Eingeschränkt geeignet:**

- GUI-Tests mit stark wechselnden Layouts
- Explorative Tests
- Usability-Tests
- Einmalige, projektbezogene Tests

Ein häufiger Fehler ist es, „alles“ automatisieren zu wollen. Eine **klare Priorisierung nach Kosten-Nutzen-Kriterien** ist entscheidend.

---

## 11.5 Architektur automatisierter Tests

Ein erfolgreiches Testautomatisierungs-Framework basiert auf einer durchdachten Architektur:

### Schichtenmodell (Test Automation Pyramid nach Mike Cohn):

```
                [ GUI-Tests ]
              [ API-/Service-Tests ]
           [ Unit-Tests (große Basis) ]
```

**Prinzipien:**

- **Mehr Tests auf niedriger Ebene (Unit)**, da diese schnell und stabil sind
- **Weniger Tests auf hoher Ebene (GUI)**, da diese fehleranfälliger und langsamer sind
- **Saubere Trennung von Testlogik und Testdaten**
- **Modularität und Wiederverwendbarkeit**

---

## 11.6 Frameworks und Tools

### 11.6.1 Unit-Test-Frameworks

- JUnit (Java), NUnit (.NET), PyTest (Python), Jest (JavaScript)

### 11.6.2 UI-Test-Tools

- Selenium (Web), Cypress, Playwright, TestCafe  
- Appium (Mobile), Detox (React Native)

### 11.6.3 API-Test-Tools

- Postman + Newman  
- RestAssured (Java), Karate DSL  
- k6 (auch Performance-fähig)

### 11.6.4 Framework-Typen

- **Data-Driven**: Testlogik bleibt gleich, Daten ändern sich (z. B. Excel, JSON)
- **Keyword-Driven**: Wiederverwendbare Schlüsselwörter als Bausteine
- **Behavior-Driven (BDD)**: Tests in natürlicher Sprache (z. B. Gherkin, Cucumber)

---

## 11.7 Best Practices

- **Früh automatisieren** („Shift Left“) – schon ab Unit-Tests
- **Regelmäßige Pflege der Tests** – sonst droht „Test Debt“
- **Sinnvolle Fehlerbehandlung** in Skripten
- **Klare Namenskonventionen und Logs**
- **Automatisierung in CI/CD integrieren** (z. B. Jenkins, GitLab CI)
- **Testdaten gezielt steuern** – für stabile, reproduzierbare Ergebnisse
- **Metriken erfassen** – z. B. Ausführungszeit, Fehlerquote, Abdeckungsgrad

---

## 11.8 Testautomatisierung im agilen Umfeld

In agilen Teams ist Testautomatisierung **kein Spezialgebiet**, sondern Teil der Entwicklungsaufgabe. Devs und Tester:innen arbeiten gemeinsam an:

- Automatisierten Unit- und Integrationstests
- Testskripten für User Stories
- Ständiger Pflege der Tests im Sprint
- Definition of Done inkl. „Tests sind grün“

Automatisierung ist Voraussetzung für **kontinuierliches Feedback** und schnelle Iterationen.

---

## 11.9 ROI der Testautomatisierung

Die Frage nach dem Return on Investment (ROI) ist legitim – insbesondere bei umfangreicher Testautomatisierung.

**Einflussfaktoren:**

- Häufigkeit der Testdurchläufe
- Stabilität des Systems
- Komplexität der Tests
- Wartungsaufwand
- Manuelle Testdauer im Vergleich

**Faustregel:**  
Je öfter ein Testfall ausgeführt wird, desto **lohnender** ist seine Automatisierung.

---

**Zusammenfassung:**  
Testautomatisierung ist ein Schlüssel für Geschwindigkeit, Effizienz und Qualität – wenn sie strategisch geplant, intelligent umgesetzt und regelmäßig gepflegt wird. Die Kombination aus solider Architektur, passenden Tools und einem klaren Fokus auf den Mehrwert macht Automatisierung zu einem unverzichtbaren Bestandteil moderner Softwareentwicklung.



# **Kapitel 12: Testing in agilen Projekten**

## 12.1 Einführung

Agile Methoden wie Scrum, Kanban oder Extreme Programming (XP) haben die Softwareentwicklung grundlegend verändert. Statt langer Planungsphasen und starrem Wasserfallmodell stehen nun **kurze Iterationen**, **kontinuierliche Lieferung** und **enge Zusammenarbeit im Team** im Vordergrund.

Auch das Testen muss sich anpassen: In agilen Projekten ist Qualität **nicht die alleinige Verantwortung eines Testteams**, sondern **eine gemeinsame Aufgabe des gesamten Teams** – von Anfang an und fortlaufend.

---

## 12.2 Prinzipien agilen Testens

Agiles Testen folgt den Werten und Prinzipien des **Agilen Manifests** und bringt spezifische Überzeugungen mit sich:

- **Testen ist integraler Bestandteil des Entwicklungsprozesses**
- **Tester:innen arbeiten eng mit Entwickler:innen und Product Ownern zusammen**
- **Tests begleiten jede User Story**
- **Frühes, häufiges und kontinuierliches Feedback ist entscheidend**
- **Automatisierung ist ein zentrales Element**
- **Manuelle und explorative Tests behalten ihren Platz – gezielt und fokussiert**

Der Fokus liegt auf **präventivem Testen**: Fehler sollen nicht nur gefunden, sondern idealerweise **gar nicht erst eingebaut** werden.

---

## 12.3 Rolle der Tester:innen im agilen Team

In klassischen Projekten existiert oft ein separates Testteam. In agilen Projekten hingegen sind Tester:innen **Teil des Entwicklungsteams** – sie bringen Qualitätsperspektive und Testspezialisierung ein.

**Aufgaben von Tester:innen im agilen Kontext:**

- Unterstützung bei der Formulierung klarer Akzeptanzkriterien
- Ableitung und Umsetzung von Testfällen für User Stories
- Erstellung und Pflege automatisierter Tests
- Durchführung explorativer Tests
- Testdatenmanagement
- Fehlermanagement und Unterstützung bei Analyse

**Soft Skills wie Kommunikation, Empathie und Flexibilität** sind besonders gefragt, da Tester:innen eine **Brückenfunktion** zwischen Entwicklung, Fachbereich und Produktverantwortung übernehmen.

---

## 12.4 Testaktivitäten im agilen Lebenszyklus

### Planung (Sprint Planning)

- Review der User Stories aus Testsicht
- Mitwirkung bei Aufwandsschätzungen
- Definition der Akzeptanzkriterien gemeinsam mit dem Team

### Umsetzung (Sprint)

- Erstellen von Testfällen parallel zur Entwicklung
- Testautomatisierung (Unit-, API-, UI-Tests)
- Exploratives Testen neuer Funktionen
- Pflege und Aktualisierung bestehender Tests

### Review und Retrospektive

- Gemeinsame Analyse von Testergebnissen
- Bewertung der Testabdeckung
- Lessons Learned zur Verbesserung der Testprozesse

**Tipp:**  
Tests gehören in die **Definition of Done (DoD)** – eine User Story ist erst fertig, wenn auch alle Tests erfolgreich abgeschlossen wurden.

---

## 12.5 Testmethoden im agilen Umfeld

Agile Teams nutzen eine Vielzahl etablierter Testmethoden – angepasst an die kurze Taktung und hohe Änderungsfrequenz:

### Testgetriebene Entwicklung (TDD)

- Tests werden **vor** dem eigentlichen Code geschrieben
- Zyklus: Test schreiben → Code schreiben → Test bestehen lassen → Refaktorieren
- Ergebnis: saubere, getestete und wartbare Einheiten

### Behavior-Driven Development (BDD)

- Gemeinsame Sprache für Fachbereich, Entwicklung und Test (z. B. Gherkin)
- Spezifikation durch Beispiele („Given – When – Then“)
- Tools: Cucumber, SpecFlow, Behave

### Akzeptanztestgetriebene Entwicklung (ATDD)

- Fokus auf **formalisierte Akzeptanzkriterien**
- Enge Zusammenarbeit mit dem Product Owner
- Automatisierte Akzeptanztests dienen als Verifikation der Geschäftsanforderungen

---

## 12.6 Automatisierung in agilen Projekten

Testautomatisierung ist in agilen Projekten **essentiell**, um mit der Geschwindigkeit und Änderungsfrequenz Schritt zu halten:

- **Unit-Tests** durch Entwickler:innen
- **API-Tests** und **Integrationstests**
- **GUI-Tests** für Ende-zu-Ende-Szenarien
- **Regressionstests** bei jedem Sprint

**Automatisierte Tests werden in die CI/CD-Pipeline integriert** und liefern unmittelbares Feedback über die Qualität neuer Commits.

---

## 12.7 Exploratives Testen im Sprint

Neben strukturierten Tests bleibt Raum für **kreative, erfahrungsbasierte Tests**, z. B.:

- Aufspüren unerwarteter Seiteneffekte
- Usability-Probleme und Unstimmigkeiten
- Nicht abgedeckte Sonderfälle

Diese Tests werden **gezielt eingesetzt**, um funktionale blinde Flecken aufzudecken – insbesondere bei neuen oder instabilen Features.

---

## 12.8 Testdokumentation in agilen Projekten

Agil heißt nicht, auf Dokumentation zu verzichten – sondern, **das richtige Maß** zu finden:

- Kurze, prägnante Testfälle (z. B. in BDD-Format oder Checklisten)
- Nachvollziehbare Testergebnisse
- Automatisierte Tests als lebende Dokumentation
- Fokus auf Verständlichkeit und Wiederverwendbarkeit

**Werkzeuge:** Jira, Xray, Zephyr, TestRail, Living Documentation Tools

---

## 12.9 Herausforderungen und Erfolgsfaktoren

### Typische Herausforderungen:

- Zeitdruck und parallele Entwicklung/Test
- Unklare oder instabile Anforderungen
- Hoher Wartungsaufwand bei Automatisierung
- Fehlende Testdaten oder Testumgebungen

### Erfolgsfaktoren:

- Frühe Einbindung von Tester:innen ins Team
- Gemeinsames Qualitätsverständnis
- Klare Definition von Done inkl. Tests
- Sinnvolle Automatisierung und Reporting
- Fokus auf Kommunikation und Feedback

---

**Zusammenfassung:**  
Agiles Testen bedeutet: früh, kontinuierlich, gemeinsam und automatisiert. Die Rolle der Tester:innen wandelt sich vom „Fehlersucher“ zum **qualitätsbewussten Teammitglied**, das aktiv den Entwicklungsprozess mitgestaltet. Erfolgreiches agiles Testen erfordert die Kombination aus methodischem Wissen, Teamarbeit und technischer Exzellenz.



# **Kapitel 13: DevOps und Continuous Testing**

## 13.1 Einführung

Die zunehmende Geschwindigkeit der Softwareentwicklung erfordert neue Ansätze zur **Integration von Entwicklung, Testing und Betrieb**. Mit **DevOps** entsteht ein ganzheitliches Paradigma, das darauf abzielt, Software schneller, zuverlässiger und kontinuierlich bereitzustellen.

In diesem Kontext spielt **Continuous Testing** eine zentrale Rolle: Tests werden **früh, häufig und automatisiert** in die Delivery-Pipeline integriert, um **kontinuierliches Feedback zur Qualität** zu liefern.

---

## 13.2 Was ist DevOps?

**DevOps** steht für die enge Verzahnung von **Development (Dev)** und **Operations (Ops)**. Es ist mehr als ein technischer Ansatz – es ist eine **Kultur und Denkweise**, die Zusammenarbeit, Automatisierung und Verantwortung über den gesamten Lebenszyklus hinweg fördert.

**Kernprinzipien von DevOps:**

- **Automatisierung über alle Phasen hinweg**
- **Kontinuierliche Integration und Lieferung (CI/CD)**
- **Monitoring und Feedback in Echtzeit**
- **Shift Left & Shift Right**: Qualität von Anfang bis Ende

In einer DevOps-Kultur ist Qualität **nicht Aufgabe einzelner Rollen**, sondern **integrierter Bestandteil jedes Schrittes**.

---

## 13.3 Was ist Continuous Testing?

**Continuous Testing** ist der Prozess, bei dem Tests automatisiert und kontinuierlich in den Softwareentwicklungs- und Bereitstellungsprozess eingebunden werden – mit dem Ziel, **schnelles und zuverlässiges Feedback** zur Produktqualität zu liefern.

### Merkmale:

- Tests laufen bei jedem Commit, Build oder Deployment
- Automatisierte Tests auf verschiedenen Ebenen (Unit, API, UI, Security, Performance)
- Integration in CI/CD-Pipelines
- Schnelle Fehlererkennung und Rückmeldung

### Ziele:

- **Risiken früh erkennen**
- **Release-Zyklen beschleunigen**
- **Qualität in Echtzeit messbar machen**

---

## 13.4 Shift Left und Shift Right Testing

### Shift Left

- Tests und Qualitätssicherung **früh im Entwicklungsprozess**
- Fokus auf Prävention statt nachträgliche Fehlerfindung
- Beispiele: TDD, Codeanalyse, API-Tests im Build

### Shift Right

- Tests und Monitoring auch **nach dem Release**
- Fokus auf **Systemverhalten im realen Betrieb**
- Beispiele: Canary Releases, A/B-Tests, Chaos Engineering, Benutzerfeedback

**Fazit:** Ein ganzheitlicher Qualitätsansatz berücksichtigt **beide Richtungen** und etabliert Tests **entlang der gesamten Value Chain**.

---

## 13.5 Testarten im DevOps-Kontext

In Continuous Testing werden verschiedene Testarten automatisiert und orchestriert:

| Testart               | Zweck                                                   | Zeitpunkt            |
|------------------------|----------------------------------------------------------|-----------------------|
| **Unit-Tests**         | Prüfung einzelner Komponenten                           | Bei jedem Commit      |
| **Integrationstests**  | Prüfung von Schnittstellen zwischen Modulen             | Nach Build            |
| **API-Tests**          | Überprüfung von Serviceschnittstellen                   | Im Build & Deployment |
| **UI-Tests**           | Validierung der Benutzeroberfläche                      | Nach Deployment       |
| **Smoke-Tests**        | Schneller Check nach Bereitstellung                     | Staging/Prod          |
| **Security-Tests**     | Schwachstellenscans, Policy Checks                      | Während der Pipeline  |
| **Performance-Tests**  | Lastsimulation, Antwortzeiten                           | On Demand oder Nightly|
| **Monitoring & Logging**| Verhalten im Betrieb, Anomalien erkennen               | Laufend               |

---

## 13.6 Toolchain für Continuous Testing

### CI/CD-Plattformen

- Jenkins  
- GitLab CI  
- GitHub Actions  
- Azure DevOps  
- CircleCI

### Testautomatisierung & Reporting

- Selenium, Cypress, Playwright (UI)  
- Postman, RestAssured, k6 (API/Performance)  
- JUnit, NUnit, PyTest (Unit)  
- Allure, ReportPortal (Reporting)

### Sicherheits- und Qualitätsanalyse

- SonarQube (Codequalität)  
- OWASP ZAP, Snyk (Security)  
- Trivy, Aqua (Container-Sicherheit)

### Monitoring & Observability

- Prometheus + Grafana  
- Elastic Stack (ELK)  
- Datadog, New Relic  
- Splunk

**Tipp:** Tools sollten **automatisiert, versionierbar und integriert** eingesetzt werden – Infrastruktur als Code gilt auch für Testumgebungen.

---

## 13.7 Testumgebungen und Infrastruktur

Continuous Testing erfordert stabile und skalierbare Testumgebungen. Klassische Herausforderungen:

- **Verfügbarkeit paralleler Testumgebungen**
- **Datenkonsistenz und Testdatenmanagement**
- **Reproduzierbarkeit von Fehlern**

**Lösungen:**

- Virtualisierung und Containerisierung (Docker, Kubernetes)
- On-Demand-Umgebungen per Infrastructure as Code (Terraform, Helm)
- Snapshot- und Mocking-Technologien
- Service-Virtualisierung für nicht verfügbare Komponenten

---

## 13.8 Erfolgsfaktoren für Continuous Testing

- **Teststrategie als Teil der Delivery-Strategie**
- **Hoher Automatisierungsgrad mit sinnvollem Scope**
- **Schnelles Feedback und kurze Testlaufzeiten**
- **Monitoring-gestützte Validierung im Livebetrieb**
- **Eng verzahnte Teams (Dev, QA, Ops)**
- **Kultur des Experimentierens und Lernens**

---

## 13.9 Herausforderungen

- Komplexität bei Integration in bestehende Prozesse
- Hoher initialer Aufwand bei Automatisierung
- Vermeidung instabiler Testskripte („Flaky Tests“)
- Überwachung der Testqualität selbst (z. B. durch „Test Debt“)
- Kulturwandel: Qualität als gemeinsame Verantwortung verankern

---

**Zusammenfassung:**  
DevOps und Continuous Testing bringen Geschwindigkeit und Qualität in Einklang. Durch frühes, automatisiertes und kontinuierliches Testen entsteht ein belastbarer Software-Lifecycle, der schnelle Releases und hohe Kundenzufriedenheit ermöglicht. Doch entscheidend sind nicht nur Tools – sondern die richtige Strategie, Teamzusammenarbeit und Qualitätskultur.



# **Kapitel 14: Testen von modernen Architekturen**

## 14.1 Einführung

Moderne Softwarearchitekturen wie **Microservices**, **Cloud-native Anwendungen**, **containerisierte Systeme** oder **eventgetriebene Architekturen** stellen neue Anforderungen an das Software Testing. Klassische Teststrategien greifen hier oft zu kurz – es braucht **neue Werkzeuge, Paradigmen und Denkweisen**, um Qualität in hochdynamischen, verteilten Systemen sicherzustellen.

In diesem Kapitel beleuchten wir, wie sich Testprozesse an moderne Architekturen anpassen lassen und welche Besonderheiten in Planung, Automatisierung und Infrastruktur zu beachten sind.

---

## 14.2 Testherausforderungen moderner Architekturen

Moderne Architekturen zeichnen sich durch folgende Eigenschaften aus:

- **Verteilte Komponenten** (Microservices, APIs, externe Services)
- **Dynamische Infrastruktur** (z. B. in Kubernetes orchestriert)
- **Schnelle Release-Zyklen**
- **Unabhängig deploybare Module**
- **Komplexe Schnittstellen und Datenflüsse**

Daraus ergeben sich typische Testprobleme:

| Herausforderung                    | Testauswirkung                                           |
|------------------------------------|----------------------------------------------------------|
| Unabhängige Services               | Integrationstests sind aufwändiger                      |
| Asynchrone Kommunikation           | Timing-Fehler und Event-Ketten schwer zu verfolgen      |
| Kurzlebige Umgebungen              | Testumgebung muss automatisiert reproduzierbar sein     |
| API-First-Design                   | Fokus auf Schnittstellenverträge und deren Validierung  |
| Polyglotte Technologiestacks       | Tests müssen technologieunabhängig orchestriert werden  |

---

## 14.3 Testing in Microservice-Architekturen

**Microservices** sind kleine, unabhängige Dienste mit klar definierten Schnittstellen. Sie werden eigenständig entwickelt, getestet, deployed und skaliert.

### Teststufen im Microservices-Kontext:

| Ebene                | Inhalt                                               | Ziel                                               |
|----------------------|------------------------------------------------------|----------------------------------------------------|
| **Unit-Tests**       | Logik innerhalb eines Services                      | Fehler früh erkennen                              |
| **Contract Tests**   | Überprüfung der API-Verträge                        | Sicherstellen der Kompatibilität                  |
| **Service-Tests**    | Tests einzelner Microservices über REST/HTTP etc.   | Black-Box-Verifikation der Funktionalität         |
| **Integrationstests**| Zusammenspiel mehrerer Services                     | Fehler an Schnittstellen aufdecken                |
| **End-to-End-Tests** | Gesamtsystem mit allen Services                     | Benutzerfluss und kritische Pfade testen          |

**Tipp:** Besonders bewährt hat sich das **Testing Pyramid Model**, ergänzt um **Contract-Testing**.

---

## 14.4 API-Tests

APIs sind das Rückgrat moderner Systeme. Eine saubere Teststrategie umfasst:

- **Funktionsprüfung einzelner Endpunkte** (GET, POST, PUT, DELETE …)
- **Validierung der Ein- und Ausgabeformate** (JSON, XML)
- **Statuscodes, Fehlerbehandlung, Timeouts**
- **Authentifizierung/Autorisierung (OAuth, JWT, API Keys)**
- **Vertragstests (Consumer-Driven Contracts)** z. B. mit Pact

**Werkzeuge:**
- Postman, Newman  
- RestAssured (Java), Karate DSL  
- Insomnia, Hoppscotch  
- Pact, Spring Cloud Contract

---

## 14.5 Container- und Infrastrukturtests

Mit der zunehmenden Verwendung von **Docker-Containern** und **Infrastructure as Code** (IaC) müssen auch Infrastruktur und Deployments getestet werden.

### Wichtige Aspekte:

- **Build-Tests**: Ist das Container-Image korrekt aufgebaut?
- **Configuration Tests**: Stimmt die Umgebungskonfiguration?
- **Security Scans**: Enthält das Image bekannte Schwachstellen?
- **IaC-Tests**: Validierung von Terraform, Helm, Ansible etc.
- **Runtime-Tests**: Verhalten in der Zielumgebung (z. B. Kubernetes)

**Werkzeuge:**

- Testcontainers (Java, Node, Python)  
- Trivy, Clair, Anchore (Sicherheit)  
- Terratest (Go), Kitchen-Terraform  
- Kubeval, Helm-Test

---

## 14.6 Event-Driven Architectures und Messaging

Eventbasierte Systeme (z. B. mit Kafka, RabbitMQ, SNS/SQS) kommunizieren asynchron über Ereignisse. Das Testen erfordert hier neue Techniken:

- **Verifikation von Events**: Inhalte, Formate, Sequenzen
- **Testen von Consumer-Logik**: Wie wird auf Events reagiert?
- **Simulation von Producer/Consumer** durch Mocks oder Test-Topics
- **Chaos- und Delay-Tests**: Was passiert bei verspäteten oder doppelten Nachrichten?

**Herausforderung:**  
Testen in einem **nicht-deterministischen Umfeld** mit potenziellen Seiteneffekten.

---

## 14.7 Monitoring, Observability & Testing in Production

In dynamischen Architekturen ist das **Testen im Livebetrieb (Shift Right)** oft notwendig oder sinnvoll:

- **Canary Releases**: Neue Funktionen werden schrittweise für Teilmengen der Nutzer aktiviert
- **Feature Toggles**: Aktivieren/Deaktivieren einzelner Funktionen zu Testzwecken
- **A/B-Tests**: Vergleich verschiedener Varianten im Echtbetrieb
- **Chaos Engineering**: Kontrolliertes Einführen von Fehlern, um Resilienz zu testen
- **Monitoring & Tracing**: Live-Daten zur Systemgesundheit

**Beispiel-Werkzeuge:**

- Prometheus + Grafana  
- OpenTelemetry, Jaeger  
- LaunchDarkly (Feature Toggles)  
- Gremlin (Chaos Engineering)

---

## 14.8 Testumgebungen und Daten

**Reproduzierbare, automatisierte Testumgebungen** sind Pflicht. Sie sollten:

- **On-Demand erzeugbar** sein (z. B. per Helm, Docker Compose)
- **Realitätsnah** (aber nicht identisch mit Produktion) sein
- **Echte Testdaten** enthalten – DSGVO-konform oder anonymisiert

**Empfehlung:** Testdaten und Testumgebungen gehören in die CI/CD-Pipeline wie der Code selbst.

---

## 14.9 Best Practices

- **Frühzeitige Testbarkeit bei der Architektur berücksichtigen** (Testability as Design Principle)
- **Service-Verträge festlegen und testen (Contract Testing)**
- **Infrastruktur als Code auch testen**
- **Shift-Left und Shift-Right kombinieren**
- **Monitoring und Telemetrie als Teil der Qualitätssicherung verstehen**
- **Fehlertoleranz und Wiederherstellbarkeit gezielt prüfen**

---

**Zusammenfassung:**  
Moderne Architekturen verlangen ein neues Denken im Software Testing: vernetzt, automatisiert, dynamisch. Klassische Testansätze werden erweitert um API-Tests, Container-Validierung, Eventfluss-Prüfungen und Production Observability. Wer testbare Architekturen baut und das Testing als integralen Teil versteht, schafft robuste Systeme in einer komplexen Welt.



# **Kapitel 15: Softwarequalität ganzheitlich verstehen**

## 15.1 Einführung

Was ist eigentlich **Softwarequalität**? Die meisten würden sagen: Eine Software funktioniert fehlerfrei. Doch Qualität umfasst weit mehr als nur die Abwesenheit von Bugs. Sie betrifft **wie gut eine Software ihren Zweck erfüllt, wie zuverlässig sie läuft, wie sicher, bedienbar und wartbar** sie ist – heute und in Zukunft.

In diesem Kapitel werfen wir einen ganzheitlichen Blick auf Softwarequalität und zeigen, wie sie systematisch beschrieben, gemessen und abgesichert werden kann.

---

## 15.2 Qualität aus verschiedenen Perspektiven

Softwarequalität ist **mehrdimensional** und hängt von den jeweiligen Stakeholdern ab:

| Perspektive        | Fokus                                              |
|--------------------|----------------------------------------------------|
| **Endnutzer**       | Benutzerfreundlichkeit, Zuverlässigkeit           |
| **Kunde/Auftraggeber** | Erfüllung der Anforderungen, Wirtschaftlichkeit  |
| **Entwicklungsteam** | Wartbarkeit, Lesbarkeit, Erweiterbarkeit          |
| **Betrieb**         | Stabilität, Monitoring, Sicherheit                 |
| **Gesetzgeber/Regulator** | Konformität mit Normen und Standards           |

**Fazit:** Qualität entsteht im Zusammenspiel von Technik, Funktion, Mensch und Organisation.

---

## 15.3 Das ISO/IEC-25010 Qualitätsmodell

Die internationale Norm **ISO/IEC 25010** definiert ein umfassendes Modell zur Bewertung von Softwarequalität. Sie unterscheidet zwischen:

- **Produktqualität**
- **Qualität im Gebrauch**

### 15.3.1 Produktqualität

Hier geht es um **inhärente Eigenschaften** der Software. Das Modell definiert acht Hauptmerkmale:

1. **Funktionale Eignung** – Erfüllt die Software ihre vorgesehenen Aufgaben?
2. **Zuverlässigkeit** – Wie robust ist sie gegenüber Fehlern und Last?
3. **Benutzbarkeit** – Wie gut ist sie bedienbar und verständlich?
4. **Effizienz** – Wie performant und ressourcenschonend arbeitet sie?
5. **Wartbarkeit** – Wie leicht lässt sie sich ändern oder erweitern?
6. **Übertragbarkeit** – Wie gut läuft sie in anderen Umgebungen?
7. **Sicherheit** – Wie gut schützt sie Daten und Systeme?
8. **Kompatibilität** – Wie gut funktioniert sie im Zusammenspiel mit anderen Systemen?

### 15.3.2 Qualität im Gebrauch

Diese Perspektive bewertet die **Wirkung der Software im Anwendungskontext**:

- **Effektivität** – Zielerreichung durch den Nutzer
- **Effizienz** – Aufwand im Verhältnis zum Ergebnis
- **Zufriedenheit** – Subjektive Nutzererfahrung
- **Freiheit von Risiken** – Vermeidung unerwünschter Nebeneffekte
- **Kontextabdeckung** – Anpassungsfähigkeit an verschiedene Nutzungsszenarien

---

## 15.4 Qualität messbar machen

Um Qualität systematisch zu verbessern, muss sie **messbar** sein. Beispiele für **Qualitätsmetriken**:

| Qualitätsmerkmal     | Mögliche Metriken                                   |
|----------------------|-----------------------------------------------------|
| **Funktionalität**    | Testabdeckung, Anzahl erfüllter Anforderungen       |
| **Zuverlässigkeit**   | Mean Time Between Failures (MTBF), Crash Rate       |
| **Benutzbarkeit**     | Fehlbedienungsrate, Nutzerfeedback, Usability Score |
| **Effizienz**         | Antwortzeit, Durchsatz, CPU-/Speichernutzung        |
| **Wartbarkeit**       | Zyklomatische Komplexität, Änderungsaufwand         |
| **Sicherheit**        | Anzahl offener Schwachstellen, Penetration-Test-Ergebnisse |

**Tipp:** Metriken müssen **zielgerichtet, nachvollziehbar und kontinuierlich interpretiert** werden – sonst bleiben sie reine Zahlen.

---

## 15.5 Qualität in Prozessen und Teams

Qualität entsteht nicht nur im Produkt, sondern auch im Prozess:

- **Klare Definition von Anforderungen und Akzeptanzkriterien**
- **Code Reviews und Pair Programming**
- **Automatisierte Tests und Continuous Integration**
- **Refactoring und technisches Schuldenmanagement**
- **Testgetriebene Entwicklung (TDD)**
- **Retrospektiven und kontinuierliche Verbesserung**

**Teamkultur** spielt eine zentrale Rolle: Qualität wird nur entstehen, wenn sie **gelebt wird** – nicht nur dokumentiert.

---

## 15.6 Qualitätsziele und Trade-offs

In der Realität stehen Qualitätsmerkmale oft **in Konkurrenz zueinander**:

- Performance vs. Sicherheit  
- Time-to-Market vs. Wartbarkeit  
- Funktionsvielfalt vs. Zuverlässigkeit

Deshalb müssen **Qualitätsziele priorisiert und kommuniziert** werden:

- Was ist „gut genug“ für die aktuelle Version?
- Welche Risiken sind tolerierbar – und welche nicht?
- Wo lohnt sich Investition in Test, Automatisierung oder Redesign?

Ein gemeinsames Qualitätsverständnis zwischen Stakeholdern, Entwicklung und Test ist essenziell.

---

## 15.7 Qualität by Design

„Quality is not an accident; it is always the result of intelligent effort.“ – John Ruskin

**Qualitätsorientiertes Design** bedeutet, Qualität von Anfang an zu berücksichtigen:

- **Testability as a Design Principle**
- **Secure by Design**
- **User-Centered Design**
- **Modularisierung und lose Kopplung**
- **Monitoring und Feedbackmechanismen einplanen**

Nicht zuletzt gilt: **Testbarkeit ist ein Qualitätsmerkmal an sich** – wer testbare Software schreibt, schreibt oft auch wartbare, robuste und verständliche Software.

---

**Zusammenfassung:**  
Softwarequalität ist mehr als nur „funktioniert“. Sie ist ein vielschichtiges Konzept, das Technik, Mensch, Organisation und Kontext vereint. Wer Qualität ganzheitlich versteht, kann sie gezielt planen, messen, verbessern – und als strategischen Erfolgsfaktor nutzen.




# **Kapitel 16: Ethik im Software Testing**

## 16.1 Einführung

Software beeinflusst täglich das Leben von Milliarden Menschen – direkt oder indirekt. Entsprechend groß ist die Verantwortung derjenigen, die diese Systeme **entwickeln, testen und freigeben**. Tester:innen stehen dabei oft an der **Schnittstelle zwischen Technik und Auswirkung**, zwischen Fehler und Vertrauen.

**Ethik im Software Testing** bedeutet, sich dieser Verantwortung bewusst zu sein und die eigenen Handlungen – von der Testauswahl bis zur Kommunikation von Ergebnissen – an **Werten wie Integrität, Transparenz und Fairness** auszurichten.

---

## 16.2 Verantwortung des Testers

Ein Test ist niemals neutral. Schon durch die Auswahl dessen, **was getestet wird und was nicht**, treffen wir **implizit Entscheidungen über Risiken, Prioritäten und Werte**. Wer testet, übernimmt Verantwortung:

- Für die Qualität des Produkts
- Für die Benutzer:innen, die es nutzen
- Für die Gesellschaft, die durch Software beeinflusst wird

**Kernfragen:**

- Welche Folgen kann ein nicht entdeckter Fehler haben?
- Wer ist betroffen, wenn eine Funktion nicht wie erwartet arbeitet?
- Welche ethischen Risiken verbergen sich hinter technischen Entscheidungen?

---

## 16.3 Wahrhaftigkeit und Transparenz

Ethisches Verhalten im Testing bedeutet auch, **offen und ehrlich** mit Testergebnissen, Risiken und Grenzen umzugehen. Dazu gehört:

- **Keine Manipulation von Testergebnissen**, um ein System „besser dastehen zu lassen“
- **Offene Kommunikation über bekannte Schwächen** – auch wenn sie unbequem sind
- **Klares Benennen von Risiken**, auch wenn sie nicht durch Tests abgedeckt wurden
- **Keine „Kosmetiktests“**, nur um Zahlen zu erfüllen

**Integrität bedeutet**: lieber ein unangenehmer Befund als ein beschönigter Report.

---

## 16.4 Umgang mit Testdaten

Testdaten enthalten oft **sensible Informationen** – ob aus realen Datenbanken, Kundenmustern oder externen Quellen. Der ethisch verantwortungsvolle Umgang mit Testdaten ist zwingend notwendig:

- **Keine Verwendung von Produktivdaten ohne Anonymisierung**
- **Einhaltung von Datenschutzgesetzen (z. B. DSGVO)**
- **Verantwortungsbewusste Löschung temporärer Daten**
- **Schutz von personenbezogenen Daten auch in Testumgebungen**
- **Sorgfältiger Umgang mit Zugriffsrechten**

**Testdaten müssen getestet werden** – auf Sicherheit, Relevanz und Datenschutzkonformität.

---

## 16.5 Fairness und Inklusion im Testing

Software kann **diskriminieren**, wenn Teststrategien bestimmte Gruppen, Nutzungsarten oder Technologien ausschließen. Ethisches Testing bedeutet, auch **Vielfalt und Gerechtigkeit** zu berücksichtigen:

- **Barrierefreiheit testen** (z. B. für Menschen mit Seh- oder Bewegungseinschränkungen)
- **Unterschiedliche Endgeräte, Altersgruppen und Sprachniveaus berücksichtigen**
- **Benachteiligung durch Algorithmen erkennen und melden**
- **Gender- und kultursensible Benennung, Designs und Texte überprüfen**

**Beispiel:** Ein KI-System zur Kreditbewertung wird nur mit historischen Daten getestet – und übernimmt unbeabsichtigt diskriminierende Muster.

---

## 16.6 Der ethische Umgang mit Fehlern

Fehler passieren – auch im Testing. Entscheidend ist, wie damit umgegangen wird:

- **Fehler und Versäumnisse offen eingestehen**
- **Nicht nach Schuld suchen, sondern nach Ursachen**
- **Prozesse kontinuierlich verbessern**
- **Lernkultur statt Angstkultur fördern**

**Ethisch testende Teams** setzen auf Zusammenarbeit, gegenseitiges Vertrauen und den gemeinsamen Willen zur Qualität – nicht auf Schuldzuweisungen.

---

## 16.7 Ethik in der Testautomatisierung und KI

Automatisierte Tests und KI-gestützte Testverfahren bringen neue ethische Fragen mit sich:

- Wie werden Entscheidungen von KI-Systemen bewertet, die im Testing eingesetzt werden?
- Wer ist verantwortlich, wenn ein „selbstheilender“ Test einen kritischen Fehler ignoriert?
- Reproduzieren KI-Testsysteme vorhandene Biases in Daten?

**Grundsatz:** Automatisierung entbindet nicht von ethischer Verantwortung – sie **verstärkt** sie unter Umständen.

---

## 16.8 Kodizes und Standards

Verschiedene Organisationen haben ethische Richtlinien für IT-Fachkräfte und Tester:innen veröffentlicht:

- **ISTQB Code of Ethics**
- **ACM Code of Ethics and Professional Conduct**
- **IEEE Software Engineering Code of Ethics**

Diese Kodizes fordern u. a.:

- Integrität und Sorgfalt
- Schutz der Öffentlichkeit
- Ehrlichkeit in Kommunikation
- Kompetenz und Weiterbildung
- Achtung der Privatsphäre

Sie können als **Leitplanken und Diskussionsgrundlage** im Team dienen – insbesondere bei ethisch schwierigen Entscheidungen.

---

**Zusammenfassung:**  
Ethisches Testing bedeutet: bewusst, verantwortlich und menschlich testen. Nicht alles, was technisch möglich ist, ist auch richtig. Tester:innen haben die Chance – und die Pflicht –, mit ihrem Wissen zur **Verlässlichkeit, Fairness und Menschlichkeit** digitaler Systeme beizutragen. Ethik beginnt nicht am Schreibtisch – sondern bei jedem Testfall.



# **Kapitel 17: Zukunft des Software Testings**

## 17.1 Einführung

Softwareentwicklung verändert sich rasant – durch neue Technologien, Plattformen, Geschäftsmodelle und Arbeitsweisen. Damit wandelt sich auch das **Software Testing**: von einer isolierten Disziplin hin zu einem **kontinuierlichen, intelligenten und integrierten Prozess**, der zunehmend von **Automatisierung, KI und Plattformvielfalt** geprägt ist.

Dieses Kapitel wirft einen Blick in die Zukunft des Software Testings – auf **Trends, Technologien und Rollenbilder**, die das Testen von morgen prägen werden.

---

## 17.2 Technologische Treiber des Wandels

Mehrere Entwicklungen verändern die Art, wie Software getestet wird:

- **Künstliche Intelligenz (KI) und Machine Learning (ML)**
- **Cloud-Computing und hybride Infrastrukturen**
- **Internet of Things (IoT)**
- **Low-Code- und No-Code-Plattformen**
- **Edge Computing**
- **Blockchain-Anwendungen**
- **Quantencomputing (zukünftig)**

Diese Technologien bringen **neue Testobjekte, Risiken und Möglichkeiten**, erfordern aber auch neue Denkweisen im Umgang mit Testdaten, Timing, Komplexität und Sicherheit.

---

## 17.3 KI im Software Testing

KI verändert das Testing in mehrfacher Hinsicht – als **Testobjekt** und als **Testwerkzeug**.

### KI als Testwerkzeug:

- **Intelligente Testfallgenerierung** auf Basis von Anforderungen oder Nutzungsdaten
- **Predictive Analytics** für Risiko- und Fehlerprognosen
- **Visual Testing** mit automatischer Erkennung von UI-Abweichungen
- **Self-healing Tests**: Testskripte passen sich automatisch an UI-Änderungen an
- **Anomalie-Erkennung** durch maschinelles Lernen im Monitoring

**Beispiele für Tools:** Testim, Mabl, Applitools, Test.AI

### Herausforderungen:

- Nachvollziehbarkeit und Erklärbarkeit von KI-Entscheidungen
- Bias in Trainingsdaten → falsche Testpriorisierung
- Validierung von KI-gestützter Testlogik selbst

---

## 17.4 Testen von KI-Systemen

KI-basierte Systeme (z. B. Sprachmodelle, Bilderkennung, Empfehlungssysteme) sind **nicht vollständig deterministisch** – das klassische Input/Output-Verständnis stößt an Grenzen.

**Besonderheiten:**

- **Testen von Modellen statt festen Regeln**
- **Validierung von Wahrscheinlichkeiten, Genauigkeit und Verzerrungen**
- **Testdaten müssen divers, balanciert und repräsentativ sein**
- **"Black-Box"-Testing schwieriger – Explainability-Ansätze notwendig**

Zukunftsfähige Teststrategien für KI-Systeme benötigen **interdisziplinäres Denken**: zwischen Test, Ethik, Statistik und Datenwissenschaft.

---

## 17.5 Low-Code / No-Code Testing

Mit dem Aufkommen von Low-Code- und No-Code-Plattformen (z. B. Mendix, OutSystems, PowerApps) entstehen Anwendungen ohne klassische Codebasis.

### Auswirkungen auf das Testing:

- Testende arbeiten **näher am Business**, nicht nur am Code
- Klassische Unit-Tests entfallen – Fokus auf Prozessflüsse und UI
- Testwerkzeuge müssen sich **visuellen Modellen anpassen**
- Steigende Bedeutung von **modellbasiertem und explorativem Testing**

**Chancen:**  
Mehr Menschen können testen – aber auch mehr Risiken durch ungetestete Businesslogik.

---

## 17.6 Testing als Teil intelligenter Delivery Pipelines

Moderne CI/CD-Prozesse entwickeln sich zu **intelligenten Test- und Delivery-Plattformen**, die in Echtzeit entscheiden:

- Welche Tests notwendig sind (Test-Impact-Analysis)
- Wo Tests ausgeführt werden (lokal, Cloud, Edge)
- Wie schnell neue Features ausgeliefert werden können

**Zukünftige Merkmale:**

- **Adaptive Testauswahl basierend auf Code-Änderungen**
- **Dynamische Ressourcenbereitstellung für Tests**
- **"Quality Gates" mit intelligenten Regeln**
- **Autonome Testentscheidungen mit menschlicher Kontrolle**

---

## 17.7 Neue Rollen und Kompetenzen

Die Rolle des/der Softwaretester:in wandelt sich grundlegend – von der Ausführung zur **Gestaltung und Steuerung von Qualitätssystemen**.

### Zukünftige Skill-Sets:

| Kompetenzbereich         | Beschreibung                                         |
|--------------------------|------------------------------------------------------|
| **Technik & Automatisierung** | Umgang mit Frameworks, Skriptsprachen, DevOps-Tools   |
| **KI & Datenverständnis**     | Umgang mit Algorithmen, Metriken, Datensätzen        |
| **Testarchitektur**           | Design von Teststrategien über Teams und Systeme hinweg |
| **Ethik & Verantwortung**     | Risikobewertung, Fairness, Datenschutz                 |
| **Kommunikation & Coaching**  | Arbeit in cross-funktionalen Teams, Wissensweitergabe  |

**Testing wird zum strategischen Berufsfeld mit Zukunft** – für technische Generalist:innen und ethische Spezialist:innen gleichermaßen.

---

## 17.8 Vision: Das Testlabor der Zukunft

Stellen wir uns eine Zukunft vor, in der:

- Tests automatisch aus Nutzerszenarien generiert werden
- Testumgebungen sich selbst konfigurieren
- Fehler prognostiziert statt nur entdeckt werden
- Qualität als Metrik in Echtzeit sichtbar ist
- Teams mehr Zeit für kreative Tests und Ethikfragen haben

Das **Testlabor der Zukunft** ist nicht nur automatisiert, sondern auch intelligent, menschenzentriert und lernfähig.

---

**Zusammenfassung:**  
Das Software Testing der Zukunft ist schneller, datengetriebener und intelligenter – aber auch komplexer und verantwortungsvoller. Die Kombination aus Technik, Ethik, Automatisierung und interdisziplinärem Denken wird zum Erfolgsfaktor. Wer die Veränderungen annimmt, gestaltet nicht nur bessere Software – sondern auch eine bessere digitale Zukunft.
