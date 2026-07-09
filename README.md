# Projeto de introdução a ciência de dados

# Integrantes:
Antônio Duarte \
Guilherme Ribeiro \
João Gabriel \
Josué Mykael 

# Tema do projeto:
investigar a diversidade e a representatividade nos Oscars.

# Abordagem dos dados:
Os dados serão coletados por meio de bases públicas sobre os Oscars e complementados com informações sobre os artistas e filmes. \
Também será realizada uma análise temporal, comparando períodos anteriores e posteriores ao movimento #OscarsSoWhite, permitindo observar possíveis mudanças na diversidade da premiação.

## Descrição Geral dos Conjuntos de Dados:
A escolha dos conjuntos de dados deste projeto justifica-se pela necessidade de conectar as discussões socioculturais sobre representatividade com o desempenho prático, financeiro e crítico da indústria cinematográfica, permitindo avaliar se movimentos, como o #OscarsSoWhite gerou impactos reais no mercado ou se permaneceu superficial. Para viabilizar essa investigação, o grupo utiliza duas bases de dados complementares que se encontram em seu estado bruto e original, sem qualquer tipo de tratamento ou conversão aplicada até o momento. Essa decisão foi tomada porque o objetivo desta etapa inicial do projeto é puramente a visualização, o reconhecimento e a exploração da estrutura nativa dos dados, servindo como base para planejar como as variáveis qualitativas e textuais serão transformadas em métricas numéricas nas etapas futuras do pipeline de Ciência de Dados.

O primeiro conjunto é o Dataset de Demografia do Oscar, que possui 415 registros focados no perfil sociobiográfico dos vencedores das principais categorias da premiação ao longo da história, o que é fundamental para extrair proporções, taxas de inclusão e fazer o mapeamento temporal.

Já o segundo conjunto é o Dataset do IMDb, uma base de dados robusta composta por 33.600 registros que oferece o panorama comercial, técnico e avaliativo das produções cinematográficas mundiais de forma ampla. O cruzamento desta base com a anterior permite ao grupo ir além do eixo dos filmes, correlacionando fatores de diversidade com o sucesso financeiro e a recepção do público.

## Processo de Coleta de Dados
O processo de coleta de dados foi iniciado a partir de debates internos do grupo sobre qual seria a metodologia mais viável, robusta e interdisciplinar para conduzir a pesquisa. Diante desse desafio, realizamos uma busca ativa por repositórios públicos na web e selecionamos, de forma estratégica, dois conjuntos de dados complementares que melhor respondiam ao problema: o Dataset de Demografia do Oscar e o Dataset do IMDb. Com os arquivos baixados localmente em formato estruturado (CSV), utilizamos a biblioteca Pandas em Python para realizar a leitura das bases brutas.

Esta etapa inicial teve como foco exclusivo a visualização analítica, o reconhecimento estrutural e a descrição das variáveis originais, permitindo ao grupo compreender o formato nativo dos dados para planejar os próximos passos. Tendo em vista que as tabelas possuem muitas variáveis qualitativas, estabelecemos como meta para as etapas futuras a transformação de dados categóricos em numéricos. Essa abordagem nos dará uma maior capacidade de análise, permitindo manipular atributos existentes e, principalmente, definir novos atributos derivados de acordo com os critérios estabelecidos pela pesquisa. O intuito final dessa estratégia é enriquecer a análise exploratória por meio de agrupamentos complexos e geração de métricas mais relevantes e profundas para a real compreensão do problema social e econômico proposto.

### Colunas do Dataset de Demografia do Oscar

* **Nome da coluna:** `name`
  * **Descrição:** Nome completo do artista (ator, atriz ou diretor) que concorreu ao Oscar.
  * **Exemplo:** `"Denzel Washington"`

* **Nome da coluna:** `birth_year`
  * **Descrição:** Ano de nascimento do artista (tipo de dado numérico inteiro), essencial para futuros cálculos de faixa etária.
  * **Exemplo:** `1954`

* **Nome da coluna:** `birth_date`
  * **Descrição:** Data de nascimento completa do artista registrada em formato de texto.
  * **Exemplo:** `"December 28, 1954"`

* **Nome da coluna:** `birthplace`
  * **Descrição:** Cidade, estado e/ou país onde o artista vencedor nasceu.
  * **Exemplo:** `"Mount Vernon, New York, U.S."`

