---
Chapter: KVK
Part: "1"
---
# Grundlagen und Werkzeuge der Analysis
## Recap Folgen und Grenzwerte
### Folgen
__Definition 13. 1:__ Folge in $X$
-  Sei $X$ eine Menge. Eine folge in $X$ ist eine Abbildung $a -> X$
	- Wir schreiben $a_n$ anstatt $a(n)$ und nennen $a_n$ das $n$-te Folgenglied
	- Für die Folge selbst, schreiben wir $(a_n )_(n in NN)$ oder auch nur $(a_n )$
	- Folgeglieder haben eine Reihenfolge, da $NN$ geordnet ist! Unterscheide
		- Folge und Folgenglieder (geordnet)
		- Der Wertebereich einer Folge (Menge und somit ungeordnet)
- Beispiel: $a_n = (1/n)_(n in NN^+ )$
- Motivation für die  Betrachtung von Folgen
	- Diskreter fall ist leicher für das Studium von Funktionen
	- Vergleich zu AuD
### Konvergenz von Folgen und der Grenzwert
Definition 13.2 Konvergenz:
- Sei $(V, ||dot||)$ ein normierter $RR$-VR
- Eine Folge $(a_n )$ heißt convergent gegen $a$, falls für jedes $epsilon > 0$ ein $n_0$ existier mit
$$
|| a_n - a || < epsilon " für alle " n >= n_0
$$
- TODO
### Intuition für die Konvergenz-Definition
"$dots$ falls für jedes $epsilon > 0$ ein $n_0$ existiert mit $|| a_n - a || < epsilon$ für alle $n >= n_0$"
- TODO
### Weitere Beispiele zur Definition
- Konvergenz mit alternierendem Start
	- Erkenntnis: Nur das asymptotische Verhalten ist Wichtig wegen "$n >= n_0$"
- Divergenz am Beispiel der Folge $(a_n ) - ((-1)^n )_(n in NN)$
- TODO Bilder
### Konvergenz gegen $+- infinity$
__Definition 13.14__ "Konvergenz gegen $+- infinity$"
- TODO

## Übersicht Konvergenz & Divergenz #cheatsheet
- Insgesamt erkanten wir das folgende Zusammenspiel der Begriffe
- TODO Bild
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
		- Für den Grenzwert $a$ gilt $a in RR union {+-infinity}$
### Grenzwertsätze und Konvergente Folgen #Baustein
Statt Konvergenz manuell zu prüfen, nutzen wir ein "_Baustein-System_" in Form von
- __Satz 13.8__ Grenzwertsätze (Anleitung wir Bausteine kombiniert werden können)
	- Erlaubt Reduktion komplizierter Grenzwertsituationen auf einfacherer, bekannte Fälle
	- Wenn zwei Folgen konvergieren, dann konvergiert auch deren...
		- Summe, Produkt, Quotient (wenn der Nenner ungleich 0) sowie Skalierung
- __Bemerkung 13.11__ listet konvergente Folgen #Baustein 
- TODO
### Satz 13.8 Grenzwertsätze

^ca6d64

- TODO
###  H1.2 Divergenzsätze
- Häufiger Fehler ist aus Grenzwertsätzen analoge Aussagen für Divergenz 
- TODO
### Bemerkung 13.11 Wichtige konvergente Folgen
- TODO
### Kochrezept Konvergenz prüfen & Grenzwert ermitteln #Kochrezept
- __Satz 13.17__
- __Satz 13.16__
	- Wenn Folge nicht beschränkt, dann kann diese nicht konvergent in $RR$ sein
	- _Beschränktheit ist eine notwendige aber keine hinreichende Bedingung_
- Nutzen von bekannten Folgen und "Werkzeugen"
	- __[[#^ca6d64]](Grenzwertsätze 13.8)__ 
### Motivation Funktionsgrenzwerte (informell)
- Motivation: Untersuchung der Funktion $f$ an einer Stelle $a$
	- Eine Funktion weist einer Eingabe $x$ einem eindeutigen Wert $f(x)$ zu
	- Eventuell ist die Funktion in $a$ aber gar nicht definiert, d.h. wir können $f(a)$ nicht berechnen
- Idee: Was passiert mit einer Funktion, wenn wir und der sStelle $a$ annähern?
	- Gibt es einen bestimmen Wert, dem sich die Funktionswerte nähern?
	- Ist die Art (zum Beispiel Richtung) die wir uns annähern relevant?
- Formalisierung des "Annäherns" TODO
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
	- TODO
### Bemerkung 15.12 "jede Folge"
- "für jede Folge gilt"
	- nun können wir aber nicht jede Folge hinschreiben. Wie beweist man Das?
		- Schreibe: "Sei $(x_n )$ eine beliebige Folge in $D$ mit dem Grenzwert $a$"
		- Setze nun $(x_n )$ in die Funktion ein und nutzen die _13.8 Grenzwerte für Folgen_
- TODO
### Kochrezept Nachweis Funktionsgrenzwert #Kochrezept 
- In jedem Fall solltet ihr wenn möglich zuerst eine Skizze erstellen
- Wir unterscheiden zwei Fälle
	- _1. Fall_: Vermutung, dass der Grenzwert an der Stelle $a$ nicht existier
		- Idee: Zeigen, dass die Art der Annäherung an der Stelle $a$ nicht existiert
		- Ansatz: Angabe von zwei konkreten Folgen, die gegen $a$ konvergieren, für die jedoch die zugehörigen Folgen der Funktionswerte nicht den gleichen Grenzwert haben
		- Hinweis zur Wahl der Folgen:
			- Eure Skizze hilft euch dabei geeignete Folgen zu finden
			- Bei abschnittsweise definierten Funktionen, ist es hilfreich die Folgen zu so wählen, dass diese nur innerhald eines "definierten Abschnitts" bleiben, sodass ihr die Funktionsdefinition benutzen könnt
			- Bei trigonometischen Funktionen, solltet ihr die Periodizität ausnutzen, sodass die Funktionswerte de Folge immer den gleichen Wert haben
	- TODO
### Beispiel $f(x) = sin(1/x)$ #Beispiel
- Wir unterscheiden zwei Folgen mit Grenzwert $0$
	- $a_n = (1/(n*pi))$ dann ist $lim_(n -> infinity) (f(a_n)) = 0$
	- $b_n = (2/((4n+1)*pi))$ dann ist $lim_(n -> infinity) (f(b_n)) = 1$
	- Anmerkung: Dies ist ein Beispiel für den Hinweis aus dem Kochrezept
- TODO Bild
### Baustein-System für Funktionsgrenzwerte #Baustein
- _Satz 15.4_ Grenzwertsätze für Funktionsgrenzwerte
	- Da Funktionsgrenzwerte über Folgen definiert sind, können wir die Satz 13.8 Grenzwertsätze für Folgen auch hierauf anwenden
	- Einfachere Funktionsgrenzwerte können zu komplexeren kombiniert werden (_Anleitung_ für Kombination der _Bausteine_)
		- Summe, Betrag, Produkt, Quotient sowie Ordnungsrelation
	- Wichtig: Voraussetzung, dass die eingehenden Grenzwerte existieren (also "gültige _Bausteine_" sind)
- Einzelne Stellen sind sonst mittels Anwendung der Definition (Also des Kochrezepts) zu untersuchen