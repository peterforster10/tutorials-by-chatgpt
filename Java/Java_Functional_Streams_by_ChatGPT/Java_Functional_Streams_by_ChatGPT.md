# Funktionale Programmierung und Streams in Java by ChatGPT

## Prompt

Ich möchte Funktionale Programmierung (Lamda Expressions) und Streams in Java lernen. Ich kann die Grundlagen von Java. Erstelle mir eine Gliederung für einen umfassendes Tutorial.

## Inhalt

Um ein umfassendes Tutorial über funktionale Programmierung, Lambda-Ausdrücke und Streams in Java zu erstellen, ist es wichtig, eine Struktur zu haben, die schrittweise durch die Konzepte führt und dabei sowohl theoretische Grundlagen als auch praktische Anwendungen abdeckt. Hier ist eine mögliche Gliederung für ein solches Tutorial:

### Einleitung
- Überblick über funktionale Programmierung in Java
- Wichtigkeit von Lambda-Ausdrücken und Streams in modernem Java

### Teil 1: Grundlagen der funktionalen Programmierung in Java
1. **Einführung in funktionale Programmierung**
   - Was ist funktionale Programmierung?
   - Unterschiede zwischen imperativer und funktionaler Programmierung

2. **Lambda-Ausdrücke**
   - Syntax von Lambda-Ausdrücken
   - Funktionsinterfaces
   - Einsatzmöglichkeiten und Vorteile von Lambda-Ausdrücken

3. **Methodenreferenzen**
   - Syntax und Verwendung
   - Unterschiede zu Lambda-Ausdrücken

### Teil 2: Arbeiten mit Streams
4. **Einführung in Streams**
   - Was sind Streams?
   - Erstellen von Streams
   - Unterschied zwischen Collections und Streams

5. **Stream-Operationen**
   - Intermediäre Operationen (filter, map, flatMap, etc.)
   - Terminale Operationen (collect, forEach, reduce, etc.)
   - Unterschied zwischen intermediären und terminalen Operationen

6. **Collectors**
   - Sammeln von Daten aus Streams
   - Gruppieren, Zusammenführen und Partitionieren von Daten

### Teil 3: Fortgeschrittene Themen
7. **Parallel Streams**
   - Parallelisierung von Streams
   - Vor- und Nachteile, Best Practices

8. **Optionals**
   - Umgang mit Null-Werten in funktionaler Programmierung
   - Methoden von Optional

9. **Kombination von Streams und Lambda-Ausdrücken mit Collections**
   - Effektive Nutzung von Streams und Lambda-Ausdrücken mit Java Collections

### Teil 4: Praktische Anwendungen
10. **Fallstudien und Beispiele**
    - Anwendungsbeispiele für Streams und Lambda-Ausdrücke
    - Best Practices und häufige Fehler

11. **Übungen und Lösungen**
    - Praktische Übungen zu jedem Abschnitt
    - Diskussion von Lösungsansätzen

### Abschluss
- Zusammenfassung der wichtigsten Lerninhalte
- Weiterführende Ressourcen und Literatur
- Tipps für die fortlaufende Praxis und Vertiefung des Gelernten

# Teil 1: Grundlagen der funktionalen Programmierung in Java

## 1. Einführung in funktionale Programmierung

Die funktionale Programmierung (FP) ist ein Programmierparadigma, das die Anwendung von Funktionen betont und Rechenprozesse als die Auswertung von mathematischen Funktionen versteht. Im Gegensatz zur imperativen Programmierung, die den Fokus auf die Ausführung von Befehlssequenzen legt und den Programmzustand durch Änderung von Variablen kontrolliert, konzentriert sich die funktionale Programmierung auf die Definition von Funktionen und deren Zusammensetzung, um das gewünschte Ergebnis zu erreichen.

#### Unveränderlichkeit und Nebenwirkungsfreiheit

Ein Kernkonzept der funktionalen Programmierung ist die Unveränderlichkeit (Immutability). In FP sind Datenstrukturen meist unveränderlich, d.h., sie können nach ihrer Erstellung nicht mehr geändert werden. Dies vereinfacht das Verständnis und die Vorhersagbarkeit von Code, da es keine verborgenen Änderungen am Zustand gibt. 

Ein weiteres wichtiges Prinzip ist die Nebenwirkungsfreiheit (Side-effect free). Funktionen in der funktionalen Programmierung sollten keine Nebenwirkungen haben, d.h., sie beeinflussen nur ihren eigenen Output, ohne den Zustand des restlichen Programms oder externe Systeme zu verändern. Dies macht den Code sicherer und wiederverwendbarer.

#### Erste-Klasse-Funktionen und Higher-Order-Funktionen

In der funktionalen Programmierung sind Funktionen "Erste-Klasse-Bürger". Das bedeutet, dass Funktionen genauso behandelt werden wie andere Werte: Sie können Variablen zugewiesen, als Argumente an andere Funktionen übergeben oder von ihnen zurückgegeben werden. Dies führt zu dem Konzept der Higher-Order-Funktionen, also Funktionen, die andere Funktionen als Argumente annehmen oder als Ergebnis zurückgeben können.

#### Beispiel: Funktionen als Bürger erster Klasse in Java

Java unterstützt funktionale Konzepte insbesondere mit der Einführung von Lambda-Ausdrücken in Java 8. Ein einfaches Beispiel hierfür ist die Verwendung einer Funktion, die eine andere Funktion als Argument nimmt:

```java
import java.util.function.Function;

public class FunctionalExample {
    public static void main(String[] args) {
        // Definiert eine Funktion, die das Quadrat einer Zahl berechnet
        Function<Integer, Integer> square = x -> x * x;
        
        // Verwendet die Funktion in einer anderen Funktion
        int result = applyFunction(5, square);
        System.out.println(result); // Gibt 25 aus
    }

    public static int applyFunction(int x, Function<Integer, Integer> func) {
        return func.apply(x);
    }
}
```

