# Visual Semantic Understanding

[![arXiv](https://img.shields.io/badge/arXiv-2406.15359-B31B1B.svg)](https://arxiv.org/abs/2406.15359)

### Overview
The paper introduces RapidNER, a framework for constructing multilingual visual-text datasets to evaluate Vision Language Models (VLMs). The researchers developed datasets in four languages (English, Japanese, Swahili, and Urdu) for nine vision-and-language tasks, including a new task called "unrelatedness." The work addresses the lack of comprehensive evaluation datasets for low-resource languages and introduces rationales to better understand VLM reasoning processes.

### Data Creation

- Created datasets from Wikinews and Wikipedia articles across 10 categories (animals, products, buildings, locations, events, food, drinks, hobbies, works of art, and organization)
- Collected 1,000 image-text pairs initially, then selected 200 representative pairs for detailed analysis
- Used RapidNER framework which operates through:
  - Extracting domain-specific sub-graphs from Wikidata
  - Using Elasticsearch for efficient annotation (reducing annotation time from 1 minute to 0.9 milliseconds per sentence)
  - Translation tools: DeepL for English-Japanese, ChatGPT for English-Swahili, and Google Translate for English-Urdu
- Created nine vision-language tasks including Object Recognition (OR), Scene Understanding (SU), Relationship Understanding (RU), Semantic Segmentation (SS), Image Captioning (IC), and others
- Each sample includes both an answer and a rationale explaining the reasoning process

### Experiments

- Evaluated GPT-4V's performance across all tasks in four languages
- Used eight human evaluators (two for each language) to assess translation quality and task performance
- Fine-tuned LLaVA 1.5 on the test set for comparison with GPT-4V
- Used a 5-point Likert scale for human evaluation of both translations and model outputs
- Conducted cross-language performance analysis
- Evaluated model performance separately for image-only tasks versus combined image-and-text tasks

### Key Findings

- GPT-4V performed best in English (94.81% average accuracy), followed by Urdu (90.56%), Japanese (88.09%), and Swahili (83.57%)
- Model performed better on tasks requiring only image understanding compared to tasks requiring both image and text comprehension
- Object Recognition (OR) was consistently the best-performing task across languages
- Entity Extraction (EE) was generally the most challenging task
- The quality of translations impacted model performance, with Urdu translations being most accurate (81.20%), followed by Japanese (73.82%) and Swahili (65.75%)
- GPT-4V showed high self-confidence (4.826 out of 5) but was often over-confident in its responses
- LLaVA 1.5 showed limited similarity with GPT-4V responses (0.1821 average partial match score), indicating significant performance gaps between open and closed-source models

### Citation

If you find this work or dataset helpful in your research, please cite it as follows:

```bibtex
@misc{atuhurra2024constructingmultilingualvisualtextdatasets,
      title={Constructing Multilingual Visual-Text Datasets Revealing Visual Multilingual Ability of Vision Language Models}, 
      author={Jesse Atuhurra and Iqra Ali and Tatsuya Hiraoka and Hidetaka Kamigaito and Tomoya Iwakura and Taro Watanabe},
      year={2024},
      eprint={2406.15359},
      archivePrefix={arXiv},
      primaryClass={cs.CL},
      url={https://arxiv.org/abs/2406.15359}, 
}
