# The Mood Machine

The Mood Machine is a simple text classifier that begins with a rule based approach and can optionally be extended with a small machine learning model. It tries to guess whether a short piece of text sounds **positive**, **negative**, **neutral**, or even **mixed** based on patterns in your data.

This lab gives you hands on experience with how basic systems work, where they break, and how different modeling choices affect fairness and accuracy. You will edit code, add data, run experiments, and write a short model card reflection.

---

## The core concept students needed to understand

Understanding what their code is doing. Making and reviewing changes manually. Using AI as a tool while still being able to explain their specific algorithms. Explaining their work in the model card.

## Where students are most likely to struggle

Getting familiar with this codebase and trying to trace how each method works. Learning how to explain technical components in model_card.py. Misunderstanding instructions on adding true labels (adding extra stuff like "confused" rather than sticking to "negative"/"postive"/etc.).

## Where AI was helpful vs misleading

AI was helpful in giving ideas on how to implement the methods in mood_analyzer.py but was misleading when creating the score_text method by initially not taking into account negative or positive words from the dataset.py, only negation.

## One way I would guide a student without giving the answer

I would tell a student to think about what moods they would expect and evaluate ways their algorithm can assign a mood accurately. What score constitutes which mood? Which key words create a certain score or mood? They are also allowed to use AI to provide hints and explain blocks of code, and I will remind them of that.

## Repo Structure

```plaintext
├── dataset.py         # Starter word lists and example posts (you will expand these)
├── mood_analyzer.py   # Rule based classifier with TODOs to improve
├── main.py            # Runs the rule based model and interactive demo
├── ml_experiments.py  # (New) A tiny ML classifier using scikit-learn
├── model_card.md      # Template to fill out after experimenting
└── requirements.txt   # Dependencies for optional ML exploration
```

---

## Getting Started

1. Open this folder in VS Code.
2. Make sure your Python environment is active.
3. Install dependencies:

    ```bash
    pip install -r requirements.txt
    ```

4. Run the rule-based starter:

    ```bash
    python main.py
    ```

If pieces of the analyzer are not implemented yet, you will see helpful errors that guide you to the TODOs.

To try the ML model later, run:

```bash
python ml_experiments.py
```

---

## What You Will Do

During this lab you will:

- Implement the missing parts of the rule based `MoodAnalyzer`.
- Add new positive and negative words.
- Expand the dataset with more posts, including slang, emojis, sarcasm, or mixed emotions.
- Observe unusual or incorrect predictions and think about why they happen.
- Train a tiny machine learning model and compare its behavior to your rule based system.
- Complete the model card with your findings about data, behavior, limitations, and improvements.
- The goal is to help you reason about how models behave, how data shapes them, and why even small design choices matter.

---

## Tips

- Start with preprocessing before updating scoring rules.
- When debugging, print tokens, scores, or intermediate choices.
- Ask an AI assistant to help create edge case posts or unusual wording.
- Try examples that mislead or confuse your model. Failure cases teach you the most.
