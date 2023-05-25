# Dynamo DB:
O Amazon DynamoDB é um serviço de banco de dados NoSQL totalmente gerenciado fornecido pela Amazon Web Services (AWS). Ele foi projetado para oferecer alta escalabilidade, desempenho rápido e armazenamento seguro de dados estruturados sem a necessidade de provisionar ou gerenciar infraestrutura.

## Principais pontos/conceitos:
- NoSQL e Modelo de Dados:

O DynamoDB é um banco de dados NoSQL (Not Only SQL) que difere dos bancos de dados relacionais tradicionais. Ele usa um modelo de dados flexível baseado em pares de chave-valor (key-value), com suporte opcional para atributos adicionais. O modelo de dados do DynamoDB permite que você armazene e recupere dados rapidamente com base em uma chave de partição (partition key).

- Escalabilidade Automática:

O DynamoDB oferece escalabilidade automática e dimensionamento horizontal sob demanda. Isso significa que você não precisa se preocupar em provisionar capacidade de armazenamento ou ajustar manualmente o dimensionamento conforme a carga de trabalho aumenta. O DynamoDB gerencia automaticamente a distribuição dos dados em várias partições para fornecer alto desempenho e capacidade conforme necessário.

- Desempenho Rápido:

O DynamoDB é conhecido por seu desempenho rápido e previsível. Ele usa armazenamento em memória e distribuição de dados para otimizar o acesso aos dados, oferecendo latência muito baixa para operações de leitura e gravação. Além disso, você pode ajustar a capacidade de leitura e gravação conforme suas necessidades para garantir um desempenho consistente.

- Alta Disponibilidade e Durabilidade:

O DynamoDB é projetado para ser altamente disponível e durável. Os dados são automaticamente replicados de forma síncrona em três zonas de disponibilidade na mesma região, garantindo redundância e resiliência. O DynamoDB também mantém múltiplas cópias dos dados em diferentes servidores, fornecendo durabilidade e proteção contra falhas de hardware.

- Consistência:

O DynamoDB oferece modelos de consistência flexíveis para atender às necessidades do seu aplicativo. Ele suporta tanto leitura consistente (strongly consistent reads) quanto leitura eventual (eventually consistent reads), permitindo que você escolha o nível de consistência necessário para suas operações de leitura.

- Segurança e Controle de Acesso:

O DynamoDB oferece recursos de segurança robustos para proteger seus dados. Ele integra-se ao AWS Identity and Access Management (IAM), permitindo que você defina permissões granulares para acessar as tabelas do DynamoDB. Além disso, o DynamoDB suporta criptografia em repouso e em trânsito, garantindo a proteção dos dados em todas as etapas.

- Integração com Outros Serviços AWS:

O DynamoDB é altamente integrado com outros serviços da AWS. Você pode usar o DynamoDB como armazenamento de dados para aplicativos web, móveis, de jogos e IoT, além de aproveitar a integração com serviços como AWS Lambda, Amazon CloudWatch, AWS X-Ray e Amazon Redshift para análise e monitoramento.

O Amazon DynamoDB é uma opção poderosa para aplicativos que exigem armazenamento e recuperação rápidos de dados em escala.

## Partition key/Sort key:
No Amazon DynamoDB, a Sort Key e a Partition Key são dois elementos-chave que compõem a estrutura de indexação e organização dos dados armazenados na tabela.

- Partition Key (Chave de Partição):

A Partition Key é usada para determinar a partição física onde os dados serão armazenados no DynamoDB. É responsável por distribuir os dados de forma uniforme nas diferentes partições para garantir uma escalabilidade e desempenho eficientes. A escolha de uma boa Partition Key é fundamental para distribuir a carga de acesso aos dados e evitar hotspots (partições com acesso intenso).

A Partition Key é especificada durante a criação da tabela e deve ser um atributo obrigatório em cada item da tabela. É com base na Partition Key que o DynamoDB decide em qual partição o item será armazenado. Por exemplo, em uma tabela que armazena dados de usuários, a Partition Key pode ser o ID do usuário.

