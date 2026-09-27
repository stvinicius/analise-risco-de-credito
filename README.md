# Credit Risk Scoring — Give Me Some Credit (CRISP-DM)

Projeto de estudo com metodologia **CRISP-DM** aplicada a um problema de **credit scoring**, usando o dataset [Give Me Some Credit](https://www.kaggle.com/competitions/GiveMeSomeCredit/overview) do Kaggle.

**Objetivo:** prever a probabilidade de um tomador de crédito sofrer inadimplência grave (`SeriousDlqin2yrs`, atraso de 90+ dias) nos próximos 2 anos.

Este repositório é propositalmente um **esqueleto de aprendizado**: os notebooks contêm as perguntas-guia de cada fase do CRISP-DM, mas não as soluções.

**📖 COMECE AQUI:** Leia o `[GUIA_APRENDIZADO.md](GUIA_APRENDIZADO.md)` para entender as variáveis, conceitos-chave de cada fase do CRISP-DM e a estratégia de execução.

## Estrutura do projeto

```
credit_risk_scoring/
├── README.md
├── requirements.txt
├── .gitignore
├── data/
│   ├── raw/          # dados originais baixados do Kaggle (não versionado)
│   └── processed/    # dados tratados, gerados pelos seus notebooks (não versionado)
├── notebooks/
│   ├── 01_business_understanding.ipynb
│   ├── 02_data_understanding.ipynb
│   ├── 03_data_preparation.ipynb
│   ├── 04_modeling.ipynb
│   ├── 05_evaluation.ipynb
│   └── 06_deployment_notes.ipynb
├── src/               # funções reutilizáveis extraídas dos notebooks
├── models/            # modelos treinados salvos (.pkl) (não versionado)
└── reports/
    └── figures/       # gráficos exportados durante a análise
```



## Como configurar o ambiente

1. Crie e ative um ambiente virtual:
  ```bash
   python3 -m venv .venv
   source .venv/bin/activate
  ```
2. Instale as dependências:
  ```bash
   pip install -r requirements.txt
  ```
3. Registre o kernel do ambiente virtual no Jupyter (opcional, mas recomendado):
  ```bash
   python -m ipykernel install --user --name credit-risk-scoring
  ```
4. Abra os notebooks:
  ```bash
   jupyter notebook notebooks/
  ```



## Como baixar os dados

Os dados não estão incluídos neste repositório (a competição exige aceitar as regras do Kaggle). Duas opções:

**Opção A — pela interface web:**

1. Acesse a página da competição: [https://www.kaggle.com/competitions/GiveMeSomeCredit/data](https://www.kaggle.com/competitions/GiveMeSomeCredit/data)
2. Aceite as regras da competição.
3. Baixe `cs-training.csv`, `cs-test.csv` e o dicionário de dados.
4. Coloque os arquivos em `data/raw/`.

**Opção B — via Kaggle API:**

1. Gere um token em [https://www.kaggle.com/settings](https://www.kaggle.com/settings) (seção API) e salve como `~/.kaggle/kaggle.json`.
2. Instale a CLI: `pip install kaggle`.
3. Aceite as regras da competição pelo site (obrigatório mesmo usando a API).
4. Baixe os dados:
  ```bash
   kaggle competitions download -c GiveMeSomeCredit -p data/raw/
   unzip data/raw/GiveMeSomeCredit.zip -d data/raw/
  ```



## Metodologia: CRISP-DM

Este projeto segue as 6 fases do CRISP-DM. Cada fase tem um notebook próprio em `notebooks/` com perguntas-guia — não respostas prontas. A ideia é você pesquisar, formular hipóteses e documentar suas próprias conclusões.

- [ ] **1. Business Understanding** (`01_business_understanding.ipynb`) — entender o problema de negócio, os critérios de sucesso e as métricas relevantes antes de olhar os dados.
- [ ] **2. Data Understanding** (`02_data_understanding.ipynb`) — explorar os dados, identificar qualidade, distribuições, valores faltantes e outliers.
- [ ] **3. Data Preparation** (`03_data_preparation.ipynb`) — limpar, tratar e transformar os dados; engenharia de features; split treino/validação/teste.
- [ ] **4. Modeling** (`04_modeling.ipynb`) — treinar e comparar modelos (baseline e mais complexos).
- [ ] **5. Evaluation** (`05_evaluation.ipynb`) — avaliar os modelos com métricas apropriadas e confrontar com os critérios de negócio da fase 1.
- [ ] **6. Deployment** (`06_deployment_notes.ipynb`) — refletir sobre como o modelo seria colocado em produção, monitorado e mantido.

Lembre-se: CRISP-DM é iterativo. É normal e esperado voltar a uma fase anterior quando uma descoberta em uma fase posterior exigir isso (ex: descobrir na modelagem que um outlier não foi bem tratado na preparação dos dados).

