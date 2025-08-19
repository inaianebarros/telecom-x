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
- **Git/GitHub:** Controle de versão e colaboração

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

# 5. Insights e Resultados Obtidos

A análise exploratória e de correlação revelou insights cruciais sobre o comportamento de churn na Telecom X:

- **Taxa de Churn:** Aproximadamente 26.5% dos clientes da Telecom X cancelam seus serviços, indicando um problema significativo de retenção.

## 👥 Perfil Demográfico

- **Gênero (Male/Female):** distribuição praticamente equilibrada (50,5% homens e 49,5% mulheres). Isso sugere que gênero não é um fator determinante para a evasão.

- **SeniorCitizen:** apenas 16,2% são idosos. Esse grupo é pequeno, mas em estudos de churn de telecom costuma ter maior taxa de evasão, seja por menor uso de tecnologia ou custos elevados.

- **Partner e Dependents:**
  - 51,7% não têm parceiro(a) e 70% não têm dependentes.
  - Clientes sem vínculos familiares costumam apresentar maior risco de churn, pois tendem a ser mais sensíveis a preço e menos fiéis.

## ☎️ Serviços de Telefonia

- **PhoneService:** a esmagadora maioria (90,3%) possui serviço telefônico → não é um fator diferencial para retenção.

- **MultipleLines:** 42,2% têm múltiplas linhas. Esse serviço extra pode indicar maior fidelização (clientes que concentram mais serviços na mesma operadora tendem a sair menos).

## 🌐 Serviços de Internet

- **InternetService:**
   - Fibra óptica (43,9%) é o principal tipo, seguido de DSL (34,4%) e ausência de internet (21,7%).
   - Em bases de churn, fibra óptica costuma ter maior taxa de evasão, possivelmente por preços mais altos.

- **Serviços adicionais (segurança, backup, suporte, proteção de dispositivo)** → a maioria dos clientes não utiliza (65% a 71%).
   - Isso mostra baixa adesão a serviços de valor agregado, o que aumenta risco de churn, pois o cliente fica com oferta básica e pode trocar de operadora facilmente.

- **Streaming (TV e filmes):** cerca de 39% utilizam. Pode ser um fator de retenção, já que cria conveniência no pacote.

## 📑 Conta e Pagamento

- **Contract:**
  - 55% mês a mês (altíssimo risco de churn).
  - 24% dois anos e 21% um ano → contratos longos funcionam como barreira de saída.
- **PaperlessBilling:** 59% optaram pelo faturamento digital. Normalmente correlaciona com churn mais alto, pois está associado ao perfil de cliente mais independente e tecnológico.
- **PaymentMethod:**
  - Cheque eletrônico (33,6%) tem histórico de maior churn, pois geralmente envolve clientes com menos compromisso automático.
  - Débitos automáticos (cartão ou transferência) tendem a reduzir churn, pois o pagamento é simplificado.

## Matriz de Correlação - Variáveis Numéricas vs Churn

## Análise das correlações principais 
- **customer.tenure (tempo de permanência do cliente)**
     - Correlação com Churn = -0,35 → moderadamente negativa.
     - Interpretação: Quanto maior o tempo de permanência, menor a chance de churn. Clientes fiéis (antigos) tendem a cancelar menos.
- **account.Charges.Monthly (gastos mensais)**
     - Correlação com Churn = 0,19 → fraca e positiva.
     - Interpretação: Clientes com contas mensais mais altas têm uma leve tendência a cancelar, mas não é um fator determinante.

- **account.Charges.Total (valor total gasto)**
     - Correlação com Churn = -0,20 → fraca e negativa.
     - Interpretação: Clientes que já gastaram mais no total tendem a permanecer (faz sentido, pois são mais engajados).

- **account.Charges.Daily (gasto diário)**
    - Correlação com Churn = 0,19 → fraca e positiva, comportamento semelhante ao mensal.
    - Interpretação: Um valor diário mais alto pode indicar insatisfação ou perfil de cliente mais suscetível ao cancelamento.

