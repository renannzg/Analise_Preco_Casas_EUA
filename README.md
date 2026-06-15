# 🏡 Desafio: Analisando Dados de Preços de Casas nos EUA

Este repositório contém o desenvolvimento completo do desafio prático de análise de dados e modelagem preditiva utilizando o conjunto de dados público **House Prices** (Ames, Iowa) do Kaggle.

O objetivo do projeto é aplicar o pipeline completo de Ciência de Dados: desde a análise exploratória e engenharia de atributos até a aplicação de múltiplos algoritmos de aprendizagem supervisionada e não supervisionada para mapear o comportamento do mercado imobiliário.

---

## 📊 Estrutura do Desafio & Métricas Obtidas

O desenvolvimento do projeto foi estruturado de forma modular para atender rigorosamente a todos os critérios exigidos na grade de avaliação:

### 1. Análise Exploratória & Feature Engineering
* **Tratamento de Dados:** Identificação e imputação estatística de valores ausentes por mediana/moda.
* **Engenharia de Atributos:** Criação da feature de depreciação `IdadeCasa` (ano limite de 2010 menos o ano de construção do imóvel).
* **Codificação:** Conversão de variáveis textuais e categóricas estruturais utilizando a técnica de *Label Encoding*.

### 2. Aprendizagem Supervisionada (Regressão)
* Ajuste de um modelo de **Regressão Linear Múltipla** para a predição do valor contínuo do imóvel (`SalePrice`).
* **Métricas Estatísticas Obtidas:**
  * **Coeficiente de Determinação ($R^2$):** `0.7931` (79,31% da variação total dos preços é explicada pelas características físicas selecionadas).
  * **Erro Médio Absoluto (MAE):** `$25.387,53` (Margem média de desvio das previsões do modelo).
  * **Raiz do Erro Quadrático Médio (RMSE):** `$39.837,03` (Penalização decorrente de erros maiores em casas de altíssimo luxo).

### 3. Aprendizagem Supervisionada (Classificação)
* Conversão do target para um formato binário utilizando a mediana amostral (`$163.000,00`) como linha de corte para definir propriedades de **Preço Alto (1)** ou **Preço Baixo (0)**.
* Algoritmo utilizado: **Regressão Logística**.
* **Métricas de Performance Obtidas:**
  * **Acurácia Geral:** `91.78%` (Taxa global de acertos em aproximadamente 9 a cada 10 casas).
  * **Precisão:** `88.49%` (Confiabilidade ao rotular um imóvel como de alto padrão).
  * **Recall (Revocação):** `93.89%` (Capacidade de capturar as oportunidades reais de preço alto).
  * **F1-Score:** `91.11%` (Equilíbrio estável que comprova a ausência de vieses no classificador).

### 4. Aprendizagem Não Supervisionada (Clusterização)
* Segmentação natural do mercado residencial utilizando o algoritmo **K-Means** ($k=3$) baseado estritamente nas características estruturais das casas (sem informação de preço).
* **Perfis Identificados:**
  * **Cluster 0:** Imóveis Premium (Preço médio de `$313k`, novos e de altíssima qualidade).
  * **Cluster 1:** Imóveis de Entrada (Preço médio de `$118k`, antigos e de menor área útil).
  * **Cluster 2:** Imóveis Intermediários (Preço médio de `$177k`, idade e padrão construtivo moderados).

### 5. Redução de Dimensionalidade (PCA)
* Aplicação de **Análise de Componentes Principais (PCA)** para comprimir a base multidimensional em apenas 2 Componentes Principais.
* **Retenção de Informação:** **56.23%** de toda a variância e complexidade original da base de dados foram preservadas no plano bidimensional gerado.

### 6. Associação e Detecção de Outliers
* **Regras de Associação (Apriori):** Descoberta de regras lógicas com alto grau de confiança (ex: a presença conjunta de acabamento excelente garante **97,05% de certeza** de preço alto, com Lift de 1.94).
* **Local Outlier Factor (LOF):** Isolamento preciso de **30 anomalias críticas locais** (2% de contaminação), mapeando registros atípicos que geravam ruído nos modelos lineares.

### 7. Visualização Avançada & Validação Cruzada
* Geração de gráficos de dispersão cruzando as coordenadas do PCA com os resultados reais. A sobreposição visual perfeita observada entre as fronteiras dos *Clusters do K-Means* e as *Classes Reais de Preço* validou empiricamente a consistência científica de toda a modelagem.

---

## 🛠️ Como Executar o Projeto

### Pré-requisitos
Certifique-se de possuir o Python 3.x e o gerenciador de pacotes `pip` configurados no seu sistema.

1. **Clone este repositório para a sua máquina local:**
   ```bash
   git clone [https://github.com/SEU-USUARIO/Analise-Preco-Casas-EUA.git](https://github.com/SEU-USUARIO/Analise-Preco-Casas-EUA.git)
