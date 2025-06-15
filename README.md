# Análise de Churn Telecom X

Eu sou **Arley Ribeiro**, Analista de Dados, e este projeto consiste em uma análise da evasão de clientes (Churn) na empresa Telecom X.

## Objetivo do Projeto

O principal objetivo deste projeto é:
* **Compreender o problema de Churn:** Quantificar a taxa de evasão e sua distribuição dentro da base de clientes da Telecom X.
* **Identificar os principais drivers de Churn:** Descobrir quais características dos clientes, tipos de serviço e padrões de comportamento estão mais associados ao cancelamento do serviço.
* **Fornecer insights estratégicos:** Gerar recomendações baseadas em dados para ajudar a Telecom X a reduzir sua taxa de Churn e, consequentemente, aumentar a retenção de clientes e a receita.

---

## Metodologia

A análise seguiu uma metodologia estruturada para garantir a clareza dos resultados:

* **Importação dos Dados:** Coleta e carregamento dos dados de uma API externa.
* **Limpeza e Tratamento de Dados (Feature Engineering):** Preparação dos dados para análise, incluindo normalização de estruturas aninhadas, tratamento de valores ausentes, padronização de variáveis binárias, aplicação de One-Hot Encoding para variáveis categóricas e criação de novas features relevantes (`Contas_Diarias`).
* **Exploração e Análise:** Investigação detalhada das variáveis, tanto numéricas quanto categóricas, em relação à variável alvo `Churn`.
* **Visualização:** Criação de gráficos (barras, distribuição) para ilustrar padrões, proporções e relacionamentos entre as variáveis.
* **Conclusões e Recomendações:** Resumo dos principais insights e proposição de estratégias acionáveis para mitigar o problema de churn.

---

## Ferramentas Utilizadas

Este projeto foi desenvolvido utilizando as seguintes ferramentas e bibliotecas:

* **Python**
* **Jupyter Notebook / Google Colab**
* **Pandas:** 
* **Matplotlib** 
* **Seaborn** 
* **Numpy**

---

## Etapas da Análise Detalhada

O projeto foi estruturado nas seguintes fases:

1.  **Coleta e Importação de Dados:** Os dados foram obtidos a partir de uma API, contendo informações detalhadas sobre clientes, serviços telefônicos, serviços de internet e detalhes da conta.

2.  **Limpeza e Tratamento de Dados (Feature Engineering):**
    * **Normalização de Dados Aninhados:** Estruturas JSON aninhadas foram "achatadas" para criar um `DataFrame` plano e fácil de trabalhar.
    * **Tratamento de Valores Ausentes:** Identificação e tratamento de valores ausentes (NaNs), especialmente em colunas numéricas, como `account_Charges.Total`.
    * **Padronização da Variável Alvo (`Churn`):** A variável `Churn` foi convertida de categorias textuais ('Yes'/'No') para valores numéricos binários (1/0).
    * **Mapeamento de Variáveis Binárias:** Colunas categóricas binárias foram mapeadas para 0s e 1s para facilitar a análise e modelagem.
    * **One-Hot Encoding:** Variáveis categóricas com múltiplas opções (e.g., tipo de contrato, método de pagamento, serviço de internet) foram transformadas usando One-Hot Encoding, criando colunas indicadoras.
    * **Criação de Novas Features:** Uma nova coluna, `Contas_Diarias`, foi criada para representar o custo médio diário do serviço, oferecendo uma granularidade adicional.

3.  **Análise Exploratória de Dados (EDA):**
    * **Análise Descritiva:** Geração de estatísticas descritivas para entender a distribuição e o comportamento das variáveis numéricas e categóricas.
    * **Visualização da Distribuição de Churn:** Gráficos para entender a proporção de clientes que cancelaram vs. permaneceram.
    * **Análise de Churn por Variáveis Categóricas:** Visualização e quantificação da taxa de churn em relação a diversos atributos do cliente e serviço (gênero, tipo de contrato, serviços adicionais, método de pagamento, etc.). Isso incluiu a criação de múltiplos gráficos de barras com porcentagens claras, além de um resumo textual detalhado desses insights.

---

## Conclusões e Insights

A análise revelou padrões associados ao churn:

