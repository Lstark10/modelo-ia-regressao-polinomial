# 📊 Modelo de Predição de Salário com Regressão Polinomial

## 📋 Descrição do Projeto

Este projeto implementa um modelo de Machine Learning para predição de salários baseado em **Regressão Polinomial**. O modelo utiliza como variáveis preditoras o tempo de empresa e o nível hierárquico do funcionário para estimar o salário em reais.

O projeto inclui:
- 🔬 **Análise Exploratória de Dados (EDA)** completa
- 🤖 **Modelo de Machine Learning** com validação cruzada
- 🚀 **API REST** desenvolvida com FastAPI
- 🖥️ **Interface Web** desenvolvida com Streamlit
- 📈 **Comparação entre modelos** Linear vs Polinomial

## 🛠️ Tecnologias Utilizadas

- **Python 3.8+**
- **Machine Learning**: scikit-learn
- **Análise de Dados**: pandas, numpy
- **Visualização**: matplotlib, seaborn, pingouin
- **API**: FastAPI, uvicorn
- **Interface Web**: Streamlit
- **Testes Estatísticos**: scipy, statsmodels
- **Serialização**: joblib

## 📁 Estrutura do Projeto

```
regressao-polinomial/
├── modelo_ia.ipynb           # Notebook principal com análise e treinamento
├── dataset.csv               # Dataset com dados de salários
├── modelo_salario.pkl        # Modelo treinado serializado
├── api_modelo_salario.py     # API REST para predições
├── app_streamlit_salario.py  # Interface web Streamlit
├── requirements.txt          # Dependências do projeto
└── README.md                # Documentação do projeto
```

## 📊 Dataset

O dataset contém **1.002 registros** com as seguintes variáveis:

| Variável | Descrição | Tipo |
|----------|-----------|------|
| `tempo_na_empresa` | Tempo em meses que o funcionário está na empresa | Numérica |
| `nivel_na_empresa` | Nível hierárquico do funcionário (1-10) | Numérica |
| `salario_em_reais` | Salário em reais (variável target) | Numérica |

### 📈 Características dos Dados

- **Correlações identificadas**: 
  - Tempo na empresa vs Salário: Correlação positiva moderada
  - Nível na empresa vs Salário: Correlação positiva forte
- **Outliers**: Identificados através de boxplots
- **Distribuição**: Análise através de histogramas e pairplots

## 🔬 Metodologia

### 1. Análise Exploratória de Dados (EDA)
- ✅ Verificação de valores ausentes
- ✅ Análise estatística descritiva
- ✅ Detecção de outliers com boxplots
- ✅ Análise de correlações (Spearman)
- ✅ Visualizações de distribuições
- ✅ Bucketing para análise categórica

### 2. Modelagem
- **Validação Cruzada**: K-Fold com 5 splits
- **Pré-processamento**: StandardScaler para normalização
- **Pipeline**: Preprocessamento + Features Polinomiais + Regressão Linear

### 3. Comparação de Modelos
- **Modelo Linear**: Baseline
- **Modelos Polinomiais**: Graus de 1 a 10
- **Seleção**: Baseada em RMSE e R² Score

### 4. Análise de Resíduos
- ✅ Linearidade dos resíduos
- ✅ Homocedasticidade
- ✅ Normalidade (Shapiro-Wilk, Kolmogorov-Smirnov, Lilliefors)
- ✅ QQ-Plot para validação visual

## 📊 Métricas do Modelo

O modelo final apresenta as seguintes métricas de performance:

- **RMSE Treino**: ~XXX (valor obtido após execução)
- **RMSE Teste**: ~XXX (valor obtido após execução)
- **R² Score**: ~XXX (valor obtido após execução)
- **% Diferença RMSE**: Controle de overfitting

## 🚀 Como Executar o Projeto

### 1. Instalação das Dependências

```bash
pip install -r requirements.txt
```

### 2. Executar a Análise no Jupyter

```bash
jupyter notebook modelo_ia.ipynb
```

### 3. Executar a API

```bash
python api_modelo_salario.py
```

A API estará disponível em: `http://127.0.0.1:8000`

#### Endpoint da API

**POST** `/predict`

**Request Body:**
```json
{
  "tempo_na_empresa": 80,
  "nivel_na_empresa": 7
}
```

**Response:**
```json
{
  "salario_em_reais": 5234.56
}
```

### 4. Executar a Interface Streamlit

```bash
streamlit run app_streamlit_salario.py
```

A interface estará disponível em: `http://localhost:8501`

## 🖥️ Interface Web

A interface Streamlit permite:
- 🎚️ **Sliders interativos** para ajustar parâmetros
- 📊 **Predição em tempo real**
- 💰 **Visualização do salário estimado**

### Parâmetros de Entrada:
- **Tempo na Empresa**: 1 a 120 meses
- **Nível na Empresa**: 1 a 10

## 🧪 Testes e Validação

### Testes Estatísticos Implementados:
1. **Shapiro-Wilk**: Teste de normalidade dos resíduos
2. **Kolmogorov-Smirnov**: Teste de normalidade alternativo
3. **Lilliefors**: Teste de normalidade mais rigoroso

### Validação Visual:
- **QQ-Plot**: Verificação visual da normalidade
- **Scatter Plot de Resíduos**: Verificação de homocedasticidade

## 📈 Resultados e Insights

### Principais Descobertas:
1. **Regressão Polinomial** apresentou melhor performance que modelo linear
2. **Nível hierárquico** é o preditor mais importante
3. **Tempo na empresa** contribui significativamente para predição
4. Modelo demonstra boa **generalização** com validação cruzada

### Interpretação Profissional:
- Funcionários com maior nível hierárquico recebem salários proporcionalmente maiores
- O tempo na empresa influencia positivamente no salário
- Existe uma relação não-linear entre as variáveis e o salário

## 📝 Requisitos do Sistema

- **Python**: 3.8 ou superior
- **Memória RAM**: Mínimo 4GB
- **Espaço em Disco**: 500MB livres


## 📄 Licença

Este projeto está sob a licença MIT. Veja o arquivo `LICENSE` para mais detalhes.

## 🤝 Contribuições

Contribuições são bem-vindas! Por favor:

1. Faça um fork do projeto
2. Crie uma branch para sua feature (`git checkout -b feature/AmazingFeature`)
3. Commit suas mudanças (`git commit -m 'Add some AmazingFeature'`)
4. Push para a branch (`git push origin feature/AmazingFeature`)
5. Abra um Pull Request

