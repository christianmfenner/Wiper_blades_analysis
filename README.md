# Análise de Palhetas e Chuva em São Paulo

Este repositório contém um notebook (`Análise_Palhetas.ipynb`) que cruza **tendências de busca no Google Trends** pelo termo "palheta" com **dados climáticos (chuva)** de São Paulo e região.  
O objetivo é explorar possíveis relações entre interesse popular e fatores climáticos.

---

## 📊 Estrutura da Análise

1. **Histórico de Busca ("palheta")**
   - Uso da biblioteca [pytrends](https://github.com/GeneralMills/pytrends).
   - Coleta da popularidade do termo "palheta" no estado de São Paulo.
   - Série temporal desde 2010 até a data atual.

2. **Previsão de Chuva**
   - Coleta da previsão via **API do HG Brasil**.
   - Extração da previsão de chuva diária em São Paulo (mm).

3. **Histórico de Chuva (Várias cidades de SP)**
   - Uso da **API do Open-Meteo** para obter dados históricos.
   - Cidades analisadas: São Paulo, Guarulhos, Campinas, São Bernardo, Santo André, Osasco, Sorocaba e Ribeirão Preto.
   - Cálculo da **chuva ponderada pela população de cada cidade**.

4. **Integração dos Dados**
   - Junção entre a série temporal de buscas e o histórico de precipitação.
   - Preparação de dataset final para análises comparativas.
     
5. **Modelagem Preditiva**
   - Foi treinado e testado um **modelo de Regressão Linear** para avaliar a relação entre o interesse em "palhetas" e os níveis de precipitação.
   - O modelo escolhido foi a **Regressão Linear**, devido ao seu bom desempenho e interpretabilidade.
  
---

## 🛠️ Tecnologias Utilizadas

- **Python 3**
- **Bibliotecas**:
  - `pandas` → manipulação de dados
  - `requests` → requisições às APIs
  - `pytrends` → Google Trends
  - `datetime` → manipulação de datas
  - `matplotlib` / `seaborn` (opcional) → visualizações

---

## ▶️ Como Executar

### 1. Clonar o repositório
```bash
git clone https://github.com/seu-usuario/seu-repo.git
cd seu-repo
2. Criar ambiente virtual (opcional, mas recomendado)
bash
Copiar código
python -m venv venv
source venv/bin/activate   # Linux/Mac
venv\Scripts\activate      # Windows
3. Instalar dependências
bash
Copiar código
pip install -r requirements.txt
(Se não houver requirements.txt, instale manualmente:)

bash
Copiar código
pip install pandas requests pytrends matplotlib seaborn
4. Executar o notebook
Abra o Jupyter Notebook ou Jupyter Lab:

bash
Copiar código
jupyter notebook
E rode o arquivo Análise_Palhetas.ipynb.

🔑 APIs Utilizadas
Google Trends via Pytrends

HG Brasil - Weather API

Open-Meteo Archive API

⚠️ Para a API do HG Brasil é necessário possuir uma chave de acesso (API Key).

📂 Estrutura do Repositório
bash
Copiar código
📦 projeto-palhetas-chuva
 ┣ 📜 Análise_Palhetas.ipynb   # Notebook principal
 ┣ 📜 README.md                # Documentação
 ┗ 📜 requirements.txt         # Dependências (opcional)
📌 Observações
Os dados do Google Trends são coletados em janelas trimestrais devido a limitações da API.

Os dados climáticos históricos são ponderados pela população das cidades selecionadas.

É possível adaptar o código para outros termos de busca ou regiões geográficas.

