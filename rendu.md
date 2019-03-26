##TAL labo3
#####Authors : Johanna Melly & Yohann Meyer

###Step 1

How to run the dependency parser on the test data from previous lab: 
```java -cp stanford-corenlp-3.9.2.jar edu.stanford.nlp.parser.nndep.DependencyParser -model data/UD_French -testFile data/fr-ud-test.conllu3 -outFile dependenciesOutputFile.txt
```
This give us a file named dependenciesOutputFile.txt containing the dependencies on the file tested. 

###Step 2

```java -cp stanford-corenlp-3.9.2.jar edu.stanford.nlp.parser.nndep.DependencyParser -trainFile data/fr-ud-train.conllu3 -wordCutOff 3 ‐trainingThreads 8 -maxIter 5000 -model modelOutputFile.txt.gz
```

