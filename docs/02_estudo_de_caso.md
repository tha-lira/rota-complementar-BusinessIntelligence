### Caso

Com o avanço das novas tecnologias, novos modelos de negócio também surgem, um exemplo claro disso são as plataformas como o Airbnb, que revolucionaram a maneira como as pessoas buscam e oferecem hospedagem. Nessa perspectiva empresarial, maximizar a eficiência e a rentabilidade tornou-se fundamental tanto para os anfitriões quanto para a própria plataforma.

Nesse contexto, este projeto concentra-se na exploração e análise de dados relacionados à disponibilidade de quartos no Airbnb, utilizando ferramentas e conceitos de negócios como Business Intelligence (BI) para revelar padrões, identificar oportunidades e aprimorar a tomada de decisões estratégicas.

A diversidade de informações geradas pela interação dos anfitriões e hóspedes na plataforma Airbnb resulta em um vasto conjunto de dados. Esses dados abrangem desde detalhes sobre imóveis, preços e localizações até feedback dos hóspedes. A riqueza desses dados oferece uma oportunidade única para aplicar técnicas de BI, como a integração de dados e a análise de relacionamentos entre tabelas. Buscamos descobrir insights valiosos que possibilitem aos anfitriões e ao próprio Airbnb otimizar a disponibilidade de quartos, maximizar a receita e aprimorar a experiência dos hóspedes.

Neste projeto, você realizará uma análise exploratória e utilizará técnicas avançadas de BI para visualizar tendências, identificar padrões e compreender os fatores que influenciam a ocupação do alojamento. Desde a sazonalidade elevada até as preferências regionais, diversos aspectos serão examinados para desvendar informações valiosas. O objetivo final é fornecer uma base sólida para a tomada de decisões informadas, permitindo que as partes interessadas adotem medidas estratégicas para aprimorar a eficiência operacional e lucratividade no dinâmico ecossistema do Airbnb.

### Ferramentas, linguagens e insumos

**Ferramentas e/ou plataformas**

Neste projeto você usará duas ferramentas, uma para gerenciar os dados e outra para fazer a análise exploratória:

 - Para gerenciar as tabelas, você usará o Google `BigQuery`
 - Para realizar a análise exploratória dos dados você utilizará o `PowerBI`.

**Linguagens**

Você usará a linguagem **SQL** no `BigQuery` e as fórmulas **DAX** no `PowerBI`.

**Insumos**

Neste projeto você terá um conjunto de dados estruturados com 3 tabelas (2 tabelas de dimensão e 1 de transação, leia este artigo para entender melhor este conceito com informações sobre os quartos disponíveis para reserva no Airbnb.

Abaixo, você pode consultar a descrição das variáveis ​​que compõem as tabelas:

**Tabela rooms (Dimensão):**

 - `id`: um identificador exclusivo para cada quarto.
 - `nome`: o nome do anúncio do Airbnb.
 - `bairro`: sigla para o bairro em que o anúncio do Airbnb está localizado.
 - `neighbourhood_group`: bairro onde o anúncio do Airbnb está localizado.
 - `latitude`: a coordenada de latitude do anúncio do Airbnb.
 - `longitude`: a coordenada de longitude do anúncio do Airbnb.
 - `room_type`: o tipo de quarto oferecido no anúncio do Airbnb.
 - `minimum_nights`: o número mínimo de noites aceito na reserva.

**Tabela hosts (Dimensão):**

 - `host_id`: um identificador exclusivo para cada host.
 - `nomedohost`: o nome do anfitrião do anúncio do Airbnb.

**Tabela reviews (fatos):**

 - `id`: um identificador exclusivo para cada quarto.
 - `host_id`: um identificador exclusivo para cada host.
 - `preço`: o preço por noite no anúncio do Airbnb.
 - `numberofreviews`: o número total de comentários que recebeu o anúncio do Airbnb.
 - `last_review`: a data da última review que o anúncio do Airbnb recebeu.
 - `reviewspermonth`: número médio de avaliações que o anúncio do Airbnb recebe por mês. 
 - `calculatedhostlistings_count`: o número total de listagens que o host tem.
 - `availability_365`: o número de dias que o anúncio do Airbnb estará disponível para reserva em um ano