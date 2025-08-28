---
Chapter: KVK
Part: "1"
---
# Grundlagen und Werkzeuge der Analysis
## Recap Folgen und Grenzwerte
### Folgen
__Definition 13. 1:__ Folge in $X$ ^1860dc
-  Sei $X$ eine Menge. Eine folge in $X$ ist eine Abbildung $a -> X$
	- Wir schreiben $a_n$ anstatt $a(n)$ und nennen $a_n$ das $n$-te Folgenglied
	- Für die Folge selbst, schreiben wir $(a_n )_(n in NN)$ oder auch nur $(a_n )$
	- Folgeglieder haben eine Reihenfolge, da $NN$ geordnet ist! Unterscheide
		- Folge und Folgenglieder (geordnet)
		- Der Wertebereich einer Folge (Menge und somit ungeordnet)
- Beispiel: $a_n = (1/n)_(n in NN^+ )$
  ![[Pasted image 20250827184555.png]]
- Motivation für die  Betrachtung von Folgen
	- Diskreter fall ist leichter für das Studium von Funktionen
	- Vergleich zu AuD
### Konvergenz von Folgen und der Grenzwert
- __Definition 13.2__ Konvergenz: ^c0083f
	- Sei $(V, ||dot||)$ ein normierter $RR$-VR
	- Eine Folge $(a_n )$ heißt convergent gegen $a$, falls für jedes $epsilon > 0$ ein $n_0$ existiert mit $$|| a_n - a || < epsilon " für alle " n >= n_0$$
	- Dann nennen wir $a$ den _Grenzwert_ von $(a_n )$
	- Schreibe $lim_(n -> infinity) a_n = a$ oder $a_n -> a (n -> infinity)$
	- Gibt es kein solches $a$, so heißt die Folge _divergent_ in $V$ (wobei z.B. $V = RR$)
- Motivation für die Untersuchung von Konvergenz
	- Algorithmische Terminierung
	- Maschinelles Lernen und Optimierung

### Intuition für die Konvergenz-Definition
"$dots$ falls für jedes $epsilon > 0$ ein $n_0$ existiert mit $|| a_n - a || < epsilon$ für alle $n >= n_0$"
- "für jedes $epsilon > 0$ existiert ein $n_0$", also int $n_0$ abhängig von $epsilon$
  -> Aus diesem Grund sind Konvergenz-Beweise rückwärts zu erstellen
- Norm liefert und (absoluten) Abstand zwischen $n$-tem Folgeglied und $a$
- Dieser Abstand muss ab dem $n_0$-ten Folgeglied kleiner $epsilon$ sein
Visualisierung mittels _"Epsilon-Schlauch"_ für verschiedene $epsilon > 0$ um den Grenzwert $a$
![[Pasted image 20250827184851.png]]
### Weitere Beispiele zur Definition
- Konvergenz mit alternierendem Start
	- Erkenntnis: Nur das asymptotische Verhalten ist Wichtig wegen "$n >= n_0$"
	  ![[Pasted image 20250827184952.png]]
- Divergenz am Beispiel der Folge $(a_n ) - ((-1)^n )_(n in NN)$
  ![[Pasted image 20250827185023.png]]
