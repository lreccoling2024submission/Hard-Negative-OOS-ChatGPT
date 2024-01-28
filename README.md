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

Additional Data (Note: the three tables were the only content in the respository edited after submission):

Performance comparison between OOS data with the INS data of a roBERTa model

|  Dataset  | AUROC General OOS | AUROC HN OOS | AUPR General OOS | AUPR HN OOS | FPR95 General OOS | FPR95 HN OOS |
|-----------|-------------------|--------------|------------------|-------------|-------------------|--------------|
| Clinc-150 |       0.968       |     0.914    |       0.982      |    0.914    |       0.121       |     0.326    |
| Banking77 |       0.964       |     0.810    |       0.959      |    0.826    |       0.205       |     0.639    |
|    ATIS   |       0.964       |     0.953    |       0.972      |    0.989    |       0.179       |     0.245    |
|   Snips   |       0.956       |     0.864    |       0.982      |    0.993    |       0.223       |     0.400    |
|   HWU64   |       0.921       |     0.917    |       0.971      |    0.988    |       0.392       |     0.462    |


Performance comparison between OOS data with the INS data of a roBERTa model

|  Dataset  | AUROC General OOS | AUROC HN OOS | AUPR General OOS | AUPR HN OOS | FPR95 General OOS | FPR95 HN OOS |
|-----------|-------------------|--------------|------------------|-------------|-------------------|--------------|
| Clinc-150 |       0.963       |     0.887    |       0.982      |    0.898    |       0.163       |     0.404    |
| Banking77 |       0.965       |     0.812    |       0.960      |    0.831    |       0.189       |     0.685    |
|    ATIS   |       0.976       |     0.961    |       0.981      |    0.991    |       0.146       |     0.255    |
|   Snips   |       0.931       |     0.855    |       0.969      |    0.994    |       0.384       |     0.567    |
|   HWU64   |       0.907       |     0.969    |       0.982      |    0.986    |       0.463       |     0.507    |


Performance comparison between OOS data with the INS data of a distilERT model

|  Dataset  | AUROC General OOS | AUROC HN OOS | AUPR General OOS | AUPR HN OOS | FPR95 General OOS | FPR95 HN OOS |
|-----------|-------------------|--------------|------------------|-------------|-------------------|--------------|
| Clinc-150 |       0.963       |     0.885    |       0.985      |    0.895    |       0.218       |     0.478    |
| Banking77 |       0.967       |     0.847    |       0.961      |    0.839    |       0.160       |     0.526    |
|    ATIS   |       0.986       |     0.977    |       0.990      |    0.994    |       0.011       |     0.077    |
|   Snips   |       0.966       |     0.861    |       0.984      |    0.995    |       0.149       |     0.400    |
|   HWU64   |       0.930       |     0.917    |       0.976      |    0.987    |       0.397       |     0.462    |