##  Correlação entre variáveis explicativas 
- **account.Charges.Monthly e account.Charges.Daily** → 0,99 → praticamente a mesma informação, redundância.
- **account.Charges.Total e customer.tenure**→ 0,83 → faz sentido, pois quanto mais tempo o cliente permanece, maior o gasto acumulado.
- **account.Charges.Total e account.Charges.Monthly** → 0,65 → relação moderada, esperado já que o gasto mensal influencia no acumulado.

# 📊 Principais Fatores de Risco de Evasão:

- **Contratos mensais:** Clientes com contratos mensais apresentam uma taxa de churn drasticamente maior (>42%) em comparação com contratos anuais ou bienais.

- **Clientes Recentes:** O churn é mais prevalente nos primeiros meses de contrato (Meses_Contrato tem a correlação negativa mais forte com Churn, -0.352).

- **Cobranças Mensais Elevadas:** Clientes com Cobranca_Mensal → mais alta tendem a cancelar mais (correlação positiva de 0.193).

- **Uso de internet fibra óptica sem serviços adicionais:** Clientes com Fibra Óptica têm uma taxa de churn significativamente maior (>41%) do que aqueles com DSL.

- **Método de Pagamento:** O uso de Débito Eletrônico (Electronic check) →  está associado à maior taxa de churn (>45%).

- **Ausência de Serviços Adicionais:** A falta de serviços como Segurança Online e Suporte Técnico está fortemente ligada a maiores taxas de churn.

- **Demografia:** Clientes idosos e aqueles sem parceiro(a) ou dependentes também mostram maior risco de churn.

# Fatores de Retenção (Menores Taxas de Churn):

- **Contratos de Longo Prazo:** Clientes com contratos de 1 ou 2 anos são significativamente mais leais.

- **Maior Tempo de Contrato:** Clientes mais antigos tendem a permanecer.

- **Adesão a Serviços Adicionais:** A contratação de serviços como Suporte Técnico e Segurança Online parece aumentar a retenção.

# 📊 Conclusões estratégicas

1. **Incentivar Contratos de Longo Prazo**

   Desenvolver campanhas de fidelidade que estimulem a migração de clientes de planos mensais para anuais/bienais.

   Oferecer benefícios concretos, como descontos progressivos, bônus de dados ou vantagens exclusivas para contratos estendidos.

3. **Revisar Estratégia de Preços e Valor Percebido**

   Reavaliar a precificação da Fibra Óptica, considerando seu impacto no churn.
   
   Implementar bundling de serviços de valor agregado (Segurança Online, Backup, Suporte Técnico), de forma a aumentar o valor percebido pelo cliente e reduzir sua propensão a trocar de operadora.

3. **Otimizar Métodos de Pagamento**
   
   Investigar os motivos que levam clientes com Electronic Check a apresentarem maior taxa de evasão.
   
   Incentivar formas de pagamento com menor risco de churn, como débito automático em cartão ou transferência bancária, oferecendo facilidades ou benefícios adicionais para quem aderir.

5. **Fortalecer Suporte e Serviços Adicionais**

   Promover ativamente serviços como Online Security e Tech Support, destacando seus diferenciais de segurança e conveniência.
   
   Considerar incluí-los em pacotes padrão ou oferecer períodos de teste gratuito, aumentando a adesão e a fidelização.
   
5. **Melhorar a Experiência do Cliente Recente**

   Reforçar o processo de onboarding para novos clientes, garantindo uma transição fluida e positiva.
    
   Implementar monitoramento proativo de satisfação nos primeiros meses de contrato, com contatos preventivos em casos de risco detectado.

6. **Campanhas de Retenção Segmentadas**

   Utilizar os perfis de risco identificados (ex.: clientes sem dependentes, em contratos mensais e com Electronic Check) para campanhas direcionadas.
      
   Aplicar comunicação personalizada e ofertas específicas, alinhadas ao perfil de cada cliente, aumentando a chance de retenção.

# Certificação 🥇
<img width="500" height="500" alt="badge_telecom_x" src="https://github.com/user-attachments/assets/6941fed7-c84a-4d01-918d-93b8a7312983" />

