
# Análise de Vendas Online: Tratamento e Exploração de Dados

Bem-vindo ao repositório do projeto **Análise de Vendas Online**! Este projeto demonstra habilidades em **tratamento de dados** e **análise exploratória** usando Python, com foco em limpar um dataset "sujo" de vendas online de uma loja de eletrônicos e extrair insights úteis para uma apresentação.

## Objetivo
O objetivo é transformar um dataset bruto e inconsistente em uma base limpa e estruturada, pronta para análises. A partir disso, exploramos padrões como:
- Quantidade de vendas por categoria.
- Período de maior faturamento.
- Produtos mais vendidos (em valor).
- Evolução temporal das vendas.
- Principais clientes por gasto.

## Dataset
O dataset original (`vendas_online_sujas.csv`) contém 1010 registros de vendas online, com 5 colunas:
- `ID_Pedido`: Identificador único do pedido.
- `Nome_Cliente`: Nome do cliente.
- `Valor_Compra`: Valor da compra (em reais).
- `Data_Pedido`: Data da transação.
- `Categoria_Produto`: Categoria do produto vendido.

### Problemas Identificados
- **Valores ausentes**: Nulos em `Nome_Cliente` e `Valor_Compra`.
- **Formatos inconsistentes**: Datas em vários formatos (ex.: "2022-06-28", "28/06/2022") e valores com "R$" (ex.: "R$ 689.85").
- **Erros tipográficos**: Nomes como "João Silva" e "Joao Silva123".
- **Outliers**: Valores extremos (ex.: 843431.97).
- **Duplicatas**: Pedidos repetidos (ex.: `P0123` aparece duas vezes).
- **Categorias inconsistentes**: "Smartphone" vs. "smartphone" vs. "televisão".

---

## Metodologia
O projeto foi dividido em duas fases principais:

### 1. Pipeline de Tratamento de Dados
Uma pipeline modular foi implementada em Python para limpar o dataset:
- **Carregamento**: Leitura do CSV com Pandas.
- **Datas**: Padronização para `YYYY-MM-DD`.
- **Valores**: Conversão de "R$ X" para `float`.
- **Ausentes**: Preenchimento de `Nome_Cliente` com "Desconhecido" e `Valor_Compra` com a mediana por categoria.
- **Nomes**: Normalização de variações (ex.: "Joao Silva" → "João Silva").
- **Categorias**: Uniformização (ex.: "televisão" → "TV").
- **Duplicatas**: Remoção baseada em `ID_Pedido`.
- **Outliers**: Eliminação de valores extremos com z-score > 3.

### 2. Análise Exploratória
Após a limpeza, geramos visualizações para extrair insights:
1. **Quantidade de Vendas por Categoria** (gráfico de barras).
2. **Período de Maior Venda** (barras por ano/mês).
3. **Produto Mais Vendido** (pizza com valor total por categoria).
4. **Evolução das Vendas** (linha temporal).
5. **Top Clientes** (barras horizontais com os 10 maiores gastadores).

---

## Resultados
- **Dataset Limpo**: Reduzido de 1010 para 1000 registros únicos, sem valores ausentes ou inconsistências.
- **Insights**:
  - A categoria "Smartphone" lidera em quantidade e valor de vendas.
  - Picos de faturamento ocorrem em meses como novembro (possível Black Friday).
  - Clientes como "João Silva" e "Lucas Pereira" são os maiores compradores.

### Exemplo de Visualizações

![Quantidade de Vendas por Categoria](https://github.com/user-attachments/assets/a6f8c545-a1b3-4d4f-aea6-dbbce0c12340)
![Evolução das Vendas](https://github.com/user-attachments/assets/377b567a-264b-4e1a-b2b5-4762e80b147a)


---

## Tecnologias Utilizadas
- **Python 3.x**
- **Bibliotecas**:
  - `pandas`: Manipulação de dados.
  - `numpy`: Cálculos numéricos.
  - `matplotlib` e `seaborn`: Visualizações.

---

## Como Reproduzir
1. **Pré-requisitos**:
   - Instale as dependências:
     ```bash
     pip install pandas numpy matplotlib seaborn
     ```

2. **Estrutura do Repositório**:
   ```
   ├── data/
   │   ├── vendas_online_sujas.csv  # Dataset original
   │   └── vendas_online_limpo.csv  # Dataset tratado (gerado)
   ├── images/                      # Pasta para salvar gráficos
   ├── notebook.ipynb               # Código completo (opcional)
   └── README.md
   ```

3. **Executar o Projeto**:
   - Clone o repositório:
     ```bash
     git clone https://github.com/seu_usuario/analise-vendas-online.git
     cd analise-vendas-online
     ```
   - Rode o script ou notebook:
     ```bash
     python script.py
     ```
   - O script carrega `vendas_online_sujas.csv`, aplica a pipeline e gera os gráficos.

---

## Próximos Passos
- Adicionar análises preditivas (ex.: previsão de vendas).
- Explorar sazonalidade com mais detalhes.
- Implementar testes unitários para a pipeline.

---

## Contato
- **Autor**: Jheferson Warley
- **GitHub**: [github.com/jheferson-warley](https://github.com/jheferson-warley)
- **Email**: [jhefersonwarley@gmail.com](mailto:jhefersonwarley@gmail.com)

Se gostou do projeto, deixe uma ⭐ no repositório!

---