#### Reine Funktionen

Reine Funktionen sind ein weiteres zentrales Konzept der funktionalen Programmierung. Eine Funktion gilt als rein, wenn sie für die gleichen Eingabewerte immer dasselbe Ergebnis liefert und keine beobachtbaren Nebenwirkungen hat. Dies erleichtert das Testen und die Fehlersuche, da das Verhalten einer reinen Funktion vollständig durch ihre Eingaben definiert ist.

#### Fazit

Die funktionale Programmierung bietet einen anderen Ansatz zur Problemlösung im Vergleich zur imperativen Programmierung. Durch die Nutzung von Unveränderlichkeit, Nebenwirkungsfreiheit und höherwertigen Funktionen ermöglicht sie die Entwicklung von sicherem, modularem und leicht verständlichem Code. Während Java traditionell eine objektorientierte Sprache ist, bietet es durch Lambda-Ausdrücke und die Stream API vielfältige Möglichkeiten, funktionale Programmierkonzepte zu nutzen und zu verinnerlichen.



## 2. Lambda-Ausdrücke

Lambda-Ausdrücke, eine Schlüsselkomponente der funktionalen Programmierung in Java, bieten eine klare und prägnante Möglichkeit, Interfaces mit nur einer Methode, sogenannte funktionale Interfaces, zu implementieren. Sie ermöglichen es, Methoden als Argumente zu übergeben und effizientere und lesbare Codeblöcke zu schreiben.

#### Grundlagen und Syntax

Ein Lambda-Ausdruck in Java kann als eine verkürzte Schreibweise für eine anonyme Klasse betrachtet werden, die ein funktionales Interface implementiert. Die allgemeine Syntax eines Lambda-Ausdrucks ist:

```java
(parameterliste) -> { ausdruck }
```

Falls der Körper nur aus einem einzigen Ausdruck besteht, können die Klammern weggelassen werden. Ebenso können die Typen der Parameter weggelassen werden, da der Compiler diese aus dem Kontext ableiten kann.

#### Beispiel: Verwendung von Lambda-Ausdrücken

Betrachten wir ein einfaches Beispiel, das die Verwendung eines Lambda-Ausdrucks in Java veranschaulicht:

```java
import java.util.Arrays;
import java.util.List;
import java.util.function.Predicate;

public class LambdaExample {
    public static void main(String[] args) {
        List<String> languages = Arrays.asList("Java", "Python", "JavaScript", "C++", "Scala");
        
        // Verwendung eines Lambda-Ausdrucks, um alle Sprachen auszudrucken, die mit "J" beginnen
        filterList(languages, s -> s.startsWith("J")).forEach(System.out::println);
    }

    public static List<String> filterList(List<String> list, Predicate<String> condition) {
        return list.stream()
                   .filter(condition)
                   .collect(Collectors.toList());
    }
}
```

In diesem Beispiel definiert der Lambda-Ausdruck `s -> s.startsWith("J")` eine Bedingung für das Filtern einer Liste von Zeichenketten. Der Lambda-Ausdruck implementiert die `Predicate<String>` Schnittstelle, eine funktionale Schnittstelle, die einen booleschen Wert zurückgibt.

#### Vorteile und Verwendung

Lambda-Ausdrücke ermöglichen es, Code konziser und lesbarer zu gestalten, insbesondere bei der Verwendung von Sammlungen und der Stream API. Sie ermöglichen es, Operationen wie Filtern, Sortieren und Umwandeln von Sammlungen mit weniger Boilerplate-Code durchzuführen. 

Außerdem fördern Lambda-Ausdrücke die funktionale Programmierung in Java, indem sie es erleichtern, Funktionen als Argumente zu übergeben, Funktionen zu erstellen, die Funktionen zurückgeben, und allgemein einen stärker deklarativen und weniger imperativen Programmierstil zu verfolgen.

#### Lambda-Ausdrücke und funktionale Interfaces

Ein Schlüsselaspekt von Lambda-Ausdrücken ist ihre Beziehung zu funktionalen Interfaces. Ein funktionales Interface in Java ist ein Interface mit genau einer abstrakten Methode (neben möglicherweise anderen Default- oder statischen Methoden). Lambda-Ausdrücke können als Instanzen solcher Interfaces betrachtet werden, wobei der Lambda-Ausdruck die Implementierung der abstrakten Methode bereitstellt.

Zum Beispiel definiert das `java.util.function` Paket mehrere funktionale Interfaces wie `Predicate<T>`, `Function<T,R>`, `Supplier<T>` und `Consumer<T>`, die alle mit Lambda-Ausdrücken verwendet werden können.

#### Fazit

Lambda-Ausdrücke in Java vereinfachen die funktionale Programmierung erheblich, indem sie eine klare und prägnante Syntax bieten, um Verhaltensparameter zu übergeben und Codeblöcke effizient auszudrücken. Ihre Integration in die Java-Sprache fördert einen saubereren, modulareren und flexibleren Code, der leichter zu lesen und zu warten ist.



## 3. Methodenreferenzen in Java

Methodenreferenzen in Java sind eine kompakte und leicht verständliche Form, um auf Methoden als Lambda-Ausdrücke zu verweisen. Sie bieten eine Möglichkeit, eine existierende Methode direkt in funktionalen Kontexten wie Streams oder beim Einsatz von funktionalen Interfaces zu verwenden, ohne dabei einen vollständigen Lambda-Ausdruck schreiben zu müssen. Methodenreferenzen verbessern die Lesbarkeit und Kürze des Codes, indem sie eine klare und direkte Verbindung zwischen dem Code und der aufgerufenen Methode herstellen.

#### Typen von Methodenreferenzen

Es gibt vier Haupttypen von Methodenreferenzen in Java:

1. **Statische Methodenreferenzen:** Referenzieren einer statischen Methode einer Klasse.
   
   Syntax: `Klassenname::statischeMethode`

   Beispiel:

   ```java
   Function<String, Integer> stringLength = String::length;
   ```

2. **Instanzmethodenreferenzen eines bestimmten Objekts:** Referenzieren einer Instanzmethode eines bestimmten Objekts.
   
   Syntax: `instanz::instanzMethode`

   Beispiel:

   ```java
   String myString = "Hello";
   Supplier<Integer> stringLength = myString::length;
   ```

3. **Instanzmethodenreferenzen eines beliebigen Objekts eines bestimmten Typs:** Referenzieren einer Instanzmethode auf einem beliebigen Objekt eines bestimmten Typs.
   
   Syntax: `Klassenname::instanzMethode`

   Beispiel:

   ```java
   Consumer<String> print = System.out::println;
   ```

4. **Konstruktorreferenzen:** Referenzieren eines Konstruktors.
   
   Syntax: `Klassenname::new`

   Beispiel:

   ```java
   Supplier<List<String>> listSupplier = ArrayList::new;
   ```

#### Verwendung von Methodenreferenzen

Methodenreferenzen können überall dort verwendet werden, wo funktionale Interfaces zum Einsatz kommen, wie z.B. in Streams, bei der Verwendung von Collections oder beim Einsatz von APIs, die auf funktionalen Interfaces basieren. Sie machen den Code nicht nur kürzer, sondern auch lesbarer, besonders wenn der Name der Methode die Aktion klar beschreibt.

#### Beispiel: Einsatz in Streams

Nehmen wir an, wir haben eine Liste von Namen und möchten diese in Großbuchstaben ausgeben. Mit einer Methodenreferenz kann dies sehr prägnant umgesetzt werden:

```java
List<String> names = Arrays.asList("Anna", "Bob", "Charlie");
names.stream()
     .map(String::toUpperCase)
     .forEach(System.out::println);
```

In diesem Beispiel ersetzt `String::toUpperCase` einen Lambda-Ausdruck wie `s -> s.toUpperCase()`, und `System.out::println` steht für `x -> System.out.println(x)`. Die Verwendung von Methodenreferenzen macht den Stream-Vorgang intuitiver und den Code insgesamt klarer.

#### Vorteile von Methodenreferenzen

- **Lesbarkeit:** Sie machen den Code kürzer und klarer, besonders wenn die Methode selbst beschreibend ist.
- **Wiederverwendbarkeit:** Sie fördern die Wiederverwendung von bestehendem Code und reduzieren die Notwendigkeit, zusätzliche anonyme Klassen oder Lambda-Ausdrücke zu definieren.
- **Effizienz:** In einigen Fällen können Methodenreferenzen effizienter sein als entsprechende Lambda-Ausdrücke, da sie direkter auf die zugrunde liegende Methode verweisen.

#### Fazit

Methodenreferenzen in Java sind ein leistungsstarkes Feature, das in Verbindung mit Lambda-Ausdrücken und der Stream API die funktionale Programmierung in Java vereinfacht. Sie tragen zu einem saubereren, ausdrucksstärkeren und effizienteren Code bei, indem sie eine direkte Verbindung zu vorhandenen Methoden herstellen. Durch die Nutzung von Methodenreferenzen können Entwickler die Vorteile der funktionalen Programmierung in Java voll ausschöpfen und gleichzeitig die Lesbarkeit und Wartbarkeit ihres Codes verbessern.


# Teil 2: Arbeiten mit Streams

## 4. Einführung in Streams

Streams in Java, eingeführt in Java 8, repräsentieren eine Abstraktion von Sequenzen von Elementen, über die man mit einer funktionalen Programmieransatz operieren kann. Im Gegensatz zu Collections, die eine Datenstruktur zur Speicherung von Elementen sind, ermöglichen Streams die Bearbeitung von Elementsequenzen, ohne dass diese Elemente in einer Sammlung gespeichert werden müssen. Streams erleichtern parallele Operationen, indem sie die Datenverarbeitung transparent und effizient gestalten.

#### Was sind Streams?

Ein Stream in Java ist eine Folge von Elementen, die aus einer Datenquelle wie einer Sammlung, einem Array oder Ein-/Ausgabe-Ressourcen generiert werden. Streams unterstützen verschiedene Operationen, die entweder intermediär (Operationen, die einen Stream zurückgeben, z.B. `filter`, `map`) oder terminal (Operationen, die einen endgültigen Wert liefern oder eine Seiteneffekt-Operation ausführen, z.B. `forEach`, `reduce`) sein können.

#### Grundlegende Stream-Operationen

Um mit Streams zu arbeiten, initialisiert man sie in der Regel aus einer Datenquelle. Hier ein einfaches Beispiel, wie man einen Stream aus einer Liste erstellt und grundlegende Operationen darauf anwendet:

```java
List<String> strings = Arrays.asList("Apple", "Banana", "Cherry", "Date");
Stream<String> stream = strings.stream();
stream.filter(s -> s.startsWith("B"))
      .map(String::toUpperCase)
      .forEach(System.out::println); // Gibt "BANANA" aus
```

In diesem Beispiel führen wir drei Operationen aus:

1. `filter`: Nimmt eine Prädikatfunktion und behält nur die Elemente bei, die das Prädikat erfüllen.
2. `map`: Transformiert jedes Element des Streams mit der gegebenen Funktion.
3. `forEach`: Führt eine Aktion für jedes Element des Streams aus.

#### Erstellung von Streams

Streams können auf verschiedene Weisen erstellt werden:

- **Aus Sammlungen und Arrays:** z.B. `collection.stream()` oder `Arrays.stream(array)`.
- **Von Werten:** z.B. `Stream.of("a", "b", "c")`.
- **Von Generatoren:** z.B. `Stream.generate(() -> "element").limit(10)`.
- **Von anderen Quellen:** wie Dateien, Regulären Ausdrücken etc.

