# Amazon RDS:

## O que é RDS:
O Amazon Relational Database Service (Amazon RDS) é um serviço da Web que facilita a configuração, a operação e escalabilidade de um banco de dados relacional na Nuvem AWS. Ele fornece capacidade econômica e redimensionável para um banco de dados relacional padrão do setor e gerencia tarefas comuns de administração de banco de dados.

## Banco de dados on-premises:
O Amazon Elastic Compute Cloud (Amazon EC2) oferece uma capacidade de computação escalável na Nuvem AWS. O Amazon EC2 dispensa a necessidade de investir em hardware inicialmente e, portanto, você pode desenvolver e implantar aplicações com mais rapidez.

Quando você compra um servidor on-premises, recebe CPU, memória, armazenamento e IOPS, todos no mesmo pacote. Com o Amazon EC2, estes elementos se separaram, para que você possa escalá-los independentemente. Se você precisar de mais CPU, menos IOPS ou mais capacidade de armazenamento, poderá alocá-los facilmente.

Para um banco de dados relacional em um servidor on-premises, você assume total responsabilidade pelo servidor, sistema operacional e software. Para um banco de dados em uma instância do Amazon EC2, a AWS gerencia as camadas abaixo do sistema operacional. Dessa maneira, o Amazon EC2 elimina parte do peso de gerenciar um servidor de banco de dados on-premises.

Na tabela a seguir, é possível encontrar uma comparação dos modelos de gerenciamento para bancos de dados on-premises e o Amazon EC2.

## Vantagens da amazon RDS:
- Você pode usar os produtos de banco de dados que já conhece com: MariaDB, Microsoft SQL Server, MySQL, Oracle e PostgreSQL.
- O Amazon RDS gerencia backups, patches de software, detecção automática de falhas e recuperação.
- Você pode ativar backups automatizados ou pode criar manualmente seus próprios snapshots de backup. Você pode usar esses backups para restaurar um banco de dados. O processo de restauração do Amazon RDS funciona de maneira confiável e eficiente.
- Você pode obter alta disponibilidade com uma instância primária e uma instância secundária síncrona que pode ser usada para failover em caso de problemas. Também é possível usar réplicas de leitura para aumentar a escalabilidade de leitura.
- Além da segurança em seu pacote de banco de dados, você pode ajudar a controlar quem pode acessar seus bancos de dados do RDS. Para fazer isso, você pode usar o AWS Identity and Access Management (IAM) para definir usuários e permissões. Você também pode ajudar a proteger seus bancos de dados colocando-os em uma nuvem privada virtual (VPC).

## Instâncias de banco de dados:
Uma instância de banco de dados é um ambiente isolado de banco de dados na Nuvem AWS. O bloco de construção básico do Amazon RDS é a instância do banco de dados.

Sua instância de banco de dados pode conter um ou mais bancos de dados criados pelo usuário. É possível acessar a instância de banco de dados usando as mesmas ferramentas e os mesmos aplicativos usados com uma instância de banco de dados independente. Crie e modifique uma instância de banco de dados usando a AWS Command Line Interface (AWS CLI), a API do Amazon RDS ou o AWS Management Console.

## Classes da instância de banco de dados:
A classe de instância de banco de dados determina a capacidade de computação e de memória de uma instância de banco de dados. Uma classe de instância de banco de dados consiste no tipo e no tamanho de instância de banco de dados. Cada tipo de instância oferece diferentes capacidades de computação, memória e armazenamento. Por exemplo, db.m6g é uma classe de instância de banco de dados de uso geral com a tecnologia de processadores Graviton2 da AWS. No tipo de instância db.m6g, db.m6g.2xlarge é uma classe de instância de banco de dados.

## Mecanismos de banco de dados:
Um mecanismo de banco de dados é o software de banco de dados relacional específico que é executado na sua instância de banco de dados. Atualmente, o Amazon RDS oferece suporte aos seguintes mecanismos:
- MariaDB
- Microsoft SQL Server
- MySQL
- Oracle
- PostgreSQL

