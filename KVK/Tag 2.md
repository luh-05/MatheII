---
Chapter: KVK
Part: "2"
---
## Recap Differenzierbarkeit
### Differenzierbarkeit
- __Definition 18.1__ Differenzierbarkeit
	- Es sei $x_0 in I$. Eine Funktion $f : I -> RR$ heißt _differenzierbar_ in $x_0$, wenn folgender Grenzwert in $RR$ existiert: $$lim_(x->x_0) (f(x)-f(x_0))/(x-x_0)$$
	- "Grenzwert in $RR$ existiert" bedeutet, dass der Grenzwert eine reelle Zahl ist, also insbesondere beschränkt, ist
	- Erkenntnis: Zur Definition wird ein Funktionsgrenzwert verwendet, womit auch hier unser _Baustein_-Ansatz aus Tag 1 greift #Baustein 
### Visuelle Intuition für Differenzierbarkeit
Für Stetigkeit war unsere visuelle Intuition, dass es _keine Sprünge_ gibt

__Satz 18.8__ liefert und eine visuelle Intuition für Differenzierbarkeit
- Differenzierbarkeit bedeutet keinen _Knick_ (d.h. __Kanten__ oder __Kuspen__)
- Under dem _Mikroskop_ soll die Funktion wie eine Gerade aussehen
	- Damit es als gerade approximiert werden kann, muss es eine Gerade geben
	- Dafür ist insbesondere notwendig, dass
		- die Funktion in $x_0$ Stetig ist (also ist Stetigkeit eine notwendige Bedingung)
		- es umliegende Punkte um $x_0$ gibt (also $x_0$ __innere Punkt__ ist)
- __Beispiel__: Betragsfunktion ist nicht differenzierbar in $x_0 = 0$
### Stetige Differenzierbarkeit & Höhere Ableitungen
__Definition 18.21 Stetig differenzierbar__
- Ist $f : I -> RR$ eine auf $I$ differenzierbare Funktion und ist $f^prime$ auf $I$ stetig, so nennt man $f$ _stetig differenzierbar_.

__Definition 18.22 Höherer Ableitungen__ (Iterative Definition)
- Wir nennen eine Funktion $n$__-mal differenzierbar__, wenn sie $(n-1)$-mal differenzierbar ist und diese Ableitung auch differenziert werden kann
- Insbesondere muss die Funktion um $n$__-mal differenzierbar__ sein zu können, $(n-1)$__-mal stetig differenzierbar__ sein.
- Ist eine Funktion __unendlich__ of (stetig) differenzierbar, nennen wir sie _"glatte Funktion"_ (engl. smooth)
	- Insbesondere sind alle Polynome _glatte Funktionen_ #Baustein 
	- Somit sind auch alle Potenzreihen _glatte Funktionen_ #Baustein 
	- Dies können wir bei der Hesse-Matrix für den Satz von Schwarz nutzen #Baustein 
### Ableitungsregeln für $RR$ #cheatsheet 
Liefern und wie bei Funktionsgrenzwerten und Stetigkeit wieder ein __Baustein__-System
- __Satz 18.10__ #Baustein 
	- __Linearität__: $(alpha f + beta g)^prime (x_0) = alpha f^prime (x_0) + beta g^prime (x_0)$
	- __Produktregel__: $(f g)^prime (x_0) = f^prime (x_0) g(x_0) + f(x_0) g^prime (x_0)$
	- __Quotientenregel__: $(f/g)^prime (x_0) = (f^prime (x_0) g(x_0)-f(x_0) g^prime (x_0))/(g(x_0))^2$
- __Satz 18.11 Kettenregel__ #Baustein 
	- $(f circle g)^prime (x_0) = f^prime (g(x_0)) dot g^prime (x_0)$
	- Die Reihenfolge ist in $RR$ egal (wegen dem Kommutativgesetz)
	- Gewöhnt euch jedoch die Reihenfolge "__Äußere mal Innere__" an für den mehrdimensionalen Fall
	- _Hinweis:_ Mit der Kettenregel könnt ihr euch __Quotienten-__ und __Umkehrregel__ herleiten 
- _Wichtig:_ Die Ableitungsregeln haben Voraussetzungen! Diese müsst ihr prüfen!
### Ableitungsregeln #cheatsheet 
- __Beispiel 18.12 Allgemeine Potenzfunktion__
	- Sei $phi(x) := a^x$ dann ist $phi^prime (x) = a^x ln(a)$
- __Satz 18.13__ Ableitung der Umkehrfunktion ("__Umkehrregel__") ^560892
	- $(f^-1 )^prime (y_0) = 1/(f^prime (x_0))$
- __18.16 Ableitung von Potenzreihen__
	- Innerhalb des Konvergenzradius _summandenweise differenzierbar_ #Baustein 
	- Vertauschung von zwei Grenzwertprozessen möglich!
