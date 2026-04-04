# Prova 02 — Paradigmas de Aprendizagem de Máquina

**Universidade Federal da Paraíba — Centro de Informática**  
**Aluno:** Jorge Alberto Macedo Costa de Oliveira  
**Disciplina:** Paradigmas de Aprendizagem de Máquina  

---

## Sobre o Dataset

[Diabetes 130-US Hospitals for Years 1999-2008](https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008)

Dataset com registros clínicos de pacientes diabéticos em 130 hospitais dos EUA (1999–2008). Contém **101.763 registros** e **50 atributos**, incluindo dados demográficos, diagnósticos, medicações e readmissão hospitalar.

---

## Estrutura do Projeto

```
.
├── README.md
├── requirements.txt
├── prova_2025_2_paradigmas_am.pdf        # Enunciado da prova
├── .gitignore
├── data/                                 # Não versionado (ver instruções abaixo)
│   ├── diabetic_data.csv                 # Dataset original (baixar do UCI)
│   ├── diabetes_preprocessed_topk.csv    # Gerado pela Questão 1
│   └── IDS_mapping.csv                   # Mapeamento de IDs do dataset
├── Questao1_Preprocessing.ipynb
├── Questao2_Modelos.ipynb
├── Questao3_Importancia.ipynb
├── Questao4_Clustering.ipynb
├── Questao5_Avaliacao.ipynb
└── Questao6_Reflexao.ipynb
```

---

## Questões

| # | Questão | Pontuação | Notebook |
|---|---------|-----------|----------|
| 1 | Análise inicial e pré-processamento | 2,0 | [`Questao1_Preprocessing.ipynb`](Questao1_Preprocessing.ipynb) |
| 2 | Treinamento de modelos supervisionados | 2,0 | [`Questao2_Modelos.ipynb`](Questao2_Modelos.ipynb) |
| 3 | Análise de importância dos atributos | 1,5 | [`Questao3_Importancia.ipynb`](Questao3_Importancia.ipynb) |
| 4 | Aprendizado não supervisionado | 2,0 | [`Questao4_Clustering.ipynb`](Questao4_Clustering.ipynb) |
| 5 | Avaliação da clusterização | 1,5 | [`Questao5_Avaliacao.ipynb`](Questao5_Avaliacao.ipynb) |
| 6 | Reflexão sobre o pipeline de aprendizado | 1,0 | [`Questao6_Reflexao.ipynb`](Questao6_Reflexao.ipynb) |

> **Total:** 10,0 pontos

---

## Pré-requisitos

- Python 3.10+
- pip

---

## Como Usar

### 1. Clone o repositório

```bash
git clone https://github.com/NoelOliveira1982/Prova.git
cd Prova
```

### 2. Crie um ambiente virtual (recomendado)

```bash
python -m venv .venv
source .venv/bin/activate   # Linux/macOS
# .venv\Scripts\activate    # Windows
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Baixe o dataset

Acesse o [UCI Machine Learning Repository](https://archive.ics.uci.edu/dataset/296/diabetes+130-us+hospitals+for+years+1999-2008), baixe o arquivo `diabetic_data.csv` e coloque-o na pasta `data/`:

```bash
mkdir -p data
# Mova o arquivo baixado para a pasta data/
mv ~/Downloads/diabetic_data.csv data/
```

### 5. Execute os notebooks na ordem

```bash
jupyter notebook
```

Abra e execute os notebooks **na ordem sequencial** (Q1 → Q2 → Q3 → Q4 → Q5 → Q6), pois cada questão depende dos dados gerados pelas anteriores:

1. **Questão 1** — Gera os arquivos pré-processados em `data/` usados pelas demais questões
2. **Questões 2 a 5** — Utilizam os dados gerados pela Questão 1
3. **Questão 6** — Contém apenas texto reflexivo (não requer execução de código)

---

## Observações

- O diretório `data/` está no `.gitignore` e **não é versionado**. É necessário baixar o dataset manualmente (passo 4).
- A **Questão 1** gera os CSVs pré-processados (`diabetes_preprocessed_topk.csv`) que são consumidos pelas Questões 2 a 5. Execute-a primeiro.
- A **Questão 6** é puramente textual (apenas células Markdown, sem código).
- Todos os notebooks utilizam `random_state=42` e **validação cruzada estratificada 10-fold**, conforme as instruções da prova.