#### Anwendungsfälle für Streams

Streams sind besonders nützlich für die Bearbeitung von Sammlungen von Daten. Zum Beispiel:

- Extrahieren einer Untermenge von Elementen basierend auf bestimmten Kriterien.
- Umwandlung von Elementen in einer Sammlung in eine andere Form.
- Kombinieren von Elementen einer Sammlung, um einen einzigen Wert zu erzeugen.

#### Vorteile der Verwendung von Streams

- **Verbesserte Lesbarkeit und Kürze:** Streams können komplexe Operationen in einer kompakten und intuitiven Weise ausdrücken.
- **Parallelverarbeitung:** Streams können transparent parallel verarbeitet werden, was zu erheblichen Leistungsverbesserungen führen kann.
- **Funktionaler Programmierstil:** Streams fördern einen funktionalen Ansatz zur Datenverarbeitung, der Seiteneffekte vermeidet und die Code-Wiederverwendung fördert.

#### Fazit

Java-Streams bieten eine moderne und effiziente Möglichkeit, mit Daten in Java zu arbeiten. Sie fördern einen klareren, funktionalen Programmierstil, ermöglichen die einfache Parallelverarbeitung und verbessern die Lesbarkeit des Codes. Durch die Nutzung von Streams können Entwickler komplexe Datenverarbeitungsaufgaben auf eine deklarative Weise angehen, die die Intentionen des Codes klar und verständlich macht.


## 5. Stream-Operationen

In Java ermöglichen Stream-Operationen die Verarbeitung von Datenquellen in einer deklarativen Weise. Sie können in zwei Hauptkategorien unterteilt werden: intermediäre Operationen und terminale Operationen. Intermediäre Operationen transformieren einen Stream in einen anderen, während terminale Operationen eine Stream-Verarbeitung abschließen und ein Ergebnis liefern.

#### Intermediäre Operationen

Intermediäre Operationen sind Operationen, die einen Stream zu einem anderen Stream verarbeiten. Sie sind faul, was bedeutet, dass sie nicht sofort ausgeführt werden, sondern erst, wenn eine terminale Operation aufgerufen wird.

**Beispiele für intermediäre Operationen:**

- `filter(Predicate<T>)`: Filtert Elemente basierend auf einer Bedingung.
  
  ```java
  Stream<String> names = Stream.of("John", "Sarah", "Mark", "Tanya");
  names.filter(name -> name.startsWith("S"))
       .forEach(System.out::println); // Gibt "Sarah" aus
  ```

- `map(Function<T, R>)`: Transformiert jedes Element des Streams in ein anderes Element.
  
  ```java
  Stream<String> names = Stream.of("John", "Sarah", "Mark", "Tanya");
  names.map(String::toUpperCase)
       .forEach(System.out::println); // Gibt "JOHN", "SARAH", "MARK", "TANYA" aus
  ```

- `flatMap(Function<T, Stream<R>>):`: Flacht Streams von Streams zu einem einzigen Stream ab.

  ```java
  List<List<String>> listOfLists = Arrays.asList(
    Arrays.asList("a", "b"), 
    Arrays.asList("c", "d")
  );
  listOfLists.stream()
             .flatMap(List::stream)
             .forEach(System.out::println); // Gibt "a", "b", "c", "d" aus
  ```

#### Terminale Operationen

Terminale Operationen schließen die Stream-Verarbeitung ab und liefern ein Ergebnis. Sie führen die tatsächliche Berechnung durch und beenden die Stream-Pipeline.

**Beispiele für terminale Operationen:**

- `forEach(Consumer<T>)`: Führt eine Aktion für jedes Element des Streams aus.
  
  ```java
  Stream<String> names = Stream.of("John", "Sarah", "Mark", "Tanya");
  names.forEach(System.out::println); // Gibt alle Namen aus
  ```

- `collect(Collector<T,A,R>)`: Transformiert den Stream in eine andere Form, wie z.B. eine Liste, ein Set oder eine Map.
  
  ```java
  Stream<String> names = Stream.of("John", "Sarah", "Mark", "Tanya");
  List<String> list = names.collect(Collectors.toList());
  System.out.println(list); // Gibt die Liste der Namen aus
  ```

- `reduce(BinaryOperator<T>)`: Kombiniert die Elemente des Streams zu einem einzigen Wert.
  
  ```java
  Stream<Integer> numbers = Stream.of(1, 2, 3, 4);
  int sum = numbers.reduce(0, Integer::sum);
  System.out.println(sum); // Gibt 10 aus
  ```

#### Kombination von Operationen

Streams können in einer Pipeline kombiniert werden, um komplexe Datenverarbeitungsaufgaben effizient und lesbar zu gestalten. Hier ein Beispiel, das Filter-, Map- und Reduce-Operationen kombiniert:

```java
List<String> words = Arrays.asList("apple", "banana", "cherry", "date");
int totalLength = words.stream()
                       .filter(word -> word.startsWith("a"))
                       .mapToInt(String::length)
                       .sum();
System.out.println(totalLength); // Gibt die Gesamtlänge der Wörter, die mit "a" beginnen, aus
```

In diesem Beispiel werden Wörter gefiltert, die mit einem "a" beginnen, ihre Längen berechnet und dann die Gesamtlänge ermittelt. Durch die Kombination verschiedener Stream-Operationen können wir komplexe Datenverarbeitungsaufgaben auf eine klare und deklarative Weise ausdrücken.

## 6. Collectors

In der Java Stream API spielen `Collectors` eine entscheidende Rolle, indem sie Ergebnisse aus Stream-Operationen in verschiedene Datentypen und Strukturen sammeln. Sie sind vor allem in der terminalen Operation `collect()` nützlich, die die Elemente eines Streams in eine Sammlung oder einen anderen Datentyp transformiert.

#### Was sind Collectors?

