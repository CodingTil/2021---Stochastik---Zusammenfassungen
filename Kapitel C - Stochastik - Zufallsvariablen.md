# Gliederung
 - [Zufallsvariablen und Wahrscheinlichkeitsmaße](#zufallsvariablen-und-wahrscheinlichkeitsmaße)
 - [Verteilungsfunktion und Quantilfunktion](#verteilungsfunktion-und-quantilfunktion)
 - [Mehrdimensionale Zufallsvariablen und Verteilungen](#mehrdimensionale-zufallsvariablen-und-verteilungen)
 - [Transformation von Zufallsvariablen](#transformation-von-zufallsvariablen)
 - [Erwartungswerte, Varianz, Kovarianz und Korrelation](#erwartungswerte-varianz-kovarianz-und-korrelation)
 - [Erzeugende Funktionen](#erzeugende-funktionen)

---------------

# Zufallsvariablen und Wahrscheinlichkeitsmaße
Sei $(\Omega, \mathfrak{A}, \operatorname{P})$ ein Wahrscheinlichkeitsraum. Eine Abbildung
$$\operatorname{X}: \Omega \rightarrow \mathbb{R}^n$$
heißt **Zufallsvariable** bzw. **Zufallsvektor**.

Sei $\mathcal{B}$ die Borelsche $\sigma$-Algebra über $\mathbb{R}$. Dann definiert
$$\operatorname{P}^{\operatorname{X}}: \mathcal{B} \rightarrow [0,1], A \mapsto \operatorname{P}(\{\omega \in \Omega \mid \operatorname{X}(\omega) \in A\})$$
eine **Wahrscheinlichkeitsverteilung über $\mathbb{R}$** bzw. über $\operatorname{X}(\Omega) = \{\operatorname{X}(\omega) \mid \omega \in \Omega\}$.

_Statt $\operatorname{P}^{\operatorname{X}}(A)$ schreibt man auch $\operatorname{P}(X \in A)$ oder $\operatorname{P}(X = x)$, falls $A = \{x\}$._

$\operatorname{P}^{\operatorname{X}}$ heißt **Verteilung von $\operatorname{X}$ unter $\operatorname{P}$ ($\operatorname{X} \sim \operatorname{P}$ bzw. $\operatorname{X} \sim \operatorname{P}^{\operatorname{X}}$)**.

### Indikatorfunktion
Seien $\Omega \neq \emptyset$, $(\Omega, \mathfrak{A}, \operatorname{P})$ ein Wahrscheinlichkeitsraum und $A \in \mathfrak{A}$. Die Funktion $\mathcal{1}_A: \Omega \rightarrow \mathbb{R}$ definiert durch
$$\mathcal{1}_A(\omega) = \begin{cases} 1, & \omega \in A \\ 0, & w \not\in A \end{cases}$$
heißt **Indikatorfunktion** von $A$.

$\mathcal{1}_A \sim \operatorname{bin}(1, \operatorname{p})$ mit $\operatorname{p} = \operatorname{P}(A)$.

## Stochastische Unabhängigkeit von Zufallsvariablen
Seien $I$ eine Indexmenge und $\operatorname{X}_i: (\Omega, \mathfrak{A}, \operatorname{P}) \rightarrow (\Omega, \mathfrak{A}, \operatorname{P}^{\operatorname{X}_i}), i \in I$ [Zufallsvariablen](#zufallsvariablen-und-wahrscheinlichkeitsmaße). Die Zufallsvariablen $\operatorname{X}_i$ heißen **stochastisch unabhängig**, falls:
$$\operatorname{P}(\bigcap\limits_{i \in J} \{\operatorname{X}_i \in A_i\}) = \prod\limits_{i \in J} \operatorname{P}(\operatorname{X}_i \in A_i), \forall J \subseteq I, \vert J \vert < \infty$$

 - $\operatorname{X}$ und $\operatorname{Y}$ heißen **identisch verteilt**, wenn $\operatorname{P}^{\operatorname{X}}(A) = \operatorname{P}^{\operatorname{Y}}(A)$ für alle $A \in \mathfrak{A}$
 - $\operatorname{X}_1, \dots, \operatorname{X}_n$ sind stochastisch unabhängig _und_ identisch verteilt:
$$\operatorname{X}_1, \dots, \operatorname{X}_n \overset{iid}{\sim} \operatorname{P}$$

Sind die Zufallsvariablen $\operatorname{X}_i: \Omega \rightarrow \Omega_i, i \in I$ stochastisch unabhängig und sind Abbildungen $\operatorname{f}_i: \Omega_i \rightarrow \Omega_i'$ gegeben, dann sind die **Zufallsvariablen**
$$\operatorname{f}_i \circ \operatorname{X}_i, i \in I$$ stochastisch unabhängig.
Weiterhin gilt für disjunkte Indexmengen $I_j \subseteq I, j \in J$ und Abbildungen $\operatorname{g}_j: ⨉_{i \in I_j} \Omega_i \rightarrow \Omega_j'$:
$$\operatorname{g}_j \circ (\operatorname{X}_i, i \in I_j)$$ sind stochastisch unabhängige Funktionen von Zufallsvariablen mit disjunkten Indexmengen.

### Faltung
Seien $\operatorname{X}$ und $\operatorname{Y}$ stochastich unabhängige Zufallsvariablen auf $\mathbb{Z}$ mit den Zähldichten $\operatorname{f}$ bzw. $\operatorname{g}$ (d.h. $\operatorname{P}(\operatorname{X}=n) = \operatorname{f}(n), \operatorname{P}(\operatorname{Y}=m) = \operatorname{g}(m)$). Dann hat $\operatorname{X}+\operatorname{Y}$ die Zähldichte $\operatorname{h}$ gegeben durch:
$$\begin{align*} \operatorname{h}(k) &= \operatorname{P}(\operatorname{X} + \operatorname{Y} = k) = \operatorname{P}(\{\omega \mid \operatorname{X}(\omega) + \operatorname{Y}(\omega) = k\}) \\ &= \sum\limits_{j \in \mathbb{Z}} \operatorname{f}(j) \cdot \operatorname{g}(k - j) = \sum\limits_{j \in \mathbb{Z}} \operatorname{f}(k - j) \cdot \operatorname{g}(j)\end{align*}$$
$\operatorname{h}$ heißt **Faltung der Dichten $\operatorname{f}$ und $\operatorname{g}$**.

---------------

<br>

# Verteilungsfunktion und Quantilfunktion
Seien $(\Omega, \mathfrak{A}, \operatorname{P})$ ein Wahrscheinlichkeitsraum und $\operatorname{X}$ eine Zufallsvariable auf $(\Omega, \mathfrak{A}, \operatorname{P})$ mit Wahrscheinlichkeitsverteilung $\operatorname{P}^{\operatorname{X}}$. Die Funktion
$$\operatorname{F}^{\operatorname{X}}: \mathbb{R} \rightarrow \mathbb{R}, x \mapsto \operatorname{P}^{\operatorname{X}}((-\infty, x]) = \operatorname{P}(\operatorname{X} \leq x)$$
heißt die zu $\operatorname{P}^{\operatorname{X}}$ zugehörige **Verteilungsfunktion** $\operatorname{F}$.
 - $\operatorname{f}^{\operatorname{X}}$ **Zähldichte** von $\operatorname{P}^{\operatorname{X}}$: $\operatorname{F}^{\operatorname{X}} = \operatorname{P}(\operatorname{X} \leq x) = \sum\limits_{y \leq x} \operatorname{f}^{\operatorname{X}}(y)$
 - $\operatorname{f}^{\operatorname{X}}$ **Riemann-Dichte** von $\operatorname{P}^{\operatorname{X}}$: $\operatorname{F}^{\operatorname{X}} = \operatorname{P}(\operatorname{X} \leq x) = \int\limits_{-\infty}^x \operatorname{f}^{\operatorname{X}}(y) dy$

## Rechenregeln für Verteilungsfunktionen
 - $\operatorname{P}(a < \operatorname{X} \leq b) = \operatorname{F}^{\operatorname{X}}(b) - \operatorname{F}^{\operatorname{X}}(a), a < b$
 - $\operatorname{P}(t < \operatorname{X}) = 1 - \operatorname{F}^{\operatorname{X}}(t)$
 - $\operatorname{P}(\operatorname{X} = x) = \operatorname{F}^{\operatorname{X}}(x) - \operatorname{F}^{\operatorname{X}}(x-)$, wobei $\operatorname{F}^{\operatorname{X}}(x-) = \lim\limits_{t \rightarrow x, t < x} \operatorname{F}^{\operatorname{X}}(t)$

Sei $\operatorname{F}$ ein Verteilungsfunktion. Dann heißt die durch
$$\operatorname{F}^{-1}(y) = \operatorname{inf}\{x \in \mathbb{R} \mid \operatorname{F}(x \geq y\}, y \in (0,1)$$ definierte Funktion **Quantilfunktion** oder **Pseudoinverse** von $\operatorname{F}$.

---------------

<br>

# Mehrdimensionale Zufallsvariablen und Verteilungen
Sei $\operatorname{X}=(\operatorname{X}_1, \dots, \operatorname{X}_n)$ ein Zufallsvektor mit Verteilung $\operatorname{P}^{\operatorname{X}}$. Die Verteilung von $$(\operatorname{X}_{i_1}, \dots, \operatorname{X}_{i_m})$$ heißt für $m<n$ und $1 \leq i_1 < \dots < i_m \leq n$ **$m$-dimensinale Randverteilung zu $(i_1, \dots, i_m)$**. Die Verteiung von $\operatorname{X}_i$ heißt **$i$-te Randverteilung**.

$\operatorname{X}_1, \dots, \operatorname{X}_n$ sind **stochastisch unabhängige Zufallsvariablen mit Verteilungsfunktinen $\operatorname{F}^{\operatorname{X}_1}, \dots, \operatorname{F}^{\operatorname{X}_n}$** genau dann, wenn: $$\operatorname{F}^{(\operatorname{X}_1, \dots, \operatorname{X}_n)} = \operatorname{F}^{\operatorname{X}_1}(x_1) \cdot \dots \cdot \operatorname{F}^{\operatorname{X}_n}(x_n), \forall (x_1, \dots, x_n) \in \mathbb{R}^n$$

Sei $\operatorname{f}$ eine Riemann-Dichte über $\mathbb{R}^n$.
 - **Verteilungsfunktion $\operatorname{F}$ ist stetig** mit $$\operatorname{F}(x_1, \dots, x_n) = \int_{-\infty}^{x_n} \dots \int_{-\infty}^{x_1} f(y_1, \dots, y_n) \operatorname{d}y_1 \dots \operatorname{d}y_n$$
 - **Wahrscheinlichkeiten** über Integraldarstellung $$\operatorname{F}(⨉_{i=1}^{n} [a_i, b_i]) = \int_{a_n}^{b_n} \dots \int_{a_1}^{b_1} \operatorname{f}(y_1, \dots, y_n) \operatorname{d}y_1 \dots \operatorname{d}y_n$$

---------------

<br>

# Transformation von Zufallsvariablen
Die Zufallsvariable $\operatorname{X}$ habe die Riemann-Dichte $\operatorname{f}^{\operatorname{X}}$ mit $$\operatorname{f}^{\operatorname{X}}(x) \begin{cases} >0, &x \in (a,b) \\ =0, &x \not\in (a,b) \end{cases}$$
Weiterhin sei die Funtion $\operatorname{g} : (a,b) \rightarrow (c,d)$ **bijektiv und stetig differenzierbar mit stetig differenzierbarer Umkehrfunktion $\operatorname{g}^{-1}$**. Dann besitzt die **transformierte Zufallsvariable $Y = \operatorname{g}(\operatorname{X})$ die Dichte $$\operatorname{f}^{\operatorname{Y}}(y) = \begin{cases} \vert (\operatorname{g}^{-1})'(y) \vert \operatorname{f}^{\operatorname{X}}(\operatorname{g}^{-1}(y)) , &y \in (c,d) \\ 0, &y \not\in (c,d) \end{cases}$$

---------------

<br>

# Erwartungswerte, Varianz, Kovarianz und Korrelation
#### Erwartungswert
Seien $(\Omega, \mathfrak{A}, \operatorname{P})$ ein Wahrscheinlichkeitsraum.
 - Ist $\operatorname{X}$ eine Zufallsvariable mit Zähldichte $\operatorname{f}$, so heißt $$\operatorname{E}\operatorname{X} = \sum\limits_{x \in \operatorname{X}(\Omega)} x \cdot \operatorname{f}(x) = \sum\limits_{x \in \operatorname{X}(\Omega)} x \cdot \operatorname{P}(\operatorname{X} = x)$$ **Erwartungswert von $\operatorname{X}$**.
 - Ist $\operatorname{X}$ eine Zufallsvariable mit Riemann-Dichte $\operatorname{f}$, so heißt $$\operatorname{E}\operatorname{X} = \int\limits_{-\infty}^{\infty} x \operatorname{f}(x) \operatorname{d}x$$ **Erwartungswert von $\operatorname{X}$**.

#### Momente
Als **(allgemeines) Moment einer Zufallsvariablen $\operatorname{X}$** wird der Erwartungswert einer Funktion $\operatorname{g}(\operatorname{X})$ bezeichnet.
Seien $k \in \mathbb{N}, \operatorname{X}=(\operatorname{X}_1, \dots, \operatorname{X}_n): \Omega \rightarrow \mathbb{R}^k$ ein Zufallsvektor ung $\operatorname{g}: \mathbb{R}^k \rightarrow \mathbb{R}$ eine stetige Funktion, sodass der Erwartungswert von $\operatorname{g}(\operatorname{X})$ existiert.
Dann gilt:
 - Falls $\operatorname{P}^{\operatorname{X}}$ diskret ist: $$\operatorname{E}(\operatorname{g}(\operatorname{X})) = \sum\limits_{(t_1, \dots, t_k) \in \operatorname{supp}(\operatorname{P}^{\operatorname{X}})} \operatorname{g}(t_1, \dots, t_k) \cdot \operatorname{P}(\operatorname{X}_1 = t_1, \dots, \operatorname{X}_k = t_k)$$
 - Falls $\operatorname{P}^{\operatorname{X}}$ stetig ist: $$\operatorname{E}(\operatorname{g}(\operatorname{X})) = \int\limits_{-\infty}^{\infty} \dots \int\limits_{-\infty}^{\infty} \operatorname{g}(t_1, \dots, t_k) \cdot \operatorname{f}^{\operatorname{X}}(t_1, \dots, t_k) \operatorname{d}t_1 \dots \operatorname{d}t_k$$

#### Eigenschaften
Seien $\operatorname{X}, \operatorname{Y}$ Zufallsvariablen mit endlichem Erwartungswert und $a,b \in \R$. Dann gilt:
 - $\operatorname{E}a = a$
 - $\operatorname{E}(a\operatorname{X}) = a \operatorname{E}\operatorname{X}$
 - $\operatorname{E}(\operatorname{X} + \operatorname{Y}) = \operatorname{E}\operatorname{X} + \operatorname{E}\operatorname{Y}$
 - $\operatorname{E}(\vert \operatorname{X} + \operatorname{Y} \vert) \leq \operatorname{E}(\vert \operatorname{X} \vert) + \operatorname{E}(\vert \operatorname{Y} \vert)$
 - $\operatorname{X} \leq \operatorname{Y} \Rightarrow \operatorname{E}\operatorname{X} \leq \operatorname{E}\operatorname{Y}$
 - $\operatorname{E}(\vert \operatorname{X} \vert) = 0 \Leftrightarrow \operatorname{P}(\operatorname{X} \neq 0) = 0$

Seien $\operatorname{X}_1, \dots, \operatorname{X}_n$ stochastisch unabhängige Zufallsvariablen mit endlichen existierenden Erwartungswerten. Dann gilt: $$\operatorname{E}(\prod\limits_{i=1}^n \operatorname{X}_i) = \prod\limits_{i=1}^{n} \operatorname{E}\operatorname{X}_i$$

#### Spezielle Momente
Seien $\operatorname{X}, \operatorname{Y}$ Zufallsvariablen und $c \in \R, k \in \N$.
 - $m_k(c) = \operatorname{E}((\operatorname{X} - c)^k)$: **$k$-tes Moment** von $\operatorname{X}$ um $c$
   - Für $c=0$: $m_k = \operatorname{E}\operatorname{X}^k$: **$k$-tes zetrales Moment**
 - $\operatorname{Var}\operatorname{X} = \operatorname{E}((\operatorname{X} - \operatorname{E}\operatorname{X})^2)$: **Varianz**
 - $\operatorname{Kov}(\operatorname{X}, \operatorname{Y}) = \operatorname{E}((\operatorname{X} - \operatorname{E}\operatorname{X}) \cdot (\operatorname{Y} - \operatorname{E}\operatorname{Y}))$: **Kovarianz**

Es gilt für $\operatorname{Var}\operatorname{X} < \infty$:
 - $\operatorname{Var}(a+b\operatorname{X}) = b^2 \operatorname{Var}\operatorname{X}$
 - $\operatorname{Var}\operatorname{X} = \operatorname{E}\operatorname{X}^2 - \operatorname{E}^2\operatorname{X}$
 - $\operatorname{Var}\operatorname{X} = 0 \Leftrightarrow \operatorname{P}(\operatorname{X} \neq \operatorname{E}\operatorname{X}) = 0$
 - $\operatorname{Var}\operatorname{X} = \min\limits_{a \in \R} \operatorname{E}((\operatorname{X} - a)^2)$

Seien $\operatorname{X}, \operatorname{Y}, \operatorname{Z}$ Zufallsvariablen mit endlichen _zweiten Momenten_. Dann gilt:
 - $\operatorname{Kov}(\operatorname{X}, \operatorname{Y}) = \operatorname{E}(\operatorname{X} \cdot \operatorname{Y}) - \operatorname{E}\operatorname{X} \cdot \operatorname{E}\operatorname{Y}$
 - $\operatorname{Kov}(\operatorname{X},\operatorname{X}) = \operatorname{Var}\operatorname{X}$
 - $\operatorname{Kov}(\operatorname{X}, \operatorname{Y}) = \operatorname{Kov}(\operatorname{Y}, \operatorname{X})$
 - $\operatorname{Kov}(a + b\operatorname{X}, c + d\operatorname{Y}) = bd \operatorname{Kov}(\operatorname{X}, \operatorname{Y})$
 - $\operatorname{X},\operatorname{Y}$ stochastisch unabhängig $\Rightarrow \operatorname{Kov}(\operatorname{X},\operatorname{Y})=0$
 - $\operatorname{Kov}(\operatorname{X} + \operatorname{Y}, \operatorname{XZ}) = \operatorname{Kov}(\operatorname{X}, \operatorname{Z}) + \operatorname{Kov}(\operatorname{Y}, \operatorname{Z})$

#### Verschiebungssatz
$$\operatorname{E}((\operatorname{X} - a)^2) = \operatorname{Var}\operatorname{X} + (\operatorname{E}\operatorname{X} - a)^2, a \in \R$$

#### Standardisierung
 - Eine Zufallsvariable $\operatorname{X}$ mit $\operatorname{E}\operatorname{X} = 0$ und $\operatorname{Var}\operatorname{X} = 1$ heißt **standardisiert**.
 - Ist eine Zufallsvariable $\operatorname{Y}$ mit $\operatorname{E}\operatorname{Y} = \mu$ und $0 < \operatorname{Var}\operatorname{Y} = \sigma^2 \leq \infty$, dann gilt für die Zufallsvariable $X = \frac{\operatorname{Y} - \operatorname{E}\operatorname{Y}}{\sqrt{\operatorname{Var}\operatorname{Y}}} = \frac{\operatorname{Y} - \mu}{\sigma}$: $$\operatorname{E}\operatorname{X} = 0, \operatorname{Var}\operatorname{X} = 1$$ &rarr; **Standardisierung**

#### Summen von Zufallsvariablen
Seien $\operatorname{X}, \operatorname{Y}$ Zufallsvariablen mit endlicher Varianz. Dann gilt: $$\operatorname{Var}(\operatorname{X} + \operatorname{Y}) = \operatorname{Var}\operatorname{X} + \operatorname{Var}\operatorname{Y} + 2 \cdot \operatorname{Kov}(\operatorname{X}, \operatorname{Y})$$

#### Korrelationskoeffizent
$$\operatorname{Korr}(\operatorname{X}, \operatorname{Y}) \coloneqq \frac{\operatorname{Kov}(\operatorname{X}, \operatorname{Y})}{\sqrt{\operatorname{Var}\operatorname{X}} \cdot \sqrt{\operatorname{Var}\operatorname{Y}}} \in [-1,1]$$ heißt **Korrelationskoeffizent**. Sie wird mit $\rho = \rho_{\operatorname{X}\operatorname{Y}}$ bezeichnet.

#### Varianzformel
Seien $\operatorname{X}_1, \dots, \operatorname{X}_n$ unkorrelierte Zufallsvariablen. Dann gilt: $$\operatorname{Var}(\sum\limits_{i=1}^n \operatorname{X}_i) = \sum\limits_{i=1}^n \operatorname{Var}(\operatorname{X}_i)$$

---------------

<br>

# Erzeugende Funktionen
## Wahrscheinlichkeitserzeugende Funktion
Sein $\operatorname{X}$ eine Zufallsvariable mit diskreter oder stetiger Wahrscheinlichkeitsverteilung $\operatorname{P}^{\operatorname{X}}$. Die Funktion $\operatorname{g}$ mit $$\operatorname{g}(t) = \operatorname{E}t^{\operatorname{X}}$$ für alle $t$, für die ein $\operatorname{E}t^{\operatorname{X}}$ endlich existiert, heißt **wahrscheinlichkeitserzeugende Funktion**.

 - Hat $\operatorname{X}$ eine diskrete Wahrscheinlichkeitsverteilung auf $\N_0$ mit $\operatorname{p}_k = \operatorname{P}(\operatorname{X} = k), k \in \N_0$, so ist die erzeugende Funktion gegeben durch $$\operatorname{g}(t) = \operatorname{E}t^{\operatorname{X}} = \sum\limits_{k=0}^{\infty} t^k \operatorname{p}_k$$ für alle $t$ aus dem Kovergenzbereich $K$ dieser Potenzreihe.
 - $\operatorname{g}$ ist beliebig oft differenzierbar in $t=0$ und es gilt $$\operatorname{p}_k = \frac{1}{k!}\operatorname{g}^{(k)}(0)$$, wobei $\operatorname{g}^{(k)}$ die $k$-te Ableitung bezeichnet.

## Momenterzeugende Funktion
Sei $\operatorname{X}$ eine Zufallsvariable mit diskrete oder stetiger Wahrscheinlichkeitsverteilung $\operatorname{P}^{\operatorname{X}}$. Die Funktion $\operatorname{h}$ mit $$\operatorname{h}(t) = \operatorname{E}e^{t\operatorname{X}}, t \in D = \{z \in \R \mid \operatorname{E}e^{z\operatorname{X}} < \infty\}$$ heißt **momenterzeugende Funktion**.

Enthalte $D$ ein Intervall der Form $(-\epsilon, \epsilon)$ für ein $\epsilon > 0$. Dann gilt
 - $\operatorname{h}$ bestimmt die zugrundeliegende Wahrscheinlichkeitsverteilung eindeutig.
 - Es existieren alle absoluten Momente $\operatorname{E}(\vert \operatorname{X} \vert ^k)$ endlich.
 - $\operatorname{h}$ ist im Nullpunkt beliebig oft differenzierbar und es gilt $$\operatorname{h}^{(k)}(0) = \operatorname{E}\operatorname{X}^k$$

---------------

<br>