- Sort Key (Chave de Ordenação):

A Sort Key é usada em conjunto com a Partition Key para definir a ordem de classificação dos itens armazenados dentro de cada partição. A combinação da Partition Key e da Sort Key é chamada de chave de partição-sorte.

A Sort Key permite que os itens sejam ordenados em ordem crescente ou decrescente com base em um determinado atributo. Isso facilita a recuperação de itens em uma ordem específica, permitindo consultas eficientes e filtragens com base nos valores do atributo da Sort Key.

Por exemplo, em uma tabela de pedidos, a Partition Key pode ser o ID do cliente e a Sort Key pode ser a data do pedido. Isso permitiria recuperar todos os pedidos de um determinado cliente em uma ordem cronológica.

A combinação única da Partition Key e da Sort Key determina a identidade exclusiva de cada item na tabela do DynamoDB.

Ao projetar um esquema de tabela no DynamoDB, é essencial escolher as chaves de partição e de ordenação corretas para garantir uma distribuição eficiente dos dados e atender às necessidades de acesso e consulta dos aplicativos. O projeto adequado das chaves de partição e de ordenação pode resultar em um melhor desempenho, escalabilidade e flexibilidade na utilização do DynamoDB.

## Consultas:
No Amazon DynamoDB, existem duas operações principais para recuperar dados de uma tabela: Scan e Query. Ambas têm propósitos diferentes e são usadas em situações específicas.

### Scan:
A operação Scan examina toda a tabela para recuperar todos os itens que atendem aos critérios de filtro especificados. É uma operação mais lenta e intensiva em termos de recursos, pois precisa ler todos os itens da tabela, independentemente da sua distribuição nas partições.

O Scan é útil quando você deseja recuperar todos os itens da tabela ou quando não possui informações suficientes para definir critérios de consulta mais específicos. No entanto, devido à sua natureza de varredura completa da tabela, o Scan pode ter impacto no desempenho e na capacidade de provisionamento do DynamoDB, especialmente para tabelas grandes.

### Query:
A operação Query é usada para buscar itens em uma tabela com base em critérios de filtro especificados, incluindo a chave de partição e, opcionalmente, a chave de ordenação. A Query é mais eficiente e rápida do que o Scan, pois acessa diretamente os itens que estão em uma determinada partição ou combinação de partição-sorte.

A Query é ideal para recuperar um conjunto específico de itens com base em valores de chave conhecidos ou utilizando operadores de comparação. Ela é especialmente útil quando se trata de tabelas grandes, pois permite que você busque itens de forma seletiva, evitando a necessidade de examinar todos os itens da tabela.

Em resumo, a diferença entre Scan e Query no DynamoDB é a seguinte:

- O Scan examina toda a tabela e recupera todos os itens que atendem aos critérios de filtro, mas é mais lento e intensivo em recursos.
- A Query busca itens com base em valores de chave conhecidos e é mais eficiente e rápida, pois acessa diretamente os itens de uma partição ou combinação de partição-sorte.

A escolha entre Scan e Query depende das suas necessidades de consulta e desempenho. Em geral, é recomendado utilizar Query sempre que possível para recuperar itens específicos, enquanto o Scan deve ser usado com cuidado e apenas quando necessário para varrer toda a tabela.

## Índices:
O banco de dados DynamoDB possui dois tipos de índices secundários: os locais e os globais. Os índices são chamados de secundários pois ao criar a tabela nós já definimos uma chave primária (junção entre partition key e sort key) e esse é nosso índice “primário”, embora esse termo não seja muito comum.

Os índices secundários locais (Local Secondary Index ou LSI) e índices secundários globais (Global Secondary Index ou GSI) são muito semelhantes, tendo apenas as seguintes diferenças:

