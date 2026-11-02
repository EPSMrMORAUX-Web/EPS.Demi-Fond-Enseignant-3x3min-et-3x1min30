# 📋 EPS Demi-Fond — Guide d'utilisation

Application web de gestion des tests de demi-fond (Bac GT) — Saisie des plots, zones d'arrivée, notation AFL et export des résultats.

---

## 🔐 Accès

L'application est protégée par un mot de passe au lancement.  
Le mot de passe est **connu uniquement de l'enseignant** et n'est **pas stocké en clair** dans le fichier (sécurisé par chiffrement SHA-256).

> En cas de perte du mot de passe, contacter le créateur de l'application.

---

## 🚀 Lancement

1. Ouvrir le fichier `eps_chrono_v2.html` dans un navigateur moderne (Chrome, Firefox, Safari, Edge)
2. Saisir le mot de passe enseignant
3. L'application s'ouvre directement — **aucune installation requise**

> 💡 Fonctionne sur tablette et téléphone, idéal en bord de piste.

---

## 🗂️ Structure des onglets

| # | Onglet | Description |
|---|--------|-------------|
| 01 | **Import** | Charger une liste d'élèves depuis Excel |
| 02 | **2nde · 3×3min** | Notation des élèves de Seconde |
| 03 | **Term · 3×1'30** | Notation des élèves de Terminale |
| 04 | **Barème 2nde** | Tableau de barème complet 2nde |
| 05 | **Barème Term** | Tableau de barème complet Terminale |
| 06 | **Résultats** | Synthèse, stats et export |

---

## 📥 Onglet Import — classes et sous-onglets

