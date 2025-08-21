# Facebook_Data_Sentimental_Analysis_

This repository contains a synthetic dataset mentioning the name "Ramya" for sentiment analysis and name-occurrence counting.

Files
- ramya_dataset.csv: CSV version of the dataset
- ramya_dataset.json: JSON version of the dataset
- load_and_validate.py: Python script to load the CSV and print a summary
- ramya_dataset_version.txt: simple version tag

Usage
- Run load_and_validate.py to load the dataset and compute basic stats:
  - Counts of Positive/Neutral/Negative sentiments
  - Total score
  - Ramya appearances per item

Notes
- The dataset contains 30 items. Each item includes the exact name "Ramya" with simple punctuation variants.
- You can extend or modify the data as needed for your project.

Example outputs
- Positive/Neutral/Negative counts
- Total score

## Program
```
import json
from textblob import TextBlob

# Load Facebook data (assuming JSON format)
with open("facebook_data.json", "r", encoding="utf-8") as f:
    data = json.load(f)

# Extract all text (e.g., posts + comments)
all_text = " ".join([post.get("text", "") for post in data["posts"]])

# Perform sentiment analysis
blob = TextBlob(all_text)
sentiment = blob.sentiment.polarity

if sentiment > 0:
    sentiment_result = "Positive"
elif sentiment < 0:
    sentiment_result = "Negative"
else:
    sentiment_result = "Neutral"

# Count occurrences of your name "Ramya"
your_name = "Ramya"
name_count = all_text.lower().count(your_name.lower())

print("Sentiment of Facebook data:", sentiment_result)
print(f"Occurrences of '{your_name}':", name_count)

```

## Example Output

```
Sentiment of Facebook data: Positive
Occurrences of 'Ramya': 42
```

## Conclusion Data

Total Posts: 30, Positive: 13, Neutral: 13, Negative: 4.
Average Score: 0.30, Ramya Mentions: 30

## Result

Thus, Successfully data are processed in the format "Out of thirty posts, thirteen are positive, thirteen are neutral, and four are negative.
On average, the overall score is zero point three, and Ramya is mentioned in all thirty posts".

