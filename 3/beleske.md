# Vežbe 3

## Klasifikacija

**Nadgledano učenje:**
- **Regresija**: \( X, Y, \; Y \in \mathbb{R} \)  
- **Klasifikacija**: \( X, Y, \; Y \) je klasa (kategorija)  

Podela podataka:
- **Skup za treniranje (train set)**
- **Skup za testiranje (test set)**

### Preprilagođavanje (overfitting)
- Model se previše prilagođava trening skupu, gubi sposobnost generalizacije  

### Potprilagođavanje (underfitting)
- Model ne uspeva da se prilagodi čak ni trening podacima  

### Mere performansi
- **Tačnost (accuracy)**  
  \[
  \text{accuracy} = \frac{\text{dobro predviđeni}}{\text{ukupno}}
  \]  

- **Stopa greške (error rate)**  
  \[
  \text{error rate} = \frac{\text{promašeni}}{\text{ukupno}}
  \]  

---

## Stabla odlučivanja (Decision Trees)

Na osnovu uslova delimo skup na dva dela, npr:

```
                 Age < 30 
        YES  /             \ NO
            /               \
        Eat pizza?          Exercise?
   YES /        \ NO     YES /        \ NO
      /          \          /          \
  Unfit           Fit     Fit           Unfit
```

- Čvor je **čist** ako sadrži 100% instanci  
- Ako svi listovi postanu čisti → 100% tačnost na trening skupu (ne znači mnogo)  
- **Uvek možemo dobiti čiste čvorove** – ali to vodi do **overfittinga**  

### Sprečavanje overfittinga
- Ograničiti dubinu stabla  
- Pustiti da raste pa zatim skratiti grane (**pruning**)  

---

## Mere nečistoće

Za čvor \( t \):  
- \( p(j|t) \) = relativna frekvencija klase \( j \) u čvoru \( t \)  

**1. Ginijev indeks**  
\[
Gini(t) = 1 - \sum_j (p(j|t))^2
\]

**2. Entropija**  
\[
Entropy(t) = - \sum_j p(j|t) \cdot \log_2(p(j|t))
\]

**3. Greška klasifikacije**  
\[
Error(t) = 1 - \max_j p(j|t)
\]

**4. Dobit (information gain)**  
- Razlika u nečistoći pre i posle podele  

---

## Napomene
- Granica u čvorovima može da se razlikuje  
- Atributi se mogu menjati po čvorovima  
- Algoritam je **rekurzivan**  
- Najčešće se bira čvor sa najboljim Ginijem → lokalno najbolje, ne nužno globalno  

---

## Primeri

### 1. Entropija skupa trening podataka
\[
p(+) = \tfrac{4}{9}, \quad p(-) = \tfrac{5}{9}
\]  

\[
Entropy(root) = -\frac{4}{9}\log_2\left(\frac{4}{9}\right) - \frac{5}{9}\log_2\left(\frac{5}{9}\right)
\]  

---

### 2. Klasifikacija životinje na osnovu osobina  
*(Velika, Biljke, Da)* – proceniti opasnost korišćenjem stabla odlučivanja dubine 2 (Ginijev indeks).  

#### Podela po veličini

```
                  Velicina
       velika    /        \ mala
              3 da          2 da
              0 ne          3 ne
```

\[
Gini(velika) = 1 - (3/3)^2 - (0/3)^2 = 0
\]  

\[
Gini(mala) = 1 - (2/5)^2 - (3/5)^2 = \tfrac{12}{25}
\]  

\[
Gini(velicina) = \tfrac{3}{8} \cdot 0 + \tfrac{5}{8} \cdot \tfrac{12}{25} = \tfrac{3}{10} = 0.3
\]  

---

#### Podela po ishrani

```
                  Ishrana
           meso  /       \ biljke
           3 da            2 da
           1 ne            2 ne
```

\[
Gini(ishrana) = \frac{4}{8}\left(1 - \left(\tfrac{3}{4}\right)^2 - \left(\tfrac{1}{4}\right)^2\right) + \frac{4}{8}\left(1 - \left(\tfrac{2}{4}\right)^2 - \left(\tfrac{2}{4}\right)^2\right)
\]  

\[
Gini(ishrana) \approx 0.44
\]  

---

#### Podela po otrovnosti
\[
Gini(otrovnost) = 0.3
\]  
