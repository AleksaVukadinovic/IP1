# Stabla (Decision Tree)

Ne treba pretprocesiranje

---

# KNN

**Obavezno** pretprocesiranje, koristiti StandardScaler ili MinMaxScaler

---

# Naivni Bajes

- CategoricalNB: Ponekad je potebno pretprocesiranje u obliku encodovanja kategorija (OrdinalEncoder)
- MultinomialNB: Koristi se kod broja ponavljanja reci, prethodno treba koristiti CounteVectorizer(TF) ili tfIDFVectorizr(tfIDF)

---

# PCA

**Obavezno prerptocesiranje**, koristiti StandardScaler za raspon \[0,1\]

---

# SVC

Treba pretprocesiranje (StandardScaler ili MinMaxScaler)

---

# K - Means

**Obavezno** - Moze i Standard i MinMax

---

# Hijerarhijsko klasterovanje

Pozeljno pretprocesiranje, moze i Standard i MinMax

---

# DBSCAN

Potrebno, moze i Standard i MinMax