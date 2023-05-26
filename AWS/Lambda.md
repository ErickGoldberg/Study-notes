# Lambda:
O AWS Lambda é um serviço de computação sem servidor fornecido pela Amazon Web Services (AWS). Ele permite executar código de forma escalável e sem a necessidade de provisionar ou gerenciar servidores.

O AWS Lambda é usado principalmente para executar funções ou pequenos trechos de código em resposta a eventos. Você pode escrever seu código usando várias linguagens de programação suportadas, como Python, Node.js, Java, C#, Go e outros. Essas funções são acionadas por eventos, como acionadores de tempo, alterações em buckets do Amazon S3, atualizações de tabelas no DynamoDB, invocações de API Gateway, entre outros.

## O que é serverless:
Serverless é um modelo de serviço de nuvem onde você não precisa se preocupar com a infraestrutura da sua aplicação. Esse servidor ainda existe, entretanto ele é totalmente gerenciado pelo provedor de nuvem, te permitindo focar somente na lógica do seu negócio.

Um diferencial do Serveless é que você paga somente o que sua aplicação utilizar. Ao contrário de uma EC2 tradicional, você pode ser cobrado pelo tempo ocioso nessa EC2, em momentos onde sua aplicação não tem nenhuma atividade.

Além do Lambda, temos outros exemplos de serviços da AWS que funcionam no modelo de Serveless. Alguns exemplos são o S3 para armazenamento de arquivos, o AWS RDS Aurora e DynamoDB para banco de dados, e SNS e SQS, serviços usados para gerenciar filas e mensageiria.

## Principais características e benefícios:
- Escalabilidade Automática: 

O AWS Lambda escala automaticamente sua capacidade de computação com base na demanda. Ele aloca recursos de acordo com a carga de trabalho, executando várias instâncias de função de forma paralela para lidar com picos de tráfego.
- Sem Servidores para Gerenciar: 

Com o AWS Lambda, você não precisa se preocupar em provisionar, gerenciar ou escalar servidores. A AWS cuida de toda a infraestrutura subjacente, permitindo que você se concentre apenas no código.

- Pagamento por Uso: 

O AWS Lambda segue o modelo de pagamento por uso, o que significa que você só paga pelos recursos consumidos durante a execução de suas funções. Não há cobrança quando as funções não estão sendo executadas.

- Integração com Serviços da AWS: 

O AWS Lambda é altamente integrado com outros serviços da AWS. Você pode facilmente acionar suas funções em resposta a eventos gerados por serviços como S3, DynamoDB, API Gateway, entre outros.
- Facilidade de Monitoramento e Depuração: 

O AWS Lambda fornece ferramentas para monitorar e depurar suas funções, como registros detalhados, métricas de desempenho e integração com serviços de monitoramento, como CloudWatch.

- Análise os logs enquanto trabalha:

Imagine a criação de uma função do AWS Lambda para coletar os logs do AWS Cloudtrail ou de outros aplicativos de log, como o Cloudwatch. O Lambda observa os triggers e as entradas de log específicas, chamando uma notificação do SNS quando isso acontece. Essas notificações também podem ser facilmente enviadas ao Slack, ao Jabber ou a sistemas de suporte, como o Zendesk, por chamadas nos endpoints da API no Lambda.

- Boa automação antiga de backups e rotina diária:

As funções do Lambda podem ser chamadas dentro do cronograma, o que o torna uma ferramenta de automação perfeita para tarefas repetitivas, como a verificação de recursos ociosos, a criação de backups, a geração de relatórios e a execução de vários outros trabalhos de rotina. Basta usar as bibliotecas boto3 do Python e se livrar do trabalho de administração mundano para sempre!

- Suporte a várias tarefas do AWS S3:

Se o usuário configurar o AWS Lambda para receber notificações de eventos do S3, ele poderá executar qualquer processamento de objetos armazenados em depósitos do S3. Por exemplo, poderá usá-lo para geração de miniaturas de imagens sem a necessidade de se preocupar com recursos suficientes, porque o Lambda fará o escalonamento tanto quanto for necessário.

- Otimização de operações de backend:

O backend de um site não deve ser a fonte de interrupções para a experiência do usuário final. O Lambda pode fazer o parse da entrada do visitante e armazená-lo em um banco de dados (ou processar a entrada de qualquer outra forma) enquanto o site renderiza a próxima página. Os dados de entrada serão enviados para o banco de dados ou aplicativo necessário e usados no devido tempo, enquanto o visitante desfruta da experiência perfeita do site!

O AWS Lambda pode e deve ser um dos principais recursos para lidar com tarefas repetitivas ou demoradas, junto com os outros trabalhos pesados do mundo de processamento de dados. Ele libera os principais serviços online para se concentrar em tarefas frontend de alta prioridade, como responder rapidamente a solicitações de usuários, o que permite descarregar muitos processos que, de outra forma, deixariam o sistema mais lento.

O AWS Lambda é amplamente utilizado para construir aplicativos sem servidor, microsserviços, pipelines de processamento de dados, automação de tarefas, integrações de serviços, entre outros casos de uso. Ele permite que você desenvolva e execute código de forma mais ágil e escalável, sem se preocupar com a infraestrutura subjacente.

## Tipos de inicialização de função:
Existem duas diferentes inicializações de uma função na AWS Lambda: quente (hot) ou fria (cold).

Cold start é quando a runtime não está sendo executada, então tudo deve ser inicializado e só depois nossa função handler é executada. Isso é necessário quando a função passa um determinado tempo sem ser executada. A AWS Lambda automaticamente interrompe a execução da runtime.

Hot start é quando a runtime já está em execução, precisando apenas executar nossa função handler. Essa é a inicialização mais comum quando nossa função é executada com frequência.

Algumas runtimes possuem uma maior demora para realizar o cold start, como é o caso de Java e C#. Nesses casos, não é incomum nós executarmos periodicamente a função para manter a runtime sempre executando, caso nossa função não receba muitas requisições sempre. Isso garante uma inicialização mais rápida (mas há o custo de executar a função nesses momentos também).

## Quando não utilizar Lambda:
existem algumas situações onde não é interessante utilizar Lambda. A primeira situação é:
- Rodar uma aplicação web tradicional. Você até consegue fazer isso, mapeando os eventos enviados com uma requisição web que sua aplicação utiliza, porém você estará subutilizando o potencial do Lambda, publicando uma aplicação completa dentro de uma única função e executando trechos de código que podem ser redundantes, como a configuração de rotas.
- Processos de longa duração também não são recomendados. O tempo limite de execução de uma função é de 15 minutos. Isso pode acontecer ao processar um grande volume de dados de uma só vez. O ideal nesse caso é quebrar esse processo em partes menores, e executar somente uma unidade por função, ao invés de processar várias unidades de uma vez.
- Uma função lambda também não tem acesso a um disco permanente. A manipulação de arquivos pelo lambda acontece em um disco efêmero e de baixa capacidade, tornando impossível manipular arquivos muito grandes numa função. Dessa forma é necessário recorrer a um serviço de armazenamento externo como o S3.
- Por fim, temos que considerar o vendor lock-in. Em outras palavras, ao desenvolver uma função lambda não será possível migrar o código para outro provedor no futuro. Para migrar o Lambda para Azure Functions, por exemplo, posteriormente você precisa reimplementar toda a lógica que trata os eventos e suas integrações com outros serviços. Praticamente, você irá criar uma nova função.
