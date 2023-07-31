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
