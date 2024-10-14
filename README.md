# Sistema de Previsão de Avaliação de Produtos

## Descrição do Projeto

Este projeto utiliza aprendizado de máquina para prever se um cliente vai gostar de um produto com base em características de compras anteriores. Ele usa um **Random Forest Classifier** para classificar se um cliente dará uma avaliação positiva ("Gostou") ou negativa ("Não Gostou") para um produto.

### Principais Funcionalidades:

1. **Carregamento de Dados:**
   - Dataset contendo registros de vendas de produtos eletrônicos foi utilizado. Ele inclui colunas como:
     - `Age` (Idade do Cliente),
     - `Gender` (Gênero do Cliente),
     - `Total Price` (Preço Total da Compra),
     - `Unit Price` (Preço Unitário do Produto),
     - `Quantity` (Quantidade de Produtos Comprados),
     - `Product Type` (Tipo de Produto),
     - `Rating` (Avaliação do Produto pelo Cliente).

2. **Preparação dos Dados:**
   - O dataset foi pré-processado para criar uma variável alvo chamada `Liked`, que indica se o cliente gostou ou não do produto. Se a avaliação (`Rating`) foi igual ou superior a 4, a coluna `Liked` é marcada como 1 (Gostou). Se for menor que 4, é marcada como 0 (Não Gostou).
   
3. **Codificação de Variáveis Categóricas:**
   - O `LabelEncoder` foi utilizado para codificar variáveis categóricas como `Gender` (gênero) e `Product Type` (tipo de produto).

4. **Treinamento do Modelo:**
   - Um modelo de **Random Forest Classifier** foi treinado usando os dados históricos. As variáveis de entrada utilizadas foram:
     - `Age` (idade),
     - `Gender` (gênero),
     - `Total Price` (preço total da compra),
     - `Unit Price` (preço unitário),
     - `Quantity` (quantidade de produtos comprados),
     - `Product Type` (tipo de produto).
   - O modelo é capaz de prever se o cliente gostou ou não do produto com base nessas informações.

5. **Previsão:**
   - Uma função `predict_liked()` foi criada para fazer previsões com base em novos inputs. A função leva em consideração idade, gênero, preço total, preço unitário, quantidade e tipo de produto, e retorna se o cliente provavelmente "Gostou" ou "Não Gostou".

6. **Avaliação do Modelo:**
   - Foram calculados a **matriz de confusão** e métricas de desempenho como **accuracy**, **precision**, **recall**, e **f1-score** para avaliar o modelo.
   - Além disso, foi gerado um gráfico de **importância das características** para mostrar quais variáveis tiveram mais impacto na previsão.

---

## Como Rodar o Projeto

1. **Instalação das Dependências:**
   - As bibliotecas necessárias para rodar o projeto estão listadas no arquivo `requirements.txt`.
   - Para instalar as dependências, execute:

     ```bash
     pip install -r requirements.txt
     ```

2. **Rodando o Código:**
   - Para rodar o código e treinar o modelo, utilize o Jupyter Notebook ou um ambiente de execução Python compatível.
   - O dataset deve ser carregado em um DataFrame utilizando `pandas`:
     ```python
     import pandas as pd
     data = pd.read_csv('caminho/para/o/dataset.csv')
     ```

3. **Fazendo Previsões:**
   - Utilize a função `predict_liked()` para prever se um cliente gostará de um produto:
     ```python
     result = predict_liked(35, 'Female', 150, 50, 2, 'Smartwatch')
     print(f"A previsão é: {result}")
     ```
     
<br>


