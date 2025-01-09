# **Chinese HSK Text Generator** 🎓 📖
Generating text aligned with HSK 3.0 (July 2021+) levels to aid language learning.
---

<div align="left">
  <a href="https://github.com/katherine-welbourne/hsk-text-generator/blob/main/hsk_demo.png">
    <img src="hsk_demo.png" alt="HSK Text Generator" width="400">
  </a>
</div>

---

## **Table of Contents** 📚
1. [Overview](#overview)
2. [Dataset](#dataset)
3. [Model](#model)
4. [Installation](#installation)
5. [Usage](#usage)
6. [Example Output](#example-output)
7. [Future Enhancements](#future-enhancements)
8. [License](#license)

---

## **Overview** 📝
The HSK Text Generator is a machine learning project that generates text based on the HSK 3.0 vocabulary levels. The generated sentences focus on vocabulary from a specified HSK level while allowing the use of lower-level vocabulary for naturalness. Additionally, the tool displays the generated sentences in **Pinyin** to aid pronunciation practice.

### Key Features:
- Input HSK levels: HSK1, HSK2, HSK3, HSK4, HSK5, HSK6, HSK7-9. 🛠️
- Emphasizes vocabulary from the target level. ✍️
- Utilizes Hugging Face Transformers for text generation. 🤖
- Color-coded output to indicate HSK levels of used vocabulary. 🌈
- Displays Pinyin for generated sentences. 🗣️

---

## **Dataset** 📊
The dataset used is a custom HSK vocabulary dataset:
- **Source File**: `/content/drive/MyDrive/ML/Datasets/CHINESE_HSK_WORDS.csv`
- **Columns**:
  - `headword`: Chinese word (Simplified).
  - `HSK`: HSK level (1 to 9).

---

## **Model** 🤖
The project uses Hugging Face’s pre-trained GPT-2 model adapted for Chinese text generation:
- **Base Model**: [GPT-2-Chinese](https://huggingface.co/uer/gpt2-chinese-cluecorpussmall) 🚀
- **Fine-Tuned For**: HSK-constrained text generation.
- **Framework**: Hugging Face Transformers. 🛠️

---

## **Installation** ⚙️
To set up the project locally, follow these steps:

1. Clone the repository:
   ```bash
   git clone https://github.com/katherine-welbourne/hsk-text-generator.git
   cd hsk-text-generator
   ```

2. Install dependencies:
   ```bash
   pip install transformers torch pandas pypinyin
   ```

---

## **Usage** 🏋️
### Generate Text:
```python
# Example usage
level = "HSK3"  # Desired HSK level
prompt = "我喜欢"  # ("I like")
max_length = 50
output_text = generate_text_hsk(level=level, prompt=prompt, max_length=max_length)
print(output_text)

# Display Pinyin
from pypinyin import pinyin, Style
print(" ".join(["".join(x) for x in pinyin(output_text, style=Style.NORMAL)]))
```

### Visualize HSK Levels:
Color-code the generated text by HSK level:
```python
color_text_by_hsk(output_text, df)
```

---

## **Example Output** 🏆
### Input
- HSK Level: HSK3
- Prompt: "我喜欢"  ("I like")

### Output
```plaintext
我喜欢在日本的朋友们和我一起去买东西。
```
### Pinyin:
```plaintext
wǔ xǐ huān zài rì běn de péng yǔ men hé wǔ yī qǔ qù mǎi dōng xī。
```

### HSK Distribution:
- HSK1: 5 words
- HSK2: 3 words
- HSK3: 4 words
- HSK4: 2 words
- HSK5: 1 word
- HSK6: 0 words
- HSK7-9: 0 words

---

## **Future Enhancements** 🚀
- Add support for Traditional Chinese characters.
- Fine-tune models for domain-specific vocabulary.
- Develop an interactive demo using Gradio or Streamlit.

---

## **License** 📜
This project is licensed under the [MIT License](LICENSE). 📖

---

