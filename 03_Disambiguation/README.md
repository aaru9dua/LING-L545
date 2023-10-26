<h1> Constraint Grammar</h1>

Steps:

$ git clone https://github.com/ftyers/ud-scripts.git

Now get a UD corpus:

$ git clone https://github.com/UniversalDependencies/UD_English-GUM

Make the morphological analyser:

$ cat UD_English-GUM/*.conllu | python3 ud-scripts/conllu-analyser.py -t eng-analyser.tsv

And then analyse new sentences as follows:

$ echo "At the start of the century, the majority of English people worked in the countryside economy." |\
  python3 ud-scripts/conllu-analyser eng-analyser.tsv


Rules:

1. Remove VerbForm=Fin if the preceding token is the

REMOVE FINITE IF (-1 THE) ;

2. Remove infintive if there's no prepostion or modal :

REMOVE INF IF (NOT -1 PREP OR MODAL);

3. Remove past particple if there's no third form auxillary verb ('was','were','have','had','has')

REMOVE PP IF (NOT -1 AUX);

4. Remove First Person pronoun if there's no first person pronoun

REMOVE V + FP IF (NOT -1 FP);
