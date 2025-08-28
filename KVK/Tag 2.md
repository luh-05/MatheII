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
	- Das Symbol $nabla$ heißt __nabla__ (und wird "_nabla_" geschrieben)
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
		- Haben nun mehrere __Koordinatenfunktionen__ in unserer Aufgabe
		- __Frage__: Wie behandeln wir die Koordinatenfunktion?
- __Satz 21.8__ Untersuchung vektorwertiger Funktionen auf __(stetig) partielle Differenzierbarkeit__
	- Wir untersuchen Koordinatenfunktionen einzeln, also __komponentenweise__!
	- Folgerung: Bisherige Erkenntnis zu __partiellen Ableitungen__ und __Gradient__ trifft für jede der __Komponentenfunktionen__ zu
	- Wir können also für jede __Komponentenfunktion__ den __Gradienten__ ermitteln!
### Zusammenhang Jacobi-Matrix & Gradient #cheatsheet 
- Für Funktionen $RR^d -> RR^p$ sagt man, dass wir
	- $d$ Richtungen und
	- $p$ Koordinatenfunktionen (oder auch Komponenten) haben
- Wir wissen nun auch
	- Je Richtung gibt es eine partielle Ableitung, d.h. $d$ partielle Ableitungen
	- Je Koordinatenfunktion gibt es einen Gradienten, d.h. $p$ Gradienten
- __Definition 21.10__ Jacobi-Matrix
	- Die $p times d$ Matrix (also $p$-Zeilen und $d$-Spalten) aller partiellen Ableitungen von $f$ heißt __Jacobi-Matrix__ von $f$ und lässt sich aus den Gradienten konstruieren $$ J_f (x_0) = mat(nabla f_1 (x_0);dots.v;nabla f_p (x_0)) = mat(diff_1 f_1 (x_0), dots.c, diff_d f_1 (x_0);dots.v, dots.down, dots.v;diff_1 f_p (x_0), dots.c, diff_d f_p(x_0)) $$
	  ![[Pasted image 20250828155557.png]]
### Kochrezept Gradient und Jacobi-Matrix #Kochrezept 
1. Dimension der Jacobi-Matrix bzw. des Gradienten angeben
   -> "Die Funktion ist $f : RR^d -> RR^p$ also hat die Jacobi-Matrix $p$-Zeilen und $d$-Spalten, ist also eine $p times d$ Matrix"
2. Alle __partiellen Ableitungen__ bestimmen (je _Richtung_ und _Koordinatenfunktion_)
3. Angabe des __Gradienten__ jeder Koordinatenfunktion, d.h. $nabla f_1, nabla f_2$ bis $nabla f_d$
4. Allgemeinen Aufbau der __Jacobi-Matrix__ angeben ("Stapeln der Gradienten")
5. __Jacobi-Matrix__ hinschreiben durch einsetzen der __Gradienten__ (und somit __partiellen Ableitungen__)
6. Prüfung, ob Dimension korrekt ist
7. Prüfung, ob die angegebene Elemente der __Jacobi-Matrix__ stetig, da dann
   -> Die Funktion __stetig differenzierbar__ also auch __total differenzierbar__ ist
   -> Die __Jacobi-Matrix__ der linearen Abbildung $Phi$ aus __Definition 21.18__

- __Empfehlung__: Notiert immer die Struktur der Jacobi-Matrix. Dies bringt euch Sicherheit und ist nachvollziehbar für die korrigierende Person. Das sind gut investierte <60 Sekunden
### Stetig partielle & höhere partielle Ableitungen
- __Definition 21.3(2)__ Stetig partiell differenzierbar
	- Ist $f$ __partiell differenzierbar__ und sind sämtliche partiellen Ableitungen _stetig_, so nennt man $f$ _stetig_ __partiell differenzierbar__
- __Definition 21.13__ Höhere partielle Ableitungen
	- Man nennt $f$ _n_-mal (__stetig__) **partiell differenzierbar** in $x_0$, wenn
		- $f$ schon (*n-1*)-mal (**stetig**) **partiell differenzierbar** ist und
		- alle (*n-1*)-mal (**stetig**) **partiell differenzierbaren** Ableitungen in $x_0$ wieder (**stetig**) **partiell differenzierbar** sind
- Schreibe beispielsweise $diff_1 diff_2 f = (diff f)/(diff_1 diff_2)$ für die zweifache partielle Ableitung von $f$, wobei erst nach $2$ und dann nach $1$ partiell abgeleitet wurde
### Beispiel höhere partielle Ableitung #Beispiel 
![[Pasted image 20250828161047.png]]
### Satz von Schwarz #cheatsheet 
**Satz 21.15** **Satz von Schwarz** #Baustein 
- Ist eine Funktion $n$-mal **stetig partiell differenzierbar**, dann sind die **partiellen Ableitungen** bis zu der Ordnung $n$ vertauschbar
	- Vertauschbar bedeutet, dass wie im vorherigen beispiel gilt: $diff_2 diff_1 f(x, y) = diff_1 diff_2 f(x, y)$
	- *Achtung*: Dies ist eine Implikation! Die Umkehrung ist falsch!

