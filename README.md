## 📌 Objetivo do Projeto

O desafio consiste em analisar os dados da TelecomX, empresa com alto índice de cancelamento de clientes (churn), para identificar os principais fatores que levam à evasão.

A solução está estruturada em um pipeline de ETL (Extract, Transform, Load) seguido de Análise Exploratória de Dados (EDA), com visualizações interativas.

## 🛠️ Tecnologias Utilizadas

- Python 3.10+

- Pandas (manipulação de dados);

- NumPy (operações numéricas);

- Plotly Express (visualizações interativas/animadas);

- Google Colab (execução do notebook);

## 🔄 Pipeline ETL

1. Extração

Leitura do dataset em formato JSON (simulação de resposta de API).

Conversão para DataFrame Pandas via json_normalize.

<img width="386" height="129" alt="image" src="https://github.com/user-attachments/assets/850d7b54-d106-4770-a3ed-daf857490715" />

2. Transformação

- Padronização de colunas;

- Conversão de tipos (tenure, charges para numérico);

- Transformação de Churn em variável binária (0 = Não, 1 = Sim);

**Criação de feature derivada:**

avg_monthly_spend = total_charges / tenure.

<img width="597" height="169" alt="image" src="https://github.com/user-attachments/assets/92d204e4-66e9-4237-87a7-016f93cbe907" />

3. Carga

Dataset final exportado em CSV para facilitar futuras análises/modelagem.

<img width="390" height="94" alt="image" src="https://github.com/user-attachments/assets/44f31541-2bc6-4869-9b00-e90b4244238b" />


## 🔎 Análise Exploratória de Dados (EDA)
1. Taxa de Churn

26,5% dos clientes cancelaram.

Distribuição bastante desbalanceada (maioria não cancela).

2. Contrato

Contratos mensais apresentam churn muito superior.

Contratos de 1 ou 2 anos retêm clientes melhor.

3. Método de Pagamento

Electronic Check (cheque eletrônico) tem a maior taxa de churn.

Outros métodos como cartão de crédito apresentam churn menor.

4. Mensalidade (Monthly Charges)

Clientes que cancelaram possuem mensalidades mais altas em média.

Boxplots mostram clara separação entre grupos.

5. Tenure

Clientes que ficam menos tempo (até 12 meses) apresentam churn mais elevado.

A partir de ~24 meses, a taxa de retenção melhora.

## 📊 Visualizações Estratégicas

- Distribuição de churn (histograma interativo);

- Boxplot mensalidade x churn;

- Churn rate por tipo de contrato;

- Churn rate por método de pagamento;

- Histograma de tenure com animação por coorte de tempo;

- Scatter animado (tenure vs gasto médio).

(As visualizações foram feitas com Plotly, permitindo interatividade e animações.)

## 📈 Principais Insights

- Clientes com contratos mensais e pagamento via cheque eletrônico são os mais propensos a cancelar;

- Mensalidades mais altas estão associadas a churn maior;

- Clientes que permanecem mais tempo na base (tenure > 24 meses) tendem a ficar;

- Serviços adicionais (backup, suporte, streaming) parecem contribuir para maior retenção.

## 🚀 Próximos Passos

- Criar modelo preditivo de churn (ex: Random Forest, XGBoost);

- Usar SHAP para interpretar quais variáveis mais impactam as previsões;

- Desenvolver um dashboard interativo (Streamlit ou Dash) para monitorar métricas de churn em tempo real;

- Criar estratégias de retenção personalizadas para os clientes de alto risco identificados.

## 🛠️ Tecnologias Utilizadas

<p align="center">
  <img src="A_2D_digital_graphic_displays_the_logos_of_four_pr.png" alt="Tecnologias" width="500"/>
</p>

- **Python** → Linguagem principal para ETL e análise de dados.  
- **Pandas** → Manipulação e tratamento de dados tabulares.  
- **NumPy** → Operações matemáticas e numéricas de alto desempenho.  
- **Plotly** → Visualizações interativas e animadas.

----

## 📚 Recomendações de Estudo e Boas Práticas

## 🔧 Aprendizado das Tecnologias

- **Python**  
  - [Python.org (documentação oficial)](https://docs.python.org/pt-br/3/)  
  - [Curso Python para Data Science - DataCamp](https://www.datacamp.com/courses/tech:python)  
  - [W3Schools - Python](https://www.w3schools.com/python/)  

- **Pandas**  
  - [Documentação oficial Pandas](https://pandas.pydata.org/docs/)  
  - [Guia rápido Pandas - Kaggle](https://www.kaggle.com/learn/pandas)  

- **NumPy**  
  - [Documentação oficial NumPy](https://numpy.org/doc/stable/)  
  - [W3Schools - NumPy](https://www.w3schools.com/python/numpy/default.asp)  

- **Plotly (visualizações interativas)**  
  - [Documentação oficial Plotly Express](https://plotly.com/python/plotly-express/)  
  - [Tutoriais Plotly - Medium](https://towardsdatascience.com/interactive-data-visualization-with-plotly-in-python-4d4e7a3a0d37)  

- **ETL (Extração, Transformação e Carga)**  
  - [Artigo - ETL com Python e Pandas](https://towardsdatascience.com/etl-pipeline-using-pandas-python-8c183ab4a548)  
  - [FreeCodeCamp - Data Engineering com Python](https://www.freecodecamp.org/news/etl-data-pipeline-tutorial/)  

---

## 💡 Dicas de Boas Práticas (Versionamento e Colaboração)

- **Git & GitHub**  
  - Use `git init` para iniciar o repositório.  
  - Faça commits pequenos e frequentes com mensagens descritivas:  
    ```bash
    git commit -m "feat: adiciona etapa de transformação no ETL"
    ```  
  - Utilize **branches** para novas features (`feature/eda-graficos`).  
  - Faça **Pull Requests (PRs)** para revisão de código.  
  - Use **Issues** e **Projects (Kanban)** do GitHub para organizar tarefas (similar ao Trello).  

- **Controle de Versão do Notebook**  
  - Evite salvar saídas pesadas no `.ipynb` (limpe antes de commitar).  
  - Versione também os **dados tratados** (`TelecomX_clean.csv`) e não apenas o bruto.  
 