Cada mecanismo de banco de dados tem seus próprios recursos compatíveis, e cada versão de um mecanismo de banco de dados pode incluir recursos específicos. O suporte para recursos do Amazon RDS varia entre Regiões da AWS e versões específicas de cada mecanismo de banco de dados. Além disso, cada mecanismo de banco de dados tem um conjunto de parâmetros em um grupo de parâmetros de banco de dados que controlam o comportamento dos bancos de dados que ele gerencia.

## Principais funcionalidades:
### Replica:
Uma replica é uma cópia assíncrona de uma instância de banco de dados RDS em tempo real. Ela é usada para melhorar a disponibilidade do banco de dados e permitir a leitura escalável dos dados. Ao criar replicas, você pode distribuir a carga de leitura entre várias instâncias, aumentando assim o desempenho geral do sistema.

As replicas no RDS são gerenciadas automaticamente pela AWS, e você pode criar replicas em outras zonas de disponibilidade na mesma região ou até mesmo em regiões diferentes para garantir a resiliência do banco de dados. Além disso, as replicas podem ser promovidas a instâncias de produção em caso de falhas, tornando o processo de recuperação mais rápido.

#### Replica de Leitura (Read Replica):
Uma replica de leitura é uma cópia assíncrona do banco de dados primário que é usada para distribuir a carga de leitura entre várias instâncias de banco de dados. Essas replicas são usadas principalmente para melhorar o desempenho e a escalabilidade do sistema, permitindo que as consultas de leitura sejam executadas nas replicas em vez de na instância primária.
As replicas de leitura são atualizadas continuamente com as alterações feitas na instância primária, usando a replicação assíncrona. Isso significa que pode haver um pequeno atraso entre as alterações na instância primária e sua replicação para as replicas de leitura. As replicas de leitura são somente leitura, o que significa que as operações de gravação (escrita) devem ser realizadas na instância primária.

Uma vantagem das replicas de leitura é que elas podem ser criadas em diferentes zonas de disponibilidade dentro da mesma região, ou até mesmo em regiões geograficamente distintas. Isso fornece maior disponibilidade e tolerância a falhas. Além disso, as replicas de leitura podem ser promovidas para se tornarem instâncias autônomas em caso de falha da instância primária.

#### Replica de Backup (Backup Replica):
Uma replica de backup é uma cópia sincronizada do banco de dados primário que é criada para fins de backup. Essa replica é usada para fornecer uma cópia atualizada dos dados caso seja necessário restaurar o banco de dados em caso de falha ou perda de dados acidental.
A replica de backup é criada automaticamente pelo RDS quando você ativa a opção de backup multi-AZ (Multi-AZ backup). A replicação síncrona é usada para garantir que a replica de backup esteja sempre atualizada com os dados da instância primária.

Ao contrário da replica de leitura, a replica de backup não está disponível para consultas de leitura. Sua finalidade principal é garantir a disponibilidade e a recuperação de dados em caso de necessidade de restauração.

Ambos os tipos de replica (leitura e backup) são gerenciados automaticamente pelo RDS, e você pode criar, modificar e excluir replicas usando a console de gerenciamento do RDS, a API ou a interface de linha de comando (CLI).

### Backup:
O backup no Amazon RDS envolve a criação de cópias dos dados do seu banco de dados em intervalos regulares. Esses backups são armazenados de forma segura na AWS e podem ser usados para restaurar o banco de dados em caso de falhas ou perda de dados acidental.

O RDS oferece duas opções de backup: backups automáticos e backups manuais. Os backups automáticos são habilitados por padrão e são criados regularmente de acordo com uma programação definida. Eles são armazenados na AWS por um período de retenção configurável. Os backups manuais, como o nome sugere, são iniciados manualmente pelo usuário e permitem a criação de pontos de recuperação adicionais.

