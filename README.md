# Desambiguação de Nomes de Autores Usando RandomForest e TF-IDF

Este projeto implementa dois modelos para a desambiguação de nomes de autores com base em metadados de publicações. Os modelos utilizam o **RandomForestClassifier** e comparam duas abordagens de engenharia de atributos:
1. **TF-IDF** (Term Frequency - Inverse Document Frequency) aplicado aos campos textuais (título, coautores, resumo e venue).
2. **Número de Coautores** utilizado como um atributo numérico adicional.

## Visão Geral do Projeto

- **Objetivo**: Prever o `author_id` correto com base em metadados como título da publicação, coautores, resumo e venue.
- **Modelos**:
  - Um modelo utiliza **TF-IDF** para transformar os atributos textuais em vetores numéricos.
  - O outro modelo usa o **número de coautores** como uma feature adicional sem aplicar TF-IDF aos nomes dos coautores.

### Dataset

O dataset utilizado contém metadados das publicações, incluindo os seguintes campos:
- **author_id**: Identificação única do autor.
- **author_name**: Nome do autor.
- **coauthors**: Lista de coautores da publicação.
- **publication_title**: Título da publicação.
- **abstract**: Resumo da publicação.
- **venue**: Local ou conferência onde a publicação foi apresentada.

O dataset utilizado é o AMiner12, disponível em [AMiner-12](https://www.aminer.cn/disambiguation)

### Dependências

Para rodar o projeto, você precisará instalar as seguintes bibliotecas:

```bash
pip install pandas scikit-learn
```

### Execução do Código

Para rodar o código, basta seguir os seguintes passos:

1. Clone o repositório:

```bash
git clone https://github.com/natansr/and_tfidf_random_forest.git
```

2. Navegue até o diretório do projeto:

```bash
cd and_tfidf_random_forest
```

3. Execute o script principal:

```bash
python main.ipynb
```

### Funcionalidades

O código principal realiza os seguintes passos:

1. Carregamento e pré-processamento dos dados.
2. Treinamento de dois modelos:
   - Um modelo que utiliza **TF-IDF** para vetorização dos textos.
   - Outro modelo que utiliza o **número de coautores** como feature.
3. Previsão do `author_id` com base em novos dados de teste.
4. Cálculo de métricas como **Precision**, **Recall** e **F1-Score**.

### Exemplos de Uso

Para prever o `author_id` de uma nova publicação, use a função `prever_author`:

```python
print(prever_author("Distributed Computing", "John Doe, Jane Smith", "CCGRID", "An abstract about computing", 2, usar_tfidf=True))
```

Isso retornará o `author_id` previsto com base nos metadados fornecidos.

### Métricas de Avaliação

O desempenho dos modelos é avaliado com as seguintes métricas:

- **Precisão (Precision)**: Proporção de previsões corretas para cada classe.
- **Revocação (Recall)**: Proporção de instâncias corretas recuperadas.
- **F1-Score**: Média harmônica entre precisão e recall.

### Autores

- Natan Rodrigues
- Leonardo Seger
- Contato: [email](mailto:natan5souza@gmail.com)
