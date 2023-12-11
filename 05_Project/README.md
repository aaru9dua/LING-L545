<h1>Vyakaran Correction</h1>

<p>This project introduces an automated system for correcting grammatical mistakes in Hindi text using advanced natural language processing techniques. The system focuses on fixing spelling errors for individual words that are lexically invalid, rather than addressing real-world errors.</p>

<p>The correction process leverages an n-gram language model and neural approaches to suggest the most probable valid word given the surrounding context.</p>

<h3>Key Features</h3>

<ul>
<li><strong>Dataset</strong>: The Hindi conllu corpus is used to train all models. https://github.com/UniversalDependencies/UD_Hindi-HDTB</li>

<li><strong>Correction Model</strong>: Integrates three probability scores for misspelling correction:
<ul>
  <li>Candidate word frequency</li>  
  <li>Common bigram characters</li>
  <li>BERT-based classifier prediction score for grammatical validity</li>
</ul></li>  
</ul>

<h3>Usage</h3>

<p>Use the Jupyter notebook "automated-vyakaran-correction.ipynb" for the VyakaranCorrection system.</p>

<p>The fine-tuned BERT model weights are available in the Model_save directory. The model can be loaded as follows:</p>

<pre>
<code>
from transformers import BertForSequenceClassification 
output_dir = '/model_save'
 
import torch
tokenizer = BertTokenizer.from_pretrained(output_dir)
model_loaded = BertForSequenceClassification.from_pretrained(output_dir)
</code>
</pre>

<h3>Performance</h3>  

<p>On a synthetic dataset with artificially inserted errors, the BERT model achieved a validation loss of 0.03.</p>