# Model Card: Mood Machine

This model card is for the Mood Machine project, which includes **two** versions of a mood classifier:

1. A **rule based model** implemented in `mood_analyzer.py`
2. A **machine learning model** implemented in `ml_experiments.py` using scikit learn

You may complete this model card for whichever version you used, or compare both if you explored them.

## 1. Model Overview

**Model type:**  
Rule based

**Intended purpose:**  
Classify short text messages as moods like positive, negative, neutral, or mixed.

**How it works (brief):**  
Score of 0 is neutral, -1 is negative, 1 is positive. Score is calculated based on key words or phrases.



## 2. Data

**Dataset description:**  
There are 11 sample posts with varying moods and new true labels that apply to each one.

**Labeling process:**  
I chose labels based on what overall emotion the post conveyed, even if some words or emojis seemed conflicting. 

**Important characteristics of your dataset:**  
- Contains slang or emojis  
- Includes sarcasm  
- Some posts express mixed feelings  
- Contains short or ambiguous messages

**Possible issues with the dataset:**  
Too small of a sample, not exploring enough nuances in language.


## 3. How the Rule Based Model Works (if used)

**Your scoring rules:**  
Negation and negative words decrease the score. Positive words increase the score. Score of 1 is positive, 0 is neutral, -1 is negative. 

**Strengths of this approach:**  
Simple sentences and even with negation.

**Weaknesses of this approach:**  
It fails on shorter phrases, complex emotions, and sarcasm.

## 4. Evaluation

**How you evaluated the model:**  
The rule based accuracy is evaluated to be 55% based upon the predicted vs expected outputs. 

**Examples of correct predictions:**  
"I love this class so much" was appropiately marked as positive since it expresses gratitude. "I am not happy about this" was appropiately marked as negative since it expresses dissatisfaction.

**Examples of incorrect predictions:**  
"Yeah I'm totally excited about this 🥲" was incorrectly marked positive due to sarcasm. "What the hell!" was incorrectly marked neutral since it is a short phrase with none of the listed key words.

## 5. Limitations

- The dataset is small  
- It cannot detect sarcasm reliably  
- It depends heavily on the words you chose or labeled

## 6. Ethical Considerations

- Misclassifying a message expressing distress  
- Misinterpreting mood for certain language communities  
- Privacy considerations if analyzing personal messages

## 8. Ideas for Improvement
- Add more labeled data  
- Add better preprocessing for emojis or slang  
- Improve the rule based scoring method  
- Add a real test set instead of training accuracy only
