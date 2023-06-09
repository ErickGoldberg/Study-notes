# Tudo sobre EC2:

## O que é o EC2:
  O Amazon Elastic Compute Cloud (Amazon EC2) oferece uma capacidade de computação escalável na Nuvem da Amazon Web Services (AWS). O uso do Amazon EC2 elimina a necessidade de investir em hardware inicialmente, portanto, você pode desenvolver e implantar aplicativos com mais rapidez. É possível usar o Amazon EC2 para executar quantos servidores virtuais forem necessários, configurar a segurança e as redes e gerenciar o armazenamento. O Amazon EC2 permite aumentar ou reduzir a escala para lidar com alterações nos requisitos ou com picos em popularidade, reduzindo sua necessidade de prever o tráfego.
  
## Recursos do Amazon EC2:
O Amazon EC2 fornece os seguintes recursos:

* Ambientes de computação virtual, conhecidos como instâncias*

* Os modelos pré-configurados para suas instâncias, conhecidos como Imagens de máquina da Amazon (AMIs), que empacotam os bits de que você precisa para seu servidor (incluindo o sistema operacional e software adicional)

* Várias configurações de capacidade de CPU, memória, armazenamento e redes para suas instâncias, conhecidas como tipos de instância

* Informações seguras de login para suas instâncias usando pares de chave (a AWS armazena a chave pública e você armazena a chave privada em um lugar seguro)

* Volumes de armazenamento para dados temporários que são excluídos quando você interrompe, hiberna ou encerra sua instância, conhecidos como volumes de armazenamento de instâncias

* Volumes de armazenamento persistentes para seus dados usando o Amazon Elastic Block Store (Amazon EBS), conhecidos como volumes do Amazon EBS

* Vários locais físicos para seus recursos, como instâncias e volumes do Amazon EBS, conhecidos como regiões e zonas de disponibilidade

* Um firewall que permite especificar os protocolos, portas e intervalos de IPs de origem que podem acessar suas instâncias usando grupos de segurança

* Os endereços IPv4 estáticos para computação em nuvem dinâmica, conhecidos como endereços IP elásticos

* Metadados, conhecidos como tags, que você pode criar e atribuir aos recursos do Amazon EC2

* Redes virtuais isoladas logicamente do restante da Nuvem AWS que você pode criar e, opcionalmente, conectar à sua própria rede, conhecida como nuvens virtuais privadas (VPCs)

## Security groups:
Um grupo de segurança atua como firewall virtual para as instâncias do EC2 visando controlar o tráfego de entrada e de saída. As regras de entrada controlam o tráfego de entrada para a instância e as regras de saída controlam o tráfego de saída da instância. Ao executar sua instância, é possível especificar um ou mais grupos de segurança. Se você não especificar um grupo de segurança, o Amazon EC2 usará o grupo de segurança padrão. É possível adicionar regras a cada grupo de segurança que permite tráfego de entrada ou de saída nas instâncias associadas. É possível modificar as regras de um grupo de segurança a qualquer momento. As regras novas e modificadas são aplicadas automaticamente para todas as instâncias que estão associados ao grupo de segurança. Quando o Amazon EC2 decide se deve permitir que o tráfego atinja uma instância, ele avalia todas as regras de todos os grupos de segurança associados à instância.

Ao executar uma instância em uma VPC, você precisa especificar um grupo de segurança criado para a VPC. Depois de executar uma instância, é possível alterar seus grupos de segurança. Os grupos de segurança estão associados a interfaces de rede. A alteração dos grupos de segurança de uma instância altera os grupos de segurança associados à interface de rede primária (eth0).

## Diferença entre modelo e imagem:
Ao criarmos uma instância a partir de uma imagem, podemos selecionar todo o hardware (tipo de instância, rede, etc) e algum software já vem pré-instalado. Já com o Modelo, nós podemos selecionar qualquer imagem e o hardware já estará pré-configurado. Inclusive nós criaremos um modelo mais adiante no curso para que a AWS possa criar instâncias automaticamente para nós.

Obs: Na hora de criar uma imagem, parar a instância sempre é a recomendação. Desta forma, garantimos a integridade dos dados.

