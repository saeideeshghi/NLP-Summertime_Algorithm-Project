# Hybrid NLP Summarization Project 🚀

A hybrid text summarization system combining **extractive** (LexRank) and **abstractive** (BART) approaches with transformer-based fusion. This project is inspired by the paper **"Two-Stage Hybrid Model for Abstractive Text Summarization"** and features several improvements in architecture and result integration.

## ✨ Key Features
- **Hybrid Approach:** Merges extractive and abstractive summarization for enhanced summary quality.
- **Advanced Preprocessing:** Utilizes Stanza for tokenization, lemmatization, and named entity recognition.
- **TF-IDF & Structural Features:** Extracts TF-IDF scores and features such as the count of proper nouns.
- **Automated Evaluation:** Evaluates summaries using ROUGE-1, ROUGE-2, and ROUGE-L.
- **Transformer-based Fusion:** Smartly integrates extractive and abstractive summaries using a BART model.
- **GPU Support:** Accelerates processing when a GPU is available.

## 📊 Results and Model Comparison
| Model                               | ROUGE-1 (F1) | ROUGE-2 (F1) | ROUGE-L (F1) |
|-------------------------------------|--------------|--------------|--------------|
| Seq2Seq + Attention (150k Vocab)    | 30.49        | 11.17        | 28.08        |
| Pointer Generator                   | 36.44        | 15.66        | 33.42        |
| Two Stage Network                   | 37.76        | 17.81        | 33.83        |
| **Hybrid Model (This Project)**     | **41.13**    | **19.04**    | **29.09**    |

*Results are computed on a 10% sample of the test dataset.*

## 🛠 Installation & Setup

### Prerequisites
- Python 3.8+
- GPU (optional but recommended)

### Install Required Libraries

Create a file named `requirements.txt` with the following content:

```txt
pandas
stanza
torch
scikit-learn
rouge-score
nltk
transformers
sumy
tqdm
```


Then install the dependencies via pip:
```txt
pip install -r requirements.txt
```

Also, download the necessary NLTK resources:

```txt
python -m nltk.downloader stopwords punkt

```

And download the English model for Stanza:
```txt
import stanza
stanza.download('en')
```

#▶️ Running the Pipeline
The dataset should include the following columns:
- article: The original article text.
- highlights: The reference summary.
To run the complete summarization pipeline, execute:

```txt
python Untitled.py

```

# 📂 Project Structure
```txt
.
├── data/                   # Datasets
├── out/                    # Preprocessed data and results
├── main.py                 # Main script for running the pipeline
├── utils.py                # Utility functions
├── requirements.txt        # List of required libraries
└── README.md               # Project documentation

```

# 🔗 References
- Base Paper: "Neural_Attention_Model_for_Abstractive_Text_Summarization_Using"
- BART Model: BART model by Hugging Face
- Dataset: CNN/DailyMail

# 🤝 Contributing
Contributions are very welcome! To contribute:

- 1.Fork the repository.
- 2.Create a new branch (e.g., git checkout -b feature/YourFeature).
- 3.Commit your changes (e.g., git commit -m 'Add Your Feature').
- 4.Push to your branch (git push origin feature/YourFeature).
- 5.Open a Pull Request.

# 📜 License
This project is licensed under the MIT License.
