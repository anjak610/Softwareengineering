# Sommersemester 2017

## Lernziele

 - Erlernen und Verstehen neuerer Sprachkonstrukte in zeitgemäßen Programmiersprachen
 - Anwendung dieser Sprachkonstrukte in der OpenSource 3D-Library FUSEE, Made in
   Furtwangen 
 - Kollaborative Erarbeitung einer größeren Feature-Set in Kleingruppen
 - PROGRAMMIEREN KÖNNEN

## Inhalte

- Managed Sprachen im allgemeinen
- Reflection
- Generics/Container/Iterator
- Reflection/DependencyInjection/DoubleDispatch
- Events/Delegates/Anonymous methods
- Lambdas, evtl. LINQ
- Concurrency/Threads/Async&Await

## Struktur der Veranstaltung

Projektbezogene Arbeit an FUSEE. Thema:
FUSEE um Graphical User Interface Elemente erweitern.
Wechsel aus o.g. Inhalten und

## Gemeinsam zu erarbeitende Grundlagen

- Klassendesign
- Picking
- Rect-Transform Rendering
- Infrastruktur für 

## Themen für Gruppenarbeit (variiert ggf. noch)

- Klassen für Textobjekte
- Event-System für User-Eingaben
- Klassen für interaktive Objekte (Buttons, Radio-Boxen, Slider etc.)
- Skalierbarer 9-teiliger UI-Element-Klasse
- UI-Image-Klasse inkl Transparenz
- Reflection basierter Dialog-Aufbau

Vielleicht auch:
- Klassen für Listen- und Baumdarstellung
- Hilfs-Tools zum Erstellen von UI-Layouts
- Konverter zum Konvertieren aus bestehenden (welchen?) UI-Datenformaten


## Semesterplan

| Datum          | Inhalt             | 
|----------------|--------------------| 
| 13. Mrz        | Einführung         | 
| 20. Mrz        | Selbständige Einarbeitung in FUSEE. Christoph Müller nicht anwesend.  | 
| 27. Mrz        | Traversierung und Suche in FUSEE - o.g. Technologien verstehen.      | 
| 03. Apr        | Double Dispatch & Traversierung. Aufgabe: Picking     | 
| 10. Apr        | Picking continued                   | 
| _17. Apr_      | _Ostern_                            | 
| 24. Apr        | Rect-Transform Rendering       | 
| _01. Mai_      | _Maifeiertag_      | 
| 08. Mai        | Klassendesign                   | 
| 15. Mai        | Klassendesign continued                 | 
| 22. Mai        | Beginn Gruppenarbeit            | 
| 29. Mai        | TODO                   | 
| _05. Jun_      | _Pfingsten_             | 
| 12. Jun        | TODO                      | 
| 19. Jun        | Klausurvorbereitung               | 
| 26. Jun        | Präsentation der Gruppenarbeiten  | 

## TODO bis zum 20.03.

Tools Installieren & Umgebung aufbauen
- [Visual Studio IDE](https://www.visualstudio.com/) in der Visual Studio _Professional_ oder _Enterprise_ Edition.
  Kostenlos über den [HFU Microsoft-Imagine-Zugang](https://e5.onthehub.com/WebStore/Welcome.aspx?ws=59962a70-148d-e311-93fa-b8ca3a5db7a1)

- [FUSEE](http://fusee3d.org). Installationshinweise unter [Getting Started](https://github.com/FUSEEProjectTeam/Fusee/wiki/Getting-Started)


## TODO bis zum 27.03.

- [Fusee Tutorials](https://github.com/griestopf/Fusee.Tutorial) nachvollziehen (vor allem Tutorial 05) und Fragen vorbereiten.

- Rect Transform und hierarchischer Aufbau von UIs in Unity verstanden haben (Zusammenhang zwischen Anchor und Position/Größe)


## TODO bis zum 3.04.

- ALLE vorangegangenen TODOs erledigen

- Szenengraph für Roboter in _SearchAndFind_ implementiert.

- Mit FUSEE's Suchfunktion einen der Nodes im Szenengraph nach Namen suchen und
  die Rotation abändern:

  ```C#
  var forearm = _scene.Children.FindNodes(n => n.Name == "Forearm").First().GetTransform();

  forearm.Rotation = new float3 (3.1415f, 0, 0);
  ```
  Gerne auch interaktiv auf Grund von Benutzereingaben.
  Erklärung dazu in [Tutorial 05](https://github.com/griestopf/Fusee.Tutorial/tree/master/Tutorial05#accessing-scene-properties) nachlesen.

- FREIWILLIG als Programmierübung: eine oder mehrere der leeren Implementierungen
  in [SimpleMeshes.cs](01_SearchAndFind/Core/SimpleMeshes.cs) mit Leben füllen.  

## TODO bis zum 10.04.

- Verstehen, wie Delegates funktionieren und wie man sie verwendet.
  - Deklarieren eines Delegate-Typs
  - Deklarieren von Variablen/Feldern/Parametern, die Delegates enthalten
  - Verwenden einer expliziten (benannten) Methode als Delegate
  - Verwenden einer anonymen Methode als Delegate

- Verstehen, wie Lambdas funktionieren und wie man sie verwendet.
  - Der `=>` Operator als Methodendeklaration
  - Parameterliste ohne Typen
  - Einelementige Parameterliste ohne `(`und `)`
  - Einzeilige Funktionsrümpfe ohne `{`, `}` und `return`

- Literatur dazu:
  - C#-Programmierhandbuch zu Delegates in
     [Englisch](https://docs.microsoft.com/en-us/dotnet/articles/csharp/programming-guide/delegates/index) oder 
     [Deutsch](https://msdn.microsoft.com/de-de/library/ms173171(v=vs.140).aspx).
  - C#-Programmierhandbuch zu Lambdas in
    [Englisch](https://docs.microsoft.com/en-us/dotnet/articles/csharp/programming-guide/statements-expressions-operators/lambda-expressions) oder 
    [Deutsch](https://msdn.microsoft.com/de-de/library/bb397687.aspx).
  - C# 3.0 cookbook - Chapter 9. Delegates, Events, and Lambda Expressions (kostenlos als E-Book in der 
    [Bibliothek](http://www.hs-furtwangen.de/willkommen/die-hochschule/zentrale-services/informations-und-medienzentrum/die-bibliotheken.html))

- Musterlösung nachvollziehen
  - Aufbau des Roboterszenengraphen mit "Parent-Only"-Nodes zur Festlegung des korrekten Rotationszentrums
  - Rekursive Traversierung des Szenengraphen mit [`FindNodeByName`](02_SearchAndFindSolved/Core/SearchAndFind.cs#L144).

- Freiwillig
  - Verstehen, was ein "Closure" im Zusammenhang mit Delegates ist.

## TODO bis zum 24.04.

- Mit der Methode [`PointInTriangle`](https://github.com/FUSEEProjectTeam/Fusee/blob/develop/src/Math/Core/float2.cs#L972)
  vertraut werden. Ggf. kleinen Test schreiben
- 03_Pick bauen und [`PickAtPosition`](03_Pick/Core/Pick.cs#L164) implementieren

