# 🧠 Personalized News Article Summarizer with Emotion Detection

This project uses NLP and deep learning to generate short, meaningful summaries from full-length news articles. It also detects the emotional tone of the summaries, enabling personalized news delivery based on emotion.

---

## 🚀 Key Features
- Abstractive summarization of news articles using a fine-tuned **T5 model**
- Emotion labeling of summaries (happy, sad, angry, etc.)
- ROUGE-based evaluation of summarization quality
- Interactive Gradio UI for live summarization

---

## 🧱 Technologies Used
- Python, Pandas, NumPy
- Hugging Face Transformers (`T5`, `datasets`, `tokenizer`)
- Google Colab (for all development)
- Gradio (for the interactive UI)
- Matplotlib / tqdm (for progress and analysis)

---

## 📁 Dataset
- Source: News Summary Dataset from Kaggle
- Cleaned and preprocessed to create:
  - `news_summary_clean.csv`
  - `news_summary_with_emotion.csv`

---

## 📓 Notebooks
| Notebook Name | Description |
|---------------|-------------|
| `1_emotion_labelling.ipynb` | Labels each news summary with an emotion |
| `2_summarization_finetune.ipynb` | Fine-tunes T5 model on article → summary |
| `3_model_inference_evaluation.ipynb` | Generates summaries and evaluates with ROUGE |
| `4_gradio_interface.ipynb` | Gradio UI for live user interaction |

---

## 🧠 Fine-Tuned T5 Summarizer Model

The model used for this project is a fine-tuned version of `t5-small` from Hugging Face.

### 🔹 Base Model:
- `t5-small` — a lightweight transformer pre-trained on text-to-text tasks

### 🔹 Fine-tuning Details:
- Trained on ~98,000 news articles
- Task: Summarize full `article` into short `headline/summary`
- Training Parameters:
  - Max input length: 512 tokens
  - Max target length: 64 tokens
  - 2–3 epochs (Colab-friendly)
  - ROUGE used for evaluation
- Training performed using the Hugging Face `Trainer` API

### 📂 Model Files:
Saved under [`/model/t5_my_summarizer_model/`](https://github.com/vaishnal16/news_article_summarizer/tree/main/model/t5_summarizer_model) directory in this repo. It includes:
- `pytorch_model.bin`
- `config.json`
- `tokenizer_config.json`
- `spiece.model`
- `special_tokens_map.json`

This model can be reloaded directly using Hugging Face Transformers for inference or further training.

---

---

## 🖥️ Gradio Interface Demo

Below is a screenshot of the interactive UI built using [Gradio](https://www.gradio.app/), which allows users to input a news article and instantly view the generated summary:

![gradio_interface](https://github.com/user-attachments/assets/57c5b5ca-1912-4acf-b877-af6cc3c85a91)

---

## 📈 Evaluation
- **ROUGE-1 F1**: ~0.3961
- **ROUGE-2 F1**: ~0.1731
- **ROUGE-L F1**: ~0.3472

These scores reflect good performance for a lightweight T5-small model trained on a custom dataset in Colab.

---

## 🧪 How to Use
1. Clone the repo
2. Run the notebooks in order:
   - Label data
   - Train the model
   - Evaluate it
   - Try the Gradio demo
3. Explore the dataset and results

---

## 💡 Future Enhancements
- Use emotion labels for filtering or emotion-aware summarization
- Add full HTML/CSS UI for web deployment
- Host as a Hugging Face Space or Streamlit app

---

## 📌 Author
**Vaishnal Mali** — Passionate about ML, NLP, and building real-world AI apps!

---
