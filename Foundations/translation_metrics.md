
# Evaluation Metrics for Machine Translation

## BLEU (Bilingual Evaluation Understudy)

### Description
BLEU is one of the oldest and most widely used metrics for evaluating machine translations.

### How it Works
It compares the n-grams (typically up to 4-grams) of the machine-generated translation to those of one or more reference translations. The more n-grams in the candidate translation that match n-grams in the reference translations, the higher the BLEU score.

### Calculation
- **Precision**: Measures how many n-grams in the candidate translation appear in the reference translations.
- **Brevity Penalty**: Accounts for the length of the candidate translation to avoid rewarding overly short translations.
- **Formula**: 
  \[
  	ext{BLEU} = BP \cdot \exp \left( \sum_{n=1}^N w_n \log p_n ight)
  \]
  - \( BP \) is the brevity penalty.
  - \( w_n \) are the weights (typically equal).
  - \( p_n \) are the precision scores for each n-gram size.

## CHRF (Character n-gram F-score)

### Description
CHRF evaluates translations based on character-level n-grams rather than word-level n-grams.

### How it Works
It computes precision and recall of character n-grams between the candidate and reference translations and then calculates the F-score.

### Benefits
CHRF is particularly useful for morphologically rich languages and languages with different word boundaries.

### Formula
\[
	ext{CHRF} = F_eta = rac{(1+eta^2) \cdot 	ext{Precision} \cdot 	ext{Recall}}{(eta^2 \cdot 	ext{Precision}) + 	ext{Recall}}
\]
- **Precision**: The proportion of character n-grams in the candidate that appear in the reference.
- **Recall**: The proportion of character n-grams in the reference that appear in the candidate.
- \( eta \): Balances precision and recall (usually set to 2).

## COMET (Cross-lingual Optimized Metric for Evaluation of Translation)

### Description
COMET is a newer, learned metric based on neural networks.

### How it Works
It uses pre-trained multilingual embeddings to compare the candidate translation with the reference translation, incorporating context and semantics more effectively than n-gram-based metrics.

### Benefits
COMET often correlates better with human judgment because it captures semantic meaning and contextual information.

### Training
COMET models are typically trained on human-rated translations to predict quality scores directly.

## Comparison

- **BLEU**: Fast, simple, widely used, but sometimes criticized for not capturing meaning and context well.
- **CHRF**: More sensitive to character-level differences, useful for certain languages, but still limited by n-gram matching.
- **COMET**: Leverages deep learning to understand context and semantics, often aligning better with human judgment, but requires more computational resources and training data.

Each of these metrics has its strengths and weaknesses, and they are often used together to provide a comprehensive evaluation of translation quality.
