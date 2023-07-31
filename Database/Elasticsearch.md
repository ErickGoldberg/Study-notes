# Elasticsearch:
## Para que o Elasticsearch é usado?
A velocidade e escalabilidade do Elasticsearch e sua capacidade de indexar muitos tipos de conteúdo significam que ele pode ser usado para inúmeros casos de uso:

- Busca em aplicação
- Busca em website
- Busca empresarial
- Logging e analítica de log
- Métricas de infraestrutura e monitoramento de container
- Monitoramento de performance de aplicação
- Análise e visualização de dados geoespaciais
- Análise de segurança
- Business Analytics

## Como o Elasticsearch funciona:
Os dados brutos fluem para o Elasticsearch de uma variedade de fontes, incluindo logs, metrics de sistema e aplicações web. Ingestão de dados é o processo pelo qual os dados brutos são analisados, normalizados e enriquecidos antes de serem indexados no Elasticsearch. Depois que os dados são indexados no Elasticsearch, os usuários podem executar consultas complexas com base em seus dados e usar agregações para recuperar resumos complexos dos dados. Do Kibana, os usuários podem criar visualizações avançadas dos dados, compartilhar dashboards e gerenciar o Elastic Stack.

## Por que usar o Elasticsearch:
O Elasticsearch é rápido. Como o Elasticsearch é desenvolvido sobre o Lucene, ele fica insuperável em busca de texto completo. O Elasticsearch também é uma plataforma de busca praticamente em tempo real, significando que a latência do momento em que um documento é indexado até que ele se torne buscável é muito pequena — normalmente um segundo. Consequentemente, o Elasticsearch é bem adaptado para casos de uso sensíveis ao tempo como análise de dados de segurança e monitoramento de infraestrutura.

O Elasticsearch é distribuído de fábrica. Os documentos armazenados no Elasticsearch são distribuídos em diferentes containers conhecidos como shards, que são duplicados para oferecer cópias redundantes dos dados em caso de falha de hardware. A natureza distribuída do Elasticsearch permite fazer a escalabilidade horizontal para centenas (talvez milhares) de servidores e manipular petabytes de dados.

O Elasticsearch é fornecido com um amplo conjunto de recursos. Além da velocidade, escalabilidade e resiliência, o Elasticsearch tem inúmeros recursos integrados avançados que tornam o armazenamento e a busca de dados ainda mais eficiente, como os rollups de dados e o gerenciamento do ciclo de vida de índices.

O Elastic Stack simplifica a ingestão, a visualização e os relatórios de dados. A integração com os Beats e o Logstash facilita o processamento dos dados antes de indexar no Elasticsearch. E o Kibana fornece visualização em tempo real dos dados do Elasticsearch, além de UIs para acessar rapidamente os dados de APM (monitoramento de performance de aplicação), de logs e de metrics de infraestrutura.

## O que é um índice do Elasticsearch?
Um índice do Elasticsearch é um conjunto de documentos que estão relacionados entre si. O Elasticsearch armazena dados como documentos JSON. Cada documento correlaciona um conjunto de chaves (nomes de campos ou propriedades) aos seus valores correspondentes (strings, números, boolianos, datas, matrizes de valores, geolocalizações ou outros tipos de dados).

O Elasticsearch usa uma estrutura de dados chamada índice invertido, que é projetada para permitir buscas de texto completo muito rápidas. Um índice invertido lista cada palavra exclusiva que apareça em qualquer documento e identifica todos os documentos em que cada palavra aparece.

Durante o processo de indexação, o Elasticsearch armazena documentos e desenvolve um índice invertido para tornar os dados dos documentos buscáveis praticamente em tempo real. A indexação é iniciada com a API de índice, pela qual você pode adicionar ou atualizar um documento JSON em um índice específico.

## Para que o Logstash é usado?
O Logstash, um dos produtos principais do Elastic Stack, é usado para agregar e processar dados e enviá-los ao Elasticsearch. O Logstash é um pipeline de processamento de dados open source e do lado do servidor que permite fazer a ingestão de dados de várias fontes simultaneamente e enriquecer e transformar esses dados antes de serem indexados no Elasticsearch.

## Para que o Kibana é usado?
O Kibana é uma ferramenta de visualização e gerenciamento de dados para o Elasticsearch que fornece histogramas em tempo real, gráficos de linhas, gráficos de pizza e mapas. O Kibana também inclui aplicações avançadas como o Canvas, que permite aos usuários criar infográficos dinâmicos personalizados com base em seus dados, e o Elastic Maps para visualizar dados geoespaciais.
