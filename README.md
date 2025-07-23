# 🤖 LSTM-Aware Emotion and Stress Detection Chatbot

This is a Colab-compatible Python chatbot that integrates:

- **BERT-based emotion detection** (`distilbert-base-uncased-emotion`)
- **Custom-trained LSTM emotion classifier**
- **Stress level inference**
- **Conversational replies using Facebook's BlenderBot**

It predicts the user’s **emotion and stress level** using both BERT and LSTM models and gives human-like responses.

---

## 🧠 Project Overview

The chatbot performs the following tasks:

1. Takes user input via command line.
2. Detects emotion using:
   - BERT model (`bhadresh-savani/distilbert-base-uncased-emotion`)
   - LSTM model trained on past conversations
3. Infers **stress level** from detected emotion.
4. Replies using BlenderBot (`facebook/blenderbot-400M-distill`).

---

## 📁 Files in This Repository

| File                         | Description                                       |
| ---------------------------- | ------------------------------------------------- |
| `chatbot.py`                 | Full Python script to run the chatbot             |
| `lstm_model.h5`              | Pre-trained LSTM model (upload to Colab)          |
| `tokenizer.pkl`              | Tokenizer fitted on the training dataset for LSTM |
| `requirements.txt`           | All necessary Python packages                     |
| `example_inputs_outputs.txt` | Sample I/O showing how the chatbot works          |
| `.gitignore`                 | Ignore compiled files, model weights, cache, etc. |

---

## 🚀 Setup Instructions

### ✅ Requirements

Install required packages using:

```bash
pip install -r requirements.txt
```

Or manually:

```bash
pip install transformers torch torchvision torchaudio tensorflow scikit-learn
```

---

### ▶️ How to Run (Colab or Local)

1. Clone or download the repo.
2. Upload the files `lstm_model.h5` and `tokenizer.pkl` when prompted.
3. Run the `chatbot.py` script:

```bash
python chatbot.py
```

> In Google Colab, use `files.upload()` to upload the two files.

---

## 🧠 Emotion & Stress Detection Logic

### Emotion Classes:

- `anger`, `fear`, `happy`, `neutral`, `sad`, `surprise`

### Stress Mapping:

| Emotion  | Stress |
| -------- | ------ |
| anger    | High   |
| fear     | High   |
| sad      | High   |
| neutral  | Low    |
| happy    | Low    |
| surprise | Low    |

---

## 💬 Sample Interaction

```text
You: I'm feeling down today.

 Bot: I'm here for you. Do you want to talk about it?
 BERT Emotion: sadness (0.92) → Stress: High
 LSTM Emotion: sad (0.88) → Stress: High

You: exit
 Bot: Take care! 💙
```

---

## 📌 Models Used

- 🔍 **Emotion Detection (BERT)**: [`bhadresh-savani/distilbert-base-uncased-emotion`](https://huggingface.co/bhadresh-savani/distilbert-base-uncased-emotion)

- ♻️ **LSTM Model**: Custom-trained TensorFlow model on labeled emotion datasets

- 💬 **Chat Response**: [`facebook/blenderbot-400M-distill`](https://huggingface.co/facebook/blenderbot-400M-distill)

---

## ⚖️ License

This project is licensed under the MIT License.

---

## 🙋‍♀️ Author

Created by **Harini Muthukumar**

Feel free to star ⭐ the repository and contribute!