### Konvergenz gegen $plus.minus infinity$
__Definition 13.14__ "Konvergenz gegen $plus.minus infinity$" ^f60b5c
- Eine Folge $(a_n )$ in $RR$ heißt konvergent gegen $infinity$, wenn es für jedes $C >= 0$ ein $n_0 in NN$ gibt, sodass $a_n >= C$ für alle $n >= n_0$ gilt
- Analog ist Konvergenz gegen $-infinity$ definiert
- _Divergenz in $RR$ ist in dieser Vorlesung also "alternieren" bzw. "mäandrieren"_
## Übersicht Konvergenz & Divergenz #cheatsheet
Insgesamt erkanten wir das folgende Zusammenspiel der Begriffe:
- konvergent
	- [[#^f60b5c]] (Def. 13.14) "konvergent gegen $infinity$" $a_n -> plus.minus infinity(n -> infinity)$
	  _Beispiel:_ $(a_n ) = n$
	  üblicherweise genannt: "bestimmte Divergenz" oder "uneigendliche Konvergenz"
	- [[#^c0083f]] (Def 13.2) Konvergent in $RR a_n -> a (n -> infinity)$
- divergent
	- [[#^c0083f]] (Def 13.2) "divergent in $RR$"
	  Beispiel: $(a_n ) = (-1)^n$

Alternative Darstellung:
![[Pasted image 20250827190024.png]]
### Formulierungen zur Beschreibung von Folgen
- Wir unterscheiden die folgenden Formulierungen fürFolgen
	- "Folge in $RR$" oder _reelle Folge_
		- Folgeglieder sind reelle WErte
		- Formal bedeutet dies $(a_n )_(n in NN) subset.eq RR$
	- "Reelle Folge konvergiert in $RR$" (im Sinne von _13.2_)
		-  Alle Folgeglieder sind reelle Weerte
		- Die Folge ist konvergent, also hat sie einen Grenzwert $a$
		- Konvergent in $RR$, somit $a in RR$
	- "Konvergente reelle Folge" (Im Sinne von _13.14_)
		- Folgeglieder sind reelle Werte
		- Die folge ist konvergent, also hat sie einen Grenzwert $a$
		- Für den Grenzwert $a$ gilt $a in RR union {plus.minus infinity}$
### Folgen Diagramm
![[Pasted image 20250827190344.png]]
### Grenzwertsätze und Konvergente Folgen
Statt Konvergenz manuell zu prüfen, nutzen wir ein "_Baustein-System_" in Form von
- __Satz 13.8__ Grenzwertsätze (Anleitung wir Bausteine kombiniert werden können) #Baustein ^c87999
	- Erlaubt Reduktion komplizierter Grenzwertsituationen auf einfacherer, bekannte Fälle
	- Wenn zwei Folgen konvergieren, dann konvergiert auch deren...
		- Summe, Produkt, Quotient (wenn der Nenner ungleich 0) sowie Skalierung
- __Bemerkung 13.11__ listet konvergente Folgen #Baustein 
- Warnung vor Nutzung der Grenzwertsätze
	- Die Voraussetzung, dass die "Folgen konvergieren" muss erfüllt sein!
	- Salopp: Eine Folge muss konvergieren, damit sie als __Baustein__ verwendet werden kann
	- Etwas zu schreiben wie "$a + infinity$" ergibt keinen Sinn! 
### Satz 13.8 Grenzwertsätze #Baustein #cheatsheet 
^ca6d64
Sei $(V, ||dot||)$ ein normierter $RR$-VR und an $(a_n ), (b_n ), (c_n )$ Folgen in $V$
Dann gilt
1. Ist $lim_(n->infinity) a_n = a$, so gilt $lim_(n->infinity) ||a_n || = ||a||$
2. Gilt $lim_(n->infinity) a_n = a$ und $lim_(n->infinity) b_n = b$, so folgt
   a) $lim_(n->infinity) (a_n +b_n ) = a+b$
   b) $lim_(n->infinity) (alpha a_n ) = alpha a$ für alle $alpha in RR$
   In $RR$ und $CC$ gilt außerdem
   c) $lim_(n->infinity) (a_n dot b_n ) = a dot b$
   d) Ist zusätzlich $b_n != 0$ für alle $n in NN$ und $b != 0$, so ist $lim_(n->infinity) (a_n / b_n ) = a/b$

Speziell für $RR$ gelten noch:
3. _Ordnungs-Theorem_  Ist $a_n <= b_n$ für alle $n in NN$ und $lim_(n->infinity) a_n = a$ und $lim_(n->infinity) b_n = b$ so gilt $a <= b$
4. _Sandwich-Theorem_  Ist $a_n <= c_n <= b_n$ für alle $n in NN$ und sind $(a_n )$ und $(b_n )$ konvergent mit Grenzwert $a$, so ist auch $(c_n )$ konvergent mit Grenzwert $a$
### H1.2 Divergenzsätze #cheatsheet 
- Häufiger Fehler ist aus Grenzwertsätzen analoge Aussagen für Divergenz abzuleiten (sogenannte "_Divergenzsätze_")
- Nur folgende Aussage ist allgemein gültig:
  Ist $(a_n )$ konvergent in $RR$ und $(b_n )$ divergent in $RR$, so ist $(a_n + b_n )$ divergent in $RR$
- Die sonstige Addition und Multiplikation konvergenter/divergenter Folgen, ist nicht automatisch divergent:
	- Ist $(a_n )$ _konvergent_ in $RR$ und $(b_n )$ _divergent_ in $RR$, so ist $(a_n dot b_n )$ _divergent_ in $RR$
	  Gegenbeispiel: $(a_n ) = 0$ und $(b_n )$ beliebige divergente Folge
	- Ist $(a_n )$ _divergent_ in $RR$ und $(b_n )$ _divergent_ in $RR$, so ist $(a_n + b_n )$ _divergent_ in $RR$
	  Gegenbeispiel: $(a_n ) = n$ und $(b_n ) = -n$
	- Ist $(a_n )$ divergent in $RR$ und $(b_n )$ _divergent_ in $RR$, so ist $(a_n dot b_n )$ _divergent_ in $RR$
	  Gegenbeispiel: $(a_n ) = (-1)^n$ und $(b_n ) = (-1)^n$
### Bemerkung 13.11 Wichtige konvergente Folgen #Baustein #cheatsheet 
- Ist $(a_n )$ eine konvergente Folge in $RR$ mit Grenzwert $a$ und gilt $a >= 0$ für alle $n in NN$, so ist jedes $p in NN^+$ auch $lim_(n->infinity) root(p, a_n ) = root(p, a)$
- Die Folge $(q_n )$ mit $q in RR$ konvergiert genau dann, wenn $q in (-1, 1]$ und es gilt
	- $lim_(n->infinity) q^n = 1$ falls $q = 1$
	- $lim_(n->infinity) q^n = 0$ falls $q = 0$
- $lim_(n->infinity) root(n, c) = 1$ für jedes $c in RR_+$ 
- $lim_(n->infinity) root(n,n) = 1$
- Die Folge $a_n =: (1+ 1/n)^n$, $n >= 1$ ist konvergent mit dem Grenzwert $e$  
### Kochrezept Konvergenz prüfen & Grenzwert ermitteln #Kochrezept
- __Satz 13.17__ Konvergenz Komponentenweise prüfen
- __Satz 13.16__ Folge beschränkt im Sinne von _Definition 13.5_? 
	- Wenn Folge nicht beschränkt, dann kann diese nicht konvergent in $RR$ sein
	- _Beschränktheit ist eine notwendige aber keine hinreichende Bedingung_
- Nutzen von bekannten Folgen und "Werkzeugen"
	- [[#^c87999]](Grenzwertsätze 13.8) bspw. Sandwich-Theorem in Verbindung mit
		- bekannten Grenzwerten _13.10(1)_ oder _13.11_
	- Bei Bruch von Polynom _13.10 (2)_: Kürzen durch die höchste Potenz
	- In $RR$: _13.20_ Monotonie-Kriterium oder _13.23_ Cauchy-Kriterium
Definition der Konvergenz
- [[#^1860dc]] (Def. 13.1) Konvergenz
- _Skript-Übungsaufgabe 13.4_ bzw. _G1.1_: $|| a_n - a ||$ muss Nullfolge sein
## Recap Funktionsgrenzwerte
### Motivation Funktionsgrenzwerte (informell)
- Motivation: Untersuchung der Funktion $f$ an einer Stelle $a$
	- Eine Funktion weist einer Eingabe $x$ einem eindeutigen Wert $f(x)$ zu
	- Eventuell ist die Funktion in $a$ aber gar nicht definiert, d.h. wir können $f(a)$ nicht berechnen
- Idee: Was passiert mit einer Funktion, wenn wir und der sStelle $a$ annähern?
	- Gibt es einen bestimmen Wert, dem sich die Funktionswerte nähern?
	- Ist die Art (zum Beispiel Richtung) die wir uns annähern relevant?
- Formalisierung des "Annäherns" mittels Folgen
	- Wir betrachten Folgen $(x_n )$, die gegen a konvergieren
	- Wir setzen diese folgen in die Funktion ein und gucken, wie sich die Funktionswerte verhalten
	- Wir sagen der _Funktionsgrenzwert_ existiert, wenn die Folgen gegen einen Wert konvergieren und es egal ist, wie wir und annähern
- Hauptmotivation: Grundlage für die Definition von Stetigkeit
### Grenzwertbegriff für Funktionen
- __Definition 15.1 Funktionsgrenzwert__
	- Sei $D subset.eq V$ Teilmenge eines normierten Vektorraums und $f: D -> W$
	- Wir Sagen, dass $f$ für $x$ gegen $a in overline(D)$ den _Funktionsgrenzwert_ $b in W$ hat, wenn $dots$
		- Für jede Folge $(x_n )$ in $D$, die gegen $a$ konvergiert
		- Die Folge $(f(x_n ))$ gegen $b$ konvergiert
	- Schreibe dann: $lim_(x-> a) f(x) = b$
- Saloppe Formulierung der Definition
	- Anforderung, "jede Folge" bedeutet, das es egal ist, wie wir und der stelle $a$ annähern
	- $a in overline(D)$ bedeutet, dass $a$ ein _Adhärenzpunkt_ ist, also die Funktion muss dort nicht mal definiert sein
- Unterschiede
	- __Funktionswert $f_a$__  ist ein Wert, den $f$ gemäß Funktionsdefinition an der Stelle $a$ annimmt
	- __Funktionsgrenzwert__ ist der Grenzwert, gegen den _alle Folgen_ der Funktionswerte konvergieren $$lim_(x -> a) f(x) = b " oder " lim_(n -> infinity) (f(x_n )) " mit " lim_(n-> infinity) x_n = a$$
### Beispiel $f(x) = 1/x$
- An der Stelle $a = 0$ ist die Funktion nicht definiert, aber trotzdem interessant
- Wie verhält sich $f(x)$, wenn wir uns der Stelle nähern?
	- _$a_n = (1/n)$ dann ist $lim_(n -> infinity) (f(a_n )) = infinity$ (nähern uns von rechts)_
	- $b_n = (-1/n)$ dann ist $lim_(n->infinity) (f(b_n)) = -infinity$ (nähern uns von Links)
	  ![[Pasted image 20250827201259.png]]
### Bemerkung 15.12 "jede Folge"
- "für jede Folge gilt"
	- nun können wir aber nicht jede Folge hinschreiben. Wie beweist man Das?
		- Schreibe: "Sei $(x_n )$ eine beliebige Folge in $D$ mit dem Grenzwert $a$"
		- Setze nun $(x_n )$ in die Funktion ein und nutzen die _13.8 Grenzwerte für Folgen_
- Anmerkung
	- Es muss mindestens eine Folge im Definitionsbereich geben, die gegen $a$ konvergiert (sonst wäre Aussage trivialerweise erfüllt "_Allquantor & leere Menge_")
### Kochrezept Nachweis Funktionsgrenzwert #Kochrezept 
- In jedem Fall solltet ihr wenn möglich zuerst eine Skizze erstellen
- Wir unterscheiden zwei Fälle
	- _1. Fall_: Vermutung, dass der Grenzwert an der Stelle $a$ nicht existier
		- Idee: Zeigen, dass die Art der Annäherung an der Stelle $a$ nicht existiert
		- Ansatz: Angabe von zwei konkreten Folgen, die gegen $a$ konvergieren, für die jedoch die zugehörigen Folgen der Funktionswerte nicht den gleichen Grenzwert haben
		- Hinweis zur Wahl der Folgen:
			- Eure Skizze hilft euch dabei geeignete Folgen zu finden
			- Bei abschnittsweise definierten Funktionen, ist es hilfreich die Folgen zu so wählen, dass diese nur innerhald eines "definierten Abschnitts" bleiben, sodass ihr die Funktionsdefinition benutzen könnt
			- Bei trigonometrischen Funktionen, solltet ihr die Periodizität ausnutzen, sodass die Funktionswerte de Folge immer den gleichen Wert haben
	- _2. Fall_: Vermutung, dass der Grenzwert an der Stelle $a$ existiert
		- Sei $(x_n )$ eine beliebige Folge mit $lim_(n->infinity) (x_n ) = a$
		- Setzt diese Folge in die Funktionsdefinition ein
		- Wendet darauf dann _[[#^c87999]] (Satz 13.8) Grenzwerte für Folgen_ an
### Beispiel $f(x) = sin(1/x)$ #Beispiel
- Wir unterscheiden zwei Folgen mit Grenzwert $0$
	- $a_n = (1/(n*pi))$ dann ist $lim_(n -> infinity) (f(a_n)) = 0$
	- $b_n = (2/((4n+1)*pi))$ dann ist $lim_(n -> infinity) (f(b_n)) = 1$
	- Anmerkung: Dies ist ein Beispiel für den Hinweis aus dem Kochrezept
![[Pasted image 20250827201620.png]]
### Baustein-System für Funktionsgrenzwerte
- _Satz 15.4_ Grenzwertsätze für Funktionsgrenzwerte #Baustein 
	- Da Funktionsgrenzwerte über Folgen definiert sind, können wir die Satz 13.8 Grenzwertsätze für Folgen auch hierauf anwenden
	- Einfachere Funktionsgrenzwerte können zu komplexeren kombiniert werden (_Anleitung_ für Kombination der _Bausteine_)
		- Summe, Betrag, Produkt, Quotient sowie Ordnungsrelation
	- Wichtig: Voraussetzung, dass die eingehenden Grenzwerte existieren (also "gültige _Bausteine_" sind) #Baustein 
- Einzelne Stellen sind sonst mittels Anwendung der Definition (Also des Kochrezepts) zu untersuchen
### Folgen Diagramm 2
![[Pasted image 20250827201712.png]]
## Recap Stetigkeit
### Stetigkeit
Bei _Funktionsgrenzwerten_ haben wir den _Funktionswert_ selbst nicht beachtet. Dies ändert sich nun:
- __Definition 15.7__ 3 Forderungen für Stetigkeit von $f: D -> W$ an der Stelle $a$ ^3b2570
  1. Grenzwert der Funktion $f$ and der Stelle $a$ existiert $lim_(x->a) f(x) = b$
  2. _Funktionswert_ existiert $f(a)$
  3. Es gilt _Funktionswert_ $=$ _Funktionsgrenzwert_, also $lim_(x->a) f(x) = f(a)$
- Vertauschbarkeit von Grenzwertübergang und Funktionsauswertung $lim_(x->a) f(x) = f(a) = f(lim_(x->a) x)$
	- Forderung: Wenn wir wissen, dass eine Funktion stetig ist, können wir Den _Limes_ in die Funktion ziehen
- Salopp
	- Kleine Änderungen am Argument bewirken nur kleine Änderungen im Funktionswert
	- Die Funktion verhält sich "erwartbar" und macht _keine Sprünge_
- Anmerkung
	- Für den _Funktionsgrenzwert_ reicht es wenn $a$ ein _Adhärenzpunkt_ ist, also $a in overline(D)$
### Baustein-System für Stetigkeit
Auch Stetigkeit ist über Folgen definiert, sodass der _Baustein_-Ansatz greift #Baustein 
- __Satz 15.11__: Verknüpfung stetiger Funktionen ist stetig
- __Satz 15.12__: Verkettung stetiger Funktionen ist stetig
	- Bei beiden Sätzen muss auf den Definitionsbereich geachtet werden!
- Erkenntnis
	- Wir zeigen Stetigkeit nicht manuell, sondern konstruieren Stetigkeit aus _Bausteinen_
	- Dieses Vorgehen entspricht dem Vorgehen der Grenzwertsätze für Folgen & Funktionen
	- Schreibe: "Die Funktion ist als _Verknüpfung_ stetiger Funktionen wiederum stetig"
- Die folgenden Funktionen dürft ihr wegen Vorlesung/Skript als stetig betrachten
	- Polynomfunktionen, Potenzfunktionen, Logarithmusfunktionen, trigonometrische Funktionen #Baustein 
	- bitte begründet immer durch ein kurzen Verweis auf das Skript
Frage: Wie verhält es sich für abschnittsweise definierte Funktionen?
### Unstetigkeit
- Wie sieht Unstetigkeit (in $RR$) aus?
	- _1. Fall_: Grenzwert existier, aber ist unterschiedlich vom Funktionswert
	- Grenzwert existiert nicht
		- _2. Fall_: "Links- und rechtsseitiger" Grenzwert sind verschieden ("Sprung")
		- _3. Fall_: Einer der Grenzwerte existiert nicht
	Anmerkung: Wir nutzen $circle$ um zu zeigen, dass die Stelle nicht enthalten ist
![[Pasted image 20250827203051.png]]
Grafik aus _Appell - Analysis in Beispielen & Gegenbeispielen S.15_
### Nachweis von (Un)Stetigkeit #Kochrezept 
Zum Nachweis der (Un)Stetigkeit an einer Stelle haben wir zwei Optionen
- __Definition 15.7__[[#^3b2570]] Stetigkeit bzw. __Bemerkung 15.8__("Folgenkriterium")
  1. Ermittle den Funktionswert $f(a)$
  2. Prüfe, ob der Grenzwert an der Stelle $a$ existiert
  3. Prüfe Gleichgewicht von Funktionswert und Grenzwert
     - __Gleichheit__: Funktion stetig in $a$ gemäß __Definition 15.7__[[#^3b2570]]
     - __Ungleichheit__: Funktion unstetig in $a$ gemäß __Bemerkung 15.8__
- __Satz 15.14__ Epsilon-Delta-Kriterium ($epsilon$-$delta$-Kriterium)
	- Siehe Material aus der Hörsaalübung
### Beispiel für eine stetig Funktion(?!)
- "können die Funktion zeichnen, ohne den Stift abzusetzen"
	- Stimmt dies wirklich? Die Funktion aus der Skriptübung ist nämlich stetig!
	  ![[Pasted image 20250827203754.png]]
	- $x=2$ ist ein isolierter Punkt und nach __G4.1h)__ sind Funktionen darin stetig
	- Folgenkriterium:
		- Es ist $lim_(x->2) f(x) = f(2)$ für alle Folgen die gegen $2$ konvergieren und deren Glieder ungleich 2 sind
		- Es gibt nämlich keine solche Folge - Allquantor über leere Menge ist trivialerweise erfüllt!
### Kochrezept Parameterwahl für Stetigkeit #Kochrezept 
1. Angabe, dass die Funktion abschnittsweise stetig ist und Übergangspunkte ("Schnittstellen") zu untersuchen sind
   -> Begründung für Stetigkeit in den Abschnitten mittels __Baustein-Ansatz__
2. Schnittstelle $x_0$ ermitteln
3. Funktionswert $f(x_0)$ berechnen
4. Allgemeine Folge $(x_n )$ mit Grenzwert $x_n$ in andere Abschnittsdefinition einsetzen
5. Parameter wählen, sodass Grenzwert und Funktionswert übereinstimmen
- Aufschrieb und Beispiel in G4.2b)
## Recap L'Hospital
### Satz von l'Hospital
__Satz 19.5__ Satz von l'Hospital
- Bestimmung "_uneigentlicher Grenzwerte_" der Form $0/0$ oder $plus.minus infinity/infinity$
	- Formalisiert die Idee des Wachstumsvergleichs durch die lokale Änderung
		- Beispiel Fall $0/0$: Wir haben zwei Autos $f, g$ die bremsen - welches bremst schneller und kommt zuerst zum Halt?
	- Dies kann unter anderem hilfreich sein für besonders knifflige Mastertheoreme in AuD
- Satz hat viele Voraussetzungen, die alle nötig sind!

Sei $(a, b) subset.eq RR$ und $f, g: (a, b) -> RR$ _diffbar_ auf $(a,b)$ mit $g^prime (x) != 0$ für alle $x in (a,b)$
- Wenn nun
	- $f, g$ die _uneigentliche Grenzwert_-Eigenschaft erfüllen, also mit $lim_(x->a) f(x) = lim_(x->a) g(x) = 0$ (oder beide $plus.minus infinity$)
	- der Grenzwert $L := lim_(x->a) (f^prime (x))/(g^prime (x))$ mit $L in RR union {plus.minus infinity}$ existiert
- dann gilt $lim_(x->a) (f(x))/(g(x)) = L$
### Kochrezept Satz von l'Hospital #Kochrezept 
__Voraussetzung prüfen__
1. Angabe eines offenen Intervalls $(a,b) subset.eq RR$ und $a < b$
2. Benennung der Funktionen $f,g: (a,b) -> RR$
3. Nachweis $f,g$ auf $(a,b)$ diffbar (Angabe der Ableitungen)
4. Angabe, dass $g^prime (x) != 0$ für alle $x in (a,b)$
5. Nachweis _uneigentlicher Grenzwert_-Eigenschaft
   -> "Für $x->a$ hat $f(x)/g(x)$ die Form "$0/0$" bzw. "$plus.minus infinity/infinity$" "
   -> ggf. Umformungen durchführen, um diese Eigenschaft herzustellen
6. Berechnung Grenzwert $L := lim_(x->a) (f^prime (x))/(g^prime (x))$
__Folgerung mittels Satz von l'Hospital__
7. Folgerung für ursprüngliche Funktion $f(x)/g(x)$

Anmerkung: Statt $x->a$ können wir auch $x->b$ betrachten
### Hinweise zum Satz Von de L'Hospital #cheatsheet 
- Euer Aufschrieb sollte sich an __Beispiel 19.7__ orientieren
- __Beispiel 19.7(3)__ zeigt: eine Mehrfachanwendung von L'Hospital ist möglich.
	- Wenn der im _6. Schritt_ berechnete Grenzwert $L = plus.minus infinity$ ist, dann könnt ihr auf diese Funktion erneut L'Hospital anwenden
	- Hierbei sind dann wieder alle Voraussetzungen zu prüfen
- L'Hospital kann auch genutzt werden für Funktionen, die zunächst nicht die _uneigentliche Grenzwert_-Eigenschaft haben durch Überführung in "$0/0$" bzw. "$plus.minus infinity/infinity$"
	- "$0 dot infinity$" als Quotient Beschreiben (vgl. __Beispiel 19.7(2)__)
	-  "$infinity - infinity$" über gemeinsamen Nenner
	- Potenzen "$0^0$" "$1^infinity$" oder "$infinity^0$" umformen mittels $a^b = exp(b dot ln(a))$
### Folgen Diagramm 3
![[Pasted image 20250827210453.png]]
## Recap Reihen
### Definition Reihe un Partialsumme
- __Definition 14.1__ Reihe (engl. series)
	- Sei $(a_n )$