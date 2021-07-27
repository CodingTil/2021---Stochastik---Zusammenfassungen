# Gliederung
 - [Problemstellungen der Schließenden Statistik](#problemstellungen-der-schließenden-statistik)
 - [Punktschätzungen](#punktschätzungen)
 - [Maximum-Likelihood-Schätzung](#maximum-likelihood-schätzung)
 - [Konfidenzintervalle](#konfidenzintervalle)
 - [Schätzungen bei Normalverteilungen](#schätzungen-bei-normalverteilungen)

---------------

# Problemstellungen der Schließenden Statistik
Ist $\operatorname{T}: \R^n \rightarrow \R$ eine Funktion der Stichprobe $(\operatorname{X}_1, \dots, \operatorname{X}_n)$, so wird $\operatorname{T}(\operatorname{X}_1, \dots, \operatorname{X}_n)$ als **Statistik** bezeichnet.
 - Im Schätzkontext wird sie auch als **Schätzer**,
 - bei der Verwendung im Rahmen von Hypothesentests **Teststatistik** genannt.

Kann jedes Element $\operatorname{P} \in \mathcal{P}$ eindeutig durch die Angabe eines Parameter(-vektors) $\vartheta \in \Theta \subseteq \R^k$ identifiziert werden, so heißt das Verteilungsmodell **parametrische Verteilungssannahme**: $$\mathcal{P} = \{\operatorname{P}_\vartheta \mid \vartheta \in \Theta\}$$
Die Menge $\Theta$ der möglichen Parameter heißt **Parameterraum**.
Ist keine derartige Parametrisierung gegeben, wird das Modell als **nichtparametrisches Verteilungsmodell** bezeichnet.

---------------

<br>

# Punktschätzungen
Sei $(\operatorname{X}_1, \dots, \operatorname{X}_n)$ eine Stichprobe. Dann heißen:
 - $\overline{\operatorname{X}} = \frac{1}{n} \sum\limits_{i=1}^n \operatorname{X}_i$ **Stichprobenmittel**
 - $\hat{\sigma}^2 = \frac{1}{n-1} \sum\limits_{i=1}^n (\operatorname{X}_i - \overline{\operatorname{X}})^2$ **Stichprobenvarianz**
 - $\hat{\sigma}_\mu^2 = \frac{1}{n} \sum\limits_{i=1}^n (\operatorname{X}_i - \mu)^2$ die mittlere quadratische Abweichung von $\mu$
 - $\operatorname{S}^2 = \frac{1}{n} \sum\limits_{i=1}^n (\operatorname{X}_i - \overline{\operatorname{X}})^2$ die **mittlere quadratische Abweichung**

Sei $\operatorname{X}_1, \dots, \operatorname{X}_n \overset{iid}{\sim} \operatorname{P}_\vartheta, \vartheta \in \Theta$ ein parametrisches Verteilungsmodell. Ein Schätzer $\hat{\vartheta}$ heißt **erwartungstreu** für den Parameter $\vartheta$, falls $$\operatorname{E}_\vartheta \hat{\vartheta} = \vartheta$$

### Erzeugung von erwartungstreuen Schätzern mittels linearer Transformation
Sei $\operatorname{X}_1, \dots, \operatorname{X}_n \overset{iid}{\sim} \operatorname{P}_\vartheta, \vartheta \in \Theta$ und $\tilde{\vartheta} = \tilde{\vartheta}(\operatorname{X}_1, \dots, \operatorname{X}_n)$ ein Schätzer für $\vartheta$ mit $$\operatorname{E}_\vartheta \tilde{\vartheta} = a_n + b_n \vartheta$$ wobei $a_n,b_n \in \R, b_n \neq 0$ bekannte Werte sind. Dann ist durch $$\hat{\vartheta} = \frac{\tilde{\vartheta} - a_n}{b_n}$$ eine erwartungstreue Schätzung für $\vartheta$ gegeben.

### Mittlerer quadratischer Fehler
Der mittlere quadratische Fehler **MSE** (_mean square error_) eines Schätzers $\hat{\vartheta}$ bzgl. des Parameters $\vartheta$ ist definiert durch $$\operatorname{MSE}_\vartheta(\hat{\vartheta}) = \operatorname{E}_\vartheta (\hat{\vartheta} - \vartheta)^2$$

Sei $\hat{\vartheta}$ eine Schätzung für $\vartheta$. Dann gilt: $$\operatorname{MSE}_\vartheta (\hat{\vartheta}) = \operatorname{Var}_\vartheta (\hat{\vartheta}) + (\operatorname{E}_\vartheta \hat{\vartheta} - \vartheta)^2$$
 - Der Term $\operatorname{E}_\vartheta \hat{\vartheta} - \vartheta$ heißt **Verzerrung** oder **Bias** des Schätzers.

---------------

<br>

# Maximum-Likelihood-Schätzung
Seien $\operatorname{X}_1, \dots, \operatorname{X}_n \overset{iid}{\sim} \operatorname{P}_\vartheta, \vartheta \in \Theta$ sowie $x_1, \dots, x_n$ eine Realisation von $\operatorname{X}_1, \dots, X_n$. Dann heißt die durch $$\operatorname{L}(\vartheta \mid x_1, \dots, x_n) = \begin{cases} \prod\limits_{i=1}^n \operatorname{P}_\vartheta(\operatorname{X}_i = x_i), & \operatorname{P}_\vartheta \text{ diskrete Verteilung} \\
\prod\limits_{i=1}^n \operatorname{f}_\vartheta(x_i), & \operatorname{P}_\vartheta \text{ stetige Verteilung mit Dichte } \operatorname{f}_\vartheta \end{cases}$$ definierte Funktion $\operatorname{L}(\cdot \mid x_1, \dots, x_n): \Theta \rightarrow \R$ **Likelihoodfunktion**.
Der Logarithmus der Likelihoodfunktion wird og-Likelihoodfunktion genannt und mit $l = \ln \operatorname{L}$ bezeichnet.

---------------

<br>

# Konfidenzintervalle
Seien $\alpha \in  (0,1)$ eine feste vorgegebene Wahrscheinlichkeit sowie $$\operatorname{X}_1, \dots, \operatorname{X}_n \sim \operatorname{P}_\vartheta, \vartheta \in \Theta \subseteq \R$$. Ein Intervall $[\hat{u}, \hat{o}]$ heißt **Intervallschätzung** oder **Konfidenzintervall** zum Niveau $1 - \alpha$ für den Parameter $\vartheta$, falls $$\operatorname{P}_\vartheta (\vartheta \in [\hat{u}, \hat{o}]) \geq 1 - \alpha$$ Hierbei sind $\hat{u} = \hat{u}(\operatorname{X}_1, \dots, \operatorname{X}_n)$ und $\hat{o} = \hat{o}(\operatorname{X}_1, \dots, \operatorname{X}_n$ Statistiken mit $\hat{u}(x_1, \dots, x_n) \leq \hat{o}(x_1, \dots, x_n)$
$1 - \alpha$ heißt **Konfidenzniveau**.

---------------

<br>

# Schätzungen bei Normalverteilungen
Für $\operatorname{X}_1, \dots, \operatorname{X}_m \overset{iid}{\sim} \operatorname{N}(\mu, \sigma^2)$ ($\mu$ oder $\sigma^2>0$ unbekannt) ist der Maximum-Likelihood-Schätzer gegeben durch:
 - $\hat{\mu} = \overline{\operatorname{X}}$ _($\mu$ unbekannt, $\sigma^2>0$ bekannt)_
 - $\hat{\sigma}_\mu^2 = \frac{1}{n} \sum\limits_{i=1}^n (\operatorname{X}_i - \mu)^2$ _($\mu$ bekannt, $\sigma^2>0$ unbekannt)_
 - $(\hat{\mu}, \tilde{\sigma}^2)$ mit $\hat{\mu} = \overline{\operatorname{X}}$, $\tilde{\sigma}^2 = \operatorname{S}^2 = \frac{1}{n} \sum\limits_{i=1}^n (\operatorname{X}_i - \overline{X})^2.$ _(beides unbekannt)_