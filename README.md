# 📊 Projeto de Análise de Cancelamento de Clientes

Este projeto tem como objetivo analisar uma base de dados de clientes para identificar os principais fatores que levam ao **cancelamento de serviços**. Ao final, são sugeridas estratégias para **redução do cancelamento** com uma **simulação de impacto** dessas ações.

## 🧠 Motivação

O cancelamento recorrente de clientes pode afetar diretamente a receita e o crescimento de uma empresa. A análise preditiva dos fatores que contribuem para o cancelamento permite que a empresa atue de forma preventiva, criando estratégias de retenção mais eficazes.

---

## ⚙️ Ferramentas e Bibliotecas Utilizadas

Este projeto foi desenvolvido em **Python**, dentro de um **Jupyter Notebook (`.ipynb`)**, aproveitando a divisão em blocos de código e texto para documentar cada etapa.

As principais bibliotecas utilizadas foram:

- `pandas` → manipulação de dados
- `numpy` → operações matemáticas
- `openpyxl` → suporte a arquivos `.xlsx`
- `nbformat` / `ipykernel` → estruturação do notebook
- `plotly` → criação de gráficos interativos

Para instalar uma biblioteca no notebook, utilize:
```python
!pip install nome_da_biblioteca
```

---

## 🪜 Etapas do Projeto

### ✅ 1. Importação da Base de Dados

A base de dados `cancelamentos_sample.csv` foi carregada com:
```python
import pandas as pd
tabela = pd.read_csv("cancelamentos_sample.csv")
```

### ✅ 2. Visualização da Tabela

Utilizamos `display(tabela)` para visualizar os dados no notebook, facilitando a leitura em comparação ao `print()`.

### ✅ 3. Tratamento de Dados

- Remoção de colunas irrelevantes (ex: `CustomerID`)
- Verificação da estrutura da tabela: `tabela.info()`
- Exclusão de linhas com valores nulos: `tabela = tabela.dropna()`

### ✅ 4. Análise Inicial

Verificação da proporção de cancelamentos na base:
```python
display(tabela["cancelou"].value_counts())
```

### ✅ 5. Investigação das Causas

Análise visual com gráficos interativos (`plotly`) comparando a coluna `cancelou` com:

- **Tipo de contrato**
- **Nº de ligações ao call center**
- **Dias de atraso no pagamento**

Os gráficos revelaram padrões relevantes.

---

## 🔍 Principais Insights

A análise revelou três fatores fortemente ligados ao cancelamento:

1. **Tipo de contrato:** Todos os clientes com contrato mensal cancelaram.
   - 💡 Estratégia: **Oferecer descontos nos planos trimestrais e anuais**
2. **Nº de ligações ao call center:** Clientes que ligaram mais de 4 vezes cancelaram.
   - 💡 Estratégia: **Resolver problemas em até 3 ligações**
3. **Atrasos no pagamento:** Clientes que atrasaram mais de 20 dias cancelaram.
   - 💡 Estratégia: **Equipe financeira atuante para resolver atrasos em até 10 dias**

---

## 🧪 Simulação com Estratégias Aplicadas

Filtramos a base de dados considerando:

- Remoção de clientes com contrato mensal
- Limite de 4 ou menos ligações ao call center
- Atrasos de no máximo 20 dias

### Resultado:

#### 📊 Antes:
- Clientes que cancelaram: **28.393**
- Clientes que não cancelaram: **21.603**

#### 📉 Depois:
- Clientes que cancelaram: **4.821**
- Clientes que não cancelaram: **21.446**

#### ✅ Proporção após a aplicação:
- **18,3%** cancelaram
- **81,6%** permaneceram

### ✅ Conclusão

A aplicação das estratégias reduz drasticamente o cancelamento de **56,8% para 18,3%**, validando a importância de:

- Incentivar contratos mais longos
- Melhorar o atendimento ao cliente
- Atuar sobre atrasos nos pagamentos

---

## 📌 Observações

- Todo o projeto foi documentado em um arquivo `.ipynb` com células interativas e blocos de Markdown explicativos.
- Os gráficos podem ser integrados ao **Power BI** para a criação de dashboards.

---

## 📁 Estrutura do Projeto

```
📦 Projeto Análise de Dados com Python
├── 📄 cancelamentos_sample.csv
├── 📓 analise_cancelamento.ipynb
├── 📄 README.md
```

---

Projeto desenvolvido como parte de um exercício prático na área de análise de dados, integrando Python, estatística e visualização de dados.