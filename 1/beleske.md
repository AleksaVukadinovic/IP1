# Istraživanje podataka

**Istraživanje podataka** je proces automatskog otkrivanja korisnih informacija u velikom skladištu podataka.

## Faze istraživanja podataka
1. Priprema podataka  
2. Primena tehnika istraživanja podataka  
3. Evaluacija rezultata  
4. Primena rezultata  

---

## Tipovi učenja

### Nadgledano učenje
- **Klasifikacija** – raspoređivanje objekata u kategorije (klase)  
- **Regresija** – predviđanje neprekidnih vrednosti  

### Nenadgledano učenje
- **Klasterovanje** – grupisanje sličnih podataka  

---

## Predstavljanje podataka

- **Tabela podataka** – redovi su objekti, kolone su atributi objekata  
- **Slike**  
  - Grayscale: `h × w`  
  - RGB: `h × w × 3` (kanali)  
- **Grafovi** – primer: društvene mreže (klasifikacija uticajnih ljudi)  
- **Tekstualni podaci** – klasifikacija članaka pomoću frekvencija reči  
  - **TF matrica** (Term Frequency) – redovi su dokumenti, kolone reči  
  - **IDF** (Inverse Document Frequency):  
    \[
    \text{IDF}(t) = \log \frac{N}{n_t}
    \]  
    gde je `N` broj dokumenata, a `n_t` broj dokumenata koji sadrže termin `t`.

---

# Skupovi podataka i atributi

## Tipovi podataka
- **Vremenski podaci** – video, zvuk, EKG (x-osa vreme, y-vrednost funkcije)  
- **Prostorni podaci** – npr. temperatura  
- **Redosledni podaci** – npr. DNK sekvence  

Ne rade isti algoritmi za sve tipove, potrebno ih je prilagoditi.

---

## Podela atributa prema operacijama

1. **Imenski (nominalni)** – razlika `=`, `≠`  
   - Primer: `Pera = Pera`, `Pera ≠ Jelena`  
   - Uređivanje leksikografski moguće, ali bez stvarnog smisla  

2. **Redni (ordinalni)** – razlika + uređenost `<, >`  
   - Primer: saradnik < asistent < docent < profesor  

3. **Intervalni** – razlika, uređivanje, aditivnost  
   - Primer: `3.2.2022 < 5.3.2022`, može se računati razlika datuma  

4. **Razmerni (ratio)** – sve operacije uključujući i množenje/deljenje  
   - Primer: udaljenost između gradova  

👉 1 i 2 = **kvalitativni atributi**  
👉 3 i 4 = **kvantitativni atributi**  

---

## Podela atributa prema vrednostima

- **Diskretni** – konačan ili prebrojivo beskonačan skup vrednosti  
  - *Specijalni slučaj*: binarni atributi  
- **Kontinuirani** – vrednosti iz skupa realnih brojeva  

### Asimetrični (retki) podaci
- Prisustvo nenultih vrednosti je značajno  
- Asimetrični binarni atributi – bitne su nenulte vrednosti  

---

## Zadatak: klasifikacija atributa

- Starost u godinama → **diskretan, kvantitativan, razmerni**  
- Vreme u oznakama AM/PM → **binarni, kvalitativni, redni**  
- Osvetljenje (ljudskom procenom) → **diskretan, kvalitativan, redni**  
- Uglovi u stepenima → **neprekidan, kvantitativan, razmerni**  
- Medalje (bronza, srebro, zlato) → **diskretan, kvalitativan, redni**  
- ISBN brojevi knjiga → **diskretan, kvalitativan, imenski**  
- Providnost (neproziran, poluprovidan, transparentan) → **diskretan, kvalitativan, redni**  
- Rang u vojsci → **diskretan, kvalitativan, redni**  
- Rastojanje od centra kampusa → **neprekidan, kvantitativan, razmerni**  
- Broj garderobe → **diskretan, kvalitativan, imenski**  

---

## Tipovi skupova podataka

- **Slogovi**
  - Matrica podataka (numerički atributi)  
  - Dokumenti (atributi istog tipa, često asimetrični)  
  - Transakcioni podaci (objekat = skup stavki)  
- **Grafovi**  
- **Podaci sa poretkom**
  - Prostorni  
  - Vremenski (zavisni)  
  - Redosledni  

---

# Šum i elementi van granice

- **Šum** – modifikacija originalnih vrednosti (npr. greška u unosu)  
- **Elementi van granica (outliers)** – objekti čije su vrednosti značajno različite od većine  

### Poređenje
- Da li je šum interesantan? → **Ne**  
- Da li su outlieri interesantni? → **Da**  
- Može li objekat sa šumom biti outlier? → **Da**  
- Da li su svi objekti sa šumom outlieri? → **Ne**  
- Da li su svi outlieri rezultat šuma? → **Ne**  
- Može li šum pretvoriti očekivanu vrednost u neuobičajenu ili obrnuto? → **Da**  