## IP elástico:
Um Endereço IP elástico é um endereço IPv4 estático projetado para computação em nuvem dinâmica. Um endereço IP elástico é alocado para a conta da AWS e será seu até que você o libere. Com um endereço IP elástico, é possível mascarar a falha de uma instância ou software remapeando rapidamente o endereço para outra instância na conta. Como alternativa, é possível especificar o endereço IP elástico em um registro DNS para o seu domínio, para que ele acione a sua instância. Um endereço IP elástico é um endereço IPv4 público, que é acessível pela Internet. Se a instância não tiver um endereço IPv4 público, será possível associar um endereço IP elástico a ela para permitir a comunicação com a Internet. Por exemplo, isso permite que você se conecte à instância do computador local.

obs: O IP elástico não é cobrado se a instância estiver ligada, apenas se tiver desligada.

## Volume: 
Um volume do Amazon EBS é um dispositivo de armazenamento em blocos durável que é possível anexar às suas instâncias. Depois de anexar um volume a uma instância, será possível usá-lo como você usaria um disco rígido físico. Os volumes do EBS são flexíveis. Para volumes de geração atual anexados a tipos de instância de geração atual, é possível aumentar o tamanho dinamicamente, modificar a capacidade de IOPS provisionadas e alterar o tipo de volume em volumes de produção em tempo real.

É possível usar os volumes do EBS como armazenamento principal de dados que exigem atualizações frequentes, como o drive do sistema para uma instância ou armazenamento de uma aplicação de banco de dados. Também é possível usá-los para aplicações com muita throughput que executam verificações de disco contínuas. Os volumes do EBS persistem independentemente da vida útil de uma instância do EC2.

## Snapshot: 
É um backup, um clone do seu volume (disco EBS), e a partir dele você pode gerar novos volumes (restaurar um backup). Você pode realizar snapshots manuais, agendar via Lambda ou usar o serviço do AWS Backup para agendar seus snapshots.

## Elastic Load Balancing: 
O Elastic Load Balancing é compatível com os seguintes tipos de balanceadores de carga: Application Load Balancers e Network Load Balancers. Os serviços do Amazon ECS podem usar esses tipos de balanceador de carga. Os application load balancers são usados para encaminhar o tráfego HTTP/HTTPS (ou Camada 7). Os network load balancers e os classic load balancers são usados para encaminhar o tráfego TCP (ou da Camada 4).

### Application Load Balancer
Um Application Load Balancer toma decisões de roteamento na camada da aplicação (HTTP/HTTPS), oferece suporte ao roteamento com base em caminho e pode encaminhar solicitações para uma ou mais portas em cada instância de contêiner no cluster. Os application load balancers oferecem suporte ao mapeamento de porta de host dinâmico. Por exemplo, se a definição de contêiner da tarefa especifica a porta 80 para uma porta de contêiner NGINX e a porta 0 para a porta do host, a porta do host é escolhida dinamicamente com base no intervalo de portas temporário da instância de contêiner (como entre 32768 e 61000 na AMI otimizado para Amazon ECS mais recente). Quando a tarefa é inicializada, o contêiner NGINX é registrado no Application Load Balancer como uma combinação de ID e porta da instância, e o tráfego é distribuído para o ID e para a porta da instância correspondentes a este contêiner. Esse mapeamento dinâmico permite várias tarefas de um único serviço na mesma instância de contêiner.

### Network Load Balancer
Um Network Load Balancer toma decisões de roteamento na camada de transporte (TCP/SSL). Ele pode processar milhões de solicitações por segundo. Após o load balancer receber uma conexão, ele seleciona um destino do grupo de destino para a regra padrão usando um algoritmo de roteamento de hash de fluxo. Ele tenta abrir uma conexão TCP para o destino selecionado na porta especificada na configuração do listener. Ele encaminha a solicitação sem modificar os cabeçalhos. Os network load balancers oferecem suporte ao mapeamento de porta de host dinâmico. Por exemplo, se a definição de contêiner da tarefa especifica a porta 80 para uma porta de contêiner NGINX e a porta 0 para a porta do host, a porta do host é escolhida dinamicamente com base no intervalo de portas temporário da instância de contêiner (como entre 32768 e 61000 na AMI otimizado para Amazon ECS mais recente). Quando a tarefa é inicializada, o contêiner NGINX é registrado no Network Load Balancer como uma combinação de ID e porta da instância, e o tráfego é distribuído para o ID e para a porta da instância correspondentes a este contêiner. Esse mapeamento dinâmico permite várias tarefas de um único serviço na mesma instância de contêiner.

