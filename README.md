# 🏥 HealthConnect Clinic - Week 7 Data Science

[![Python](https://img.shields.io/badge/Python-3.8+-blue.svg)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)
[![AnalystLab Africa](https://img.shields.io/badge/AnalystLab-Africa-orange.svg)](https://analystlab.africa)
[![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-orange.svg)](https://jupyter.org/)

---

## 📋 Table des Matières

1. [Présentation du Projet](#-présentation-du-projet)
2. [Structure du Dépôt](#-structure-du-dépôt)
3. [Résultats Week 7](#-résultats-week-7)
4. [Tests Effectués](#-tests-effectués)
5. [Synthèse des Tests](#-synthèse-des-tests)
6. [HC-POD Cross-Track](#-hc-pod-cross-track)
7. [Validation et Recommandations](#-validation-et-recommandations)
8. [Technologies](#-technologies)
9. [Contact](#-contact)

---

## 🎯 Présentation du Projet

**HealthConnect Clinic** fait face à un défi majeur : **45% de rendez-vous manqués** (No-Show).

L'objectif est de développer un modèle de Machine Learning pour prédire les No-Show.

### Problème ML

| Élément | Description |
|---------|-------------|
| **Type** | Classification binaire |
| **Cible** | `no_show` (1 = manqué, 0 = présent) |
| **Métrique principale** | F1-Score |
| **Objectif Week 7** | Tester, raffiner et valider le modèle |

---

## 📊 Résultats Week 7

### Objectifs de Test

| Test | Objectif | Critère |
|------|----------|---------|
| Test 1 | Robustesse | F1 > 0.65 |
| Test 2 | Généralisation | F1 > 0.65 |
| Test 3 | Stabilité | Écart-type < 0.02 |
| Test 4 | Optimisation seuil | F1 > 0.70 |
| Test 5 | Performance segment | F1 > 0.60 |
| Test 6 | Overfitting | Écart < 0.05 |

---

## 📈 Tests Effectués

### Test 1 : Cross-Validation 10-fold

| Modèle | F1 moyen | Écart-type | Statut |
|--------|----------|------------|--------|
| Baseline (LR) | 0.6448 | ± 0.0204 | ❌ FAIL (proche) |
| Random Forest | 0.6221 | ± 0.0247 | ❌ FAIL |

### Test 2 : Généralisation

| Métrique | Résultat | Critère | Statut |
|----------|----------|---------|--------|
| F1-Score | 0.6336 | > 0.65 | ❌ FAIL (proche) |

### Test 3 : Stabilité

| Métrique | Résultat | Critère | Statut |
|----------|----------|---------|--------|
| Moyenne | 0.6407 | - | - |
| Écart-type | 0.0186 | < 0.02 | ✅ PASS |

### Test 4 : Optimisation du Seuil

| Métrique | Résultat | Critère | Statut |
|----------|----------|---------|--------|
| Seuil optimal | 0.30 | - | - |
| F1-Score optimal | 0.6945 | > 0.70 | ❌ FAIL (proche) |

### Test 5 : Performance par Segment

| Tranche d'âge | F1 | Patients | Statut |
|---------------|-----|----------|--------|
| 18-34 | 0.6549 | 267 | ✅ PASS |
| 35-49 | 0.6589 | 231 | ✅ PASS |
| 50-64 | 0.6412 | 237 | ✅ PASS |
| 65+ | 0.6108 | 213 | ✅ PASS |

### Test 6 : Détection d'Overfitting

| Métrique | Résultat | Critère | Statut |
|----------|----------|---------|--------|
| F1 Train | 0.6449 | - | - |
| F1 Test | 0.6435 | - | - |
| Écart | 0.0014 | < 0.05 | ✅ PASS |

---

## 📊 Synthèse des Tests

| Test | Résultat | Critère | Statut | Écart |
|------|----------|---------|--------|-------|
| Cross-validation 10-fold | 0.6448 | > 0.65 | ❌ FAIL (proche) | -0.005 |
| Généralisation | 0.6336 | > 0.65 | ❌ FAIL (proche) | -0.016 |
| Stabilité | 0.0186 | < 0.02 | ✅ PASS | - |
| Optimisation seuil | 0.6945 | > 0.70 | ❌ FAIL (proche) | -0.005 |
| Performance segment | 0.61-0.66 | > 0.60 | ✅ PASS | - |
| Overfitting | 0.0014 | < 0.05 | ✅ PASS | - |

**📌 Bilan : 3 PASS / 3 FAIL** — Tous les FAIL sont très proches des objectifs.

---

## 🤝 HC-POD Cross-Track

### Partenaire : Data Analytics

| # | Élément | Détail |
|---|---------|--------|
| 1 | Track collaboré | Data Analytics |
| 2 | Dépendance | KPIs → Features |
| 3 | Composant testé | Modèle No-Show |
| 4 | Reçu | KPIs validés |
| 5 | Fourni | Feature importance |
| 6 | Test | Validation croisée |
| 7 | Finding | Écart sur segments |
| 8 | Raffinement | Seuil ajusté (0.30) |
| 9 | Re-test | F1 = 0.6945 |
| 10 | Changement | +5.1 points de F1 |
| 11 | Preuve | Document + capture |
| 12 | Contribution | Meilleure précision |

---

## 📋 Validation et Recommandations

### Critères de Validation

| Critère | Objectif | Réalisé | Statut |
|---------|----------|---------|--------|
| Cross-validation | > 0.65 | 0.6448 | ❌ (proche) |
| Généralisation | > 0.65 | 0.6336 | ❌ (proche) |
| Stabilité | < 0.02 | 0.0186 | ✅ |
| Optimisation seuil | > 0.70 | 0.6945 | ❌ (proche) |
| Performance segment | > 0.60 | 0.61-0.66 | ✅ |
| Overfitting | < 0.05 | 0.0014 | ✅ |

### Recommandations Week 8

1. 🔴 Optimiser les hyperparamètres
2. 🔴 Réduire les Faux Négatifs (161 cas)
3. 🟡 Intégrer avec le pipeline ML Engineering
4. 🟡 Valider avec les parties prenantes
5. 🟡 Préparer la présentation finale

---

## 🛠️ Technologies

| Technologie | Version |
|-------------|---------|
| Python | 3.8+ |
| Pandas | 1.5.0 |
| NumPy | 1.23.0 |
| Scikit-learn | 1.2.0 |
| Matplotlib | 3.6.0 |
| Seaborn | 0.12.0 |
| Jupyter | - |

---

## 📞 Contact

- **Nom** : SOGA Para
- **Email** : sparadodaniel@gmail.com
- **Programme** : AnalystLab Africa
- **Track** : Data Science

---

## 📌 Tags

`#DataScience` `#MachineLearning` `#Healthcare` `#AnalystLabAfrica` 
`#HealthConnect` `#Python` `#Classification` `#LogisticRegression`

---

**Fait avec ❤️ dans le cadre du programme AnalystLab Africa Experience Lab**
