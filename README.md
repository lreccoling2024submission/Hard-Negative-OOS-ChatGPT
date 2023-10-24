# Hard-Negative-OOS-ChatGPT

All 5 hard-negative out-of-scope datasets generated using ChatGPT can be found in the 'hard-negative oos datasets' folder.

The code used for generating hard-negative OOS datasets are in the 'hard-negative OOS prompting' folder.
Here are the steps to generate hard-negative OOS and verify if the data is OOS with ChatGPT:
  1, organize your in-scope dataset in a list of tuples that are ['utterance', 'intent']
  2, use 'keyword_mining.py' to find the most frequently appearing keywords for each intent.
  3, use 'hard_negative_oos_prompting.py' to generate hard-negative OOS utterances and perform step one of the two-step OOS verification method.
  4, use 'process_generated_conversation.py' to organize the results from prompting and step one of OOS verificatio, it will calculate statistics and separate the generated data into in-scope and hard-negative OOS.
  5, use 'step_2_oos_verification' to check if the hard-negative OOS that passed the first round of verification are OOS with respect to the entire dataset.
  6, use 'process_final_hard_negative_OOS.py' to organize results from step 2 of the two-step OOs verfication and collect the generated hard-negative OOS datasets.

The 'evaluation results' folder contain results from evaluating 'ATIS', 'Banking77', 'Clinc-150', 'HWU64' and 'Snips' against 'BERT', 'RoBERTa', 'DistilBERT' when the models are trained only on in-scope data. The code used to obtain our results can be found in 'evaluate_hard_negative_oos.py'

The 'oos_in_training_results' folder contain results and code from evaluating the five datasets on BERT when we used:(1) in-scope and general out-of-scope (2) in-scope and hard-negative out-of-scope (3) in-scope, general out-of-scope, and hard-negative out-of-scope, in training. 
