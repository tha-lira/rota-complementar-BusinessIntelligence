
1. Identificação do Projeto

Projeto: Análise de Dados do Airbnb – Eficiência e Rentabilidade
Autora: Thais Lira
Data: Outubro/2025
Ferramentas: Google Colab, Power BI
Linguagens: Python, DAX

2. Contexto e Justificativa de Negócio

Com o avanço das novas tecnologias, plataformas como o Airbnb revolucionaram o mercado de hospedagem (...).
Este projeto visa explorar e analisar dados sobre a disponibilidade de quartos, utilizando ferramentas de Business Intelligence para gerar insights que melhorem a eficiência operacional e a rentabilidade da plataforma e dos anfitriões.

3. Objetivo do Projeto

Realizar uma análise exploratória e integrada das informações de quartos, anfitriões e avaliações do Airbnb, a fim de:

 - Identificar padrões de preços, demanda e disponibilidade;

 - Avaliar a performance de hosts e tipos de quarto;

 - Oferecer suporte à tomada de decisão estratégica com dashboards interativos no Power BI.

4. Estrutura dos Dados

Os dados são organizados em 3 tabelas — duas dimensões e uma tabela fato.

🏠 Tabela rooms (Dimensão)

| Coluna                | Tipo   | Descrição                                            |
| :-------------------- | :----- | :--------------------------------------------------- |
| `id`                  | int    | Identificador exclusivo do quarto                    |
| `nome`                | string | Nome do anúncio                                      |
| `bairro`              | string | Bairro (sigla)                                       |
| `neighbourhood_group` | string | Região/Bairro completo                               |
| `latitude`            | float  | Coordenada geográfica                                |
| `longitude`           | float  | Coordenada geográfica                                |
| `room_type`           | string | Tipo de acomodação (entire home, private room, etc.) |
| `minimum_nights`      | int    | Número mínimo de noites aceitas                      |

👤 Tabela hosts (Dimensão)

| Coluna       | Tipo   | Descrição                       |
| :----------- | :----- | :------------------------------ |
| `host_id`    | int    | Identificador exclusivo do host |
| `nomedohost` | string | Nome do anfitrião               |


⭐ Tabela reviews (Fato)
| Coluna                         | Tipo  | Descrição                                   |
| :----------------------------- | :---- | :------------------------------------------ |
| `id`                           | int   | Identificador do quarto (chave estrangeira) |
| `host_id`                      | int   | Identificador do host (chave estrangeira)   |
| `preço`                        | float | Preço por noite                             |
| `numberofreviews`              | int   | Total de avaliações                         |
| `last_review`                  | date  | Data da última avaliação                    |
| `reviewspermonth`              | float | Média de avaliações mensais                 |
| `calculatedhostlistings_count` | int   | Total de listagens do host                  |
| `availability_365`             | int   | Dias disponíveis por ano                    |

5. Modelo de Dados (Relacionamentos)

- reviews é a tabela fato (contém os eventos — as avaliações).

- rooms e hosts são tabelas dimensão (contêm atributos descritivos).

Chaves primárias:

- rooms.id ↔ reviews.id

- hosts.host_id ↔ reviews.host_id

Esse modelo facilita consultas analíticas (OLAP) e a criação de dashboards de BI.

6. Etapas do Projeto