## Auto Scaling:
O Amazon EC2 Auto Scaling ajuda a garantir que você tenha o número correto de instâncias do Amazon EC2 disponíveis para processar a carga da sua aplicação. Você cria coleções de instâncias EC2, chamadas de grupos de Auto Scaling. Você pode especificar o número mínimo de instâncias em cada grupo do Auto Scaling, e o Amazon EC2 Auto Scaling garante que seu grupo nunca seja menor que esse tamanho. Você pode especificar o número máximo de instâncias em cada grupo do Auto Scaling, e o Amazon EC2 Auto Scaling garante que seu grupo nunca seja maior que esse tamanho. Se você especificar a capacidade desejada, quando você criar o grupo ou em qualquer momento depois disso, o Amazon EC2 Auto Scaling garante que seu grupo tenha essa quantidade de instâncias. Se você especificar políticas de escalabilidade, o Amazon EC2 Auto Scaling poderá iniciar ou terminar instâncias à medida que a demanda da aplicação aumentar ou diminuir.

Por exemplo, o seguinte grupo do Auto Scaling tem um tamanho mínimo de uma instância, uma capacidade desejada de duas instâncias e um tamanho máximo de quatro instâncias. As políticas de escalabilidade que você define ajustam o número de instâncias, em seu número mínimo e máximo de instâncias, com base nos critérios que você especifica.

## Acessar o Amazon EC2:
  O Amazon EC2 fornece uma interface de usuário na web, o console do Amazon EC2. Depois de cadastrar-se em uma conta da AWS, você pode acessar o console do Amazon EC2 fazendo login no AWS Management Console e selecionando EC2 na página inicial do console.

Se preferir usar uma interface de linha de comando, temos as seguintes opções:

AWSInterface da linha de comando (CLI) da
  Fornece comandos para um conjunto amplo de produtos da AWS e é compatível com Windows, Mac e Linux. Para começar a usar, consulte oAWS Command Line Interface User Guide (Guia do usuário da AWS Command Line Interface). Para obter mais informações sobre comandos para o Amazon EC2, consulte ec2 na Referência de comandos da AWS CLI).

AWS Tools for Windows PowerShell
  Fornece comandos para um conjunto amplo de produtos da AWS para os usuários que usam script no ambiente do PowerShell. Para começar a usar, consulte o Guia do usuário do AWS Tools for Windows PowerShell. Para obter mais informações sobre os cmdlets do Amazon EC2, consulte a Referência de cmdlets do AWS Tools for PowerShell.

  O Amazon EC2 permite a criação de recursos usando o AWS CloudFormation. Você cria um modelo, em JSON ou YAML, que descreve seus recursos da AWS e o AWS CloudFormation provisiona e configura esses recursos para você. Você pode reutilizar seus modelos do CloudFormation para provisionar os mesmos recursos várias vezes, seja na mesma região e conta ou em várias regiões e contas. Para obter mais informações sobre os tipos de recurso e as propriedades do Amazon EC2, consulte Referência de tipo de recurso do EC2 no Guia do usuário do AWS CloudFormation.

  A Amazon EC2 fornece uma API de consulta. Essas são solicitações HTTP ou HTTPS que usam verbos HTTP GET ou POST e um parâmetro de consulta chamado Action. Para obter mais informações sobre as ações de API para o Amazon EC2, consulte Ações no Amazon EC2 API Reference.

  Se você preferir criar aplicativos usando APIs específicas de uma linguagem em vez de enviar uma solicitação via HTTP ou HTTPS, a AWS fornece bibliotecas, código de exemplo, tutoriais e outros recursos para desenvolvedores de software. Essas bibliotecas fornecem funções básicas que automatizam tarefas, como assinatura criptografada de suas solicitações, novas tentativas de solicitações e tratamento das respostas de erro, facilitando para que você comece rapidamente.