Ein `Collector` in Java ist ein Rezept, das beschreibt, wie man Elemente eines Streams in einen finalen Behälter, wie eine Liste, ein Set oder eine Map, zusammenführen kann. `Collectors` bietet eine Reihe von vordefinierten Fabrikmethoden für die gängigsten Sammeloperationen wie das Gruppieren von Elementen, das Zusammenführen von Elementen zu Listen oder Sets und das Zusammenfassen von Elementen.

#### Beispiele für Collectors

**toList() und toSet()**

Die wohl einfachsten Collectors sind `toList()` und `toSet()`, die Stream-Elemente in eine Liste bzw. ein Set sammeln.

```java
List<String> list = Stream.of("apple", "banana", "cherry")
                          .collect(Collectors.toList());
System.out.println(list); // Gibt [apple, banana, cherry] aus

Set<String> set = Stream.of("apple", "banana", "banana")
                        .collect(Collectors.toSet());
System.out.println(set); // Gibt [apple, banana] aus (Duplikate werden entfernt)
```

**toMap()**

`toMap()` sammelt Elemente in einer Map. Jedes Element wird zu einem Schlüssel-Wert-Paar transformiert.

```java
Map<String, Integer> map = Stream.of("apple", "banana", "cherry")
                                 .collect(Collectors.toMap(Function.identity(), String::length));
System.out.println(map); // Gibt {apple=5, banana=6, cherry=6} aus
```

**groupingBy()**

Ein mächtiger Collector ist `groupingBy()`, der Elemente nach einem bestimmten Kriterium gruppiert und in einer Map organisiert.

```java
Map<Character, List<String>> groupedByFirstLetter = Stream.of("apple", "banana", "cherry", "apricot")
                                                           .collect(Collectors.groupingBy(s -> s.charAt(0)));
System.out.println(groupedByFirstLetter); // Gibt {a=[apple, apricot], b=[banana], c=[cherry]} aus
```

**joining()**

`joining()` ist ein spezialisierter Collector, der String-Elemente zu einem einzigen String zusammenfügt.

```java
String result = Stream.of("apple", "banana", "cherry")
                      .collect(Collectors.joining(", "));
System.out.println(result); // Gibt "apple, banana, cherry" aus
```

**summarizingInt(), averagingInt(), summingInt()**

Diese Collectors werden verwendet, um statistische Zusammenfassungen oder Summen aus numerischen Streams zu sammeln.

```java
IntSummaryStatistics stats = Stream.of(1, 2, 3, 4)
                                   .collect(Collectors.summarizingInt(Integer::intValue));
System.out.println(stats); // Gibt Statistiken wie max, min, sum, average aus

double average = Stream.of(1, 2, 3, 4)
                       .collect(Collectors.averagingInt(Integer::intValue));
System.out.println(average); // Gibt den Durchschnitt aus
```

#### Fazit

Collectors bieten eine flexible Methode, um Daten aus Streams in Java effizient zu sammeln und zu organisieren. Sie sind ein wesentlicher Bestandteil der Stream-API und ermöglichen es, komplexe Datenverarbeitungsoperationen in klarer und konziser Weise auszudrücken. Durch die Kombination verschiedener `Collectors` können Entwickler leistungsstarke Datenaggregationen und -transformationen mit minimalem Codeaufwand durchführen.

# Teil 3: Fortgeschrittene Themen

## 7. Parallel Streams

Parallel Streams sind eine Erweiterung der Java Stream API, die das parallele Ausführen von Operationen auf Daten ermöglicht. Dies nutzt die Mehrkernarchitektur moderner Computer voll aus und kann die Leistung von datenintensiven Operationen erheblich verbessern.

#### Was sind Parallel Streams?

Ein Parallel Stream ist eine Variante eines Java Stream, die die Datenverarbeitung über mehrere Threads verteilt, sodass Operationen auf den Daten gleichzeitig (parallel) statt sequentiell ausgeführt werden. Dies ist besonders nützlich für große Datenmengen, da es die Ausführungszeit reduzieren kann.

#### Erstellen von Parallel Streams

Es gibt zwei Hauptmethoden, um einen Parallel Stream in Java zu erstellen:

1. Durch direktes Aufrufen der `parallelStream()`-Methode auf einer Collection:

   ```java
   List<String> strings = Arrays.asList("apple", "banana", "cherry", "date");
   strings.parallelStream()
          .forEach(System.out::println);
   ```

2. Durch Umwandeln eines bestehenden Streams in einen Parallel Stream mit der `parallel()`-Methode:

   ```java
   Stream<String> stream = strings.stream();
   stream.parallel()
         .forEach(System.out::println);
   ```

#### Beachtung bei der Verwendung von Parallel Streams

Während Parallel Streams leistungsstarke Verbesserungen bieten können, sind sie nicht immer die beste Wahl für alle Situationen. Die Verwendung von Parallel Streams kann in einigen Fällen zu unerwartetem Verhalten führen, insbesondere wenn die verwendeten Datenstrukturen nicht thread-sicher sind oder wenn die Operationen, die auf den Daten ausgeführt werden, voneinander abhängig sind.

Außerdem kann die Overhead-Zeit für die Verteilung der Aufgaben auf verschiedene Threads die Leistungsvorteile für kleinere Datenmengen oder einfache Operationen zunichte machen.

#### Beispiel für Parallel Streams

Hier ist ein einfaches Beispiel, das die Verwendung von Parallel Streams illustriert:

```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
int sum = numbers.parallelStream()
                  .mapToInt(Integer::intValue)
                  .sum();
System.out.println("Summe: " + sum);
```

In diesem Beispiel wird ein Parallel Stream verwendet, um die Summe einer Liste von Zahlen zu berechnen. Die Operation `mapToInt` konvertiert jedes Element des Streams in einen `int`, und `sum` berechnet die Summe dieser Werte. Da diese Berechnung parallel ausgeführt wird, kann die Ausführung schneller sein als bei einer sequentiellen Ausführung, besonders bei größeren Datenmengen.

