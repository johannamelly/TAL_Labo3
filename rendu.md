## TAL labo3
##### Auteurs : Johanna Melly & Yohann Meyer

### Éxercice 1

#### Étape 1

Cette étape consiste à lancer l'analyseur synthaxique de dépendances de Stanford sur nos données. Cela va permettre de découvrir le pourcentage de mots inconnus "rares" qui n'auraient pas été rencontrés auparavant.

La commande permettant utilisée est la suivante: 

```bash
java -cp stanford-corenlp-3.9.2.jar edu.stanford.nlp.parser.nndep.DependencyParser -model data/UD_French -testFile data/fr-ud-test.conllu3 -outFile dependenciesOutputFile.txt
```

Cet commande produit en output un fichier nommé dependenciesOutputFile.txt qui contient les dépendances dans le fichier testé.

Sur l'image ci-dessous, nous constatons qu'il y a 6.07% de "OOV Words", c'est à dire de mots inconnus par le modèle:

![Fichier props](img/parsing1.png)

#### Étape 2

Pour l'étape 2, nous entraînons notre propre modèle afin de le tester ensuite sur les données et effectuer une comparaison.

La commande utilisée est la suivante:

```bash
java -cp stanford-corenlp-3.9.2.jar edu.stanford.nlp.parser.nndep.DependencyParser -trainFile data/fr-ud-train.conllu3 -wordCutOff 3 ‐trainingThreads 8 -maxIter 5000 -model modelOutputFile.txt.gz
```



```java -cp stanford-corenlp-3.9.2.jar edu.stanford.nlp.parser.nndep.DependencyParser -trainFile data/fr-ud-train.conllu3 -wordCutOff 3 ‐trainingThreads 8 -maxIter 5000 -model modelOutputFile.txt.gz

```

### Éxercice 2

Le fichier contenant le code Python de cet exercice est disponible dans le fichier `jupyter/exercice2.ipynb`

Les triplets les plus fréquents dans le fichier utilisé sont les suivants:

```Python
('a', 'VERB'), ('Il', 'PRON') - 7
('peut', 'VERB'), ('on', 'PRON') - 4
('a', 'VERB'), ('il', 'PRON') - 4
('contrôle', 'VERB'), ('il', 'PRON') - 3
('faut', 'VERB'), ('il', 'PRON') - 3
('est', 'VERB'), ("c'", 'PRON') - 3
('écrit', 'VERB'), ('Il', 'PRON') - 2
('temps', 'NOUN'), ('il', 'PRON') - 2
('avez', 'VERB'), ('vous', 'PRON') - 2
('va', 'VERB'), ('il', 'PRON') - 2
```

### Éxercice 3

La commande utilisée pour lancer le serveur est la suivante:

```bash
java -mx4g -cp "*" edu.stanford.nlp.pipeline.StanfordCoreNLPServer -port 9000 -timeout 15000
```

