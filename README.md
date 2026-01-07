# Criando-um-Dashboard-de-Vendas
Criando um Dashboard de Vendas

import pandas as pd

# Caminho do arquivo
arquivo = "Planilha de Vendas - final.xlsx"

# Ler as abas
calculos = pd.read_excel(arquivo, sheet_name="Cálculos")
base_vendas = pd.read_excel(arquivo, sheet_name="Base_Vendas")
dashboard = pd.read_excel(arquivo, sheet_name="Dashboard")

# Exibir primeiras linhas
print("Cálculos:")
print(calculos.head())

print("\nBase de Vendas:")
print(base_vendas.head())

print("\nDashboard:")
print(dashboard.head())

# Estatísticas básicas
print("\nResumo da Base de Vendas:")
print(base_vendas.describe())

# Faturamento total por região
faturamento_regiao = base_vendas.groupby("Região")["Faturamento"].sum()
print("\nFaturamento por Região:")
print(faturamento_regiao)

# Faturamento por categoria
faturamento_categoria = base_vendas.groupby("Categoria")["Faturamento"].sum()
print("\nFaturamento por Categoria:")
print(faturamento_categoria)

# Top 5 vendedores por faturamento
top_vendedores = base_vendas.groupby("Vendedor")["Faturamento"].sum().sort_values(ascending=False).head(5)
print("\nTop 5 Vendedores por Faturamento:")
print(top_vendedores)[Planilha de Vendas - final.xlsx](https://github.com/user-attachments/files/24474605/Planilha.de.Vendas.-.final.xlsx)