- _Wichtig:_ Die Ableitungsregeln haben Voraussetzungen! Diese müsst ihr prüfen!
- Lernt die Ableitungen aus der Tabelle unter __Beispiel 18.18__
### Merkhilfe für die Umherregel #cheatsheet 
- Alternative Beweis zu __Satz 18.13__[[#^560892]]: Es gelten die gleichen Voraussetzungen
	- Wir schreiben nun jedoch die __Identität__ $x$ kompliziert als __Verkettung__ von Umkehrfunktionen und der Funktion selbst: $$ x = f^-1 circle f(x) = f^-1 (f(x)) $$
	- Anschließend nutzen wir die __Kettenregel__ "__Äußere mal Innere__" auf beiden Seiten $$ f^-1 (f(x)) = x <=> (f^-1)^prime (f(x)) dot f^prime (x) = 1 $$
	- Wir setzen $f(x) = y$ bzw. $f(x_0 ) = y_0$ und stellen anschließend nach $(f^-1)^prime (y_0)$ um $$ (f^-1)^prime (y_0) = 1/(f^prime (x_0)) $$
	- Insbesondere liefert uns dieser alternative Beweis eine __herleitbare Merkhilfe__
### Anwendung Umkehrregel #Kochrezept 
__Voraussetzungen prüfen für die Anwendung von Satz 18.13[[#^560892]] Umkehrregel__ 
1. Angabe der Funktion $f$
2. Angabe der Ableitung von $f$
3. Angabe eines Intervalls $I$ auf dem
   -> $f$ __stetig__ ist
   -> $f$ __injektiv__ ist
   -> Falls $f$ sich auf ganzem Definitionsbereich so verhält, kann dies geschrieben werden und eine weitere Prüfung ist nicht nötig
4. Falls konkretes $x_0$ gegeben: Abgabe, dass $x_0$ in $I$ und $f^prime (x_0) != 0$
__Anwendung der Formel aus Satz 18.13[[#^560892]] Umkehrregel__
5. Formel angeben
6. Werte einsetzen
7. Resubstitution durchführen und vereinfachen
### Mittelwertsatz
__Satz 19.1 Mittelwertsatz (MWS)__ ^348e20
- $(f(b)-f(a))/(b-a) = f^prime (xi)$
- Salopp: Die _Sekantensteigung_ wird an mindestens einem Punkt $xi$ als __Tangentensteigung__ angenommen 
- Der Mittelwertsatz liefert nur eine Existenzaussage. Es kann auch mehrere $xi$ geben!
- _Beispiel:_ Toll-Gate
	- Wenn die durchschnittliche Geschwindigkeit zwischen Eingang und Ausgang über der Geschwindigkeitsgrenze liegt, dann muss man auch an mindestens einem Punkt schneller gewesen sein
	- Gute Alternative statt überall Blitzer zu haben
![[Pasted image 20250828100001.png]]
### Anwendung vom Mittelwertsatz #Kochrezept 
Das Anwenden vom Mittelwertsatz zum Beweisen von Abschätzungen erfolgt meist nach folgendem Schema:
1. Funktion $f(x)$ identifizieren und angeben
2. Funktion $f^prime (x)$ ableiten
3. Funktionswert an Intervallgrenzen $(a,b)$ berechnen
4. Bausteine (Funktion, Ableitung, Funktionswerte) in Ungleichung identifizieren
5. Umformen der Gleichung des Mittelwertsatzes in die zu zeigende Abschätzung

- Hinweise
	- Die eigentliche Schwierigkeit liegt im ersten Schritt
	- Wie wollen das $xi$ aus dem Mittelwertsatz nicht ausrechnen, da darin die Komplexität versteckt wird.
	- Uns reicht es zu Wissen, dass ein solches $xi in (a, b)$ existiert, damit wir es für Abschätzungen nutzen können
### Satz von Rolle
__Satz 19.2 "Satz von Rolle"__
- Gilt $f(a) = f(b)$ und $f in C([a,b])$, so gibt es ein $xi in (a,b)$ mit $f^prime (xi) = 0$
- ist nur ein Spezialfall des __19.1 MWS[[#^348e20]]__
![[Pasted image 20250828100844.png]]
## Recap Differenzierbarkeit in mehreren Variablen
### Unterschiedliche Differenzierbarkeit
![[Pasted image 20250828112144.png]]
__Anmerkungen__
- __Total diffbar__ ist unsere vertraute __Differenzierbarkeit__ in einer Variablen
- Im Eindimensional gibt es nur eine Richtung, daher fallen __partielle__ (also Betrachtung entland der Hauptachsen) & __totale Differenzierbarkeit__ zusammen
### Partielle Differenzierbarkeit & Richtungsableitung
- __Definition 21.3__ Partiell differenzierbar
	- Ableitung entlang der Hauptachsen existiert
	- hinsichtlich "Handwerk & Anwendung" unserer wichtigster Differenzierbarkeitsbegriff
- __Definition 21.1__ Richtungsableitung
	- Ableitung entland einer bestimmten Richtung existiert
	- Richtung muss keine der Hauptachsen entsprechen
	- Verallgemeinerung von partielle Differenzierbarkeit
- Zusammenhang __partielle Differenzierbarkeit__ und __Richtungsableitung__
	- Wenn alle Richtungsableitungen existieren, existier natürlich auch die Ableitung entlang der Hauptachsen
		- Differenzierbar in __alle Richtungen__ $=>$ __partiell differenzierbar__
		- Die Umkehrung ist falsch!
	- Die Ableitung entland eines beliebigen Vektors $v$, kann durch __Linearkombination__ der partiellen Ableitungen dargestellt werden
### Partielle & totale Differenzierbarkeit
- __Theorem 21.22__ Zusammenhand totale und partielle Differenzierbarkeit
	- $f$ total differenzierbar in $x_0$, dann existiert die __Richtungsableitung__ in jede Richtung
	- Insbesondere ist $f$ auch __partiell differenzierbar__
	- Die lineare Abbildung $Phi: RR^d -> RR^p$ (d.h. Abbildungsfunktion) ist gegeben durch die Jacobi-Matrix $J_f$
- __Satz 21.24__ Totale Differenzierbarkeit in $x_0$ impliziert __Stetigkeit__ in $x_0$
	- Totale Differenzierbarkeit ist also das, was wir bisher unter "Differenzierbarkeit in einer Variablen" kannten
### Partielle Differenzierbarkeit
- __Definition 21.3__ Partielle Differenzierbarkeit (engl. partial derivative)
	- Wir haben Funktionen, die aus dem $RR^d$ abbilden, d.h. unsere Funktionen haben mehrere Argumente  oder auch "Richtungen" (sind Vektoren)
	- Partielle Ableitungen beschreiben die Veränderung, wenn wir nur eines der Argumente ändern
	- _(2)_ liefert und die Notationsmöglichkeiten ($diff$ wird "del" genannt und diff geschrieben) $$ diff_j f(x_0) := (diff f)/(diff x_j) (x_0) $$
- __Bemerkung 21.6__ Vergehen zur Bestimmung partielle Ableitungen
	- Behandle die anderen Variablen als Konstante
	- Insbesondere können wir also unsere bekannten Ableitungsregeln benutzen!
- Graphische Interpretation (für skalarwertige Funktionen, d.h. $RR^d -> RR$)
	- Vorher: Differenzierbarkeit: Tangentensteigung in dem Punkt
	- Jetzt: Schnitt mit Koordinatenachse und dann Tangentensteigung im Punkt

Anmerkung: "Partiell", da diese Form der Differenzierbarkeit nur einen Teil (part) betrachtet
### Beispiel mit Geogebra: $f(x,y) = x^2 + sin(y)$
- Wir bestimmen zunächst die partiellen Ableitungen der Funktion
	- in dem wir die jeweils andere Variable als Konstante behandeln
	- Und dann unsere eindimensionalen Ableitungsregeln anwenden

Wir erhalten
- $diff/(diff x) f(x,y) = 2x y$
- $diff/(diff y) f(x, y) = x^2 + cos (y)$

- Beide haben eine unmittelbare visuelle Interpretation
	- Geogebra-Datei im Order uebung09
### Gradient
- __Definition 21.10__ Gradient
	- Für eine skalarwertige Funktion $RR^d -> RR$ haben wir
		- $d$ Richtungen und somit
		- $d$ partielle Ableitungen
	- Wir nennen $nabla f(x_0) = (diff_1 f(x_0), diff_2 f(x_0), dots, diff_d f(x_0))$ den __Gradient von f__
	- Wichtig: Der __Gradient__ ist (in Mathe2) ein Zeilenvektor (bzw. $1 times d$-Matrix)
	- Das Symbol $nabla$ heißt __nabla__ (und wir _nabla_ geschrieben)
	- Salopp: Der __Gradient__ sammelt unsere partiellen Ableitungen in einem Zeilenvektor
- _Beispiel_: Der __Gradient__ der Funktion $f(x, y) = x^2 y + sin(y)$ ist $nabla f(x,y) = (2x y, x^2 + cos (y))$
- __Bemerkung 21.11__ Geometrische Interpretation
	- Der Gradient ist die Richtung des stärksten Anstiegs
	- Der Betrag (also die Länge des Vektors) ist die Steilheit (engl. steepness) des Anstiegs
### Skalar- vs. vektorwertige Funktionen
- Für allgemeine Funktionen $RR^d -> RR^p$ unterscheiden wir zwischen
	- $p = 1$ skalarwertige Funktionen
		- Funktionen, die wir bisher betrachtet haben
		- Sind interessant, da wie hierüber Optimierung betreiben können (vgl. __Kapitel 22__ Extremwertprobleme)
	- $p > 1$ vektorwertige Funktionen