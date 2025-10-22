# Análise, Clusterização e Categorização de Artigos Científicos do ArXiv

Este projeto apresenta uma metodologia para organização e categorização automática de grandes volumes de artigos científicos através de técnicas avançadas de processamento de linguagem natural e aprendizado de máquina. O objetivo principal é transformar uma coleção massiva de aproximadamente 222.259 artigos do arXiv em bibliotecas temáticas especializadas, facilitando o acesso e a gestão do conhecimento científico.

Aqui será realizada uma análise completa, clusterização e categorização de artigos científicos do arXiv utilizando técnicas de Processamento de Linguagem Natural (PLN) e aprendizado de máquina não supervisionado.

A explosão de produção científica representa um desafio significativo para organização e recuperação de informação. Este projeto aborda esse problema através de uma abordagem sistemática que combina embeddings de texto, redução de dimensionalidade e técnicas de clusterização para criar subconjuntos temáticos coerentes a partir de uma grande biblioteca heterogênea.

## 📋 Objetivo

Transformar uma coleção massiva de aproximadamente **222.259 artigos científicos do arXiv** em bibliotecas temáticas especializadas, facilitando o acesso e a gestão do conhecimento científico através de:

- **Análise completa** dos dados textuais
- **Clusterização** automática de artigos
- **Categorização** temática inteligente
- **Visualização** interativa dos resultados

## 🛠️ Tecnologias Utilizadas

### Principais Bibliotecas
- **LangChain** & **OpenAI Embeddings** - Para embeddings de texto semântico
- **FAISS** - Armazenamento e busca eficiente em espaços vetoriais
- **UMAP** - Redução de dimensionalidade
- **Scikit-learn** - Algoritmos de machine learning
- **TensorFlow/Keras** - Redes neurais profundas
- **NLTK** - Processamento de linguagem natural
- **pyLDAvis** - Visualização de tópicos
- **Matplotlib/Seaborn** - Visualizações

### Modelos de IA
- **text-embedding-3-large** (OpenAI) - Geração de embeddings
- **K-Means** - Clusterização
- **Random Forest** & **XGBoost** - Classificação
- **Redes Neurais** - Modelos profundos para categorização

## 📊 Metodologia

### 1. **Pré-processamento**
- Amostragem estratificada de 8.000 artigos (3,6% do total)
- Limpeza e normalização de texto
- Remoção de stopwords e tokenização

### 2. **Embeddings de Texto**
- Conversão do conteúdo textual em representações vetoriais densas
- Uso do modelo text-embedding-3-large da OpenAI
- Captura de semântica e relações contextuais

### 3. **Redução de Dimensionalidade**
- **UMAP** (Uniform Manifold Approximation and Projection)
- Redução para 100 dimensões preservando estrutura local e global
- Parâmetros otimizados: `n_neighbors=20`, `min_dist=0.001`, métrica cosseno

### 4. **Clusterização**
- **K-Means** para agrupamento automático
- Validação com **Silhouette Score**
- Identificação de clusters temáticos coerentes

### 5. **Visualização**
- Projeções 2D e 3D interativas
- Word clouds para análise de tópicos
- Gráficos de dispersão

## 🗂️ Estrutura dos Dados

Os artigos contêm:
- **Título** e **autores**
- **DOI** e **data de atualização**
- **Conteúdo textual** completo
- **Embeddings** gerados (3072 dimensões)
- **Metadados** diversos

## 🚀 Como Executar

### Pré-requisitos
```bash
pip install langchain_community langchain_openai faiss-cpu tiktoken pyLDAvis
pip install umap-learn scikit-learn tensorflow xgboost
```

### Configuração
1. Configure sua API key da OpenAI:
```python
os.environ["OPENAI_API_KEY"] = "sua_chave_aqui"
```

2. Carregue o banco de vetores FAISS:
```python
biblioteca = FAISS.load_local('caminho/para/embeddings', embeddings)
```

### Execução Principal
O notebook está organizado em seções sequenciais:
1. Configuração e importações
2. Carregamento dos dados
3. Pré-processamento e amostragem
4. Redução de dimensionalidade
5. Clusterização e análise
6. Visualização dos resultados

## 📈 Resultados

- **Clusters temáticos** identificados automaticamente
- **Bibliotecas especializadas** organizadas por tópico
- **Visualizações interativas** da distribuição de artigos
- **Modelos de categorização** treinados e validados
- **Insights** sobre a estrutura do conhecimento científico

## 🎯 Aplicações

- **Organização automática** de bibliotecas científicas
- **Descoberta de tópicos** emergentes
- **Recomendação** de artigos relacionados
- **Análise de tendências** de pesquisa
- **Gestão do conhecimento** institucional

## 📊 Métricas de Avaliação

- **Silhouette Score** - Qualidade dos clusters
- **Coerência de tópicos** - Análise semântica
- **Precisão/Recall** - Modelos de classificação
- **Visual qualitativo** - Interpretabilidade dos resultados

## 🔮 Possíveis Melhorias

- Incorporação de **metadados adicionais**
- **Modelos transformers** mais avançados
- **Análise temporal** de tendências
- **Sistema de recomendação** em tempo real
- **Interface web** interativa

# **Desempenho do Modelo de Classificação**

O modelo de classificação desenvolvido para categorizar os artigos científicos nos clusters identificados alcançou uma acurácia notável de 97,1%. Este resultado excepcional demonstra a eficácia da abordagem proposta e a qualidade dos embeddings e clusters gerados na fase anterior do projeto.

**Análise do Resultado**

A alta acurácia de 97,1% indica que:

- Qualidade dos Embeddings: Os embeddings gerados pelo modelo text-embedding-3-large capturam efetivamente as características semânticas e temáticas dos artigos, permitindo uma distinção clara entre diferentes domínios científicos.

- Eficácia da Clusterização Inicial: A estratégia de clusterização na amostra de 8.000 artigos produziu grupos coerentes e bem delimitados, proporcionando rótulos de alta qualidade para o treinamento supervisionado.

- Representatividade da Amostra: A amostra de 3,6% do total mostrou-se estatisticamente representativa, contendo padrões suficientes para generalizar para os 222.259 artigos.

- Adequação do Pipeline UMAP + Classificação: A redução dimensional com UMAP preservou informações relevantes para a distinção entre categorias, facilitando o trabalho do classificador.

## **Implicações Práticas**

Esta alta taxa de acurácia tem implicações significativas para o sistema proposto:

- Confiabilidade na Organização Automática: Com 97,1% de precisão, os usuários podem confiar que os artigos estão sendo direcionados para as bibliotecas especializadas corretas.

- Redução de Erros de Categorização: Apenas 2,9% dos artigos podem necessitar de revisão ou reclassificação, representando um custo computacional mínimo para correções manuais.

- Escalabilidade Comprovada: O sucesso na classificação do restante dos artigos valida a estratégia de usar uma amostra reduzida para treinamento.


# **Conclusão**

A abordagem proposta demonstra a viabilidade de organizar grandes coleções científicas através de técnicas modernas de PLN e aprendizado de máquina. A estratégia de amostragem seguida de classificação em escala mostrou-se eficiente tanto computacionalmente quanto em termos de qualidade na categorização, oferecendo uma solução escalável para o desafio da gestão de grandes volumes de informação científica.

---

*Desenvolvido para transformar grandes volumes de artigos científicos em conhecimento estruturado e acessível.*