Nutzen diese Erkenntnis
- Wenn wir begründen können, dass eine Funktion hinreichend of **stetig partiell differenzierbar** ist, können wir uns das Bestimmen einzelner Ableitungen sparen
- Insbesondere können wir bei der **Hesse-Matrix** Ableitungen einsparen, wenn die Funktion $f$ **zweimal stetig partiell** differenzierbar ist (schreibe $C^2$)
- Wie wissen, dass glatte und analytische Funktionen beliebig oft stetig differenzierbar (und somit insbesondere $C^2$) sind! #Baustein 
## Recap Integrierbarkeit
### Treppenfunktion
- **Definition 23.1** Treppenfunktion
	- Eine Funktion $f : [a, b] -> RR$ ist genau dann eine **Treppenfunktion**, wenn es Zahlen $$ a = t_0 < t_1 < dots.c < t_n = b $$ und Konstanten $c_1, dots, c_n in RR$ gibt, so dass $$ f(x) = c_i " für alle " x in (t_(i-1), t_i) " und " i = 1, dots, n "." $$
	- Das heißt auf jedem Teilstück $(t_(i-1), t_i)$ nimmt $f$ den konstanten Wert $c_i$ an.
	- Für eine solche Funktion definiert man dann das Integral von $a$ bis $b$ als $$ integral_a ^b f(x)d x = sum_(i=1) ^n c_i(t_i -t_(i-1)) $$
	  also die Summe der Produkte Aus dem Wert $c_i$ und der Länge jedes Teilstücks $(t_i - t_(i-1))$
![[Pasted image 20250828162219.png]]
### Stetigkeit und Integrale #Achtung 
- Stetigkeit ist eine Voraussetzung für Differenzierbarkeit
- Stetigkeit ist **keine** Voraussetzung für Integrierbarkeit (siehe Treppenfunktionen)
  ![[Pasted image 20250828162331.png]]
- **Satz 23.4** Sei $f : [a, b] -> RR$ eine Funktion
	- Ist $f$ stetig, so ist $f$ integrierbar
	- Ist $f$ monoton wachsend oder monoton fallend, so ist $f$ integrierbar
### Standardabschätzung
- Es seien $a, b in RR$ mit $a < b$ und $f: [a, b] -> RR$ integrierbar. Dann ist auch $|f|$ integrierbar, und es gilt $$ |integral_a ^b f(x) d x )| <= integral_a^b|f(x)| d x <= (b-a) sup_(x in [a,b]) |f(x)| $$
### Das Integral im Betrag
- Flächenanteile von $f$ unter der $x$-Achse zählen negativ: $|integral_a^b f(x) d x|$
  ![[Pasted image 20250828163056.png]]
### Das Integral über die Funktion um Betrag
- Flächenanteile von $f$ unter der $x$-Achse zählen nun positiv: $integral_a^b |f(x)|d x$
  ![[Pasted image 20250828163207.png]]
### Rechtecksabschätzung über das Supremum
- Obere Schranke durch umspannendes Rechteck: $(b-a) sup_(x in [a,b]) |f(x)|$
  ![[Pasted image 20250828163330.png]]
### Zusammenfassung Standardabschätzung
Die Aussage ist also, dass die Flächeninhalte jeweils größer werden durch die Abschätzungen:
![[Pasted image 20250828163437.png]]
### Rechenregeln Integrale #Baustein #cheatsheet 
Es seien $a, b in RR$ mit $a < b$ und integrierbare Funktionen $f, g : [a,b] -> RR$ gegeben. Dann gelten folgende aussagen:
- **Linearität** Seien $alpha, beta in RR$, so ist auch $alpha f + beta g$ integrierbar und es gilt $$ integral_a^b alpha f(x) + beta g(x) d x = alpha integral_a^b f(x) d x + beta integral_a^b g(x) d x $$
- **Monotonie** Ist $f(x) <= g(x)$ fur alle $x in [a, b]$, so ist auch $$ integral_a^b f(x) d x <= integral_a^b g(x) d x $$
- **Additivität des Integrals** Ist $c in (a,b)$, so ist $f$ auch integrierbar auf $[a, c]$ und $[c,b]$ und es gilt $$ integral_a^b f(x) d x = integral_a^c f(x) d x + integral_c^b f(x) d x $$
- **Definition 23.8** Es seien $a,b in RR$ mit $a < b$ und $f: [a, b] -> RR$ sein integrierbar. Dann setzt man für jedes $c in [a,b]$ $$ integral_c^c f(x) d x := 0 " und " integral_b^a f(x) d x := -integral_a^b f(x) d x $$
### Logarithmische Integration #cheatsheet 
- **Beispiel 23.14** Für eine stetig Differenzierbare Funktion $phi: RR -> RR_(>0)$ betrachten wir $$ f: RR->RR, quad quad quad f(x) = (phi^prime (x))/(phi(x)) $$
- Funktion ist stetig und somit integrierbar. Aus der Kettenregel folgt, dass $F(x) = ln(phi(x))$ eine Stammfunktion ist. Also gilt für alle $a, b in RR, a < b$, mit dem Hauptsatz, dass $$ integral_a^b (phi^prime (x))/(phi(x)) d x = ln(phi(b)) - ln (phi (a)) $$
- Diese Integration spielt eine wichtige Rolle bei Differenzialgleichungen
### Vom Differenzieren zum Integrieren
- Durch den **Hauptsatz** können wir die meisten Differenzierungsregeln rückwärts auf das Integrieren übertragen:
	- Das Gegenstück zur **Summenregel** haben wir bereits gesehen:
	  Integrale von Summen und konstanten Vielfachen zerfallen in die Summe der Integrale.
	- **Beispiel 23.10** Das Gegenstück zur **Potenzregel** ist $(n in NN)$: $$ integral_a^b x^n d x = [1/(n+1) x^(n+1)]_a^b $$
	- Es fehlen also noch:
		- Das Gegenstück zur **Produktregel**
		- Das Gegenstück zur **Kettenregel**
	- **Anmerkung**: Zur Quotientenregel gibt es kein Gegenstück