* **Nome da coluna:** `race_ethnicity`
  * **Descrição:** Classificação étnico-racial categórica do vencedor mapeada pelo dataset.
  * **Exemplo:** `"Black"``

* **Nome da coluna:** `religion`
  * **Descrição:** Credo ou religião declarada ou associada ao artista premiado.
  * **Exemplo:** `"Christian"`

* **Nome da coluna:** `sexual_orientation`
  * **Descrição:** Orientação sexual declarada ou registrada do artista na base de dados.
  * **Exemplo:** `"Straight"`

* **Nome da coluna:** `year_edition`
  * **Descrição:** Ano em que ocorreu a edição da cerimônia do Oscar na qual o prêmio foi entregue (marco para a divisão temporal de 2015).
  * **Exemplo:** `2002`

* **Nome da coluna:** `category`
  * **Descrição:** A categoria específica da premiação do Oscar na qual o indivíduo saiu vencedor.
  * **Exemplo:** `"Best Actor"` ou `"Best Director"`

* **Nome da coluna:** `movie`
  * **Descrição:** O título do filme pelo qual o artista foi premiado, utilizado como chave de cruzamento com a base do IMDb.
  * **Exemplo:** `"Training Day"`

### Colunas do Dataset do IMDb

* **Nome da coluna:** `id`
  * **Descrição:** Código de identificação alfanumérico único do filme na plataforma do IMDb.
  * **Exemplo:** `"tt0139654"`

* **Nome da coluna:** `title`
  * **Descrição:** O título original da obra cinematográfica em língua inglesa.
  * **Exemplo:** `"Training Day"`

* **Nome da coluna:** `link`
  * **Descrição:** URL de acesso direto à página oficial do filme no site do IMDb.
  * **Exemplo:** `"https://www.imdb.com/title/tt0139654/"`

* **Nome da coluna:** `year`
  * **Descrição:** Ano oficial de lançamento comercial do filme nos cinemas.
  * **Exemplo:** `2001`

* **Nome da coluna:** `duration`
  * **Descrição:** Tempo total de duração da obra cinematográfica formatado como texto.
  * **Exemplo:** `"122 min"`

* **Nome da coluna:** `rating_mpa`
  * **Descrição:** Classificação indicativa de faixa etária do filme baseada no sistema da Motion Picture Association.
  * **Exemplo:** `"R"` (Restrito para menores de 17 anos desacompanhados)

* **Nome da coluna:** `rating_imdb`
  * **Descrição:** Nota média de avaliação do filme atribuída pelo público geral na plataforma (escala de 1.0 a 10.0).
  * **Exemplo:** `7.7`

* **Nome da coluna:** `vote`
  * **Descrição:** Quantidade total de votos e avaliações numéricas que a obra recebeu de usuários no IMDb.
  * **Exemplo:** `340000.0`

* **Nome da coluna:** `budget`
  * **Descrição:** Orçamento estimado de produção do filme em dólares americanos (USD).
  * **Exemplo:** `45000000.0`

* **Nome da coluna:** `gross_world_wide`
  * **Descrição:** Faturamento/Bilheteria total acumulada pelo filme a nível mundial em dólares (USD).
  * **Exemplo:** `104876233.0`

* **Nome da coluna:** `gross_us_canada`
  * **Descrição:** Faturamento/Bilheteria acumulada especificamente no mercado da América do Norte (EUA e Canadá) em dólares (USD).
  * **Exemplo:** `76631907.0`

* **Nome da coluna:** `gross_opening_weekend`
  * **Descrição:** Faturamento obtido pelo filme especificamente no seu primeiro fim de semana de estreia nos cinemas em dólares (USD).
  * **Exemplo:** `22555759.0`

* **Nome da coluna:** `director`
  * **Descrição:** Nome do diretor principal responsável pelo comando técnico e artístico do filme.
  * **Exemplo:** `"Antoine Fuqua"`

* **Nome da coluna:** `writer`
  * **Descrição:** Nome do roteirista ou criador da história e do argumento do filme.
  * **Exemplo:** `"David Ayer"`

* **Nome da coluna:** `star`
  * **Descrição:** Nome do ator ou atriz principal que protagoniza o elenco do filme.
  * **Exemplo:** `"Denzel Washington"`

* **Nome da coluna:** `genre`
  * **Descrição:** Gêneros cinematográficos nos quais a obra se enquadra (armazenados como texto separado por vírgulas).
  * **Exemplo:** `"Crime, Drama, Thriller"`

* **Nome da coluna:** `country_origin`
  * **Descrição:** País ou países de origem responsáveis pelo financiamento e produção do filme.
  * **Exemplo:** `"United States"`

* **Nome da coluna:** `filming_location`
  * **Descrição:** Locais geográficos, cidades ou estúdios reais onde as filmagens e gravações da obra ocorreram.
  * **Exemplo:** `"Los Angeles, California, USA"`

* **Nome da coluna:** `production_company`
  * **Descrição:** Empresa, estúdio de cinema ou produtora responsável pelo desenvolvimento do projeto.
  * **Exemplo:** `"Warner Bros."`

* **Nome da coluna:** `language`
  * **Descrição:** O idioma original falado na maior parte dos diálogos da obra cinematográfica.
  * **Exemplo:** `"English"`

* **Nome da coluna:** `win`
  * **Descrição:** Quantidade total de prêmios de qualquer festival de cinema que o filme conquistou ao longo de sua trajetória.
  * **Exemplo:** `18`

* **Nome da coluna:** `nomination`
  * **Descrição:** Número total de indicações a prêmios que o filme recebeu no circuito de festivais de cinema.
  * **Exemplo:** `25`

* **Nome da coluna:** `oscar`
  * **Descrição:** Variável numérica indicadora que contabiliza ou sinaliza a presença e o volume de estatuetas do Oscar recebidas pela produção.
  * **Exemplo:** `1`
