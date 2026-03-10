# 📉 Análise de Evasão de Clientes (Churn) - Telecom X

## 📖 Sobre o Projeto

Este projeto foi desenvolvido com o objetivo de analisar os dados de clientes da **Telecom X**, uma empresa de telecomunicações que vem enfrentando um alto índice de cancelamentos de serviços (Churn). A análise busca entender a fundo o perfil dos clientes e os fatores operacionais e financeiros que os levam a deixar a empresa.

A partir de uma base de dados estruturada em JSON (simulando o consumo de uma API), foram aplicados conceitos de ETL (Extração, Transformação e Carga) e Análise Exploratória de Dados (EDA) para extrair insights estratégicos que poderão guiar as equipes de negócios na retenção de clientes.

A análise foi realizada utilizando **Python**, com foco em manipulação e limpeza de dados, além da criação de visualizações para apoiar decisões de negócios.

---

## 🎯 Objetivo da Análise

Identificar os principais fatores de risco associados à evasão de clientes, considerando:

* O impacto do tipo de contrato e método de pagamento no cancelamento.
* A relação entre os serviços de internet contratados (como Fibra Óptica) e a evasão.
* O comportamento do cliente em relação ao tempo de permanência (tenure) e aos seus gastos mensais.

O objetivo final é fornecer uma base analítica sólida, limpa e padronizada para que a equipe de Data Science possa, em uma etapa futura, desenvolver modelos preditivos.

---

## 🛠️ Tecnologias Utilizadas

* **Python**
* **Pandas** – manipulação, limpeza e achatamento (flatten) de dados
* **Matplotlib & Seaborn** – criação de gráficos e visualizações estatísticas
* **JSON** – leitura de dados aninhados simulando requisições de API
* **Google Colab / Jupyter Notebook** – ambiente de desenvolvimento

---

## 📂 Estrutura do Projeto

```text
telecom-x-churn-analysis
│
├── TelecomX_BR.ipynb           # Notebook com todo o pipeline de ETL e Análise
├── TelecomX_Data.json          # Base de dados bruta importada no projeto
├── TelecomX_dicionario.md      # Dicionário detalhando as variáveis do dataset
├── README.md                   # Documentação do projeto

```

---

## 📊 Etapas e Análises Realizadas

Durante o projeto, o pipeline de dados foi estruturado em grandes etapas fundamentais:

### 1️⃣ Extração de Dados

Os dados brutos foram consumidos do formato JSON. Como possuíam estrutura aninhada, foi utilizada a função `json_normalize` do Pandas para achatar os dados, transformando dicionários complexos em um DataFrame estruturado.

### 2️⃣ Transformação e Limpeza

Garantia da qualidade dos dados através de:

* Conversão de tipos de dados (correção de gastos totais de *string* para *float*).
* Tratamento de valores nulos, preenchendo vazios de clientes recém-adquiridos.
* Padronização de textos (remoção de espaços, conversão para minúsculas e simplificação de categorias redundantes).
* Exclusão de registros inválidos sem a variável alvo (`Churn`).

### 3️⃣ Análise Exploratória (EDA)

Exploração profunda para entender o comportamento do Churn:

* **Análise Descritiva:** Geração de estatísticas de tendência central e dispersão.
* **Distribuição da Variável Alvo:** Identificação do desbalanceamento da base (aprox. 26% de evasão).
* **Análise Categórica e Numérica:** Cruzamento do Churn com o perfil demográfico, tipo de contrato e informações financeiras dos usuários.

---

## 📈 Visualizações

Para sustentar os insights, foram gerados painéis visuais focados na clareza da informação:

* Gráfico de barras indicando o volume absoluto e a distribuição da taxa de evasão.
* *Subplots* (painéis de múltiplos gráficos) comparando o impacto do gênero, tipo de contrato, método de pagamento e tipo de internet na retenção.
* *Boxplots* revelando a concentração das evasões nos primeiros meses de contrato e a correlação com mensalidades mais altas.

---

## 🧠 Conclusão

A análise confirmou que o problema de evasão da Telecom X possui padrões muito claros:

* **O Perigo do Curto Prazo:** A esmagadora maioria dos cancelamentos ocorre nos primeiros meses de assinatura e está fortemente atrelada a contratos do tipo "mês a mês" (*month-to-month*), que não oferecem barreira de saída.
* **Alerta no Serviço Premium:** O serviço de Fibra Óptica possui uma taxa de rejeição preocupante. Considerando que mensalidades altas mostraram forte correlação com a evasão, o cliente da fibra pode não estar enxergando valor no serviço ou enfrentando problemas técnicos.
* **Método de Pagamento:** Clientes que utilizam "electronic check" apresentaram taxas anormais de cancelamento em comparação a pagamentos automatizados.

Com essas informações, a empresa pode direcionar campanhas de incentivo para migração de contratos anuais e focar em ações proativas de *Customer Success* nos primeiros meses de vida do cliente.

---

## 🚀 Possíveis Melhorias Futuras

Como próximos passos lógicos para a evolução deste projeto, sugere-se:

* **Modelagem Preditiva:** Treinamento de algoritmos de Machine Learning (como Random Forest ou Regressão Logística) para identificar clientes atuais com alto risco de cancelamento antes que eles tomem a decisão.
* **Balanceamento de Base:** Aplicação de técnicas estatísticas (como SMOTE) para lidar com o desbalanceamento da variável alvo antes do treinamento de modelos preditivos.
* **Análise de Cohort:** Avaliar o comportamento de retenção de grupos de clientes ao longo do tempo.

---

## 👩‍💻 Autora

Projeto desenvolvido por **Nicole Marcondes**.