Um LSI precisa ser implementado no momento da criação da tabela. Não é possível criá-los depois. Já um GSI pode ser feito a qualquer momento após a criação da tabela;
LSI não pode ter como sua definição uma outra partition key. Apenas a sort key pode ser diferente. Já um GSI pode ter tanto partiion key quanto sort key, diferentes do que foi definido na tabela.

### Projeção de atributos:
A projeção de atributos em um índice do Amazon DynamoDB refere-se à seleção dos atributos que serão incluídos no índice como parte dos itens indexados. Em outras palavras, a projeção determina quais atributos serão disponibilizados para consulta quando você acessar o índice.

Existem dois tipos de projeção de atributos no DynamoDB:
- All (Todos) - A projeção inclui todos os atributos do item original na tabela. Isso significa que, quando você consulta o índice, terá acesso a todos os atributos do item.
- Keys Only (Apenas Chaves) - A projeção inclui apenas as chaves do item original. Isso significa que, quando você consulta o índice, terá acesso apenas às chaves do item e não a outros atributos.

A escolha da projeção de atributos depende das suas necessidades de consulta e do desempenho desejado. Se você precisa acessar todos os atributos do item diretamente do índice, deve optar pela projeção "All". Isso pode ser útil quando você deseja recuperar rapidamente todos os atributos de um item com base em um índice específico, evitando a necessidade de acessar a tabela principal.

Por outro lado, se você só precisa acessar as chaves do item para identificar os itens relevantes, pode optar pela projeção "Keys Only". Isso pode ser útil quando você precisa localizar rapidamente itens com base em uma chave de pesquisa específica e não precisa dos demais atributos para essa operação.

A projeção de atributos é uma opção de configuração quando você cria um índice no DynamoDB. É importante escolher a projeção adequada com base nos requisitos de consulta do seu aplicativo, pois isso afetará a eficiência e o desempenho das suas consultas no DynamoDB.

## Price:
A precificação do Amazon DynamoDB, serviço de banco de dados NoSQL oferecido pela Amazon Web Services (AWS), é baseada em vários fatores, incluindo capacidade provisionada (Provisioned Capacity) e capacidade sob demanda (On-Demand Capacity).
### Capacidade provisionada (Provisioned Capacity):
- Taxa horária: Você paga uma taxa por hora pela capacidade de leitura e gravação provisionada que você configurou.
- Capacidade de leitura provisionada: Você define a quantidade de capacidade de leitura por segundo (Throughput Capacity Units - TCUs) necessária para sua tabela.
- Capacidade de gravação provisionada: Você define a quantidade de capacidade de gravação por segundo (Throughput Capacity Units - TCUs) necessária para sua tabela.
- Preço por TCU: Existem diferentes níveis de preços para capacidade de leitura provisionada e capacidade de gravação provisionada, dependendo da região e do volume contratado.

### Capacidade sob demanda (On-Demand Capacity):
- Com a capacidade sob demanda, você não precisa provisionar antecipadamente a capacidade de leitura e gravação. O DynamoDB ajusta automaticamente a capacidade conforme necessário para lidar com os picos de tráfego.
- Você paga pelo uso real da capacidade de leitura e gravação, calculado em unidades de capacidade de leitura (Read Capacity Units - RCUs) e unidades de capacidade de gravação (Write Capacity Units - WCUs).
- Há um preço por RCU e WCU com base na região em que você está usando o DynamoDB.

Além disso, é importante levar em consideração outros fatores que podem impactar o custo total do DynamoDB, como armazenamento, transferência de dados e operações adicionais, como consultas e varreduras. Cada região da AWS pode ter preços diferentes, portanto, é recomendável verificar a página de preços da AWS ou usar a calculadora de preços da AWS para obter detalhes específicos sobre os custos do DynamoDB na sua região.

É importante ressaltar que as informações sobre a precificação estão atualizadas até a data de corte do meu conhecimento, em setembro de 2021. Recomenda-se verificar a página oficial de preços da AWS para obter informações mais atualizadas sobre a precificação do DynamoDB.

