---
Chapter: "13"
Topic: Mengen
Part: A
---
Sei $(V, ||dot||)$ ein normierter $RR$-VR
# Definition 13.35
Eine Menge $M subset.eq V$ heißt beschränkt, falls es ein $C >= 0$ gibt, so dass $||x|| <= C$ für alle $x in M$ gilt.
# Definition 13.36
## 1.
Es seien $x_0 in V$ und $r in (0, infinity)$. Dann heißt die Menge
$$B_r (x_0) := {x in V : ||x-x_0|| < r}$$
(offene) Kugel um $x_0$ mit Radius $r$.
## 2.
Eine Menge $M subset.eq V$ heißt offen, falls es für jeden Punkt $x_0 in M$ einen Radius $r > 0$ gibt, so dass $B_r (x_0) subset.eq M$ gilt.
## 3. 
Eine Menge $M subset.eq V$ heißt abgeschlossen, wenn die Menge $M^C = V without M$ offen ist.
## 4.
Es sei $M subset.eq V$. Ein Punkt $z in V$ heißt innerer Punkt von $M$, falls es ein $r > 0$ gibt, so dass $B_r (z) subset.eq M$ ist. Man nennt
$$M^circle := {z in V : z " innerer Punkt von M"}$$
das innerer von M.
## 5.
Es sei $M subset.eq V$ eine Teilmenge. ein Punkt $z in V$ heißt Adhärenzpunkt von $M$, wenn eine Folge $(x_n )_n$ mit $x_n in M$ für alle $n$ existiert, so dass
$$lim_(n -> infinity) x_n = z$$
gilt. Man nennt
$$overline(M) := {z in V ; z " ist Adhärenzpunkl von M"}$$
den Abschluss von M.
## 6.
Es sei $M subset.eq V$ eine Teilmenge. Dann nennt man
$$diff M := overline(M) without M^circle$$
den Rand von M.
# Bemerkung 13.37
Achtung: Mengen sind keine Türen! Die meisten Mengen sind weder offen noch abgeschlossen, betrachten Sie z.B. ein halboffenes Intervall in $RR$. Hüten Sie sich also vor dem Fehlschluss: Ich habe festgestellt, dass meine Menge nicht offen ist, also ist sie abgeschlossen$dots$
# Bemerkung 13.38
Sei $M subset.eq V$ eine Teilmenge. Dann gilt:
$$M^circle subset.eq M subset.eq overline(M)$$
# Beispiel 13.39
In $RR$ sind für $a, b in RR$ mit $a <= b$ die Intervalle $(a,b)$ offen und beschränkt. Die Intervalle $[a,b]$ sind abgeschossen und beschränkt.
# Beispiel 13.40
Sei $r > 0$ eine reelle Zahl und $x_0 in V$. Sei $B_r (x_0) = {x in V : ||x-x_0 || v < r}$. Dann ist $B_r (x_0)$ offen, und man hat
$$
overline(B_r (x_0)) = {x in V : ||x - x_0 || <= r} \
diff  B_r (x_0) = {x in V : || x -x _0 || = r}
$$
_Beweis._ Um einzusehen, dass $B_r (x_0 )$ offen ist, wählen wir ein $x in B_r (x_0)$. Wir müssen nun zeigen, dass es einen Radius $rho > 0$ gibt, so dass $B_rho (x) subset.eq B_r (x_0)$ gilt. Da $x in B_r (x_0)$ ist, gilt $|| x - x_0 || < r$. Die Zahl
$$
rho = (r - ||x - x_0 ||)/(2)
$$
ist also strikt größer als Null.
Sei nun $y in B_rho (x)$. Dann gilt nach der Driecksgleichung:
$$
||y -x_0 || = ||y - x +x - x_0 || <= || y - x || + ||x -x_0 ||
$$
Der erste Summand ist kleiner als $rho = (r - || x - x_0 ||)/2$, denn $y$ ist ja in der Kugel um $x$ mit Radius $rho$. Also erhalten wir 
$$
|| y - x_0 || < r/2 - (x - x_0 )/(2) + ||x -x_0 || = r/2 + (||x - x_0 ||)/(2)
$$
Weiter war $||y - x_0 || < r$, also finden wir
$$
||y - x_0 || < r/2 +r/2 = r
$$
Damit haben wir $B_rho (x) subset.eq B_r (x_0 )$ gezeigt und sind fertig.
Um die Beschreibung von $B_r (x_0 )$ einzusehen, ersetzen wir jeden Vektor $x$ durch $x -x_0$.
Dann können wir $x_0 = 0$ annehmen, was Schreibarbeit spart. Wir zeigen wir erst einmal, dass die rechte Seite in der linken Seite enthalten ist. Sei also $c in V$ mir $|| x - x_0 || = ||x|| <= r$. Für $n >= 1$ setze $x_n := (1 - 1/n )x$. Da $lim_(n -> infinity) (1+ 1/n) = 1$ ist gilt $lim_(n -> infinity) x_n = 1 dot x = x$. Außerdem $||x_n || =  | 1- 1/n| ||x|| < r$, d.h., $x_n in B_r (0)$.
Also haben wir eine Folge $(x_n )_n$ gefunden mit $x_n in B_r (0)$ so dass $x = lim_(n -> infinity) x_n$, also $x in overline(B_r (0))$.
Wie zeigen nun, dass auch die umgekehrte Inklusion gilt. Sei $x in overline(B_r (0))$. Dann existiert also eine Folge $(x_n )$ mit $x_n in B_r (0)$, so dass $lim_(n -> infinity) x_n = x$. Dann gilt auch $lim_(n -> infinity) ||x_n || = ||x||$. Da $||x_n || <= r$, gilt also auch $||x|| <= r$ nach der Monotonie des Grenzwertes (Satz 13.8).