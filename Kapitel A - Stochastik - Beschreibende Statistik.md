# Gliederung
 - [Einführung und Grundbegriffe](#einführung-und-grundbegriffe)
 - [Tabellarische und graphische Darstellung](#tabellarische-und-graphische-darstellung)
 - [Lage- und Streuungsmaße](#lage--und-streuungsmaße)
 - [Klassierte Daten und Histogramm](#klassierte-daten-und-histogramm)
 - [Zusammenhangsmessung](#zusammenhangsmessung)
 - [Regressionsanalyse](#regressionsanalyse)

---------------

# Einführung und Grundbegriffe
## Grundlegende Begriffe
### Merkmal
= Spezielle Eigenschaft statistischer Einheiten
 - Wert eines [Merkmals](#merkmal): **Merkmalsausprägung**
 - Menge aller Merkmalsausprägungen: **Wertebereich**
 - **Univariantes Merkmal**: _Eine_ Eigenschaft wird gelesen
 - **Multivariantes Merkmal**: _Mehrere_ Eigenschaften werden gelesen

### Datum
= An einer statistischen Einheit gemessene [Merkmalsausprägung](#merkmal)
<br>
_alt: Messwert, Beobachtungswert_

### Skala
= Vorschrift, die jeder statistischen Einheit der Stichprobe einen [Beobachtungswert](#datum) zuordnet

---------------

## Klassifikation von [Merkmalen](#merkmal)
### Qualitatives Merkmal
 - [Ausprägungen](#datum) geben nur eine Zugehörigkeit oder Beurteilung wieder
 - Dienen der Unterscheidung verschiedener Arten von Eigenschaften
 - **Differenzen _nicht_ interpretierbar!**

#### Nominales Merkmal
 - [Ausprägungen](#datum) sind Begriffe (oder durch Zahlen codiert)
 - **Dichotromes Merkmal**: Nominales Merkmal mit genau 2 [Ausprägungen](#datum)

#### Ordinales Merkmal
 - [Ausprägungen](#datum) genügen einer Rangfolge

<br>

### Quantitatives Merkmal
 - [Ausprägungen](#datum) werden durch Zahlen erfasst
 - **Differenzen sind _sinnvoll_ interpretierbar!**
<br>
_alt: Metrisches Merkmal_

#### Verhältnisskaliertes Merkmal
 - Die zur Messung verwendeten [Skalen](#skala) haben einen gemeinsamen Nullpunkt
 - &rarr; **Verhältnisse sind _sinnvoll_ interpretierbar!**

#### Absolutskaliertes Merkmal
 - [Verhältnisskaliertes Merkmal](#verhältnisskaliertes-merkmal), zu dessen Messung nur _eine_ [Skala](#skala) sinnvoll verwendet werden kann

#### Diskretes Merkmal
 - Der [Wertebereich](#merkmal) ist abzählbar

#### Stetiges Merkmal
 - Der [Wertebreich](#merkmal) ist ein Intervall
 - **Quasi-stetiges Merkmal**: Kein Intervall, aber sehr feine Abstufungen

<br>

### Klassiertes Merkmal
 - [Ausprägungen](#datum) sind Intervalle

---------------

<br>

# Tabellarische und graphische Darstellung

## Grundlegende Begriffe
Sei $X$ [Merkmal](#merkmal), $u_{1}, \dots,u_{m}$ [Merkmalsausprägungen](#datum), $x_{1}, \dots,x_{n}$ Urliste

### Absolute Häufigkeit
$$n_{j} \coloneqq \vert \{i \in \{1, \dots,n\} \mid x_{i} = u_{j}\}\vert$$
Es gilt:
$$\sum_{i=1}^{m} n_{i} = n$$

### Relative Häufigkeit
$$f_{i} \coloneqq \frac{n_{i}}{n}$$
Es gilt:
$$\sum_{i=1}^{m} f_{j} = 1$$

 - Tabellarische Darstellung: **Häufigkeitstabelle**
 - $f_{1}, \dots, f_{m}$: **Häufigkeitsverteilung**
 - **kumulierte Häufigkeiten**: [Merkmalsausprägungen](#datum) werden zusammengefasst und zugehörige Häufigkeiten addiert

---------------

## Stabdiagramm
= **Höhe** eines Stabes ist proportional zur [relativen Häufigkeit](#relative-häufigkeit)

---------------

## Säulendiagramm
= **Höhe** einer Säule ist proportional zur [relativen Häufigkeit](#relative-häufigkeit)

---------------

## Kreisdiagramm
= **Fläche** bzw. **Winkel** eines Kreissegments ist proportional zur [relativen Häufigkeit](#relative-häufigkeit)
$$Winkel_{j}^{\circ} \coloneqq f_{j} \cdot 360^{\circ}$$

---------------

## Liniendiagramm
= **Abstand zur Grundlinie** ist proportional zur [relativen Häufigkeit](#relative-häufigkeit)
 - suggeriert Abfolge der [Merkmalsausprägungen](#datum)

---------------

## Empirische Verteilungsfunktion
 - Graphische Darstellung für Häufigkeiten [quantitativer Merkmale](#quantitatives-merkmal)
	- [Ausprägungen](#datum) werden auf der [Abszisse](https://en.wikipedia.org/wiki/Abscissa_and_ordinate) abgetragen
	- [kumulierte Häufigkeiten](#tabellarische-und-graphische-darstellung##grundlegende-begriffe) werden auf der [Ordinate](https://en.wikipedia.org/wiki/Abscissa_and_ordinate) abgetragen

Für [Ausprägungen](#datum) $x_{1}, \dots, x_{n} \in \mathbb{R}$ wird $F_{n}: R \rightarrow [0,1]$ definiert durch:
$$x \mapsto \frac{1}{n} \sum_{i=1}^{n} \mathfrak{1}_{(- \infty, x]}(x_{i})$$

Für [Ausprägungen](#datum) $y_{1}, \dots, y_{n} \in \mathbb{R}$ eines [metrischskalierten Merkmals](#quantitatives-merkmal) heißt die aufsteigend geordnete Auflistung der [Ausprägungen](#datum) **Rangwertreihe**:
$$y_{(1)} \leq \dots\leq y_{(n)}$$

Ligen im Datensatz $x_{1}, \dots, x_{n}$ insgesamt $m$ verschiede [Ausprägugnen](#datum) $u_{(1)} < \dots< u_{(m)}$ mit zugehörigen [relativen Häufigkeiten](#relative-häufigkeit) $f_{(1)}, \dots, f_{(m)}$ vor, so gilt:
$$F_{n}(x) = \begin{cases} 0, & x < u_{(1)} \\ \sum_{j=1}^{k} f_{(j)}, & u_{(k)} \leq x < u_{(k+1)}, k \in \{1, \dots, m-1\} \\ 1, & x \geq u_{(m)} \end{cases}$$

Es gilt:
 - $f_{(j)} = F_{n}(u_{(j)}) - F_{n}(u_{(j - 1)})$
 - $F_{n}(x) \hat{=}$ Anteil der Beobachtungswerte im Intervall $(- \infty, x]$
 - $1 - F_{n}(x) \hat{=}$ Anteil der Beobachtungswerte im Intervall $(x, \infty)$
 - $F_{n}(y) - F_{n}(x)$ Anteil der Beobachtungswerte im Intervall $(x, y])$

---------------

<br>

# Lage- und Streuungsmaße

## Modus
Sei:
 - $X$ Merkmal mit Datensatz $x_{1}, \dots, x_{n}$
 - mögliche [Ausprägungen](#datum) $u_{1}, \dots, u_{m}$
 - [absolute Häufigkeiten](#absolute-häufigkeit) $n_{1},\dots, n_{m}$
 - [relative Häufigkeiten](#relative-häufigkeit) $f_{1}, \dots, f_{m}$

Jede Ausprägung $u_{j^{*}}$ mit $n_{j^{*}} = \max(n_{1}, \dots, n_{m})$ bzw. $f_{j^{*}} = \max(f_{1}, \dots, f_{m})$, wird als **Modus** bezeichnet.
$$\Rightarrow x_{mod} \coloneqq u_{j^{*}}$$
Der **Modalwert** ist die Realisation des Modus im Datensatz.

---------------

## $p$-Quantile
Sei $x_{(1)} \leq \dots\leq x_{(n)}$ die Rangwertreihe eines [qualitatives](#qualitatives-merkmal) Datensatzes.
Das $p$-Quantil $\tilde{x}_{p}$ des Datensatzes wird definiert durch:
$$\tilde{x}_{p} \in \begin{cases} \{x_{(k)}\}, & n \cdot p < k < n \cdot p + 1, n \cdot p \not\in \mathbb{N} \\ \{x_{(k)}, x_{(k)}\}, & n \cdot p \in \mathbb{N} \end{cases}$$

Sei $x_{(1)} \leq \dots\leq x_{(n)}$ die Rangwertreihe eines [quantitatives](#quantitatives-merkmal) Datensatzes.
Das $p$-Quantil $\tilde{x}_{p}$ des Datensatzes wird definiert durch:
$$\tilde{x}_{p} = \begin{cases} x_{(k)}, & n \cdot p < k < n \cdot p + 1, n \cdot p \not\in \mathbb{N} \\ \frac{1}{2} \cdot (x_{(k)} + x_{(k)}), & n \cdot p \in \mathbb{N} \end{cases}$$

$\tilde{x} \coloneqq \tilde{x}_{0.5}$ wird **Median** genannt.

---------------

## Arithmetisches Mittel
Sei $x_{1}, \dots, x_{n}$ der Datensatz aus [Beobachtungswerten](#datum) eines [quantitativen Merkmals](#qualitatives-merkmal).
Das **arithmetische Mittel** $\bar{x}_{n}$ bzw. $\bar{x}$ ist definiert durch:
$$\bar{x}_{n} \coloneqq \frac{1}{n} \cdot \sum_{i=1}^{n} x_{i}$$
$$\bar{x}_{n} = \sum_{i=1}^{m} f_{j} \cdot u_{j}$$

Seien $g_{1}, \dots, g_{n} \geq 0$ mit $\sum_{i=1}^{n} g_i = 1$.
Das **gewichtete arithmetische Mittel** ist definiert durch:
$$\bar{x}_{g} \coloneqq \sum_{i=1}^{n} g_{i} \cdot x_{i}$$

&rarr; Folglich ist $\bar{x}$ das gewichtete arithmetische Mittel $\bar{x}_f$ der Ausprägungen $u_{1}, \dots, u_{m}$ mit Gewichten $f_{1}, \dots, f_{m}$

Sei:
 - $\bar{x}$ das arithmetische Mittel von $x_{1}, \dots, x_{n_{1}} \in \mathbb{R}$
 - $\bar{y}$ das arithmetische Mittel von $y_{1}, \dots, y_{n_{1}} \in \mathbb{R}$

Das arithmetische Mittel $\bar{z}$ des **zusammengesetzen Datensatzes**
$$z_{1} = x_{1}, \dots, z_{n_{1}} = x_{n_{1}}, z_{n_{1} + 1} = y_{1}, \dots, z_{n_{1} + n_{2}} = y_{n_{2}}$$
lässt sich bestimmen als:
$$\bar{z} = \frac{n_{1}}{n_{1} + n_{2}} \cdot \bar{x} + \frac{n_{2}}{n_{1} + n_{2}} \cdot \bar{y}$$

&rarr; Möchte man an einen Datensatz $x_{1}, \dots, x_{n}$ einen Beobachtungswert $x_{n+1}$ anfügen, lässt sich das neue arithmetische Mittel berechnen aus:
$$\bar{x}_{n+1} = \frac{n}{n + 1} \cdot \bar{x}_{n} + \frac{1}{n + 1} \cdot x_{n + 1}$$

---------------

## Lagemaße
 - Beschreiben ein Zentrum oder eine Position
 - Anwendbarkeit hängt vom [Merkmalstyp](#klassifikation-von-merkmalen) ab

### Lagemaße für [qualitative](#qualitatives-merkmal) Daten
Verwendung von [Modus](#modus), [Median und $p$-Quantilen](#p-quantile)


#### Lagemaße für [ordinale](#ordinales-merkmal) Daten
[Rangwertreihe](#empirische-verteilungsfunktion) ist bezüglich der Häufigkeit aufsteigend sortiert.

### Lagemaße für [quantitative](#quantitatives-merkmal) Daten
Verwendung von [Modus](#modus), [Median, $p$-Quantilen](#p-quantile) und [arithmetischen Mitteln](#arithmetisches-mittel).

---------------

## Streuungsmaße
***NUR FÜR [QUANTITATIVE](#quantitatives-merkmal) DATEN!***
 - Streuung manchmal interessanter als Lage

### Spannweite und Quartilsabstand
Für einen [metrischen](#quantitatives-merkmal) Datensatz $x_{1}, \dots, x_{n}$ ist die **Spannweite** $R$ definiert als
$$R \coloneqq x_{(n)} - x_{(1)}$$
und der **Quartilsabstand** $Q$ definiert als
$$Q \coloneqq \tilde{x}_{0.75} - \tilde{x}_{0.25}$$

Visualisierung mittels **Box-Plots**.

### Abweichmessung
#### Varianz und Standardabweichung
**Empirische Varianz**:
$$s^{2} = s_{n}^{2} \coloneqq \frac{1}{n} \cdot \sum_{i=1}^{n} (x_{i} - \bar{x}_{n})^{2}$$
$$s^{2} = s_{n}^{2} \coloneqq \sum_{j=1}^{m} f_{j} (u_{j} - \bar{x}_{n})^{2}$$
**Empirische Standardabweichung**:
$$s = s_{n} \coloneqq \sqrt{s_{n}^{2}}$$

Es gilt für $a \in \mathbb{R}$: $\frac{1}{n} \cdot \sum_{i=1}^{n} (x_{i} - a)^{2} = s^{2} + (\bar{x} - a)^{2}$
bzw. für $a=0$: $s^{2} = \bar{x^{2}} - \bar{x}^{2}$

Sei:
 - $\bar{x}$ das [arithmetische Mittel](#arithmetisches-mittel) von $x_{1}, \dots, x_{n_{1}} \in \mathbb{R}$
 - $\bar{y}$ das [arithmetische Mittel](#arithmetisches-mittel) von $y_{1}, \dots, y_{n_{1}} \in \mathbb{R}$
 - $\bar{x}_{gesamt}$ das [arithmetische Mittel](#arithmetisches-mittel) des zusammengesetzen Datensatzes.

Für die Varianz $s_{gesamt}^{2}$ gilt:
$$s_{gesamt}^{2} = \frac{n_{1}}{n_{1} + n_{2}} \cdot (s_{x}^{2} + (\bar{x} - \bar{x}_{gesamt})^{2}) + \frac{n_{2}}{n_{1} + n_{2}} \cdot (s_{y}^{2} + (\bar{y} - \bar{x}_{gesamt})^{2})$$

#### Mittlere Absolute Abweichung
Für $x_{1}, \dots, x_{n}$ heißt
$$d \coloneqq \frac{1}{n} \cdot \sum_{i=1}^{n} \vert x_{i} - \tilde{x}_{0.5} \vert$$
$$d \coloneqq \sum_{j=1}^{m} f_{j} \vert u_{j} - \tilde{x}_{0.5} \vert$$
**mittlere absoute Abweichung**.
$$d \leq s$$

---------------

## Lineare Transformation
Seien $a,b \in \mathbb{R}$ und $y_{1}, \dots, y_{n}$ der linear transformierte Datensatz von $x_{1}, \dots, x_{n}$:
$$y_{i} = a + b \cdot x_{i}, i \in \{1, \dots, n\}$$
Dann gilt:
 - $\tilde{y} = a + b \cdot \tilde{x}$
 - $\bar{y} = a + b \cdot \bar{x}$
 - $s_{y}^{2} = b^{2} \cdot s_{x}^{2}$ bzw. $s_{y} = \vert b \vert \cdot s_{x}$
 - $d_{y} = \vert b \vert d_{x}$


### Zentrierung
Für $x_{1}, \dots, x_{n} \in \mathbb{R}$ eines [metrischen](#quantitatives-merkmal) Datensatzes heißt die [lineare Transformation](#lineare-transformation)
$$y_{i} = x_{i} - \bar{x}, i \in \{1, \dots, n\}$$
**Zentrierung**. Alle $y_{i}$ werden dann als **Residuen** bezeichnet. Es gilt dann:
$$\bar{y} = 0$$

### Standardisierung
Für $x_{1}, \dots, x_{n}$ heißt die [lineare Transformation](#lineare-transformation)
$$z_{i} = \frac{x_{i} - \bar{x}}{s_{x}}, i \in \{1, \dots, n\}$$
**Standardisierung**. Es gilt dann::
$$\bar{z} = 0, s_{z} = 1$$

---------------

<br>

# Klassierte Daten und Histogramm
## Kategorisierung der Messwerte
Seien $[a,b]$ der [Wertebereich](#merkmal) eines [Merkmals](#merkmal) $X$ mit Daten $x_{1}, \dots, x_{n}$ und $a = v_{0} < v_{1} < \dots < v_{M-1} < v_{M} = b$
$M$ Klassen $K_{j} = (v_{j-1}, v_{j}], 1 < j \leq M$ und $K_{1} = [v_{0}, v_{1}]$ bilden **Zerlegung** mit [Häufigkeiten](#absolute-häufigkeit):
$$n(K_{j}) \coloneqq \sum_{i: u_{i} \in K_{j}} n_{i}$$
$$f(K_{j}) \coloneqq \sum_{i: u_{i} \in K_{j}} f_{i}$$

**Klassenbreite**: $b_{j} = v_{j} - v_{j-1}$

---------------

## Histogramm
= **Fläche des Rechtecks** über der Klasse $K_{j}$ ist proportional zur [relativen Häufigkeit](#relative-häufigkeit) $f(K_{j})$
 - Breite: $b_{j}$
 - Höhe: $h_{j} \coloneqq \frac{f(K_{j})}{b_{j}} \cdot c$ ($c > 0$ zur **Skalierung**)

&rarr; Anteile von Beobachtungen in _gleichbreiten (Teil-)Intervallen_ sind über die Höhe vergleichbar.

---------------

<br>

# Zusammenhangsmessung
 - Oftmals werden mehrere [Merkmale](#merkmal) gleichzeitig gemessen
 - _Hier_: Paare von [**quantitativen Merkmalen**](#quantitatives-merkmal) $X$ und $Y$
 - $(X,Y)$ heißt **bivariates Merkmal**.
 - Datensatz $(x_{1}, y_{1}), \dots, (x_{n}, y_{n})$
 - Visualisierung im **Scatterplot**

## Empirische Kovarianz
Seien $(x_{1}, y_{1}), \dots, (x_{n}, y_{n})$ Messwerte eines bivarianten, quantitativen Merkmals $(X,Y)$. Dann heißt

$$\begin{align*} s_{xy} & \coloneqq \frac{1}{n} \cdot \sum_{i=1}^{n} (x_{i} - \bar{x}) \cdot (y_{i} - \bar{y}) \\ & = \frac{1}{n} \cdot (\sum_{i=1}^{n} x_{i} \cdot y_{i}) - \bar{x} \cdot \bar{y} \\ & = \bar{xy} - \bar{x} \cdot \bar{y} \end{align*}$$

---------------

## Lineare Transformation
$(x_{1}, y_{1}), \dots, (x_{n}, y_{n})$ Messwerte eines zweidimensionalen Merkmals $(X,Y)$ mit [Kovarianz](#empirische-kovarianz) $s_{xy}$. Die gemäß
$$x_{i}^{*} = a + b \cdot x_{i}, a,b \in \mathbb{R} \text{ und } y_{i}^{*} = c + d \cdot y_{i}, c,d \in \mathbb{R}$$
linear transformierten Daten $(x_{1}^{*}, y_{1}^{*}), \dots, (x_{n}^{*}, y_{n}^{*})$ haben die Kovarianz
$$s_{x^{*}y^{*}} = b \cdot d \cdot s_{xy}$$

---------------

## Korrelationskoeffizient von Bravais-Pearson
Seien $(x_{1}, y_{1}), \dots, (x_{n}, y_{n})$ ein gepaarter Datensatz zum bivariaten Merkmal $(X,Y)$ und $s_{x} > 0$ bzw. $s_{y} > 0$ die [Standardabweichungen](#varianz-und-standardabweichung) von $x_{1}, \dots, x_{n}$ bzw. $y_{1}, \dots, y_{n}$

Der **Bravais-Pearson-Korrelationskoeffizient** $r_{xy}$ ist definiert durch:
$$r_{xy} \coloneqq \frac{s_{xy}}{s_{x} \cdot {s_{y}}}$$

$-1 \leq r_{xy} = r_{yx} \leq 1$
Falls $r_{xy} = -1$:
> Es gibt eine _negative_ Zahl $b < 0$ und eine reele Zahl $a \in \mathbb{R}$ mit
$$y_{i} = a + b \cdot x_{i}, i \in \{1, \dots, n\}$$
Es gibt also einen linearen Zusammenhang zwischen $X$ und $Y$ derart, dass wenn $X$ um eine Einheit steigt, $Y$ um $\vert b \vert$ Einheiten fällt.
&rarr; Ordnungsverhalten ist **gegensinnig**.

Falls $r_{xy} = 1$:
> Es gibt eine _positive_ Zahl $b > 0$ und eine reele Zahl $a \in \mathbb{R}$ mit
$$y_{i} = a + b \cdot x_{i}, i \in \{1, \dots, n\}$$
Es gibt also einen linearen Zusammenhang zwischen $X$ und $Y$ derart, dass wenn $X$ um eine Einheit steigt, $Y$ um $b$ Einheiten steigt.
&rarr; Ordnungsverhalten ist **gleichsinnig**.

### Korrelation
Merkmale X und Y heißen
$$\begin{align*} & \text{positiv korrliert:} & r_{xy} > 0 \\ & \text{unkorrliert:} & r_{xy} = 0 \\ & \text{negativ korrliert:} & r_{xy} < 0 \\ & \text{schwach korrliert:} & 0 \leq \vert r_{xy} \vert < 0.5 \\ & \text{stark korrliert:} & 0.8 \leq \vert r_{xy} \vert \leq 1 \end{align*}$$


---------------

<br>

# Regressionsanalyse
 - **funktionaler Zusammenhang** zwischen Merkmalen $X$ und $Y$
 - $Y = \operatorname{f}(X)$ mit $\operatorname{f}: \mathbb{R} \rightarrow \mathbb{R}$
 - Oft von unbekannten Parametern abhängig
<br>
 - Merkmal $X$ heißt **Regressor** bzw. **erklärende Variable**
 - Merkmal $Y$ heißt **Regressand** bzw. **abhängige Variable**
 - $\operatorname{f}$ heißt **Regressionsfunktion**
 - Werte $\hat{y}_{i} \coloneqq \operatorname{f}(x_{i})$ heißen **Regressionswerte**
 - $\hat{y}_{i} \neq y_{i}$ _kann_ gelten (z.B. durch Schwankungen oder Messfehler)

Für Merkmale $X,Y$ wird der Zusammenhang
$$Y = \operatorname{f}(X) + \epsilon$$
unterstellt. $\epsilon$ repräsentiert Abweichungen.

Abweichung in der $i$-ten Messung (**Residuum**): $\epsilon_{i} = y_{i} - \hat{y}_{i}$

**Problemstellung:** Finde optimales $\operatorname{f}$

## Methode der kleinsten Quadrate
Seien:
 - Datensatz $(x_{1}, y_{1}), \dots, (x_{n}, y_{n})$
 - Regressionsmodell $Y = \operatorname{f}(X) + \epsilon$ mit einer Regressionsfunktion $f \in H$, wobei $H$ gegeben ist.

Suche Funktion $\hat{\operatorname{f}} \in H$, sodass die Fehlerquadratsumme
$$\operatorname{Q}(\operatorname{f}) \coloneqq \sum_{i=1}^{n} (y_{i} - \operatorname{f}(x_{i}))^{2} = \sum_{i=1}^{n} \epsilon_{i}^{2}$$
minimal ist, d.h.
$$\operatorname{Q}(\hat{\operatorname{f}}) \leq \operatorname{Q}(\operatorname{f}), f \in H$$

Für parametrische Funktionen $f_{b_{1}, \dots, b_{j}} \in H$, die durch $j$ Parameter $b_{1}, \dots, b_{j} \in \mathbb{R}$ beschrieben wird:
$$\operatorname{Q}(b_{1}, \dots, b_{j}) \coloneqq \sum_{i=1}^{n} (y_{i} - \operatorname{f}_{b_{1}, \dots, b_{j}}(x_{i}))^{2}$$
suche Tupel $(\hat{b}_{1}, \dots, \hat{b}_{j}) \in \mathbb{R}^{j}$ mit
$$\operatorname{Q}(\hat{b}_{1}, \dots, \hat{b}_{j}) \leq \operatorname{Q}(b_{1}, \dots, b_{j}), (b_{1}, \dots, b_{j}) \in \mathbb{R}^{j}$$

#### Lineares Regressionsmodell
Ist $\operatorname{f}$ eine lineare Funktion
$$\operatorname{f}(x) = a + b \cdot x, x \in \mathbb{R}$$
so heißt
$$Y = a + b \cdot X + \epsilon$$
**lineares Regressionsmodell**. Die [Regressionsfunktion](#regressionsanalyse) heißt auch **Regressionsgerade**.

Für $s_{x}^{2} > 0$ gilt für die Lösung:
$$\begin{align*} \hat{b} & \coloneqq \frac{s_{xy}}{x_{x}^{2}} \\ \hat{a} & \coloneqq \bar{y} - \hat{b} \cdot \bar{x} \end{align*}$$

 - **Minimaler Abstand**: $\operatorname{Q}(\hat{a}, \hat{b}) = n \cdot s_{y}^{2} \cdot (1 - r_{xy}^{2})$
 - **Geschätzte Regressionsgerade**: $\hat{f}(x) = \hat{a} + \hat{b} \cdot x$
 - $\hat{\operatorname{f}}(\bar{x}) = \bar{y}$
 - $\bar{\hat{y}} = \bar{y}$
 - $\sum_{i=1}^{n} \epsilon_{i} = 0$
 - Für $s_{y}^{2} > 0$ ist $\hat{\operatorname{f}}$ genau dann wachsend, wenn:
$$\hat{b} = \frac{s_{y}}{s_{x}} \cdot r_{xy} \begin{cases} > \\ < \\ = \end{cases} 0 \Leftrightarrow r_{xy} \begin{cases} > \\ < \\ = \end{cases} 0$$

---------------

## Lineare Transformation
Seien:
 - $s_{x}^{2} > 0$
 - $\hat{\operatorname{f}} = \hat{a} + \hat{b} \cdot x$ die zu $(x_{1}, y_{1}), \dots, (x_{n}, y_{n})$ zugehörige [Regressionsgerade](#lineares-regressionsmodell)

Werden Beobachtungswerte mit $\beta \neq 0, \delta \neq 0, \alpha, \gamma \in \mathbb{R}$ [(linear) transformiert](#lineare-transformation) gemäß
$$\begin{align*} u_{i} & = \alpha + \beta \cdot x_{i} \\ v_{i} & = \gamma + \delta \cdot y_{i} \end{align*}$$
so gilt für die Koeffizienten der zu $(u_{1}, v_{1}), \dots, (u_{n}, v_{n})$ gehörigen [Regressionsgerade](#lineares-regressionsmodell) $\hat{\operatorname{g}}(u) = \hat{c} + \hat{d} \cdot u$:
$$\begin{align*} \hat{c} & = \delta \cdot \hat{a} + \gamma - \frac{\alpha \cdot \delta}{\beta} \cdot \hat{b} \\ \hat{d} & = \frac{\delta}{\beta} \cdot \hat{b} \end{align*}$$

---------------

## Bewertung der Anpassung
Sei $\hat{\operatorname{f}}$ die mittels der [Methode der kleinsten Quadrate](#methode-der-kleinsten-quadrate) geschätzte [Regressionsgerade](#lineares-regressionsmodell).
 - Die Differenzen $\hat{e}_{i} = y_{i} - \hat{y}_{i}$ mit $\hat{y}_{i} = \hat{\operatorname{f}}(x_{i})$ werden als **Residuen** bezeichnet.
 - Für $\sum_{i=1}^{n} \hat{e}_{i}^{2} > 0$ sind die **standardisierten Residuen** definiert durch (siehe [Standardisierung](#standardisierung)):
$$\hat{d}_{i} = \frac{\hat{e}_{i}}{\sqrt{\sum_{i=1}^{n} \hat{e}_{i}^{2}}}$$
 - Seien $\hat{d}_{1}, \dots, \hat{d}_{n}$ die standardisierten Residuen zu $\hat{e}_{1}, \dots, \hat{e}_{n}$:
   - $-1 \leq \hat{d}_{i} \leq 1$
   - $\sum_{i=1}^{n} \hat{d}_i = 0, \sum_{i=1}^{n} \hat{d}_i^{2} = 1$
 - Für $\sum_{i=1}^{n} \hat{e}_{i}^{2} = 0$ ist $y_{i} = \hat{y}_{i}, i \in \{1, \dots, n\}$

Die Güte der Approximation der [Regressionsfunktion](#regressionsanalyse) an die Daten wird gemessen durch das **Bestimmtheitsmaß**
$$B_{xy} = r_{xy}^{2}$$
 - $0 \leq B_{xy} \leq 1$
 - $B_{xy} = 1$ impliziert optimale Anpassung
 - $B_{xy} = 0$ signalisiert schlechte _lineare_ Anpassung