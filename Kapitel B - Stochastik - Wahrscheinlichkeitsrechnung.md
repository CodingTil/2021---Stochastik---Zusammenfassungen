# Gliederung
 - [Grundlagen der Wahrscheinlichkeitsrechnung](#grundlagen-der-wahrscheinlichkeitsrechnung)
 - [Diskrete Wahrscheinlichkeitsverteilung](#diskrete-wahrscheinlichkeitsverteilung)

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

| Ziehen von $k$ Kugeln aus $n$ Kugeln | mit Zurücklegen | ohne Zurücklegen |
| :--- | :---: | :---: |
| **mit Reihenfolge** | $(n,k)$-Permitation mit Wiederholung $$\vert \Omega_{\operatorname{PmW}} \vert = n^{k}$$ | $(n,k)$-Permitation ohne Wiederholung $$\vert \Omega_{\operatorname{PoW}} \vert = \frac{n!}{(n-k)!}$$ |
| **ohne Reihenfolge** | $(n,k)$-Kombination mit Wiederholung $$\vert \Omega_{\operatorname{KmW}} \vert = {{n+k-1} \choose k}$$ | $(n,k)$-Kombination ohne Wiederholung $$\vert \Omega_{\operatorname{KoW}} \vert = {n \choose k}$$ |

---------------

<br>

# Diskrete Wahrscheinlichkeitsverteilung

---------------

<br>