### Importer une classe
1. Saisir le **nom de la classe** dans le champ « 🏫 Classe à importer » (ex : `Term Obeiron`). Les classes déjà créées sont proposées en suggestion.
2. Glisser-déposer le fichier Excel (`.xlsx` / `.xls`) avec les noms / prénoms. Les colonnes Nom · Classe · Sexe sont détectées automatiquement (surlignées dans l'aperçu).
3. Cliquer **« Envoyer → 2nde »** ou **« Envoyer → Terminale »**.

➡️ Un **sous-onglet à ce nom** est créé dans l'onglet choisi, avec uniquement les élèves de cette classe.
Pour une autre classe : changer le nom dans le champ, importer un autre fichier, envoyer. Les classes **ne se mélangent jamais** (un même nom d'élève peut exister dans deux classes différentes).

- Si le champ classe est vide mais que le fichier contient une colonne « Classe », les sous-onglets sont créés automatiquement d'après cette colonne.
- Si le champ est vide et qu'aucune colonne classe n'existe, l'application demande d'indiquer le nom de la classe.
- Les doublons (même nom + même classe) sont ignorés.
- Le résumé des classes existantes (2nde / Terminale, avec effectifs) s'affiche sous le champ.

### Sous-onglets de classes (onglets 2nde et Terminale)
Une barre **CLASSE :** apparaît sous la barre de recherche :

| Bouton | Action |
|--------|--------|
| **Toutes (n)** | Affiche tous les élèves de l'onglet (séparés par vague) |
| **Nom de classe (n)** | Affiche uniquement cette classe |
| **＋ Classe** | Crée une classe vide (on peut ensuite ajouter des élèves avec « + Élève ») |
| **✎** | Renomme la classe sélectionnée (les élèves suivent) |
| **🗑** | Supprime la classe sélectionnée **et ses élèves** (confirmation demandée) |

Le compteur, la barre de progression et les filtres de vague s'appliquent à la classe affichée.
Dans « + Élève », le champ classe est pré-rempli avec le sous-onglet actif.

---

## 👥 Gestion des élèves (onglets 2nde / Terminale)

### Ajouter un élève manuellement
- Bouton **+ Élève** → renseigner Nom, Classe, Sexe, Plot VMA et Vague

### Modifier une carte élève
Chaque carte affiche et permet de modifier :

| Élément | Action |
|---------|--------|
| **[G] [F]** | Cliquer pour changer le sexe |
| **[V1][V2][V3][V4]** | Cliquer pour changer la vague |
| **[ABSENT] [DISPENSÉ]** | Cliquer pour activer/désactiver le statut (recliquer = retour normal) |
| **PLOT VMA [−][+]** | Ajuster le plot global (met à jour les 3 courses) |
| **C1/C2/C3 [−][+]** | Ajuster le plot **individuellement par course** |
| **Zone arrivée** | Cliquer le bouton de course → panneau de sélection de zone |

### Sélectionner une zone d'arrivée
Un panneau glissant s'ouvre avec :
- Réglage du **plot de départ** pour cette course spécifique
- Boutons de zones colorés : **B** (Bleue), **J/J−** (Jaune), **R/R−** (Rouge), **W/W−** (Blanche), **N/N−** (Hors zone)
- La zone sélectionnée se valide automatiquement après 0,5 s

### AFL2 et AFL3
- Cliquer sur **[1][2][3][4]** pour attribuer le degré
- Recliquer sur le même degré = effacer
- Le score s'affiche en temps réel

### Barre de progression
En haut de chaque onglet : `NOTÉS : X/Y` avec barre de progression (élèves avec zones + AFL renseignés)

---

## ⏱️ Chronomètre

Barre de chrono sticky en haut de chaque onglet de test.

| Contrôle | Fonction |
|----------|----------|
| **▶ Lancer** | Démarre la séquence de courses |
| **⏸ Pause** | Suspend le chrono (reprendre avec ▶) |
| **■ Arrêter** | Remet à zéro |
| **REPOS (toggle)** | Active/désactive la pause automatique entre blocs |

**Durées :**
- 2nde : 3 blocs × 3 minutes · Repos : **10 minutes**
- Terminale : 3 blocs × 1 min 30 · Repos : **7 minutes**

Alertes sonores automatiques : bips de compte à rebours (3, 2, 1) + fanfare de fin de séquence.

---

## 🌊 Système de vagues

Les élèves sont organisés par vagues (V1 à V4) :
- **Filtre** : cliquer [Toutes][V1][V2][V3][V4] pour afficher une vague
- **Séparateur** : quand toutes les vagues sont affichées, elles sont visuellement séparées
- **Attribution** : sur chaque carte, cliquer [V1/V2/V3/V4] pour changer la vague

---

## 📊 Barèmes

### 2nde — Total /20
```
AFL1 Perf /8  +  AFL1 Maîtrise /6  +  AFL2 /4  +  AFL3 /2  =  /20
```

| Zone | Code | Maîtrise |
|------|------|----------|
| Bleue (exacte) | B | 2 pts |
| Jaune au-delà | J | 1,5 pt |
| Jaune en deçà | J− | 1 pt |
| Rouge au-delà | R | 0,75 pt |
| Rouge en deçà | R− | 0,5 pt |
| Blanche au-delà | W | 0,25 pt |
| Blanche en deçà | W− | 0 pt |
| Hors zone | N/N− | 0 pt |

### Terminale — Total /20
```
AFL1 Perf /6  +  AFL1 Maîtrise /6  +  AFL2 /4  +  AFL3 /4  =  /20
```

Zones ± donnent le **même score** en terminale (J et J− = 1,5 pt, R et R− = 0,75 pt, etc.)

### AFL2 — Autonomie
| Degré | 2nde | Terminale | Description |
|-------|------|-----------|-------------|
| 1 | 0 pt | 0 pt | Passif — échauffement absent |
| 2 | 1 pt | 1 pt | Partiel — suit les propositions |
| 3 | 2 pt | 2,5 pt | Autonome — séance adaptée |
| 4 | 4 pt | 4 pt | Expert — projet anticipé et ajusté |

### AFL3 — Chronométreur
| Degré | 2nde | Terminale | Description |
|-------|------|-----------|-------------|
| 1 | 0 pt | 0 pt | Passif |
| 2 | 0,5 pt | 1 pt | Basique |
| 3 | 1 pt | 2,5 pt | Actif |
| 4 | 2 pt | 4 pt | Expert |

---

## 💾 Sauvegarde et reprise

### Sauvegarde TOTALE (onglet Import)
- **💾 Sauvegarde totale** : un seul fichier Excel `EPS_sauvegarde_TOTALE_AAAA-MM-JJ.xlsx` contenant **2nde + Terminale, toutes les classes (sous-onglets), tous les élèves et toutes leurs données**.
- **📂 Restaurer une sauvegarde totale** : recharge tout à l'identique (classes, vagues, zones, AFL…). L'application demande confirmation avant de remplacer les données actuelles.

### Sauvegarde d'un seul onglet (barre de chaque onglet)
- **💾 Exporter** / **📂 Réimporter** : même principe, limité à l'onglet 2nde ou Terminale **avec toutes ses classes**.
- Un fichier de sauvegarde totale peut aussi être réimporté dans un seul onglet (seule la feuille correspondante est lue).

**Ce qui est sauvegardé et restauré pour chaque élève :** nom, classe, sexe, **vague (V1–V4)**, statut (présent / absent / dispensé), plot de départ, plot et zone de chaque course (C1, C2, C3), degrés AFL2 et AFL3 et, en Terminale, la **répartition AFL2/AFL3** (2/6, 4/4, 6/2). Les **classes vides** et l'ordre des sous-onglets sont conservés.

Les points AFL, notes Perf / Maîtrise, total /20 et distance figurent dans le fichier **à titre de lecture** : ils sont recalculés à l'import.

**À savoir :**
- Une sauvegarde 2nde importée dans l'onglet Terminale (ou l'inverse) déclenche un avertissement.
- Ne pas renommer les onglets `Sauvegarde_…` / `Classes_…` ni les titres de colonnes dans Excel.
- L'application mémorise aussi automatiquement les données (classes comprises) dans le navigateur : elles survivent à un rafraîchissement de la page, mais sont propres à l'appareil. La sauvegarde totale sert à changer d'appareil ou à archiver.

---

## 📈 Onglet Résultats

- Basculer entre **2nde** et **Terminale**, puis filtrer par **classe** (liste déroulante) : stats, tableau, Excel et PDF suivent la classe choisie
- Statistiques : total, notés, absents, dispensés, moyenne, meilleure note
- Tableau trié par **classe, vague puis alphabétique**, absents/dispensés en fin de liste
- Numérotation automatique des élèves présents

---

## 💾 Export

### Excel (.xlsx)
- Bouton **📊 Excel** dans l'onglet Résultats
- Colonnes : Nom, Classe, Sexe, Vague, Statut, Plot C1/C2/C3, Zone C1/C2/C3, Degrés AFL, Scores détaillés, Total

### PDF / Impression
- Bouton **🖨 PDF / Imprimer** dans l'onglet Résultats
- Une page d'aperçu s'affiche — cliquer **Imprimer** dans le navigateur
- Format A4 paysage recommandé
- Après impression, cliquer **✕ Fermer** ou simplement annuler la boîte de dialogue

> ⚠️ Si l'écran devient blanc après impression, actualiser la page (F5). Les données ne sont **pas sauvegardées** entre sessions.

---

## ⚠️ Notes importantes

- **Pas de sauvegarde automatique** : les données sont en mémoire le temps de la session. Pour conserver les résultats, **exporter en Excel** avant de fermer.
- **Rechargement de page** : efface toutes les données saisies. Toujours exporter avant.
- **Compatibilité** : fonctionne sur Chrome 90+, Firefox 88+, Safari 14+, Edge 90+
- **Pas d'internet requis** après le premier chargement des polices Google Fonts (Barlow + Share Tech Mono)

---

## 🛠️ Fichiers

```
eps_chrono_v2.html    Application complète (fichier unique auto-suffisant)
README.md             Ce guide d'utilisation
```

---

## 📐 Calcul automatique de la note

La note de performance est calculée à partir de la **distance totale extrapolée sur 3 courses** :

```
distance_course = (plot_vma + écart_zone) × durée_course_en_min × 1000/60
distance_totale = moyenne_des_courses_réalisées × 3
note_perf = barème(distance_totale, sexe)
```

Le calcul fonctionne même si toutes les courses ne sont pas encore saisies (extrapolation sur la moyenne).

---

*Application créée pour la gestion des évaluations EPS Demi-Fond — Baccalauréat Général et Technologique · 2025-2026*