#### Fazit

Parallel Streams bieten eine einfache und effektive Möglichkeit, die Leistung von datenintensiven Operationen in Java zu verbessern. Jedoch sollten sie mit Bedacht eingesetzt werden, da sie nicht für alle Situationen geeignet sind und ihre Verwendung sorgfältig geprüft werden sollte, um sicherzustellen, dass sie die gewünschten Leistungsvorteile bringen.

## 8. Optionals

### Optionals in Java

Java's `Optional` ist eine Container-Klasse, die verwendet wird, um die Präsenz oder Abwesenheit eines Wertes auszudrücken. Es wurde in Java 8 eingeführt, um eine bessere Alternative zu `null` zu bieten und NullPointerExceptions zu vermeiden.

#### Einführung in Optionals

Ein `Optional` ist eine Art von Wrapper oder Container, der entweder einen Wert enthält oder leer ist. Es wird oft in Situationen verwendet, in denen ein Wert vorhanden sein kann oder auch nicht, um explizit zu machen, dass das Fehlen eines Wertes eine gültige, erwartete Möglichkeit ist.

#### Erstellen von Optionals

Optionals können auf verschiedene Weisen erstellt werden:

1. `Optional.empty()`: Erstellt ein leeres Optional.
   
   ```java
   Optional<String> emptyOptional = Optional.empty();
   ```

2. `Optional.of(value)`: Erstellt ein Optional mit einem Wert. Wenn der Wert `null` ist, wird eine `NullPointerException` geworfen.

   ```java
   Optional<String> optionalWithValue = Optional.of("Hello");
   ```

3. `Optional.ofNullable(value)`: Erstellt ein Optional, das einen Wert enthält, wenn der übergebene Wert nicht `null` ist; andernfalls wird ein leeres Optional zurückgegeben.

   ```java
   String nullValue = null;
   Optional<String> optionalFromNullable = Optional.ofNullable(nullValue);
   ```

#### Verwendung von Optionals

Optionals bieten verschiedene Methoden, um auf den Wert zuzugreifen oder mit ihm zu arbeiten:

- `isPresent()`: Überprüft, ob ein Wert vorhanden ist.
  
  ```java
  if (optionalWithValue.isPresent()) {
      System.out.println("Wert vorhanden");
  }
  ```

- `ifPresent(consumer)`: Führt den gegebenen Consumer aus, wenn ein Wert vorhanden ist.
  
  ```java
  optionalWithValue.ifPresent(value -> System.out.println("Wert: " + value));
  ```

- `orElse(defaultValue)`: Gibt den Wert zurück, wenn er vorhanden ist, sonst den `defaultValue`.
  
  ```java
  String valueOrDefault = optionalWithValue.orElse("Standardwert");
  ```

- `orElseGet(supplier)`: Ähnlich wie `orElse`, aber der Standardwert wird durch einen Supplier bereitgestellt, der nur im Falle der Abwesenheit eines Wertes aufgerufen wird.
  
  ```java
  String valueOrGetDefault = optionalWithValue.orElseGet(() -> "Standardwert");
  ```

- `map(function)`: Wendet eine Funktion auf den Wert des Optional an, wenn einer vorhanden ist.
  
  ```java
  Optional<Integer> stringLength = optionalWithValue.map(String::length);
  ```

#### Best Practices und Fallstricke

- Verwende `Optional` nicht als Parameter in Methoden. Stattdessen sollte der Einsatz von `Optional` in der Regel auf Rückgabetypen beschränkt sein.
- Vermeide es, `Optional` für primitiv typisierte Werte zu verwenden, da es spezialisierte Primitive Optional-Klassen gibt, wie `OptionalInt`, `OptionalLong` und `OptionalDouble`.
- Verwende `Optional` nicht für Kollektionen oder Arrays. Eine leere Sammlung oder ein leeres Array kann bereits das Fehlen von Elementen ausdrücken.

#### Beispiel

Hier ist ein einfaches Beispiel, das die Verwendung von `Optional` illustriert:

```java
public Optional<String> findUserById(String id) {
    // Suche Benutzer anhand der ID und gebe Optional zurück
    return users.stream()
                .filter(user -> user.getId().equals(id))
                .findFirst();
}

public void demoOptionalUsage() {
    Optional<String> userOptional = findUserById("123");
    userOptional.ifPresent(user -> System.out.println("Benutzer gefunden: " + user));
}
```

In diesem Beispiel wird `Optional` verwendet, um das Ergebnis einer Benutzersuche darzustellen. Die Methode `findUserById` gibt ein `Optional` zurück, das entweder den Benutzer enthält, wenn einer mit der gegebenen ID gefunden wurde, oder leer ist, wenn kein solcher Benutzer existiert. Der Aufrufer kann dann `ifPresent` verwenden, um auf den Benutzer zuzugreifen, falls einer gefunden wurde.

## 9. Kombination von Streams und Lambda-Ausdrücken mit Collections

Die Kombination von Streams und Lambda-Ausdrücken mit Java Collections ermöglicht eine effiziente und deklarative Verarbeitung von Datensammlungen. Diese Techniken vereinfachen die Implementierung komplexer Datenmanipulationsaufgaben.

#### Transformation von Collections

Mit Streams können Collections transformiert werden, indem Operationen wie `map`, `filter` und `sorted` angewendet werden. Lambda-Ausdrücke ermöglichen dabei eine klare und kompakte Syntax.

```java
List<String> names = Arrays.asList("Anna", "Bob", "Charlie", "Diana");
List<String> upperCaseNames = names.stream()
                                   .map(String::toUpperCase)
                                   .collect(Collectors.toList());
System.out.println(upperCaseNames); // [ANNA, BOB, CHARLIE, DIANA]
```

#### Filterung von Collections

