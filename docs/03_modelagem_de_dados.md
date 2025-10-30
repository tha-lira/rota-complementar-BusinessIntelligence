### Marco obrigatório - Mãos à obra!

Business Intelligence (BI), traduzido para o portugués como inteligência de negócios ou inteligência empresarial, refere-se ao conjunto de processos, aplicações e tecnologias que permitem às empresas coletar, armazenar e analisar dados para tomar decisões informadas. O principal objetivo do business intelligence é converter grandes quantidades de dados em informações significativas e úteis, fornecendo às empresas uma visão mais clara de suas operações, clientes, fornecedores e outros aspectos relevantes.

As soluções de Business Intelligence geralmente incluem ferramentas e sistemas que facilitam a extração, transformação e carregamento de dados (ETL), armazenamento de dados, relatórios e painéis de controle (dashboards), bem como análise de dados para descobrir padrões, tendências e oportunidades. Essas ferramentas permitem aos usuários, como executivos, analistas e gerentes, acessarem informações de forma rápida e compreensível, facilitando a tomada de decisões estratégicas.

Neste projeto, você mergulhará na criação de uma estrutura de relacionamentos de tabelas que permitirão a construção de um completo painel de controle (dashboard) com recursos visuais integrados. Além disso, você terá a oportunidade de aplicar na prática todo o conhecimento adquirido sobre narrativa de dados, com o objetivo final de obter um painel fácil de usar.

### 🟦 Processar e preparar a base de dados

**📊 Conexão e Importação dos Dados**

**📊 Identificar E Gerenciar Valores Nulos**

**Rooms**

Linhas e colunas: 48.875 linhas e 8 colunas

Colunas: id, name, neighbourhood, neighbourhood_group, latitude, longitude, room_type, minimum_nights

Valores nulos: Nenhum (0 nulos em todas as colunas)

✅ Dataset limpo, sem valores faltantes.

**Reviews**

Linhas e colunas: 48.875 linhas e 8 colunas

Colunas: id, host_id, price, number_of_reviews, last_review, reviews_per_month, calculated_host_listings_count, availability_365

⚠️ Valores nulos:

`number_of_reviews`: 20 (0,04%)  preencher com 0

`last_review`: 10.019 (20,54%) preencher com sem review

`reviews_per_month`: 10.019 (20,50%) preencher com 0

`availability_365`: 156 (0,32%) preencher com  mediana

💡 Durante a análise exploratória do dataset de listagens, foram identificadas colunas com valores nulos que precisavam de tratamento para garantir a integridade dos dados e permitir análises consistentes. A coluna `number_of_reviews` apresentou 20 valores nulos, correspondendo a 0,04% do total. Esses registros foram preenchidos com 0, uma vez que imóveis sem avaliações registradas naturalmente possuem zero reviews, tornando o preenchimento coerente com a realidade dos dados. A coluna `last_review` apresentou 10.019 valores nulos, equivalentes a 20,54% do total. Para esses casos, optou-se por preencher os valores com a expressão “sem review”, preservando a informação de que tais imóveis ainda não receberam avaliações e evitando distorções em análises temporais. Já a coluna `reviews_per_month`, que também apresentou 10.019 valores nulos (20,50%), foi preenchida com 0, mantendo a coerência com a coluna `number_of_reviews`, pois imóveis sem avaliações mensais registradas devem ter média de reviews igual a zero. Por fim, a coluna `availability_365` apresentou 156 valores nulos (0,32%) e foi preenchida com a mediana da coluna. Essa abordagem numérica preserva a distribuição da variável e evita que outliers distorçam os resultados. Com essas ações, todos os valores nulos foram tratados de maneira consistente, garantindo que o dataset esteja pronto para análises estatísticas e de negócio confiáveis.

**Hosts**

Linhas e colunas: 37.484 linhas e 2 colunas

Colunas: host_id, host_name

⚠️ Valores nulos:

`host_name`: 18 nulos (0,05%)

💡 Remoção dos valores nulos, 18 valores nulos em 37.484 linhas (~0,05%), a remoção é totalmente segura sem impactar sua análise ou gerar distorção no numeros.

```
# ----------------------------------------------------
# 1. IDENTIFICAÇÃO DE VALORES NULOS
# ----------------------------------------------------

print("\n🔍 Verificando valores nulos por coluna:\n")
print(df.isnull().sum())

# Percentual de nulos
print("\n📊 Percentual de valores nulos por coluna:")
print((df.isnull().mean() * 100).round(2))
```

**📊 Identificar E Gerenciar Valores Duplicados**

Foi realizada a verificação de registros duplicados nos três datasets: Room, Reviews eHosts.

💡 Tosos os data sets estão livres de duplicidade, garantindo que não haj resistros repetidos que possam distorer analises estatisticas ou rwlatorios de negocios 

```
# ----------------------------------------------------
# 1. IDENTIFICAÇÃO DE VALORES DUPLICADOS
# ----------------------------------------------------

duplicados = df.duplicated()
print("Total de linhas duplicadas:", duplicados.sum())
```
### Identificar E Manejar Dados Fora Do Alcance Da Análise

✅ Rooms ()

Colunas categóricas:

 - id, name, neighbourhood, neighbourhood_group, room_type

Colunas numéricas:
 - latitude, longitude, minimum_nights.

✅ Reviews ()

Colunas categóricas:

Colunas numéricas:

✅ Hosts ()

Colunas categóricas:

Colunas numéricas:

**📊 Identificar E Gerir Dados Discrepantes Em Variáveis Categóricas**

Ajustar a escrita para padronização da escrita 

**📊 Identificar E Gerenciar Dados Discrepantes Em Variáveis Numéricas**




**📊 Verificar E Alterar Tipo De Dado**

**📊 Criar Novas Variáveis**

**📊 Unir Tabelas**






