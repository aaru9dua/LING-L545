<h1> Tokenization </h1>

<b>Step 1: Install Required Libraries</b>

Make sure you have the necessary Python libraries installed. You can install them using pip:

pip install numpy


<b>Step 2: Prepare the Data</b>

Place the 'ja_gsd-ud-train.conllu' and 'ja_gsd-ud-test.conllu' files in the same directory as the Python script.
'ja_gsd-ud-train.conllu' is used for training, while 'ja_gsd-ud-test.conllu' is used for testing. Ensure that the file paths are correct in the script.

<b> Code overview </b>
1. The script reads the training data from '.conllu' files for making word dictionary.
2. It segments the text from test data using the maxalgo function.
3. Word Error Rate (WER) is calculated for evaluation

<b>Step 4: Running the Code</b>

Execute the Python script.

python Tokenization.ipynb

The script will process the test data, calculate WER scores, and save the results in a CSV file named 'wer_scores.csv'.






