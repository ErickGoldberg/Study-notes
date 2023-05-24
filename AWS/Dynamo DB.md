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

## Índices:
O banco de dados DynamoDB possui dois tipos de índices secundários: os locais e os globais. Os índices são chamados de secundários pois ao criar a tabela nós já definimos uma chave primária (junção entre partition key e sort key) e esse é nosso índice “primário”, embora esse termo não seja muito comum.

Os índices secundários locais (Local Secondary Index ou LSI) e índices secundários globais (Global Secondary Index ou GSI) são muito semelhantes, tendo apenas as seguintes diferenças:

Um LSI precisa ser implementado no momento da criação da tabela. Não é possível criá-los depois. Já um GSI pode ser feito a qualquer momento após a criação da tabela;
LSI não pode ter como sua definição uma outra partition key. Apenas a sort key pode ser diferente. Já um GSI pode ter tanto partiion key quanto sort key, diferentes do que foi definido na tabela.

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

## Tabelas globais
Tabelas globais são um recurso muito interessante para tornar a disponibilidade do seu banco de dados ainda maior. Uma tabela global é basicamente uma tabela que não pertence a uma região específica da AWS, mas sim está replicada em todas as regiões.

Segundo a própria documentação da AWS, ela consiste em diversas tabelas replicadas (uma por região da AWS), que o DynamoDB trata como uma única unidade. Cada réplica possui o mesmo nome de tabela e o mesmo esquema de chave primária. Quando uma aplicação grava dados em uma tabela-réplica em uma região, o DynamoDB propaga automaticamente a gravação nas outras tabelas-réplicas nas outras Regiões da AWS.

## DAX
O DynamoDB Accelerator (DAX) é um cache em memória totalmente gerenciado e altamente disponível para o Amazon DynamoDB. O DAX faz todo o trabalho pesado necessário para adicionar aceleração em memória às tabelas do DynamoDB, sem que devs tenham de gerenciar invalidação de cache, preenchimento de dados ou gerenciamento de clusters.

Sendo assim, essa funcionalidade, quando habilitada, adiciona uma camada de cache ao seu banco de dados DynamoDB para aumentar ainda mais a performance, mas isso vem com um custo, claro. O DynamoDB cobra pela capacidade de DAX por hora.
