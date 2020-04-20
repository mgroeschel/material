# Assignment: Architekturentwurf CP

Sommersemester 2020 | Prof. Thomas Smits | Ausgabe: 22.4.2020

Ziel dieses Assignment is es, aus den vorhandenen funktionalen und nicht-funktionalen Anforderungen einen _ersten Entwurf_ der Architektur zu machen. Dies wird nicht das letzte Mal sein, dass Sie sich mit der Architektur befassen, da diese bei einem agilen Projekt immer wieder revidiert wird. Nichtsdestotrotz müssen Sie jetzt einige grundlegenden Entscheidungen treffen und werden einige (z.B. die gewählte Technologie) später nur schwer ändern können. Deswegen ist es sinnvoll jetzt die möglicherweise bisher impliziten Entscheidungen zur Architektur explizit niederzulegen, damit diese klar sind.

> Drum prüfe, wer sich ewig bindet,<br>
> Ob sich das Herz zum Herzen findet.<br>
> Der Wahn ist kurz, die Reu‘ ist lang.<br>
> _Friedrich Schiller, Das Lied von der Glocke (Gedicht)_

Die Komponente ist das zentrale Element für die folgenden Architekturdiskussionen, weshalb Sie mit ihr beginnen sollten.


## Komponenten

Überlegen Sie sich, aus welchen _Komponenten_ Ihre Software bestehen wird. Eine Komponente sollte sich dadurch auszeichnen, dass ihre Teile intern eng miteinander zusammen arbeiten und sie nach außen eine klar definierte Schnittstelle hat über die man auf sie zugreift. Ordnen Sie jeder Komponente die Anforderungen (funktional und nicht-funktional) zu, die sie umsetzt. Es ist normal, dass eine Komponente mehrere Anforderungen umsetzt und dass eine Anforderung von mehreren Komponenten umgesetzt wird.

Einige Teile Ihrer Anwendung werden zustandsbehaftet sein, andere nicht. Denken Sie darüber nach, welche Komponenten einen Zustand halten müssen und welche nicht, welche zustandslos sind.

*Ergebnis*:

  * [Komponentendiagramm (UML)](https://www.oose.de/wp-content/uploads/2012/05/UML-Notations%C3%BCbersicht-2.5.pdf)
  * Liste mit der Zuordnung Komponente/Anforderung
  * Kurze Begründung, warum die jeweilige Komponente so geschnitten wurde
  * Information, ob die Komponente zustandsbehaftet is oder nicht


## Schnittstellen

Beschreiben Sie für jede Komponente grob die Schnittstelle, die sie anbieten wird, d.h. welche Daten gehen raus, welche rein, welche Funktionen/Methoden bietet sie an. Diese Angaben müssen nicht bis auf das Datenfeld herunter erfolgen aber man sollte grob erkennen können, welchen Zweck die Schnittstelle erfüllt.

Denken Sie auch an externe Komponenten und stellen Sie zusammen, welche externen Dienste Ihre Lösung verwenden wird und finden Sie heraus, welche Schnittestellen und Protokolle diese Dienste verwenden.

*Ergebnis*:

  * Liste der Schnittstellen pro Komponente mit den Daten und Funktionen
  * Liste der Schnittstellen der externen Dienste mit Daten und Funktionen


## Protokolle

Überlegen Sie, welche Schnittstellen welche Protokolle verwenden. Für jede Schnittstelle sollte bekannt sein:

  * Welches Protokoll wird für die Kommunikation eingesetzt (z.B. HTTP/REST, Webservice, RPC, lokaler Methodenaufruf, etc.)
  * Welches Datenformat wird über die Schnittstelle ausgetauscht (z.B. Binär, JSON, YAML, Methodenaufruf ...)

Denken Sie daran, dass Sie für jede Schnittstelle mindestens die Wahl zwischen einem REST-basierten und einem Stil haben, der sich an Methodenaufrufen orientiert. Überlegen Sie daher, welcher Stil für welche Schnittstelle der beste ist.

*Ergebnis*:

  * Zu jeder Schnittstelle Angaben zum Protokoll
  * Zu jeder Schnittstelle Angaben zum Datenformat
  * Zu jeder Schnittstelle Angaben zum Kommunikationsstil
  * Kurze Begründung, warum die Wahl auf dieses Protokoll gefallen ist


## Technologien

Überlegen Sie sich für jede Komponente, in welcher Technologie sie entwickelt werden soll. Hierzu gehören

  * die _Programmiersprache_ (z.B. Java, TypeScript, PHP, ...)
  * die _Ablaufumgebung_ (z.B. Tomcat, Jetty, im Browser, NodeJS, ...)
  * die eingesetzten _Frameworks_ (z.B. Spring, Vue.js, React, ...)

Denken Sie daran, dass jede Technologie mit spezifischen Vor- und Nachteilen daher kommt und machen Sie in der unten geforderten Begründung klar, warum Sie genau diese Technologie gewählt haben und nicht die Alternativen.

*Ergebnis*:

  * Zu jeder Komponente eine Liste der eingesetzten Technologien
  * Eine Begründung für die Technologieauswahl


## Persistenz

Machen Sie sich Gedanken zu der Frage, welche Persistenz sie verwenden wollen. Hierbei müssen Sie sich festlegen, ob Sie auf eine SQL oder NoSQL-artige Persistenz setzen wollen und welche Daten (grob) persistiert werden müssen. Überlegen Sie auch, welche Komponenten eine Persistenz benötigen und welche nicht.

*Ergebnis*:

  * Festlegung auf Persistenztechnologie(n)
  * Liste, welche Komponente, welche Persistenz verwendet


## Verteilungssicht

Ausgehend von den definierten Komponenten legen Sie fest, wo die Komponenten ausgeführt werden, z.B. Server, Mobiltelefon, Browser, Datenbank, Middleware etc. Beachte Sie, dass jede Systemgrenze zwischen Komponenten Auswirkungen auf das Protokoll hat, mit dem die Komponenten miteinander kommunizieren können, da sie ein Remote-Protokoll erzwingt. Beachten Sie, dass auch die Persistenz eine Komponente ist und in der Verteilungssicht auftauchen sollte.

*Ergebnis*:

  * [Einsatz- und Verteilungsdiagramm (UML)](https://www.oose.de/wp-content/uploads/2012/05/UML-Notations%C3%BCbersicht-2.5.pdf)
