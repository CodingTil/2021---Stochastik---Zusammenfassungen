# Gliederung
 - [Grundlagen der Wahrscheinlichkeitsrechnung](#grundlagen-der-wahrscheinlichkeitsrechnung)
 - [Diskrete Wahrscheinlichkeitsverteilung](#diskrete-wahrscheinlichkeitsverteilung)
 - [Wahrscheinlichkeitsmaße mit Riemann-Dichten](#wahrscheinlichkeitsmaße-mit-riemann-dichten)
 - [Eigenschaften von Wahrscheinlichkeitsmaßen](#eigenschaften-von-wahrscheinlichkeitsmaßen)
 - [Bedingte Wahrscheinlichkeiten](#bedingte-wahrscheinlichkeiten)
 - [Stochastische Unabhängigkeiten von Ereignissen](#stochastische-unabhängigkeiten-von-ereignissen)

---------------

# Grundlagen der Wahrscheinlichkeitsrechnung
 - Modelle für reale, zufallsabhängige Vorgänge

## Grundraum, Grundmenge
Die Menge alle möglichen Ergebnisse eines Zufallsvorgangs heißt **Grundraum** (bzw. **Grundmenge**):
$$\Omega = \{\omega \mid \omega \text{ ist mögliches Ergebnis}\}$$
 - $\omega \in \Omega$: **Ergebnis**
 - Menge von Ergenissen $A \subseteq \Omega$: **Ereignis**
 - $A$ Ereignis mit $\vert A \vert = 1$: **Elementarereignis**

Seien $A,B$ Ereignisse in einem Grundraum $\Omega$:
 - $A \cap B$: **Schnittereignis** von $A$ und $B$
 - $A \cup B$: **Vereinigungsereignis** von $A$ und $B$
 - $A \subseteq B$: $A$ **Teilereignis** von $B$
 - $A^{C} \coloneqq \Omega \setminus A$: **Komplementärereignis** von $A$
 - $B \setminus A$: **Differenzereignis** von $B$ und $A$ (**Komplement** von $A$ in $B$)

---------------

## Wahrscheinlichkeitsverteilung
Seien $\Omega = \{\omega_{1}, \omega_{2}, \dots\}$ ein _endlicher_ oder _abzählbar unendlicher_ [Grundraum](#grundraum-grundmenge) und $\mathfrak{A} = \mathcal{P}(\Omega)$ die Potenzmenge von $\Omega$. Ferner sei $\operatorname{f}: \Omega \rightarrow [0,1]$ eine Abbildung mit $\sum\limits_{\omega \in \Omega} \operatorname{f}(\omega) = 1$. Die durch
$$\operatorname{P}(A) \coloneqq \sum_{\omega \in A} \operatorname{f}(\omega), A \in \mathfrak{A}$$
definierte Abbildung $\operatorname{P}: \mathfrak{A} \rightarrow [0,1], A \mapsto \operatorname{P}(A)$, die jedem Ereignis $A$ eine Wahrscheinlichkeit $\operatorname{P}(A)$ zuordnet, heißt **diskretes Wahscheinlichekitsmaß** oder **Wahrscheinlichkeitsverteilung** auf $\mathfrak{A}$ (oder über $\Omega$).

 - Abbildung $\operatorname{p}$: **Zähldichte**
 - Für $\omega \in \Omega$ heißt $\operatorname{P}(\{\omega\}) = \operatorname{f}(\omega)$ **Elementarwahrscheinlichkeit** des [Elementareriegnisses](#grundraum-grundmenge) $\{\omega\}$; kurz: $\operatorname{P}(\omega) = \operatorname{P}(\{\omega\})$

### Kolmogorov-Axiome
Für die [diskrete Wahrscheinlichkeitsverteilung](#wahrscheinlichkeitsverteilung) $\operatorname{P}$ gilt:
 - $0 \leq \operatorname{P}(A) \leq 1$ für jedes $A \in \mathfrak{A}$
 - $\operatorname{P}(\Omega) = 1$
 - $\operatorname{P}$ ist [$\sigma$-additiv](https://en.wikipedia.org/wiki/Sigma_additivity)

### Diskreter Wahrscheinlichkeitsraum
Seien $\Omega = \{\omega_{1}, \omega_{2}, \dots\}$ ein _endlicher_ oder _abzählbar unendlicher_ [Grundraum](#grundraum-grundmenge), $\mathfrak{A} = \mathcal{P}(\Omega)$ und $\operatorname{P}$ [diskretes Wahrscheinlichkeitsmaß](#wahrscheinlichkeitsverteilung) auf $\mathfrak{A}$.
 - $(\Omega, \operatorname{P})$ heißt **diskreter Wahrscheinlichkeitsraum**
 - Ist $\Omega$ endlich, d.h. $\Omega = \{\omega_{1}, \dots, \omega_{n}\}$, so heißt $(\Omega, \operatorname{P})$ **endlich diskreter Wahrscheinlichkeitsraum**

#### Träger
Sei $(\Omega, \operatorname{P})$ ein [diskreter Wahrscheinlichkeitsraum](#diskreter-wahrscheinlichkeitsraum). Die Menge
$$\operatorname{T}(=\operatorname{supp}(\operatorname{P})) \coloneqq \{\omega \in \Omega \mid \operatorname{P}(\omega) > 0\}$$
heißt **Träger** von $\operatorname{P}$.

### Laplace-Raum
Ist $\Omega = \{\omega_{1}, \dots, \omega_{n}\}, n \in \mathbb{N}$, dann wird durch
$$\operatorname{P}(A) = \frac{\vert A \vert}{\vert \Omega \vert} = \frac{\vert A \vert}{n}, A \subseteq \Omega$$
ein Wahrscheinlichkeitsmaß über $\mathcal{P}(\Omega)$ definiert.
 - $\operatorname{P}$ heißt **Laplace-Verteilung** oder **diskrete Gleichverteilung** über $\Omega$
 - $(\Omega, \operatorname{P})$ heißt **Laplace-Raum** über $\Omega$

---------------

## Grundmodelle der Kombinatorik
### Urnenmodelle
 - Urne enthalte $n$ nummerierte Kugeln $\mathcal{U}_{n} = \{1, \dots, n\}$
 - Ziehen einer Kugel aus der Urne entspricht der (zufälligen) Auswahl eines Objektes aus der Gesamtheit
 - **Resultat einer Ziehung von $k$ Kugeln**
$$\text{(geordnetes) Tupel } (\omega_{1}, \dots, \omega_{k})$$
 - Jede Kugel wird mit _derselben_ Wahrscheinlichkeit gezogen &rarr; [Laplace-Modell](#laplace-raum)

| Ziehen von $k$ Kugeln aus $n$ Kugeln |                                            mit Zurücklegen                                             |                                           ohne Zurücklegen                                            |
| :----------------------------------- | :----------------------------------------------------------------------------------------------------: | :---------------------------------------------------------------------------------------------------: |
| **mit Reihenfolge**                  |        $(n,k)$-Permitation mit Wiederholung $$\vert \Omega_{\operatorname{PmW}} \vert = n^{k}$$        | $(n,k)$-Permitation ohne Wiederholung $$\vert \Omega_{\operatorname{PoW}} \vert = \frac{n!}{(n-k)!}$$ |
| **ohne Reihenfolge**                 | $(n,k)$-Kombination mit Wiederholung $$\vert \Omega_{\operatorname{KmW}} \vert = {{n+k-1} \choose k}$$ |   $(n,k)$-Kombination ohne Wiederholung $$\vert \Omega_{\operatorname{KoW}} \vert = {n \choose k}$$   |

---------------

<br>

# Diskrete Wahrscheinlichkeitsverteilung
 - [Träger](#träger) (Grundmenge) $T=\{x_1, x_2, \dots \}$
 - Ordner $x_k \in T$ über eine [Zähldichte](#wahrscheinlichkeitsverteilung) $\operatorname{f}$ eine
   - Wahrscheinlichkeit $p_k = \operatorname{f}(x_k) = \operatorname{P}(\{x_k\}) \in (0,1], k=1,2,\dots$ zu, wobei
   - $\sum\limits_k p_k = \sum\limits_k \operatorname{f}(x_k) = 1$
   - &rarr; Festlegung einer diskreten Verteilung
 - Für $x \in \Omega \setminus T$ gilt stets $\operatorname{f}(x)=0$ ([Zähldichte](#wahrscheinlichkeitsverteilung))

## Ausgewählte Verteilungen
$\operatorname{f}$ bezeichne im Folgenden stets die [Zähldichte](#wahrscheinlichkeitsverteilung) der diskreten Wahrscheinlichkeitsverteilung.

### Einpunktverteilung
**Einpuntverteilung** $\delta_x$ ein einem gegebenen Punkt $x \in \mathbb{R}$:
$$\operatorname{f}(x) = 1$$
d.h. die **Einpunktverteilung** (Dirac-Verteilung, Punktmaß) hat den [Träger](#träger) $T=\{x\}$.

### Diskrete Gleichverteilung
**Diskrete Gleichverteilung** auf Punkten $x_1 < \dots < x_n$:
$$\operatorname{f}(x_k)=\frac{1}{n}, k\in\{1,...,n\}$$

### Hypergeometrische Verteilung
**Hypergeometrische Verteilung** $\operatorname{hyp}(n,r,s)$:
$$\operatorname{f}(k) = p_k = \frac{{r \choose k}{s \choose {n-k}}}{{r+s} \choose n}, n-s \leq k \leq \min(r,n), k \in \mathbb{N}_0$$
für $n,r,s \in \mathbb{N}$ mit $s \leq n \leq r+s$.

> [Urnenmodell](#urnenmodelle):
> $p_k$ ist Wahrscheinlichkeit, beim $n$-maligen _Ziehen **ohne** Zurücklegen_ aus einer Urne mit insgesamt $r$ roten und $s$ schwarzen Kugeln, genau $k$ rote und $n-k$ schwarze Kugeln zu erhalten.

> Gut-Schlecht-Prüfung mittels Warenstichprobe:
> - Stichprobe vom Umfang $n$ (_**ohne** Zurücklegen_)
> - $r$ defekte und $s$ intakte Teile bei einer Lieferung von $r+s$ Teilen
> - $p_k$: Wahrscheinlichkeit für genau $k$ defekte Teile in der Stichprobe

### Binomialverteilung
**Binomialverteilung** $\operatorname{bin}(n,p)$ mit Parametern $n \in \mathbb{N}$ und $p \in [0,1]$.
$$\operatorname{f}(k) = p_k = {n \choose k} p^k (1-p)^{n-k}, 0 \leq k \leq n, k \in \mathbb{N}_0$$

> [Urnenmodell](#urnenmodelle)
> $p_k$ ist die Wahrscheinlichkeit, beim $n$-maligen _Ziehen **mit** Zurücklegen_ aus einer Urne mit insgesamt $r$ roten und $s$ schwarzen Kugelen, genau $k$ rote und $n-k$ scharze Kugeln zu erhalten.

> Gut-Schlecht-Prüfung mittels Warenstichprobe:
> - Stichprobe vom Umfang $n$ (_**mit** Zurücklegen_)
> - $r$ defekte und $s$ intakte Teile bei einer Lieferung von $r+s$ Teilen
> - $p_k$: Wahrscheinlichkeit für genau $k$ defekte Teile in der Stichprobe
> - $p = \frac{r}{r+s}$ heißt **Schlechtanteil**

> ##### Modell allgemeiner Münzwurf
> $\operatorname{bin}(1,p), p \in [0,1]$ **Trefferwahrscheinlichkeit**
> [Wahrscienlichkeitsverteilung](#wahrscheinlichkeitsverteilung) $\operatorname{P}$ mit [Zähldichte](#wahrscheinlichkeitsverteilung)
> $$\operatorname{f}(0) = 1-p, \operatorname{f}(1) = p$$

### Poisson-Verteilung
**Poisson-Verteilung** $\operatorname{po}(\lambda)$:
$$\operatorname{f}(k) = p_k = \frac{\lambda^k}{k!} \cdot e^{-\lambda}, k \in \mathbb{N}_0$$
für einen Parameter $\lambda > 0$.
&rarr; Modellierung von Anzahlen seltener Ereignisse

### Geometrische Verleiung
**Geometrische Verteilung** $\operatorname{geo}(p)$:
$$\operatorname{f}(k) = p_k = p \cdot (1-p)^k, k \in \mathbb{N}_0$$
für einen Parameter $p \in (0,1)$.

> Modellierung der Wartezeit bis zum ersten Erfolg:
> - wird erzeugt aus Modell "unendlicher Münzwurf" mit überabzählbarem Grundraum $$\Omega_{\mathcal{W}_\infty} = \{(\omega_j)_{j \in \mathbb{N}} \mid \omega_i \in \{0,1\}, i \in \mathbb{N}\}$$
> - $p_k \hat{=}$ Wahrscheinlichkeit, im $(k+1)$-ten Wurf erstmals eine $6$ (Treffer) zu würfeln.

### Polynomialverteilung
**Polynomialverteilung** (oder **Multinomialverteilung**) $\operatorname{pol}(n, p_1, \dots, p_m)$:
$$f(k_1, \dots, k_m) = {n \choose {k_1, \dots, k_m}} \prod_{j=1}^m p_j^{k_j}$$ $$,(k_1, \dots, k_m) \in \{(i_1, \dots, i_m) \in \mathbb{N}_0^m \mid \sum_{j=1}^m i_j = n\}$$
für ein $n \in \mathbb{N}$ und die Parameter $p_1, \dots, p_m \in [0,1]$ mit $\sum\limits_{j=1}^m = 1$.
${n \choose {k_1, \dots, k_m}} \coloneqq \frac{n!}{k_1! \cdot \dots \cdot k_m!}$ heißt **Polynomialkoeffizient**.

> Für $m=2, p_1=p, p_2=1-p, (k_1 = k, k_2 = n-k)$ ergibt sich die [Binomialverteilung](#binomialverteilung)

> [Urnenmodell](#urnenmodelle)
> Urne mit Kugeln in $m$ verschiedenen Farben
>  - Ziehen von $n$ Kugeln _**mit** Zurücklegen_ (jeweils $k_j$ in Farbe $j$, $j = 1, \dots, m$)
> - $p_j$: Anteil von Kugeln mit Farbe $j$.

---------------

<br>

# Wahrscheinlichkeitsmaße mit Riemann-Dichten
_Idee_: [Wahrscheinlichkeitsverteilungen](#wahrscheinlichkeitsverteilung) werden über Intervalle festgelegt
$$\operatorname{P}([0,\frac{1}{n}]) = \frac{1}{n}, \operatorname{P}([0,t]) = t, \operatorname{P}([s,t]) = t-s$$ $$n \in \mathbb{N}, s,t \in [0,1], s<t$$

## $\sigma$-Algebra
Seien $\Omega \neq \emptyset$ und $\mathfrak{A} \subseteq \operatorname{Pot}(\Omega)$ ein System von Teilmengen von $\Omega$. $\mathfrak{A}$ heißt **$\sigma$-Algebra** von Ereignissen über $\Omega$, falls gilt:
 - $\Omega \in \mathfrak{A}$
 - $A \in \mathfrak{A} \Rightarrow A^C \in \mathfrak{A}$
 - für jede Folge $A_1, A_2, \dots$ von Mengen aus $\mathfrak{A}$ gilt: $\bigcup\limits_{n=1}^\infty A_n \in \mathfrak{A}$

Eine Menga aus $\mathfrak{A}$, die keine echte Vereinigung anderer Ereignisse (Mengen aus $\mathfrak{A}$) ist, heit **Elementarereignis**.

Es folgt:
 - $\emptyset \in \mathfrak{A}$
 - für jede Folge $A_1, A_2, \dots$ von Mengen aus $\mathfrak{A}$ gilt: $\bigcap\limits_{n=1}^\infty A_n \in \mathfrak{A}$
 - Potensmenge $\operatorname{Pot}(\Omega)$ einer nicht-leeren Menge $\Omega$ ist stets eine $\sigma$-Algebra.

---------------

## Wahrscheinlichkeitsraum
Sei $\mathfrak{A}$ über $\Omega \neq \emptyset$. Eine Abbildung $\operatorname{P}: \mathfrak{A} \rightarrow [0,1]$ mit
 - $\operatorname{P}(A) \geq 0 \forall A \in \mathfrak{A}$
 - $\operatorname{P}(\Omega)$ = 1
 - $\operatorname{P}(\bigcup\limits_{n=1}^\infty A_n) = \sum\limits_{n=1}^\infty \operatorname{P}(A_n)$ für jede paarweise disjunkte Mengen aus $\mathfrak{A}$ ([$\sigma$-additiv](https://en.wikipedia.org/wiki/Sigma_additivity))

heißt **Wahrscheinlichkeitsverteilung** oder **Wahrscheinlichkeitsmaß** auf $\Omega$. $(\Omega, \mathfrak{A}, \operatorname{P})$ hei´t **Wahrscheinlichkeitsraum**, $(\Omega, \mathfrak{A})$ heißt messbarer Raum oder Messraum.

---------------

## Borelsche $\sigma$-Algebra
Wird ein Intervall $[a,b]$ oder $(a,b)$ (auch $[0,\infty), \mathbb{R}$) als Grundraum $\Omega \subseteq \mathbb{R}$ in einem Modell angesetzt, so wählt man die kleinstmögliche [$\sigma$-Algebra](#sigma-algebra), die **alle Teilmengen $(c,d] \subseteq [a,b]$ enthält**.
Diese $\sigma$-Algebra heißt **Borelsche $\sigma$-Algebra** $\mathcal{B}^1$ über $[a,b]$ bzw. $(a,b)$, sie ist eine **echte Teilmenge der Potenzmenge** von $[a,b]$ bzw. $(a,b)$.
Analog geht man in höheren Dimensionen vor.

**Grundraum** $\tilde{\Omega} \subseteq \mathbb{R}^n$:
&rarr; geeignete Borelsche $\sigma$-Algebra $\tilde{\mathcal{B}}^n = \{B \cap \tilde{\Omega} \mid B \in \mathcal{B}^n\}$ (Spur-$\sigma$-Algebra).

---------------

## Riemann-Dichte
Eine integrierbare Funktion $\operatorname{f}: \mathbb{R} \rightarrow \mathbb{R}$ mit
$$f(x) \geq 0, \int_{-\infty}^\infty \operatorname{f}(y) dy = 1$$
heißt **Riemann-Dichte** oder Riemann-Dichtefunktion.

Die Festlegung von Wahrscheinlichkeiten
$$\operatorname{F}(x) = \operatorname{P}((-\infty, x]) = \int_{-\infty}^x f(y) dy$$
definiert eindeutig ein Wahrscheilichkeitsmaß auf $\mathbb{R}$.
Die Funktion $\operatorname{F}: \mathbb{R} \rightarrow [0,1]$ heißt **Verteilungsfunktion**.

Wahrscheinlichkeit für ein Intervall $(a,b] \subseteq \Omega$:
$$\operatorname{P}((a,b]) = \int_a^b f(x) dx = \operatorname{F}(b) - \operatorname{F}(a)$$

$\operatorname{P}(\{x\}) = 0, \forall x \in \Omega$
&rarr; $\operatorname{P}((a,b)) = \operatorname{P}([a,b]) = \operatorname{P}((a,b]) = \operatorname{P}([a,b))$

### Rechteckverteilung
**Rechteckverteilung** (oder stetige Gleichverteilung) $\operatorname{R}(a,b)$:
$$\operatorname{f}(x) = \frac{1}{b-a} \mathcal{1}_{[a,b]}(x) = \begin{cases} \frac{1}{b-a}, & x \in [a,b] \\ 0, & x \not\in [a,b] \end{cases}$$

[Verteilungsfunktion](#riemann-dichte): $\operatorname{F}(x) = \begin{cases} 0, & x < a \\ \frac{x-a}{b-a}, & x \in [a,b] \\ 1, & x > b\end{cases}$

Wahrscheinlichkeit eines in $[a,b]$ enthaltenen Intervalls hängt nur von der Länge des Intervalls ab, nicht aber von dessen Lage!

### Exponentialverteilung
**Exponentialverteilung** $\operatorname{Exp}(\lambda)$ mit Parameter $\lambda > 0$:
$$\operatorname{f}(x) = \lambda e^{-\lambda x} \mathcal{1}_{(0,\infty)}(x) = \begin{cases} \lambda e^{-\lambda x}, & x > 0 \\ 0, & x \leq 0 \end{cases}$$

[Verteilungsfunktion](#riemann-dichte): $\operatorname{F}(x) = \begin{cases} 1 - e^{-\lambda x}, & x > 0 \\ 0, & x \leq 0 \end{cases}$

### Weibull-Verteilung
**Weibull-Verteilung** $\operatorname{Wei}(\alpha, \beta)$ mit Parametern $a,b > 0$:
$$\operatorname{f}(x) = \begin{cases} \alpha \beta x^{\beta - 1} e^{- \alpha x^\beta}, & x > 0 \\ 0, & x \leq 0 \end{cases}$$

[Verteilungsfunktion](#riemann-dichte): $\operatorname{F}(x) = \begin{cases} 1 - e^{-\alpha x^\beta}, & x > 0 \\ 0, & x \leq 0 \end{cases}$
$\beta = 1$ &rarr; [Exponentialverteilung](#exponentialverteilung)

### Gammaverteilung
**Gammavertelung** $\Gamma(\alpha, \beta)$ mit Parametern $\alpha,\beta > 0$:
$$\operatorname{f}(x) = \begin{cases} \frac{\alpha^\beta}{\Gamma(\beta)} x^{\beta - 1} e^{-\alpha x}, & x > 0 \\ 0, & x \leq 0 \end{cases}$$
$\Gamma(\cdot)$ ist die durch $\Gamma(z) = \int_0^\infty t^{z-1} e^{-t} dt, z > 0$ definierte Gammafunktion.

Geschlossene Darstellung der Verteilungsfunktion nur für $\beta \in \mathbb{N}$ (**Erlang-Verteilung** $\operatorname{Erl}(\beta)$):
$$\operatorname{F}(x) = \begin{cases} 1 - e^{-\alpha x} (\sum\limits_{j=0}^{\beta - 1} \frac{(ax)^j}{j!}), & x > 0 \\ 0, & x \leq 0 \end{cases}$$

$\alpha = \lambda, \beta = 1$ &rarr; [Exponentialverteilung](#exponentialverteilung)

### $\operatorname{x^2}$-Verteilung
**$\operatorname{x^2}$-Verteilung** $\operatorname{x^2}(n)$ mit $n \in \mathbb{N}$ Freiheitsgeraden:
$$\operatorname{f}(x) = \begin{cases} \frac{1}{2^{\frac{n}{2}}\Gamma(\frac{n}{2})} x^{\frac{n}{2} - 1} e^{-\frac{x}{2}}, & x > 0 \\ 0, & x \leq 0 \end{cases}$$

Speielle Gammaverteilung: $\alpha = \frac{1}{2}, \beta = \frac{n}{2}, n \in \mathbb{N}, \operatorname{x^2}(n) = \Gamma(\frac{1}{2}, \frac{n}{2})$
&rarr; Schließende Statistik

### Betaverteilung
**Betaverteilung** $\operatorname{beta}(\alpha, \beta)$ mit Parametern $\alpha, \beta > 0$:
$$\operatorname{f}(x) = \begin{cases} \frac{\Gamma(\alpha + \beta)}{\Gamma(\alpha) \Gamma(\beta)} x^{\alpha - 1} (1 - x)^{\beta - 1}, & x \in (0,1) \\ 0, & x \not\in (0,1) \end{cases}$$

Die speziellen Betaverteilungen $\operatorname{beta}(\alpha, 1)$ heißen auch **Potenzverteilungen** und besitzen die [Verteilungsfunktion](#riemann-dichte):
$$\operatorname{F}(x) = \begin{cases} 0, & x < 0 \\ x^\alpha, & 0 \leq x < 1 \\ 1, & x \geq 1 \end{cases}$$
$\alpha = \beta = 1$ &rarr; [Rechteckverteilung](#rechteckverteilung) $\operatorname{R}(0,1)$

### Pareto-Verteilung
**Pareto-Verteilung** $\operatorname{Par}(\alpha)$ mit Parameter $\alpha > 0$:
$$\operatorname{f}(x) = \begin{cases} \frac{\alpha}{x^{\alpha + 1}}, & x \geq 1 \\ 0, & x < 1 \end{cases}$$

[Verteilungsfunktion](#riemann-dichte): $\operatorname{F}(x) = \begin{cases} 1 - x^{-\alpha}, & x \geq 1 \\ 0, & x < 1 \end{cases}$

### Normalverteilung
**Normalverteilung** $\operatorname{N}(\mu, \sigma^2)$ mit Parametern $\mu \in \mathbb{R}, \sigma > 0$:
$$\operatorname{\varphi}_{\mu, \sigma^2}(x) = \frac{1}{\sqrt{2 \pi} \sigma} \exp \{- \frac{(x - \mu)^2}{2\sigma^2}\}$$

$\operatorname{N}(0,1)$ &rarr; **Standardnormalverteilung**
[Verteilungsfunktion](#riemann-dichte): $\operatorname{\Phi}_{\mu, \sigma^2}(x) = \operatorname{\Phi}(\frac{x - \mu}{\sigma})$
$\operatorname{\Phi}(x) = 1 - \operatorname{\Phi}(-x)$

### $t$-Verteilung
**$t$-Verteilung** $t(n)$ mit $n \in \mathbb{N}$ Freiheitsgraden:
$$\operatorname{f}(x) = \frac{\Gamma(\frac{n+1}{2})}{\sqrt{n \pi} \Gamma(\frac{n}{2})} (1 + \frac{x^2}{n})^{-\frac{n+1}{2}}$$

### $\mathcal{F}$-Verteilung
**$\mathcal{F}$-Verteilung** $\mathcal{F}(n,m)$ mit $n \in \mathbb{N}$ und $m \in \mathbb{N}$ Freiheitsgraden:
$$\operatorname{f}(x) = \begin{cases} \frac{\Gamma(\frac{n+m}{2})}{\Gamma(\frac{n}{2}) \Gamma(\frac{m}{2})} (\frac{n}{m})^{\frac{n}{2}} \frac{x^{\frac{n}{2} - 1}}{(1 + \frac{n}{m} x)^{\frac{n+m}{2}}}, & x > 0 \\ 0, x \leq 0 \end{cases}$$

---------------

## Träger
Sei $\operatorname{f}$ eine [Riemann-Dichtefunktion](#riemann-dichte)
Die Menge $\operatorname{supp}(\operatorname{P}) = \operatorname{supp}(\operatorname{f}) = \operatorname{supp}(\operatorname{F}) \coloneqq \{x \in \mathbb{R} \mid \operatorname{f}(x) > 0\}$ heißt **Träger** der zugehörigen [Wahrscheinlichkeitsverteilung](#wahrscheinlichkeitsverteilung) $\operatorname{P}$ (bzw. von $\operatorname{f}$ oder $\operatorname{F}$).

---------------

## Lage-/Skalentransformation
Sei $\operatorname{F}$ eine Verteilungsfunktion.
Mittels $\tilde{\operatorname{F}}(x) \coloneqq \operatorname{F}(\frac{x - a}{b}), b \geq 0, a \in \mathbb{R}$ wird eine Verteilungsfamilie definiert.

Sei $(\tilde{\alpha}, \tilde{\omega})$ das Trägerintervall von $\operatorname{F}$.
&rarr; $(a + b \tilde{\alpha}, a + b \tilde{\omega})$ Trägerintervall von $\tilde{\operatorname{F}}$

Obige Transformation führt zu einer
> [Betaverteilung](#betaverteilung) mit Trägerintervall $(a,a+b)$:
> $$\tilde{\operatorname{f}}(x) = \frac{1}{b} \operatorname{f}(\frac{x-a}{b})$$

> [Exponentialverteilung](#exponentialverteilung) mit Träger $(\mu, \infty)$:
> $$\tilde{\operatorname{f}} = \frac{1}{\vartheta} \operatorname{f}(\frac{x - \mu}{\vartheta}) = \begin{cases} \frac{1}{\vartheta} e^{- \frac{x - \mu}{\vartheta}}, & x > \mu \\ 0, & x \leq \mu \end{cases}$$
> &rarr; zweiparametrige Exponentialfunktion $\operatorname{Exp}(\mu, \frac{1}{\vartheta})$ mit Lageparameter $\mu$ und Skalenparameter $\vartheta$.

---------------

<br>

# Eigenschaften von Wahrscheinlichkeitsmaßen
Sei $(\Omega, \mathfrak{A}, \operatorname{P})$ ein [Wahrscheinlichkeitsraum](#wahrscheinlichkeitsraum). Dann gelten für $A,B \in \mathfrak{A}$:
 - $\operatorname{P}(A \cup B) = \operatorname{P}(A) + \operatorname{P}(B)$, falls $A \cap B = \emptyset$
 - $\operatorname{P}(B \setminus A) = \operatorname{P}(B) - \operatorname{P}(A)$, falls $A \subseteq B$
 - $\operatorname{P}(A^C) = 1 - \operatorname{P}(A)$
 - $A \subseteq B \Rightarrow \operatorname{P}(A) \leq \operatorname{P}(B)$
 - $\operatorname{P}(A \cup B) = \operatorname{P}(A) + \operatorname{P}(B) - \operatorname{P}(A \cap B)$

Für $A_1, A_2, \dots \in \mathfrak{A}$ gilt:
 - $\operatorname{P}(\bigcup\limits_{i=1}^{n} A_i) \leq \sum\limits_{i=1}^{n} \operatorname{P}(A_i)$
 - $\operatorname{P}(\bigcup\limits_{i=1}^{\infty} A_i) \leq \sum\limits_{i=1}^{\infty} \operatorname{P}(A_i)$
 - $$\begin{align*} \operatorname{P}(\bigcup\limits_{k=1}^{n} A_k) = \sum\limits_{k=1}^{n} \operatorname{P}(A_k) &- \sum\limits_{1 \leq i_1 < i_2 \leq n} \operatorname{P}(A_{i_1} \cap A_{i_2}) \\ &+ \sum\limits_{1 \leq i_1 < i_2 < i_3 \leq n} \operatorname{P}(A_{i_1} \cap A_{i_2} \cap A_{i_3}) \\ & \mp \dots + (-1)^{n+1} \operatorname{P}(\bigcap\limits_{k=1}^{n} A_k) \end{align*}$$

---------------

<br>

# Bedingte Wahrscheinlichkeiten
**Ziel:**
Beschreibung des Einflusses von Vor- oder Zusatzinformationen bzw. dereren Einbezug in ein stochastisches Modell.

Sei $(\Omega, \mathfrak{A}, \operatorname{P})$ ein [Wahrscheinlichkeitsraum](#wahrscheinlichkeitsraum). Für jedes $B \in \mathfrak{A}$ mit $\operatorname{P}(B) > 0$ wird durch
$$\operatorname{P}(A \vert B) = \frac{\operatorname{P}(A \cap B)}{\operatorname{P}(B)}, A \in \mathfrak{A}$$
eine [Wahrscheinlichkeitsverteilung](#wahrscheinlichkeitsverteilung) $\operatorname{P}(\cdot \vert B)$ auf $\mathfrak{A}$ definiert, die sogenannte **bedingte Verteilung** unter der Hypothese $B$. $\operatorname{P}(A \vert B)$ heißt **elementar bedingte Wahrscheinlichkeit von $A$ und $B$**.

 - $(\Omega, \mathfrak{A}, \operatorname{P}(\cdot \vert B))$ ist ein [Wahrscheinlichkeitsraum](#wahrscheinlichkeitsraum)
 - Wegen $\operatorname{P}(A \vert B) = \operatorname{P}(A \cap B \vert B)$ ist auch $(B, \{A \cap B \vert A \in \mathfrak{A}\}, \operatorname{P}(\cdot \vert B))$  ein [Wahrscheinlichkeitsraum](#wahrscheinlichkeitsraum) über dem Grundraum $B \subseteq \Omega$
 - Die Menge $\{A \cap B \vert A \in \mathfrak{A}\}$ ist eine [$\sigma$-Algebra](#sigma-algebra) über $B$.

Seien $A,B \in \mathfrak{A}$ mit $\operatorname{P}(A) > 0 < \operatorname{P}(B)$ sowie $A_1, \dots, A_n \in \mathfrak{A}$ mit $\operatorname{P}(\bigcap\limits_{i=1}^{n} A_i) > 0$. Dann gilt:
 - $\operatorname{P}(A \vert B) = \operatorname{P}(B \vert A) \cdot \frac{\operatorname{P}(A)}{\operatorname{P}(B)}$
 - $\operatorname{P}(\bigcap\limits_{i=1}^{n} A_i) = \operatorname{P}(A_1) \cdot \operatorname{P}(A_2 \vert A_1) \cdot \operatorname{P}(A_3 \vert A_1 \cap A_2) \cdot \dots \cdot \operatorname{P}(A_n \vert \bigcap\limits_{i=1}^{n} A_i)$

### Formel von der totalen Wahrscheinlichkeit
Seien $A \in \mathfrak{A}, (B_n)_n \subseteq \mathfrak{A}$, $B_n$ paarweise disjunkt mit $A \subseteq \bigcup\limits_{n=1}^{\infty} B_n$. Dann gilt:
$$\operatorname{P}(A) = \sum\limits_{n=1}^{\infty} \operatorname{P}(A \cap B_n) = \sum\limits_{n=1}^{\infty} \operatorname{P}(A \vert B_n) \cdot \operatorname{P}(B_n)$$

_Ist $\operatorname{P}(B_k) = 0$, so ist $\operatorname{P}(A \vert B_k)$ nicht defineirt. Man setzt in diesem Fall $\operatorname{P}(B_k) \cdot \operatorname{P}(A \vert B_k) = 0$ mit $\operatorname{P}(A \vert B_k) \in [0,1]$ beliebig._

### Bayessche Formel
Seien $A \in \mathfrak{A}, (B_n)_n \subseteq \mathfrak{A}$, $B_n$ paarweise disjunkt mit $A \subseteq \bigcup\limits_{n=1}^{\infty} B_n$ mit $\operatorname{P}(A) > 0$. Dann gilt für jedes $k \in \mathbb{N}$:
$$\operatorname{P}(B_k \vert A) = \frac{\operatorname{P}(B_k) \cdot \operatorname{P}(A \vert B_k)}{\sum\limits_{n=1}^{\infty} \operatorname{P}(A \vert B_n) \cdot P(B_n)}$$

---------------

<br>

# Stochastische Unabhängigkeiten von Ereignissen
Seien $(\Omega, \mathfrak{A}, \operatorname{P})$ ein [Wahrscheinlichkeitsraum](#wahrscheinlichkeitsraum) und $A,B \in \mathfrak{A}$. Die Ereignisse $A$ und $B$ heißen **stochastisch unabhängig** wenn:
$$\operatorname{P}(A \cap B) = \operatorname{P}(A) \cdot \operatorname{P}(B)$$
 - Sind $A$ und $B$ stochastisch unabhängig, dann auch
   - $A$ und $B^C$
   - $A^C$ und $B$
   - $A^C$ und $B^C$
 - Ist $\operatorname{P}(B) > 0$, so gilt:
	$A$ und $B$ stochastisch unabhängig $\Leftrightarrow$ $\operatorname{P}(A \vert B) = \operatorname{P}(A)$
 - Ist $\operatorname{P}(A) \in \{0,1\}$, so gilt für alle $B \in \mathfrak{A}$, dass
	$A$ und $B$ stochastisch unabhängig sind.

Seien $I$ eine Indexmenge, $A_i \in \mathfrak{A}, i \in I$. Dann heißen die Ereignisse
 - **paarweise stochastisch unabhängig**, falls:
	$\operatorname{P}(A_i \cap A_j) = \operatorname{P}(A_i) \cdot \operatorname{P}(A_j), \forall i,j \in I, i \neq j$
 - **(gemeinsam) stochastisch unabhängig**, falls für _jede_ endliche Auswahl von Indizes $\{i_1, \dots, i_s\} \subseteq I$ gilt:
	$\operatorname{P}(A_{i_1} \cap \dots \cap A_{i_s}) = \operatorname{P}(A_{i_1}) \cdot \dots \cdot \operatorname{P}(A_{i_s})$

**Gemeinsame** stochastische Unabhängigkeit impliziert **paarweise** stochastische Unabhängigkeit.

Sind $A_1, \dots, A_n$ stochastisch unabhängig, dann gilt:
$$\operatorname{P}(\bigcup\limits_{i=1}^{n} A_i) = 1 - \operatorname{P}(\bigcap\limits_{i=1}^{n} A_i^C) = 1 - \prod\limits_{i=1}^{n} (1 - \operatorname{P}(A_i))$$

## Produktraum
Für diskrete [Wahrscheinlichkeitsräume](#wahrscheinlichkeitsraum) $(\Omega_i, \mathfrak{A}_i, \operatorname{P}_i), 1 \leq i \leq n$ heißt $(\Omega, \mathfrak{A}, \operatorname{P})$ mit
$$\Omega \coloneqq ⨉_{i=1}^{n} \Omega_i = \{(\omega_1, \dots, \omega_n) \mid \omega_i \in \Omega_i, 1 \leq i \leq n\}$$
$\mathfrak{A}$ Potenzmenge von $\Omega$ und $\operatorname{P}$ definiert durch die Zähldichte
$$\operatorname{f}(\omega) = \operatorname{P}(\{\omega\}) = \operatorname{P}(\{(\omega_1, \dots, \omega_n)\}) = \prod\limits_{i=1}^{n} \operatorname{P}(\{\omega_i\})$$
**Produkt der Wahrscheinlichkeitsräume**. Der Wahrscheinlichkeitsraum
$$(\Omega, \mathfrak{A}, \operatorname{P}) = \bigotimes\limits_{i=1}^{n} (\Omega_i, \mathfrak{A}_i, \operatorname{P}_i)$$
heißt **Produktraum**.

---------------

<br>

