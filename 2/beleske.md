# Vežbe 2

## Bliskost – Sličnost i različitost

### Sličnost
- Numerička mera koliko su dva objekta slična  
- Što dva objekta više liče jedan na drugi, sličnost je veća  
- Često se meri vrednostima u intervalu **[0,1]**  

### Različitost
- Numerička mera koliko su dva objekta različita  
- Što dva objekta više liče jedan na drugi, različitost je manja  
- Najmanja različitost je obično **0**, gornja granica može varirati  
- Sinonim: **rastojanje**  

👉 **Blizina (eng. proximity)** označava ili sličnost ili različitost.  

---

## Različitost između objekata podataka

### Rastojanje Minkovskog
\[
dist(p, q) = \left( \sum_{k=1}^n |p_k - q_k|^r \right)^{1/r}
\]

Gde je:  
- `r` – parametar  
- `n` – broj dimenzija (atributa)  
- `p_k` i `q_k` – vrednosti k-tog atributa objekata **p** i **q**  

#### Posebni slučajevi:
- **r = 1** → Menhetn (L1 norma) rastojanje  
  - *Hamingovo rastojanje* (za binarne vektore)  
- **r = 2** → Euklidsko rastojanje  
- **r → ∞** → Supremum (Lmax norma) rastojanje  
  - Maksimalna razlika između komponenti vektora  

👉 Pre izračunavanja rastojanja često se radi **standardizacija** ili **normalizacija** atributa.  

---

### Rastojanje binarnih vektora

Za objekte predstavljene binarnim vektorima definišu se:  
- **M₀₁** – broj atributa koji su `0` u p i `1` u q  
- **M₁₀** – broj atributa koji su `1` u p i `0` u q  
- **M₀₀** – broj atributa koji su `0` u p i `0` u q  
- **M₁₁** – broj atributa koji su `1` u p i `1` u q  

---

## Priprema podataka

- **Diskretizacija** – transformacija neprekidnog atributa u kategorijski atribut  
- **Binarizacija** – transformacija atributa u jedan ili više binarnih atributa  
