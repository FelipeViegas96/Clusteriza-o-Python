# Clusteriza-o-Python
Customer clustering using K-Means to identify distinct profiles and enable targeted business actions. Project covers preprocessing, scaling and model persistence. Implemented with Python, Pandas and Scikit-learn.

# Clusterização de Clientes: Seguro de Saúde 🏥🐍

Este projeto utiliza técnicas de aprendizado não supervisionado (Clustering) para segmentar beneficiários de um plano de saúde. A análise visa identificar perfis distintos com base em características demográficas e de elegibilidade a descontos.

## 📌 Objetivo do Projeto
Agrupar os clientes da base `base_health_insurance.csv` utilizando o algoritmo **K-Means** para fornecer insights que auxiliem na personalização de serviços e estratégias de retenção.

## 🛠️ Tecnologias e Bibliotecas
* **Python 3.x**
* **Pandas & Numpy:** Manipulação e tratamento de dados.
* **Scikit-learn:** Escalonamento (`StandardScaler`) e Modelagem (`KMeans`).
* **Matplotlib:** Visualização do Método do Cotovelo.
* **Joblib:** Persistência dos modelos treinados para uso futuro.

## 📈 Etapas do Desenvolvimento

### 1. Tratamento e Limpeza de Dados (ETL)
* Conversão da coluna `bmi` (IMC) para formato numérico (substituindo vírgulas por pontos).
* Tratamento de tipos de dados para garantir a integridade da análise.
* Transformação da variável categórica `discount_eligibility` em binária (0 e 1) para processamento pelo modelo.

### 2. Pré-processamento
* **Seleção de Features:** Foco nas variáveis `age`, `bmi`, `children` e `discount_eligibility`.
* **Padronização:** Aplicação do `StandardScaler` para colocar todas as variáveis na mesma escala, evitando que variáveis com números maiores distorçam o agrupamento.

### 3. Definição do Número de Clusters
* Implementação do **Método do Cotovelo (Elbow Method)** testando de 1 a 10 clusters.
* Análise da inércia para determinar o ponto de equilíbrio ideal para a segmentação.

### 4. Treinamento e Persistência
* Configuração do modelo com `n_clusters=4` e `random_state` para garantir a reprodutibilidade.
* **Persistência do Modelo:** Exportação do modelo treinado (`.pkl`) e do escalonador utilizando a biblioteca `joblib`, permitindo que o projeto seja colocado em produção facilmente.

## 💡 Insights Extraídos
A base foi atualizada com os rótulos dos clusters, permitindo uma análise de média por grupo. Isso ajuda a identificar, por exemplo, grupos com maior IMC ou grupos com mais dependentes (children), direcionando campanhas específicas de saúde preventiva.

---
