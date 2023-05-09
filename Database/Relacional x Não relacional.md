# Diferença entre banco de dados relacional x não relacional:
Bancos de dados relacionais (RDBMS) e não relacionais (NoSQL) são tipos diferentes de sistemas de gerenciamento de banco de dados que são usados para armazenar e gerenciar informações.

Um banco de dados relacional é baseado no modelo relacional, que usa tabelas para armazenar e organizar dados. Cada tabela tem um conjunto de colunas que descrevem os atributos dos dados e um conjunto de linhas que contêm os próprios dados. Os dados são organizados em tabelas relacionadas entre si por meio de chaves estrangeiras que estabelecem relações entre as tabelas. Os bancos de dados relacionais são normalmente usados para aplicativos que exigem integridade referencial e transações complexas.

Já os bancos de dados NoSQL são projetados para lidar com grandes volumes de dados não estruturados ou semiestruturados, como documentos, gráficos e dados de mídia social. Eles geralmente não usam esquemas fixos e rígidos como os bancos de dados relacionais, permitindo uma flexibilidade maior no armazenamento de dados. Além disso, muitos bancos de dados NoSQL são escaláveis horizontalmente, o que significa que podem se adaptar facilmente ao aumento de dados e tráfego.

Em resumo, a principal diferença entre os dois tipos de banco de dados é o modelo de armazenamento e as necessidades do aplicativo. Bancos de dados relacionais são ideais para aplicativos que exigem integridade referencial e transações complexas, enquanto bancos de dados NoSQL são ideais para aplicativos que precisam lidar com grandes volumes de dados não estruturados ou semiestruturados.

## O que significa dados estruturado:
Dados estruturados são dados que são organizados e armazenados em um formato predefinido e padronizado, o que significa que a estrutura dos dados é bem definida e consistente. Isso permite que os dados sejam facilmente acessados, gerenciados e processados usando software e sistemas de gerenciamento de banco de dados.

Os dados estruturados geralmente são armazenados em tabelas com colunas predefinidas que descrevem os atributos dos dados. Por exemplo, em um banco de dados de clientes, cada linha pode representar um cliente e as colunas podem incluir o nome, endereço, telefone, e-mail, entre outros atributos relevantes.

Os dados estruturados são fáceis de pesquisar, filtrar e classificar, o que os torna ideais para análises e relatórios, além de serem essenciais para a maioria dos sistemas de gerenciamento de banco de dados relacionais.

Em resumo, dados estruturados são dados organizados em um formato predefinido e padronizado, que podem ser facilmente acessados, gerenciados e processados usando sistemas de gerenciamento de banco de dados e outras ferramentas de software.

## Exemplos de uso:
A escolha entre um banco de dados relacional (RDBMS) e um banco de dados não relacional (NoSQL) depende do tipo de aplicação e das necessidades do projeto. A seguir, vou apresentar algumas considerações que podem ajudar na escolha do tipo de banco de dados mais adequado para o seu projeto:

- Estrutura de dados: se os dados são altamente estruturados e precisam ser relacionados entre si, um banco de dados relacional pode ser a melhor opção. Por exemplo, um sistema de gerenciamento de inventário de loja de varejo pode ter informações sobre produtos, fornecedores e pedidos de compra, que precisam ser organizados e relacionados entre si. Por outro lado, se os dados não são altamente estruturados e não precisam ser relacionados entre si, um banco de dados não relacional pode ser a melhor escolha.
- Escalabilidade: se o volume de dados esperado é grande e espera-se que cresça ao longo do tempo, um banco de dados não relacional pode ser mais escalável. Isso ocorre porque muitos bancos de dados NoSQL são projetados para serem escaláveis horizontalmente, o que significa que podem ser distribuídos em vários servidores para lidar com volumes maiores de dados e tráfego.
- Flexibilidade: se os dados são heterogêneos e mudam frequentemente, um banco de dados NoSQL pode ser mais flexível. Por exemplo, um banco de dados de mídia social pode ter dados que variam de fotos a vídeos e de textos a áudios, que podem ser armazenados em diferentes formatos e estruturas.
- Velocidade: se a velocidade de acesso e processamento de dados é uma consideração importante, um banco de dados NoSQL pode ser a melhor opção. Isso ocorre porque muitos bancos de dados NoSQL são projetados para serem mais rápidos do que os bancos de dados relacionais em determinados tipos de operações, como leitura e gravação em grandes volumes de dados.
- Custos: o custo é sempre uma consideração importante em qualquer projeto. Geralmente, os bancos de dados relacionais têm um custo inicial mais alto, mas podem ser mais fáceis de manter e atualizar no longo prazo. Por outro lado, os bancos de dados não relacionais podem ter um custo inicial mais baixo, mas podem exigir mais esforço e habilidade para manter e atualizar.