Streams zusammen mit Lambda-Ausdrücken können verwendet werden, um Elemente in einer Collection basierend auf einem bestimmten Kriterium zu filtern.

```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5, 6, 7, 8, 9, 10);
List<Integer> evenNumbers = numbers.stream()
                                   .filter(n -> n % 2 == 0)
                                   .collect(Collectors.toList());
System.out.println(evenNumbers); // [2, 4, 6, 8, 10]
```

#### Aggregation von Collections

Streams bieten Aggregationsoperationen wie `sum`, `average`, `min`, `max`, und `count`, die zusammen mit Lambda-Ausdrücken zur Zusammenfassung von Collection-Daten verwendet werden können.

```java
double average = numbers.stream()
                        .mapToInt(Integer::intValue)
                        .average()
                        .orElse(0.0);
System.out.println("Durchschnitt: " + average); // Durchschnitt: 5.5
```

#### Verbindung von Streams und Collections

Durch die Kombination von Streams und Collections können komplexe Datenverarbeitungsaufgaben in einfacher und verständlicher Weise durchgeführt werden. Sie ermöglichen es, Operationen wie Suchen, Sortieren, Filtern und Umwandeln mit weniger Code und auf höherem Abstraktionsniveau zu implementieren.

```java
List<String> sortedFilteredNames = names.stream()
                                        .filter(s -> s.startsWith("A"))
                                        .sorted()
                                        .collect(Collectors.toList());
System.out.println(sortedFilteredNames); // [Anna]
```

Diese Beispiele demonstrieren, wie die Verwendung von Streams und Lambda-Ausdrücken mit Java Collections die Datenverarbeitung vereinfacht und effizienter macht.

# Teil 4: Praktische Anwendungen

## 10. Fallstudien und Beispiele

Die Integration von funktionaler Programmierung, Lambda-Ausdrücken und Streams in Java hat die Entwicklung von Anwendungen wesentlich beeinflusst. Durch praktische Beispiele und Fallstudien lässt sich die Anwendung dieser Konzepte in realen Szenarien verdeutlichen. Im Folgenden werden einige Beispiele vorgestellt, die zeigen, wie diese Features in der Praxis eingesetzt werden können, um effiziente, lesbare und wartbare Code-Lösungen zu erstellen.

#### Beispiel 1: Datenfilterung und -aggregation

**Problemstellung:** Gegeben sei eine Liste von Personenobjekten, wobei jedes Objekt Attribute wie Name, Alter und Geschlecht hat. Ziel ist es, das Durchschnittsalter aller weiblichen Personen in der Liste zu berechnen.

**Lösung mit Streams und Lambda-Ausdrücken:**

```java
List<Person> persons = Arrays.asList(
    new Person("Alice", 24, Gender.FEMALE),
    new Person("Bob", 30, Gender.MALE),
    new Person("Carol", 25, Gender.FEMALE)
);

double averageAge = persons.stream()
                           .filter(p -> p.getGender() == Gender.FEMALE)
                           .mapToInt(Person::getAge)
                           .average()
                           .orElse(Double.NaN);

System.out.println("Durchschnittsalter der weiblichen Personen: " + averageAge);
```

**Erklärung:** Dieses Beispiel demonstriert, wie Streams zur Filterung und Aggregation von Daten verwendet werden können. Die `filter`-Methode extrahiert weibliche Personen, während `mapToInt` und `average` dazu dienen, das Durchschnittsalter zu berechnen.

#### Beispiel 2: Gruppierung und Zusammenfassung

**Problemstellung:** Angenommen, es existiert eine Liste von Transaktionen, wobei jede Transaktion einen Typ (EINZAHLUNG, AUSZAHLUNG) und einen Betrag hat. Das Ziel ist es, die Summe der Beträge für jeden Transaktionstyp zu ermitteln.

**Lösung mit Streams und Collectors:**

```java
List<Transaction> transactions = Arrays.asList(
    new Transaction(TransactionType.DEPOSIT, 100),
    new Transaction(TransactionType.WITHDRAWAL, 50),
    new Transaction(TransactionType.DEPOSIT, 200)
);

Map<TransactionType, Integer> sumByType = transactions.stream()
                                                      .collect(Collectors.groupingBy(Transaction::getType,
                                                          Collectors.summingInt(Transaction::getAmount)));

sumByType.forEach((type, sum) -> System.out.println(type + ": " + sum));
```

**Erklärung:** In diesem Beispiel wird die `groupingBy`-Methode von `Collectors` verwendet, um Transaktionen nach ihrem Typ zu gruppieren und die Summen der Beträge mit `summingInt` zu berechnen. Dies zeigt, wie leistungsfähig die Kombination von Streams und Collectors für die Datenaggregation ist.

#### Beispiel 3: Datenverarbeitungspipeline

**Problemstellung:** Erstellen einer Datenverarbeitungspipeline, die eine Liste von Strings nimmt, diese in Großbuchstaben umwandelt, nach Länge sortiert und das Ergebnis in eine neue Liste speichert.

**Lösung mit Streams:**

```java
List<String> words = Arrays.asList("Stream", "Lambda", "Java");
List<String> processed = words.stream()
                              .map(String::toUpperCase)
                              .sorted(Comparator.comparingInt(String::length))
                              .collect(Collectors.toList());

System.out.println(processed);
```

**Erklärung:** Dieses Beispiel illustriert die Nutzung einer Stream-Pipeline zur Transformation von Daten. Die `map`-Methode wandelt jeden String in Großbuchstaben um, `sorted` sortiert die Strings nach ihrer Länge, und `collect` sammelt das Ergebnis in einer neuen Liste.

Diese Beispiele verdeutlichen, wie Streams und Lambda-Ausdrücke in Java genutzt werden können, um komplexe Datenverarbeitungsaufgaben auf eine klare und effiziente Weise zu lösen. Sie zeigen die Stärke der funktionalen Programmierung und wie sie dazu beiträgt, den Code kompakter, lesbarer und wartbarer zu machen.