## Classes de tabelas:
No Amazon DynamoDB, as classes de tabelas se referem às categorias de tabelas disponíveis para armazenamento de dados. O DynamoDB oferece duas classes de tabelas diferentes: Tabelas de Propósito Geral e Tabelas de Leitura Intensiva.

### Tabelas de Propósito Geral:
As tabelas de propósito geral são adequadas para uma ampla variedade de casos de uso. Elas fornecem armazenamento de dados com desempenho previsível, baixa latência de leitura e gravação, além de escala automática. Essas tabelas são altamente recomendadas para cargas de trabalho com padrões de acesso imprevisíveis ou variáveis.

- Capacidade Provisionada: Nesse modelo, você precisa provisionar capacidade de leitura e gravação para a tabela com base em suas necessidades esperadas. Você especifica a quantidade desejada de capacidade de leitura (Throughput de Leitura) e gravação (Throughput de Gravação) em unidades de capacidade.
- Escala Automática: Nesse modelo, você permite que o DynamoDB gerencie automaticamente a capacidade de leitura e gravação para a tabela, dimensionando-a com base na demanda. O DynamoDB monitora a taxa de utilização e 
ajusta a capacidade automaticamente para garantir o desempenho adequado. Você define apenas limites superiores (máximos) para a capacidade de leitura e gravação.

### Tabelas de Leitura Intensiva (DynamoDB Accelerator - DAX):
As tabelas de leitura intensiva são projetadas para cenários em que a leitura é a operação predominante. Elas utilizam o serviço DynamoDB Accelerator (DAX), que é uma camada de cache in-memory totalmente gerenciada para o DynamoDB. O DAX oferece latência extremamente baixa para consultas de leitura, reduzindo a carga sobre as tabelas principais do DynamoDB.




Ao usar as tabelas de leitura intensiva, você pode configurar um cluster do DAX para atender às solicitações de leitura do aplicativo. O DAX gerencia automaticamente o cache e mantém os dados sincronizados com as tabelas principais do DynamoDB.

As tabelas de leitura intensiva são adequadas para aplicativos que exigem um alto desempenho de leitura, como painéis de controle, aplicativos em tempo real, caches e muito mais.

É importante entender os requisitos do seu aplicativo e o padrão de acesso aos dados ao escolher a classe de tabela apropriada no DynamoDB. As tabelas de propósito geral são ideais para casos de uso com requisitos variáveis de leitura e gravação, enquanto as tabelas de leitura intensiva são recomendadas para aplicativos com foco em leitura de alto desempenho.

## Tabelas globais
Tabelas globais são um recurso muito interessante para tornar a disponibilidade do seu banco de dados ainda maior. Uma tabela global é basicamente uma tabela que não pertence a uma região específica da AWS, mas sim está replicada em todas as regiões.

Segundo a própria documentação da AWS, ela consiste em diversas tabelas replicadas (uma por região da AWS), que o DynamoDB trata como uma única unidade. Cada réplica possui o mesmo nome de tabela e o mesmo esquema de chave primária. Quando uma aplicação grava dados em uma tabela-réplica em uma região, o DynamoDB propaga automaticamente a gravação nas outras tabelas-réplicas nas outras Regiões da AWS.

## DAX
O DynamoDB Accelerator (DAX) é um cache em memória totalmente gerenciado e altamente disponível para o Amazon DynamoDB. O DAX faz todo o trabalho pesado necessário para adicionar aceleração em memória às tabelas do DynamoDB, sem que devs tenham de gerenciar invalidação de cache, preenchimento de dados ou gerenciamento de clusters.

Sendo assim, essa funcionalidade, quando habilitada, adiciona uma camada de cache ao seu banco de dados DynamoDB para aumentar ainda mais a performance, mas isso vem com um custo, claro. O DynamoDB cobra pela capacidade de DAX por hora.