### Snapshot:
Um snapshot é uma imagem dos dados do seu banco de dados em um momento específico. Ao criar um snapshot, uma cópia pontual de todo o banco de dados é tirada e armazenada na AWS. Os snapshots podem ser usados para criar novas instâncias de banco de dados, restaurar bancos de dados existentes ou copiar dados para outro local.

Os snapshots são armazenados de forma durável e podem ser retidos pelo tempo que você precisar. Eles são independentes dos backups automáticos e manuais mencionados anteriormente. Isso significa que você pode criar snapshots independentes do cronograma de backup e retê-los pelo tempo que for necessário.

Tanto os backups quanto os snapshots são importantes para garantir a disponibilidade e a proteção dos dados no RDS. Eles fornecem opções de recuperação em caso de falhas, erros humanos ou necessidade de clonagem de bancos de dados para outros propósitos, como desenvolvimento ou testes.

## Disponibilidade no RDS:
### Multi-AZ Deployment (Implantação Multi-AZ):
Ao criar uma instância de banco de dados no RDS, você pode optar por configurá-la em uma implantação Multi-AZ. Nesse caso, o RDS replica automaticamente seu banco de dados primário em uma zona de disponibilidade secundária em tempo real. Essa replicação síncrona garante que haja uma cópia atualizada dos dados em uma zona de disponibilidade separada. Em caso de falha na zona primária, o RDS realiza uma promoção automática da replica para se tornar a instância primária, minimizando o tempo de inatividade.

### Auto Scaling (Dimensionamento Automático):
O RDS oferece recursos de auto scaling para ajudar a ajustar automaticamente a capacidade de computação do banco de dados com base nas demandas de carga de trabalho. Você pode configurar políticas de auto scaling para aumentar ou diminuir a quantidade de recursos, como instâncias de banco de dados, conforme necessário. Isso garante que você tenha a capacidade adequada para lidar com picos de tráfego e evita a sobrecarga ou subutilização dos recursos.

### Read Replicas (Replicas de Leitura):
As replicas de leitura permitem que você crie cópias assíncronas de leitura do banco de dados para distribuir a carga de leitura e melhorar o desempenho. As replicas são replicadas a partir da instância primária e fornecem leitura escalável dos dados. Se a instância primária falhar, você pode promover uma replica de leitura para se tornar a instância primária e minimizar o impacto na disponibilidade.

### Pontos de Verificação Automáticos (Automated Backups):
O RDS oferece a funcionalidade de pontos de verificação automáticos, que criam backups regulares dos seus bancos de dados. Esses backups são armazenados em um local seguro na AWS e podem ser usados para restaurar o banco de dados em caso de falha. Os pontos de verificação automáticos podem ser retidos por um período configurável, permitindo a recuperação de dados de um momento anterior, se necessário.

### Multi-Region Deployment (Implantação em Múltiplas Regiões):
Para aumentar ainda mais a disponibilidade, o RDS oferece a opção de implantação em múltiplas regiões. Isso envolve a criação de instâncias de banco de dados em diferentes regiões geográficas para garantir a continuidade do serviço, mesmo se uma região inteira se tornar inacessível. As replicas podem ser configuradas entre regiões para garantir a replicação dos dados em uma localidade geograficamente separada.

Esses recursos e estratégias de disponibilidade fornecidos pelo Amazon RDS ajudam a garantir que seus bancos de dados estejam disponíveis e funcionando de forma confiável. Eles reduzem o tempo de inatividade, protegem contra falhas e fornecem a flexibilidade necessária para lidar com variações de carga de trabalho e cenários de recuperação de desastres.

Links úteis: https://aws.amazon.com/pt/rds/  &&  https://docs.aws.amazon.com/pt_br/AmazonRDS/latest/UserGuide/CHAP_GettingStarted.html
