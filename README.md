Description
# BAN_Cadastre_FR
Jeu de données France enrichi à partir de la Base Adresse Nationale (BAN), croisée avec le cadastre officiel. Chaque fichier contient jusqu’à 200 000 lignes pour faciliter la manipulation.

---

# 🇫🇷 BAN France enrichie avec Cadastre

## 📄 Description

Ce dépôt contient les fichiers d’adresses de la **Base Adresse Nationale (BAN)** pour la France métropolitaine, enrichis avec les informations cadastrales.

Chaque fichier CSV correspond à un département et contient jusqu’à **200 000 lignes** pour faciliter la manipulation et le traitement.

Une colonne supplémentaire a été ajoutée :

* `cad_parcelles` 🗂 : identifiant de la parcelle cadastrale associée à l’adresse, si disponible
* `status` ✅ : indique la qualité du lien cadastral

  * `exist` ✔️ : l’adresse avait déjà un lien cadastral
  * `add` ➕ : le lien cadastral a été ajouté lors du traitement
  * `missing` ❌ : aucun lien cadastral trouvé

---

## 🔗 Sources des données

Les données proviennent de sources officielles :

* **Base Adresse Nationale (BAN)** : [https://adresse.data.gouv.fr/data/ban/adresses/latest/csv-with-ids](https://adresse.data.gouv.fr/data/ban/adresses/latest/csv-with-ids)
* **Cadastre (GéoJSON)** : [[https://adresse.data.gouv.fr/data/ban/adresses/latest/csv-with-ids](https://files.data.gouv.fr/cadastre/etalab-cadastre/2023-01-01/geojson/departements)

Ces fichiers ont été traités et découpés pour créer cette version enrichie.

---

## 📊 Fiabilité par département

La fiabilité des informations cadastrales est estimée comme :

[
\text{Fiabilité (%)} = \frac{\text{cad_exist + cad_ajoute}}{\text{nb_adresses}} \times 100
]

| Dép | nb_adresses | cad_exist | cad_ajoute | cad_manquant | Fiabilité (%) |
| --- | ----------- | --------- | ---------- | ------------ | ------------- |
| 01  | 262078      | 89231     | 139258     | 33589        | 86,8          |
| 02  | 250852      | 40622     | 112365     | 97865        | 61,5          |
| 03  | 192199      | 71268     | 86026      | 34905        | 81,6          |
| 04  | 103268      | 65472     | 34190      | 3606         | 95,9          |
| 05  | 80874       | 66385     | 12938      | 1551         | 97,0          |
| 06  | 219947      | 73520     | 106814     | 39613        | 82,6          |
| 07  | 197711      | 83079     | 96346      | 18286        | 91,6          |
| 08  | 133068      | 27637     | 57338      | 48093        | 65,7          |
| 09  | 117331      | 53070     | 49127      | 15134        | 87,0          |
| 10  | 148238      | 25903     | 79869      | 42466        | 71,5          |
| 11  | 243491      | 109310    | 104044     | 30137        | 88,1          |
| 12  | 175211      | 45591     | 112519     | 17101        | 90,2          |
| 13  | 461068      | 253260    | 174094     | 33714        | 94,2          |
| 14  | 316264      | 310334    | 3667       | 2263         | 98,2          |
| 15  | 102483      | 32422     | 56334      | 13727        | 85,1          |
| 16  | 210870      | 134441    | 60322      | 16107        | 93,4          |
| 17  | 434889      | 174728    | 184697     | 75464        | 84,6          |
| 18  | 184480      | 60454     | 87523      | 36503        | 81,7          |
| 19  | 159778      | 96211     | 55889      | 7678         | 97,0          |
| 2A  | 55846       | 46600     | 8033       | 1213         | 96,1          |
| 2B  | 76257       | 60747     | 14260      | 1250         | 99,3          |
| 21  | 213504      | 47632     | 107473     | 58399        | 73,2          |
| 22  | 373626      | 270904    | 79726      | 22996        | 95,6          |
| 23  | 94137       | 42536     | 37370      | 14231        | 85,7          |
| 24  | 272524      | 225520    | 34176      | 12828        | 95,5          |
| 25  | 197851      | 64499     | 98807      | 34545        | 82,6          |
| 26  | 234516      | 143521    | 79077      | 11918        | 95,5          |
| 27  | 290038      | 93177     | 160256     | 36605        | 87,7          |
| 28  | 201984      | 61742     | 85908      | 54334        | 73,0          |
| 29  | 501307      | 355323    | 119317     | 26667        | 94,6          |
| 30  | 339484      | 173231    | 143234     | 23019        | 92,6          |
| 31  | 458329      | 323300    | 102743     | 32286        | 95,0          |
| 32  | 115201      | 65819     | 32125      | 17257        | 85,5          |
| 33  | 735796      | 287175    | 381893     | 66728        | 90,3          |
| 34  | 455586      | 248366    | 163918     | 43302        | 90,5          |
| 35  | 436619      | 247269    | 164193     | 25157        | 90,0          |
| 36  | 139814      | 79823     | 42348      | 17643        | 84,7          |
| 37  | 276358      | 63881     | 173101     | 39376        | 83,9          |
| 38  | 428620      | 215733    | 180704     | 32183        | 93,7          |
| 39  | 129924      | 66020     | 47770      | 16134        | 87,5          |
| 40  | 250667      | 103946    | 101952     | 44769        | 82,7          |
| 41  | 188193      | 65392     | 90720      | 32081        | 83,7          |
| 42  | 272023      | 119494    | 131268     | 21261        | 91,3          |
| 43  | 145621      | 92782     | 42842      | 9997         | 96,1          |
| 44  | 580188      | 365529    | 198355     | 16304        | 96,1          |
| 45  | 287677      | 61946     | 184133     | 41598        | 84,4          |
| 46  | 127079      | 84182     | 33422      | 9475         | 92,1          |
| 47  | 204376      | 42377     | 120407     | 41592        | 79,5          |
| 48  | 61186       | 39792     | 17592      | 3802         | 95,0          |
| 49  | 352542      | 260424    | 84067      | 8051         | 97,2          |
| 50  | 302564      | 149800    | 118502     | 34262        | 88,3          |
| 51  | 216335      | 38051     | 116852     | 61432        | 71,6          |
| 52  | 97631       | 18659     | 49830      | 29142        | 71,2          |
| 53  | 161451      | 103913    | 45676      | 11862        | 98,6          |
| 54  | 266179      | 85590     | 113130     | 67459        | 73,1          |
| 55  | 100094      | 23471     | 45108      | 31515        | 68,2          |
| 56  | 432124      | 269091    | 136065     | 26968        | 91,9          |
| 57  | 383613      | 55424     | 267458     | 60731        | 84,5          |
| 58  | 143479      | 77376     | 48392      | 17711        | 85,5          |
| 59  | 1011454     | 495336    | 303597     | 212521       | 77,6          |
| 60  | 314964      | 122806    | 130440     | 61718        | 82,9          |
| 61  | 176895      | 87440     | 58929      | 30526        | 90,0          |
| 62  | 692504      | 158235    | 319293     | 214976       | 68,9          |
| 63  | 326006      | 199035    | 94997      | 31974        | 91,8          |
| 64  | 271172      | 232281    | 29494      | 9397         | 96,0          |
| 65  | 126794      | 51119     | 53062      | 22613        | 83,2          |
| 66  | 254895      | 150778    | 78007      | 26110        | 88,9          |
| 67  | 338960      | 154117    | 149931     | 34912        | 87,5          |
| 68  | 258296      | 110367    | 124990     | 22939        | 90,4          |
| 69  | 352537      | 70670     | 259262     | 22605        | 92,0          |
| 70  | 131104      | 24564     | 74323      | 32217        | 75,2          |
| 71  | 277097      | 118496    | 114183     | 44418        | 83,8          |
| 72  | 260758      | 141528    | 100836     | 18394        | 92,4          |
| 73  | 183120      | 122167    | 54869      | 6084         | 97,5          |
| 74  | 280228      | 203685    | 68750      | 7793         | 96,9          |
| 75  | 152331      | 0         | 151887     | 444          | 99,7          |
| 76  | 465954      | 102379    | 268652     | 94923        | 81,9          |
| 77  | 453086      | 126570    | 238820     | 87696        | 81,8          |
| 78  | 343291      | 106113    | 161671     | 75507        | 77,8          |
| 79  | 209526      | 68982     | 86869      | 53675        | 74,2          |
| 80  | 275486      | 159902    | 81614      | 33970        | 85,9          |
| 81  | 220815      | 180437    | 35959      | 4419         | 98,2          |
| 82  | 135869      | 80327     | 37064      | 18478        | 87,7          |
| 83  | 400272      | 248553    | 133757     | 17962        | 95,3          |
| 84  | 259031      | 113552    | 123142     | 22337        | 92,0          |
| 85  | 436365      | 18659     | 336720     | 80986        | 90,4          |
| 86  | 214078      | 68986     | 113769     | 31323        | 84,9          |
| 87  | 182001      | 146251    | 28892      | 6858         | 99,0          |
| 88  | 190180      | 42065     | 90735      | 57380        | 70,2          |
| 89  | 200777      | 82386     | 84024      | 34367        | 82,3          |
| 90  | 44840       | 6883      | 34992      | 2965         | 95,2          |
| 91  | 337693      | 57435     | 193741     | 86517        | 73,9          |
| 92  | 166659      | 6923      | 125073     | 34663        | 77,0          |
| 93  | 235159      | 10846     | 140272     | 84041        | 63,4          |
| 94  | 201880      | 10463     | 116797     | 74620        | 63,6          |
| 95  | 286696      | 42183     | 183546     | 60967        | 79,2          |

---

## 🛠 Traitement

* Les fichiers ont été découpés en chunks de **200 000 lignes max** pour faciliter la manipulation.
* Seul le champ `cad_parcelles` a été alimenté et le champ `status` ajouté pour indiquer la fiabilité.
* Les données ont été traitées le **20 mars 2026** (date du traitement).

---

## ⚠️ Licence et responsabilité

* Ces fichiers sont fournis **tels quels**, à titre informatif.
* Les sources sont fiables (BAN et Cadastre officiel), mais **aucune garantie n’est donnée sur l’exhaustivité ou l’exactitude totale**.
* Vous êtes libre de les utiliser à des fins personnelles ou professionnelles, dans le respect des licences de la BAN et des données cadastrales.

---
