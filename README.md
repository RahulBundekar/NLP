# NLP
# 1. Overview
This project processes user reviews for the Infloso app, cleans the text, applies sentiment analysis, and extracts the top 5 most impactful reviews. The approach leverages Natural Language Processing (NLP) techniques and machine learning-based sentiment analysis.

# 2. Architecture
The project follows a text-processing pipeline consisting of the following steps:

Data Loading: Reads raw text from a .txt file.
Text Preprocessing:
Converts text to lowercase.
Removes special characters and punctuation.
Eliminates common stopwords.
Tokenizes text into words.
Sentiment Analysis:
Uses TextBlob to compute sentiment polarity scores.
Assigns labels: Positive, Neutral, or Negative.
Ranking Reviews:
Extracts the top 5 reviews based on absolute sentiment scores.

# 3. Chosen Model: TextBlob Sentiment Analysis
Model Details
TextBlob is a lexicon-based sentiment analysis tool.
It assigns a polarity score ranging from -1 (negative) to +1 (positive).
The model uses a pre-trained lexicon to evaluate word sentiment.
Why TextBlob?
Lightweight & Fast: No additional model training required.
Effective for Short Texts: Works well with social media-style reviews.
Built-in Polarity Scoring: Automatically assigns sentiment polarity.

# 4. Hyperparameters
Hyperparameter	Value	Description
Sentiment Polarity	TextBlob(text).sentiment.polarity	Returns a float score between -1 and 1.
Sentiment Thresholds	>0 (Positive), =0 (Neutral), <0 (Negative)	Categorizes sentiment scores.
Review Selection	nlargest(5) on `	Sentiment

# 5. Limitations & Considerations
Lexicon-based limitations: TextBlob relies on a predefined word list, which may not handle sarcasm or domain-specific slang well.
Binary Classification: Does not consider multi-dimensional sentiment (e.g., emotional tone beyond polarity).
Language Restriction: Non-English reviews are not processed effectively.

# 6. Future Improvements
Implement VADER Sentiment Analysis for better handling of informal language.
Use Fine-tuned Transformer models (e.g., BERT, RoBERTa) for more accurate sentiment classification.
Add keyword-based topic modeling to identify specific themes (e.g., login issues, usability problems).
