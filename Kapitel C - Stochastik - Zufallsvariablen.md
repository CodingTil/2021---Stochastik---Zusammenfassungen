# Gliederung
 - [Zufallsvariablen und Wahrscheinlichkeitsmaße](#zufallsvariablen-und-wahrscheinlichkeitsmaße)
 - [Verteilungsfunktion und Quantilfunktion](#verteilungsfunktion-und-quantilfunktion)
 - [Mehrdimensionale Zufallsvariablen und Verteilungen](#mehrdimensionale-zufallsvariablen-und-verteilungen)

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

---------------

<br>

