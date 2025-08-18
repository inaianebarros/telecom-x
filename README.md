# Telecom X - Análise de Evasão de Clientes

O projeto **Telecom X - Análise de Evasão de Clientes** tem como objetivo investigar os fatores que influenciam o cancelamento de clientes (churn) em uma empresa de telecomunicações.

A evasão de clientes é um dos maiores desafios enfrentados por empresas de telecom, pois impacta diretamente a receita e aumenta os custos de aquisição de novos consumidores. Compreender os motivos que levam os clientes a cancelar seus contratos é essencial para a definição de estratégias eficazes de retenção.

 # 1. Objetivos 🎯

- Identificar os principais fatores que influenciam o **cancelamento de clientes (churn)**.

- Estruturar um pipeline de **ETL (Extração, Transformação e Carga)** para tratamento dos dados.

- Realizar uma **Análise Exploratória de Dados (EDA)** com foco em padrões de evasão.

- Criar **visualizações estratégicas** para auxiliar a tomada de decisão.

- Gerar **insights acionáveis** para as áreas de negócio e marketing.

- Fornecer subsídios para o desenvolvimento de modelos preditivos de churn.

- Apoiar a criação de estratégias de retenção de clientes.

 # 2. Tecnologias Utilizadas 🛠️ 

- **Python 3.8+:** Linguagem principal do projeto
- **Pandas:** Manipulação e análise de dados
- **NumPy:**  Computação numérica e vetorização de operações
- **Matplotlib:** Visualizações gráficas estáticas
- **Seaborn:** Visualizações estatísticas e gráficos avançados
- **Jupyter Notebook:** Ambiente de desenvolvimento interativo
-**Git/GitHub:** Controle de versão e colaboração

# 3. Estrutura do Projeto

| Caminho/Arquivo             | Descrição                               |
| --------------------------- | --------------------------------------- |
| `📞 Telecom-X`              | Pasta raiz do projeto                   |
| `📓 telecom_x.ipynb`        | Notebook principal com análise completa |
| `📋 README.md`              | Documentação do projeto                 |

# 4. Metodologia

O projeto foi conduzido com base no processo **ETL (Extract, Transform, Load)**, que organiza a preparação e análise dos dados em três etapas principais:

## 📥 Extração (Extract)

Os dados foram importados no formato JSON e carregados em DataFrames do Pandas, utilizando técnicas de normalização automática para facilitar a manipulação. Esse processo garantiu que informações aninhadas, como dados de clientes, contratos e serviços, fossem lidas corretamente e estivessem acessíveis para tratamento.

## 🔧 Transformação (Transform)

Na etapa de transformação, foram aplicados diversos procedimentos de limpeza e padronização dos dados, incluindo:

Normalização de colunas aninhadas, como **customer, phone, internet e account**.

Encoding de variáveis categóricas, convertendo valores binários (ex.: Yes/No) em representações numéricas (1/0).

Conversão de variáveis para os tipos de dados mais adequados (ex.: datas, numéricos, strings).

Aplicação de feature engineering, com a criação de novas variáveis derivadas, como a métrica contas_diarias, útil para análise de comportamento de uso.

## 📊 Carga e Análise (Load & Analysis)

Após o tratamento, os dados foram carregados em DataFrames finais prontos para exploração. A análise contemplou:

Estatísticas descritivas para entendimento geral do conjunto de dados.

Visualizações segmentadas por variáveis categóricas e numéricas.

Análises de correlação para identificar relações entre variáveis e a evasão de clientes.