## 11. Übungen und Lösungen

Das Erlernen von funktionaler Programmierung, Lambda-Ausdrücken und Streams in Java wird durch praktische Anwendung und Übungen verstärkt. Im Folgenden finden Sie einige Übungsaufgaben mit Lösungen, die das Verständnis dieser Konzepte vertiefen sollen.

#### Übung 1: Filtern und Zählen

**Aufgabe:** Gegeben ist eine Liste von Strings. Zählen Sie, wie viele Strings in der Liste mit dem Buchstaben "J" beginnen.

**Lösung:**

```java
List<String> names = Arrays.asList("James", "David", "John", "Daniel", "Jonathan", "Jenny");
long count = names.stream()
                  .filter(name -> name.startsWith("J"))
                  .count();

System.out.println("Anzahl der Namen, die mit 'J' beginnen: " + count);
```

**Erklärung:** Diese Übung demonstriert die Verwendung von `filter` und `count` in einer Stream-Pipeline, um eine bedingte Zählung durchzuführen.

#### Übung 2: Umwandlung und Sammlung

**Aufgabe:** Gegeben ist eine Liste von Personenobjekten mit den Attributen Name und Alter. Erstellen Sie eine Liste aller Namen von Personen, die älter als 18 Jahre sind.

**Lösung:**

```java
List<Person> persons = Arrays.asList(
    new Person("Alice", 22),
    new Person("Bob", 17),
    new Person("Charlie", 24),
    new Person("Daisy", 16)
);

List<String> ofLegalAge = persons.stream()
                                  .filter(person -> person.getAge() > 18)
                                  .map(Person::getName)
                                  .collect(Collectors.toList());

System.out.println("Personen über 18: " + ofLegalAge);
```

**Erklärung:** Diese Übung nutzt `filter`, um Personen über 18 Jahre zu selektieren, `map`, um ihre Namen zu extrahieren, und `collect`, um die Ergebnisse in einer Liste zu sammeln.

#### Übung 3: Gruppierung nach Kriterium

**Aufgabe:** Gegeben ist eine Liste von Strings, die verschiedene Früchte darstellen. Gruppieren Sie die Strings nach ihrer Länge.

**Lösung:**

```java
List<String> fruits = Arrays.asList("apple", "banana", "cherry", "date", "elderberry", "fig");
Map<Integer, List<String>> groupedByLength = fruits.stream()
                                                    .collect(Collectors.groupingBy(String::length));

System.out.println("Früchte gruppiert nach Länge: " + groupedByLength);
```

**Erklärung:** Hier wird `Collectors.groupingBy` verwendet, um die Früchte basierend auf der Länge ihrer Namen zu gruppieren. Diese Übung zeigt, wie man mit Streams Daten effizient kategorisieren kann.

#### Übung 4: Summierung von Werten

**Aufgabe:** Gegeben ist eine Liste von Ganzzahlen. Berechnen Sie die Summe der Quadrate aller ungeraden Zahlen in der Liste.

**Lösung:**

```java
List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);
int sumOfSquares = numbers.stream()
                          .filter(n -> n % 2 != 0)
                          .mapToInt(n -> n * n)
                          .sum();

System.out.println("Summe der Quadrate ungerader Zahlen: " + sumOfSquares);
```

**Erklärung:** Diese Übung verwendet `filter` zur Auswahl ungerader Zahlen, `mapToInt` zur Berechnung ihrer Quadrate und `sum` zur Ermittlung der Summe dieser Quadrate.

Diese Übungen illustrieren die Vielseitigkeit von Streams und Lambda-Ausdrücken in Java und wie sie zur Lösung verschiedener Probleme eingesetzt werden können. Durch die Bearbeitung dieser und ähnlicher Aufgaben können Entwickler ihre Fähigkeiten in funktionaler Programmierung effektiv verbessern und vertiefen.

# Abschluss

In diesem Tutorial haben wir uns umfassend mit der funktionalen Programmierung in Java beschäftigt, indem wir die Verwendung von Lambda-Ausdrücken, Streams, Methodenreferenzen, Collectors und Optionals erkundet haben. Diese Konzepte erlauben es uns, klarere, kürzere und effizientere Java-Code zu schreiben.

#### Zusammenfassung der Konzepte

Lambda-Ausdrücke ermöglichen es uns, anonyme Funktionen auf eine klare und prägnante Weise zu implementieren, während Streams eine hohe Abstraktionsebene für die Sequenzverarbeitung bieten. Methodenreferenzen vereinfachen den Code weiter, indem sie es uns ermöglichen, Methoden als Lambda-Ausdrücke zu verwenden. Collectors erleichtern das Sammeln von Stream-Ergebnissen, und Optionals bieten eine robuste Lösung für das Null-Pointer-Problem.

#### Anwendung im realen Kontext

Stellen Sie sich vor, wir wollen eine Liste von Produkten nach verschiedenen Kriterien filtern und sortieren:

```java
List<Product> filteredProducts = products.stream()
                                         .filter(p -> p.getPrice() > 100)
                                         .sorted(Comparator.comparing(Product::getPrice))
                                         .collect(Collectors.toList());
```

Diese Zeile repräsentiert die Kraft der funktionalen Programmierung in Java: Wir führen eine Sequenz von Operationen effizient und verständlich aus.

#### Abschließende Gedanken

Die funktionale Programmierung in Java bietet uns leistungsstarke Werkzeuge, um unsere Codebasis zu verbessern. Durch die Nutzung von Lambda-Ausdrücken, Streams und den anderen vorgestellten Konzepten können wir unsere Programme weniger fehleranfällig, lesbarer und einfacher zu warten machen. Es lohnt sich, diese Techniken in Ihren Java-Entwicklungsworkflow zu integrieren, um die Vorteile einer funktionaleren und deklarativeren Programmierweise zu nutzen.