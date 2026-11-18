# TP1 : comptage de mots

**Auteur :** Hugo EXERTIER, cours Big Data 5A (Mohamed Quafafou), rendu du 18/11/2026.

Comparaison de quatre méthodes (Python séquentiel, PySpark, Python pseudo-MapReduce, Hadoop MapReduce) pour compter les occurrences de mots dans un fichier texte, sur trois fichiers de tailles différentes (1 000, 100 000 et 1 000 000 lignes).

## Contenu

- `comptage_mots.ipynb` : les 3 méthodes du TP (Python simple, pseudo-MapReduce en Python, Hadoop MapReduce) et la comparaison de leurs temps d'exécution.
- `comptage_mots_spark.ipynb` : la 4e méthode, avec Apache Spark (PySpark), comparée à la version Python simple.

Les fichiers de test (`mots_*.txt`) ne sont pas dans le dépôt : les notebooks les génèrent.

## Lancer les notebooks

Les notebooks sont prévus pour Linux (Google Colab, ou WSL sous Windows). Il suffit d'exécuter les cellules dans l'ordre : Java, Hadoop et PySpark sont téléchargés automatiquement dans le dossier personnel.

## Résultats

| Fichier | Python simple | Pseudo-MapReduce | Hadoop | Spark |
|---|---|---|---|---|
| petit (62 Ko) | 0,005 s | 0,006 s | 37 s | 0,5 s |
| moyen (6 Mo) | 0,2 s | 0,4 s | 36 s | 0,7 s |
| grand (63 Mo) | 2,5 s | 4,5 s | 41 s | 3,0 s |

Sur ces tailles, Python simple est le plus rapide. Hadoop paie un coût de démarrage d'environ 35 s par job, quelle que soit la taille du fichier, et Spark réduit fortement ce coût. Ces outils ne deviennent intéressants que pour des volumes trop gros pour une seule machine, répartis sur plusieurs machines.

## Voir aussi

- [TP2](https://github.com/ItaTuTsuki/TP2) : analyse des accidents de la route avec PySpark (RDD, DataFrames et Spark SQL).
- [TP3_ID6](https://github.com/ItaTuTsuki/TP3_ID6) : deux cas personnels, small data et big data.
