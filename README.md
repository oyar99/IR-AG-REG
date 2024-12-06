# Regulatory Information Retrieval And Answer Generation Shared Task

This repo contains our solution to the competition [Regulatory Information Retrieval and Answer Generation](https://www.codabench.org/competitions/3527) addressing the following subtasks.

_Passage Retrieval_. Given a regulatory question, we developed an information retrieval (IR) system that returns the most relevant passages from ADGM regulations and guidance documents. The challenge is to design a system that can retrieve these passages given the complex language and expertise required to understand the regulatory documents.

_Answer Generation_. Using the passages retrieved for a given question, we developed a system that generates a comprehensive, accurate, and coherent answer using Large Language Models (LLMS).

The repository contains four notebooks detailed below.

- `data_processing.ipynb`: This notebook processes the competition dataset and outputs training, testing, and validation datasets ready for use.

- `model.ipynb`: This notebook fine-tunes a text embedding model which is later used for the information retrieval task.

- `ObligQA.ipynb`: This notebook solves the information retrieval task and demonstrates different approaches, out of which the hybrid approach which uses both lexical and semantic techniques performs best.

- `QnA.ipynb`: This notebook solves the answer generation task and experiments with different models such as `GPT-3.5 Turbo`, `GPT4o Mini`, and `Llama 3.1`.

1. **Data Preprocessing**: The provided datasets were cleaned and preprocessed to ensure consistency and quality. This included tokenization, normalization, and removal of irrelevant information.

2. **Model Selection**: We selected the `BAAI/bge-small-en-v1.5` model from Hugging Face, which is a fine-tuned version of the BERT model widely used in natural language processing.

3. **Training**: The model was further fine-tuned on the competition dataset to improve its performance.

4. **Evaluation**: The model was evaluated using common information retrieval metrics such as `Recall@10` and `MAP@10`.

5. **Information Retrieval**: The final model was used to generate answers for the test set achieving a recall rate of 0.833 surpassing by more than 0.05 points the baseline.

6. **Answer Generation**: We integrated varios LLMs to generate a coherent and correct answer to a regulatory question using passages retrieved previously.

## Results

For further details please refer to our final paper `A hybrid Approach to Information Retrieval and Answer Generation for Regulatory Texts`.

## Usage

To reproduce the results, follow these steps:

- Use python 3.10

```sh
python --version
```

- Create virtual environment

```sh
python -m venv env
```

- Activate virtual environment

```sh
.\env\Scripts\activate
```

- Install the required dependencies

 ```bash
pip install -r requirements.txt
```

## References

- [Codabench Competition 3527](https://www.codabench.org/competitions/3527)
- [RegNLP in Action: Facilitating Compliance Through Automated Information Retrieval and Answer Generation](https://arxiv.org/abs/2409.05677)
- [TREC Eval](https://huggingface.co/spaces/evaluate-metric/trec_eval)
- [RePASs](https://github.com/RegNLP/RePASs)
- [Hugging Face Model](https://huggingface.co/raul-delarosa99/bge-small-en-v1.5-RIRAG_ObliQA)