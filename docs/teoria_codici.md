
## Codici a Blocco lineari

Rate $R=\cfrac{k}{n}$

Sia $u=[u_1,\dots, u_k]$ una generica parola di $k$ cifre binarie.\\
Il Codice a blocco lineare $C(k,n)\sub \cal{V_n}$ è l'insieme delle $2^k$ parole $x=[x_1, \dots, x_n]$ di $n$ cifre binarie ottenute con la trasformazione lineare:
$$x=uG$$

La matrice generatrice $G$ del codice ha dimensione $k\times n$
$$\begin{array}{c|ccc}
   & g_{11} & \cdots & g_{1n} \newline
   k &\vdots & \ddots & \vdots\newline
   & g_{k1} & \cdots & g_{kn} \newline \hline
   & & n &
\end{array}$$

La matrice generatrice $G$ in forma sistematica:
$$
G=[I_k|P] \newline
G\in k \times n,\quad I \in k \times k,\quad P \in k \times (n-k)
$$

Dove $P$ è la matrice di parità.

La matrice di controllo di parità $H$ è tale che per costruzioine:
$$\forall x \in C(k,n) \quad xH^T=0$$
$$
H = [P^T, I_{n-k}]\newline
H \in (n-k) \times n, \quad I \in (n-k) \times (n-k), \quad P^T \in (n-k) \times k
$$

- Rivelazione errore fino a: $d_{\text{min}}-1$
- Correzione errore fino a: $\left\lfloor\cfrac{d_{\text{min}}-1}{2}\right\rfloor$

## Cidici di Hamming

I codici di Hamming $C_H(m)$ sono definiti a partire da un parametro $m\ge 2$
$$C_H(m) = C(k,n) \quad\begin{cases} n=2^m-1\newline k=n-m\end{cases}$$

La matrice di di parità $P$ viene costruita in modo tale che le colonne di $H$ siano tutte le possibili $2^m-1$ combinazioni di $m$ bit (esclusa la n-tupla di tutti $0$)

## Coset

Sia $C(k,n)$ un codice a blocco e sia $v\in \cal{V_n}$ un vettore di $n$ cifre binarie, sin definisce $coset$ di $C(k,n)$ individuato da $v$ l'insieme:
$$C_v = C+v=\Set{x+v|x\in C}$$

- Ciascuno coset contiene $2^k$ elementi
- Ci sono $2^{n-k}$ coset distinti
- Il coset leader è la parola di peso minimo del coset $C_y$

## Sindrome

$$
s=yH^T=(x+e)H^T=xH^T+eH^T=eH^T
$$

> **NOTE**\
> Se ci troviamo in un codice di Hamming, la matrice $H$ avrà come colonne tutte le possibili combinazioni di $2^m-1$ bit; Quindi quando calcoliamo la sindrome $s=yH^T$ sarà uguale ad una colonna della matrice $H$, per cui il vettore $e$ avrà un 1 in posizione della colonna trovata.

## Codici Ciclici

Il polinomio generatore di un codice ciclico $C(k,n)$ è il polinomio 
$$g(D)=1+g_1D+\dots+D^r$$
non nullo e di grado minimo in $C(k,n)$

- Il numero di parole del codice è $2^k$
- $r = n-k$
- Un polinomio $g(D)$ è generatore di un codice ciclico $C(k,n)\iff g(D)$ è un divisore di $D^n-1$