* **Taxa de Churn Elevada:** A Telecom X apresenta uma taxa de churn geral de **26.54%**, indicando uma área crítica para intervenção.
* **Contratos Mês a Mês:** Clientes com **contrato `Month-to-month`** são o principal driver de churn, com uma taxa de **42.71%**, comparado a apenas 6.76% para outros tipos de contrato. A falta de compromisso de longo prazo é um fator de alto risco.
* **Método de Pagamento (Cheque Eletrônico):** Clientes que utilizam **`Electronic check`** como método de pagamento apresentam uma taxa de churn alarmante de **45.29%**, significativamente maior que outros métodos (17.06%).
* **Serviço de Internet (Fibra Óptica):** Clientes com **`Fiber optic`** têm uma taxa de churn de **41.89%**, quase o triplo dos clientes sem fibra (14.49%). Isso sugere problemas de qualidade no serviço de fibra ou uma base de clientes mais exigente.
* **Senior Citizens:** Clientes **`SeniorCitizen`** (idosos) mostram uma taxa de churn de **41.68%**, quase o dobro dos não-idosos (23.61%).
* **Faturamento Sem Papel (`PaperlessBilling`):** Clientes que optam por faturas sem papel (`Yes`) têm o dobro da taxa de churn (33.57%) comparado aos que recebem fatura impressa (16.33%).
* **Fatores Protetores (Menor Churn):**
    * **Contratos de Dois Anos (`Two year`):** Churn de apenas **2.83%**.
    * **Serviços Adicionais:** Clientes com **`OnlineSecurity`** (14.61%) e **`TechSupport`** (15.17%) têm taxas de churn consideravelmente mais baixas. Isso demonstra o valor percebido desses serviços.
    * **Clientes com Família:** Clientes com **`Partner`** (19.66%) e **`Dependents`** (15.45%) são mais propensos a permanecer.

---

## Recomendações

Com base nas conclusões, as seguintes ações são recomendadas para a Telecom X:

1.  **Fortalecer a Fidelização:** Implementar programas de incentivo para migrar clientes de contratos mensais para anuais/bianuais, oferecendo descontos atrativos ou benefícios exclusivos.
2.  **Atenção ao Cliente de Fibra Óptica e Cheque Eletrônico:**
    * Realizar pesquisas de satisfação e auditorias de qualidade para clientes de fibra óptica.
    * Oferecer planos de fidelidade ou suporte personalizado para clientes que pagam via cheque eletrônico.
3.  **Suporte e Ofertas para Idosos:** Desenvolver canais de atendimento mais acessíveis, materiais explicativos simplificados e pacotes de serviços que atendam às necessidades específicas do usuário idoso.
4.  **Promover Serviços de Valor Agregado:** Campanhas de marketing devem destacar os benefícios da segurança online e do suporte técnico, incentivando a adesão a esses serviços como forma de aumentar a satisfação e a retenção.
5.  **Reavaliar a Experiência da Fatura Digital:** Investigar o motivo do maior churn em clientes com fatura sem papel, buscando otimizar a comunicação digital e a experiência do usuário para esse segmento.

---

## Instruções para Executar o Projeto

Para replicar e explorar esta análise em seu ambiente, siga os passos abaixo:

1.  **Clone o Repositório:**
    ```bash
    git clone [https://github.com/ribeiroarley/challenge-telecom-x-data-science.git](https://github.com/ribeiroarley/challenge-telecom-x-data-science.git)
    ```
2.  **Navegue até o Diretório do Projeto:**
    ```bash
    cd challenge-telecom-x-data-science
    ```
3.  **Ambiente Virtual (Recomendado):**
    ```bash
    python -m venv venv
    source venv/bin/activate  # No Windows: .\venv\Scripts\activate
    ```
4.  **Instale as Dependências:**
    ```bash
    pip install pandas numpy matplotlib seaborn
    ```
5.  **Execute o Jupyter Notebook / Google Colab:**
    * Se estiver usando Jupyter Notebook localmente:
        ```bash
        jupyter notebook
        ```
    * Se for usar Google Colab, faça o upload do arquivo `.ipynb` para o seu Google Drive e abra-o com o Colab.
6.  **Execute as Células:** Abra o notebook principal do projeto (ex: `analise_churn_telecomx.ipynb` - você pode nomeá-lo como preferir) e execute as células sequencialmente para reproduzir a análise, visualizações e conclusões.

---

## Desenvolvido por 💼

Arley Ribeiro da Silva Xavier

### Agradecimentos

Agradeço à **Oracle Next Education (ONE)** e à **Alura** pelo desafio e oportunidade de aprendizado.