### Partielle Integration
- Ist das Gegenstück zur **Produktregel** beim Differenzieren, also wernden wir partielle Integration an, wenn ein Produkt von Funktionen im Integral steht
- Es seien $f,g : [a,b] -> RR$ **stetig differenzierbare Funktionen**. Dann gilt $$ integral_a^b f^prime (x) d x = [f(x) g(x)]_a^b - integral_a^b f(x) g^prime (x) d x $$
- **Beispiel**: $integral_0^2 e^x dot x d x$
	- Wie wählen $f^prime (x) = e^x$ und $g(x) = x$. Wir erhalten $f(x) = e^x$ und $g(x) = 1$ und somit $$ integral_0^2 e^x dot x d x = [e^x dot x]_0^2 - integral_0^2 e^x dot 1 d x = (e^2 dot 2 - e^0 dot 0) - (e^2 - e^0) = e^2 $$
### Tipps und Tricks partielle Integration
- **Ziel**: Das neue Integral $integral_a^b f^prime (x) g(x) d x$ soll **einfacher zu lösen** sein
- **Strategie**:
	- Wähle $g(x)$ so, dass die Ableitung $g^prime (x)$ möglichst einfach wird, im besten Fall **konstant**
	- Wähle $f^prime (x)$ als die leicht zu integrierender Funktion
- Beispiele für Funktionen, die man für $f^prime (x)$ wählt
	- Inverse trigonometrische Funktionen
	- Trigonometrische Funktionen
	- Exponentialfunktion
- Für $g(x)$ wählt man meist Polynome $(x^n)$
	- Ausnahme: der Integrand ist $x^n dot ln(x)$. Hier bietet sich $g(x) = ln(x)$ an
- Manchmal ist es notwendig mehrfach partiell zu integrieren (siehe Spezialfall)
### Partielle Integration - Spezialfall
- Was tun, wenn wir ein Produkt aus komplizierten z.B. $e^x sin(x)$ betrachten?
- Wir orientieren und an **Beispiel 23.18 (4)** und **G11.1 (c)**
	- Wir integrieren mehrfach partiell
	- Das kann dazu führen, dass das entstehende Intervall wieder dem ursprünglichen gleicht. Wir erkennen also einen **Zyknlus**
	- Wenn so ein Zyklus vorliegt, kann man nach dem ursprünglichen Integral auflösen und erhält sein Ergebnis
### Partielle Integration - Spezialfall #cheatsheet 
- **Vorgehensweise**:
	- Gebe dem Intervall einen Namen, z.B. $I$
	- Integriere partiell
	- Wiederhole die Partielle Integration auf das Restintegral so oft, bis sich $I$ wieder zeigt (**Zyklus**).
	- Löse nach $I$ auf und erhalte $k dot I = dots.c$ wobei $k$ die Anzahl der partiellen Integrationen ist
	- Teile durch $k$ und erhalte Somit das Integral für $I$
### Problem
- Was machen wir, wenn wir folgendes Integral betrachten $$ integral_0^2 e^t^2 dot 4t d t $$
- Partielle Integration scheitert, da $e^t^2$ keine elementare Stammfunktion hat
- Wir brauchen weitere Tools
### Integration durch Substitution
- Ist das Gegenstück zur **Kettenregel** beim Differenziere, also wenden wir Integration durch Substitution an, wenn der Integrand eine Verkettung $f(g(x))$ und gleichzeitig (bis auf eine Konstante) $g^prime (x)$ beinhaltet
- Es seien $[a,b] subset.eq RR " und " [c,d] subset.eq RR$ kompakte Intervall, sowie $f in C([a,b])$ mit $g([c,d]) subset.eq [a,b]$. Dann ist $$ integral_c^d f(g(t)) dot g^prime (t) d t = integral_g(c)^g(d) f(x) d x $$