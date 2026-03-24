Description
# BAN_Cadastre_FR
Jeu de données France enrichi à partir de la Base Adresse Nationale (BAN), croisée avec le cadastre officiel. Chaque fichier contient jusqu’à 200 000 lignes pour faciliter la manipulation.

---

# 🇫🇷 BAN France enrichie avec Cadastre

## 📄 Description

Ce dépôt contient les fichiers d’adresses de la **Base Adresse Nationale (BAN)** pour la France métropolitaine, enrichis avec les informations cadastrales.

---

## 🔗 Sources des données

Les données proviennent de sources officielles :

* **Base Adresse Nationale (BAN)** : [https://adresse.data.gouv.fr/data/ban/adresses/latest/csv-with-ids](https://adresse.data.gouv.fr/data/ban/adresses/latest/csv-with-ids)
* **Cadastre (GéoJSON)** : [https://files.data.gouv.fr/cadastre/etalab-cadastre/2023-01-01/geojson/departements](https://files.data.gouv.fr/cadastre/etalab-cadastre/2023-01-01/geojson/departements)

Ces fichiers ont été traités et découpés pour créer cette version enrichie.

---

## 📦 Contenu

* Données d’adresses enrichies avec identifiants cadastraux
* Fichiers organisés par département
* Format CSV

Chaque ligne peut contenir :

* 1 ou plusieurs parcelles cadastrales
* des informations de correspondance (type de match, distance, confiance)

## 🧠 Méthodologie

Les données sont générées via un pipeline Python basé sur :

* jointure spatiale (`within`) entre adresses et parcelles
* fallback `nearest` avec distance calculée
* score de confiance basé sur la distance

Types de correspondance :

* `exist` → déjà présent dans la BAN
* `within` → adresse dans la parcelle (100%)
* `nearest` → adresse proche (score selon distance)
* `missing` → aucune correspondance trouvée

## 📊 Rapports

Chaque exécution génère :

* un fichier `recap_YYYYMMDD.csv` (résumé par département)
* un fichier `run_report_YYYYMMDD.html` (rapport global)

👉 Ces fichiers permettent d’analyser :

* le taux de match
* la qualité des correspondances
* la distribution des scores de confiance

## 📅 Dernière mise à jour

* BAN : 2026-03-24
* Cadastre : 2026-03-24
* Pipeline : v5.3.2

## ⚠️ Remarques

* Les données sont fournies en l’état
* Certaines correspondances peuvent être approximatives (`nearest`)
* Le score de confiance doit être utilisé pour filtrer les résultats

## 🚀 Utilisation

Ces données peuvent être utilisées pour :

* enrichissement d’adresses
* géocodage inverse cadastral
* analyse territoriale
* croisement data immobilière / foncière

## 🔄 Mises à jour

Les données sont régénérées périodiquement en fonction :

* des mises à jour de la BAN
* des mises à jour du cadastre

## 📬 Contact

Pour toute question ou suggestion, n’hésitez pas à ouvrir une issue.

---

Projet personnel — usage libre selon les licences des sources d’origine (BAN / Etalab)
