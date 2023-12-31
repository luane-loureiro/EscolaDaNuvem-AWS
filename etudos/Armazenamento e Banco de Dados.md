# Armazenamento e Banco de Dados
## Armazenamentos de instância e Amazon Elastic Block Store (Amazon EBS)
### Armazenamentos de instâncias
Os volumes de armazenamento a nível de bloco se comportam como discos rígidos físicos.
Um armazenamento de instância(opens in a new tab) é um meio temporário de armazenamento a nível de bloco para uma instância do Amazon EC2.
Um armazenamento de instância é o armazenamento em disco fisicamente anexo ao computador host para uma instância do EC2 e, portanto, tem a mesma vida útil da instância. 
Quando a instância for terminada, você perderá todos os dados no armazenamento de instância.
O **Amazon Elastic Block Store (Amazon EBS)** é um serviço que fornece volumes de armazenamento a nível de bloco que você pode usar com instâncias do Amazon EC2. Se você interromper ou terminar uma instância do Amazon EC2, todos os dados no volume do EBS anexo permanecerão disponíveis.
Para criar um volume do EBS, defina a configuração (como tamanho e tipo do volume) e a provisão. Depois de criado, o volume do EBS pode ser anexado a uma instância do Amazon EC2.
Como os volumes do EBS são para dados que precisam perdurar, é importante fazer backup dos dados. Você pode fazer backups incrementais de volumes do EBS criando snapshots do Amazon EBS.

### Snap shot do Amazon EBS
Um **snapshot do EBS** é um backup incremental. Isso significa que o primeiro backup de um volume copia todos os dados. 
Nos backups subsequentes, somente os blocos de dados que foram alterados desde o snapshot mais recente são salvos. 
Os backups incrementais são diferentes dos backups completos, nos quais todos os dados em um volume de armazenamento são copiados cada vez que ocorre um backup.
O backup completo inclui dados que não foram alterados desde o backup mais recente.


## Amazon S3 (Simple Storage Service)
### Armazenamento de objetos
No armazenamento de objetos, cada objeto consiste em dados, metadados e uma chave.
Os **dados** podem ser uma imagem, vídeo, documento de texto ou qualquer outro tipo de arquivo. 
Os **metadados** contêm informações sobre o que são os dados, como eles são usados, o tamanho do objeto e assim por diante. 
A **chave** de um objeto é seu identificador exclusivo.

### Amazon S3
É um serviço que fornece armazenamento a nível do objeto. O Amazon S3 armazena dados como objetos em buckets.
É possível fazer upload de qualquer tipo de arquivo para o Amazon S3, como imagens, vídeos, arquivos de texto e assim por diante. 
Por exemplo, você pode usar o Amazon S3 para armazenar arquivos de backup, arquivos de mídia para um site ou documentos arquivados. 
O Amazon S3 oferece espaço de armazenamento ilimitado. O tamanho máximo de arquivo para um objeto no Amazon S3 é de 5 TB.

```
Buckets 🪣 = 📁 Diretórios, Pastas
Objetos 📦 = 📄 Arquivos
```

Ao fazer upload de um arquivo para o Amazon S3, é possível definir permissões para controlar a visibilidade e o acesso a ele. Você também pode usar o recurso de versionamento do Amazon S3 para rastrear alterações em seus objetos ao longo do tempo.

### Storage classes do Amazon S3
Com o Amazon S3, você paga somente pelo que usar. Você pode escolher dentre diversas storage classes(opens in a new tab) aquela que melhor se ajusta às suas necessidades de negócios e de custo. Ao selecionar uma storage class do Amazon S3, considere estes dois fatores:
- Com que frequência você planeja recuperar seus dados
- Seus dados precisam estar muito ou pouco disponíveis

#### Amazon S3 Standard
- Projetado para dados acessados com frequência
- Armazena dados em um mínimo de três Zonas de Disponibilidade
  
O Amazon S3 Standard fornece alta disponibilidade para objetos. Isso o torna uma boa escolha para diversos casos de uso, como sites, distribuição de conteúdo e data analytics. O Amazon S3 Standard tem um custo mais alto do que outras storage classes destinadas a dados acessados com pouca frequência e armazenamento de arquivamento.

#### Amazon S3 Standard IA (infrequent access)
- Ideal para dados com pouca frequência de acesso
- Semelhante ao Amazon S3 Standard, mas com um preço de armazenamento mais baixo e um preço de recuperação mais alto
  
O Amazon S3 Standard-IA é ideal para dados acessados com pouca frequência, mas que precisam ter alta disponibilidade para quando necessário. O Amazon S3 Standard e o Amazon S3 Standard-IA armazenam dados no mínimo em três Zonas de Disponibilidade. O Amazon S3 Standard-IA tem o mesmo nível de disponibilidade da Amazon S3 Standard, mas com um preço de armazenamento mais baixo e um preço de recuperação mais alto.


#### Amazon S3 one zone - infrequent access (S3 one zone - IA)
- Armazena dados em uma única Zona de Disponibilidade
- Tem um preço de armazenamento menor do que o Amazon S3 Standard-IA
  
Comparado com o S3 Standard e o S3 Standard-IA, que armazenam dados em um mínimo de três Zonas de Disponibilidade, o S3 One Zone – IA armazena em uma única Zona de Disponibilidade. Isso o torna uma boa storage class nas seguintes condições:

- o ideal é economizar custos com armazenamento.
- Você pode reproduzir facilmente seus dados em caso de falha na Zona de Disponibilidade.

#### Amazon S3 intelligent Tiering
- Ideal para dados com padrões de acesso desconhecidos ou em alteração
- Requer uma pequena taxa mensal de monitoramento e automação por objeto
  
Na storage class S3 Intelligent-Tiering, o Amazon S3 monitora os padrões de acesso dos objetos. Se você não acessou um objeto por 30 dias consecutivos, o Amazon S3 o move automaticamente para o nível de acesso pouco frequente S3 Standard – IA. Se você acessar um objeto no nível de acesso pouco frequente, o Amazon S3 o move automaticamente para o nível de acesso frequente S3 Standard.

#### S3 Glacier instant Retrieval
- Funciona bem para dados arquivados que requerem acesso imediato
- Pode recuperar objetos em alguns milissegundos

Ao decidir entre as opções de armazenamento de arquivamento, considere a rapidez com que deve recuperar os objetos arquivados. Você pode recuperar objetos armazenados na storage class do S3 Glacier Instant Retrieval em milissegundos, com o mesmo desempenho que o S3 Standard.

#### S3 Glacier Flexible Retrieval
- Armazenamento de baixo custo projetado para arquivamento de dados
- Capaz de recuperar objetos em poucos minutos a horas

O S3 Glacier Flexible Retrieval é uma storage class de baixo custo, ideal para o arquivamento de dados. Por exemplo, você pode usar essa storage class para armazenar registros de clientes arquivados ou arquivos de fotos e vídeos mais antigos. Você pode recuperar seus dados do S3 Glacier Flexible Retrieval de 1 minuto a 12 horas.

#### S3 Glacier deep Archive
- Storage class de objetos de menor custo, ideal para arquivamento
- Capaz de recuperar objetos em 12 horas

O S3 Deep Archive dá suporte a retenção de longo prazo e preservação digital de dados acessados uma ou duas vezes por ano. Essa storage class é o armazenamento de menor custo na nuvem AWS, com recuperação de dados de 12 a 48 horas. Todos os objetos dessa storage class são replicados e armazenados em pelo menos três Zonas de Disponibilidade geograficamente dispersas.

#### S3 Outposts
- Cria buckets do S3 no Amazon S3 Outposts
- Torna mais fácil recuperar, armazenar e acessar dados no AWS Outposts

O Amazon S3 Outposts oferece armazenamento de objetos para seu ambiente on-premises do AWS Outposts. O Amazon S3 Outposts foi projetado para armazenar dados de maneira durável e redundante em vários dispositivos e servidores em seus Outposts. Por manter os dados próximos às aplicações on-premises, ele funciona bem para cargas de trabalho que exigem um alto desempenho e a permanência dos dados no local.


## Amazon Elastic File System (Amazon EFS)
### Armazenamento de arquivos
No armazenamento de arquivos, vários clientes (como usuários, aplicações, servidores e assim por diante) podem acessar os dados armazenados em pastas de arquivos compartilhadas. Nessa abordagem, um servidor de armazenamento usa armazenamento em bloco com um sistema de arquivos local para organizar os arquivos. Os clientes acessam dados por meio de caminhos de arquivo.
Comparado ao armazenamento em blocos e ao armazenamento de objetos, o armazenamento de arquivos é ideal para casos de uso em que um grande número de serviços e recursos precisam acessar os mesmos dados ao mesmo tempo.
O **Amazon Elastic File System (Amazon EFS)** é um sistema de arquivos dimensionável usado com os AWS Cloud Services e recursos on-premises. À medida que você adiciona e remove arquivos, o Amazon EFS expande e retrai automaticamente. Ele pode dimensionar sob demanda para petabytes sem interromper os aplicativos. 

### Comparação entre EBS e EFS

![image](https://github.com/luane-loureiro/EscolaDaNuvem-AWS/assets/100947092/fa656650-2046-4e49-95c4-5944ab801c11)


## Amazon RDS - amazon relational database service
### Bamcos de dados mais comuns compativeis com a AWS
- MySQL
- PostgreSQL
- Oracle
- Microsoft MySQL Service

  
### Bancos de dados relacionais
Em um banco de dados relacional, os dados são armazenados de modo que se relacionem a outros dados. 
Um exemplo de um banco de dados relacional pode ser o sistema de gerenciamento de inventário da cafeteria. Cada registro no banco de dados incluiria dados para um único item, como nome do produto, tamanho, preço e assim por diante.
Bancos de dados relacionais usam linguagem de consulta estruturada (SQL) para armazenar e consultar dados. Essa abordagem permite que os dados sejam armazenados de forma facilmente compreensível, consistente e dimensionável. Por exemplo, os proprietários da cafeteria podem escrever uma consulta SQL para identificar todos os clientes que compravam com mais frequência um café com leite médio.

**RDBMS** - Sistema de gerenciamento de banco de dados relacional.


### Amazon Relational Database Service
O Amazon Relational Database Service (Amazon RDS) é um serviço que permite executar bancos de dados relacionais na nuvem AWS.
O Amazon RDS é um serviço gerenciado que automatiza tarefas como provisão de hardware, configuração de banco de dados, patch e backups. Com esses recursos, você pode passar menos tempo concluindo tarefas administrativas e mais tempo usando dados para inovar seus aplicativos. Você pode integrar o Amazon RDS a outros serviços para atender às suas necessidades de negócios e operacionais, como usar o AWS Lambda para consultar seu banco de dados de uma aplicação sem servidor.
O Amazon RDS tem inúmeras opções de segurança diferentes. Muitos mecanismos de banco de dados do Amazon RDS oferecem criptografia em repouso (protegendo os dados enquanto estão armazenados) e criptografia em trânsito (protegendo os dados enquanto estão sendo enviados e recebidos).

#### Mecanismos de banco de dados do Amazon RDS
O Amazon RDS está disponível em seis mecanismos de banco de dados, que otimizam memória, desempenho ou entrada/saída (E/S). Os mecanismos de banco de dados compatíveis são:
- Amazon Aurora
- PostgreSQL
- MySQL
- MariaDB
- Oracle Database
- Microsoft SQL Server

#### Vantagens do Amazon RDS
- Aplicacão de patches automatizado
- Backups
- Alta disponibilidade
- Failover
- Recuperação de desastres

### Amazon Aurora
O Amazon Aurora(opens in a new tab) é um banco de dados relacional de nível empresarial. É compatível com os bancos de dados relacionais MySQL e PostgreSQL. É até cinco vezes mais rápido do que os bancos de dados MySQL comuns e até três vezes mais rápido do que os bancos de dados PostgreSQL comuns.
O Amazon Aurora ajuda a reduzir os custos do banco de dados reduzindo operações desnecessárias de entrada/saída (E/S), garantindo que os recursos do banco de dados permaneçam confiáveis e disponíveis. 
Considere o Amazon Aurora se suas cargas de trabalho exigem alta disponibilidade. Ele replica seis cópias de seus dados em três Zonas de Disponibilidade e faz backup contínuo de seus dados para o Amazon S3.

#### Benfícios do Amazon Aurora
- MySQL
- PostgreSQL
- Um décimo do valor dos bancos de dados comerciais
- Replicação de dados
- até 15 réplicas de leitura
- backup contínuo para o Amazon S3
- Recuperação contínua com o poit time recovery

## Amazon DynamoDB
- serviço de banco de dados de chave-valor.
- Ele oferece um desempenho de um dígito de milissegundo em qualquer scaling.
- Totalmente gerenciado, sem servidor (serverless), o que significa que você não precisa provisionar, aplicar patches ou gerenciar servidores.
- Banco de dados NoSQL não relacional
- Propósito específico, nem sempre eh a melhor escolha para TODOS os usos.
- altamente escalável, a medida que o tamanho do banco de dados expande ou retrai, ele é dimencionado automáticamente para se ajustar as altereções na capacidade, ao mesmo tempo, manter o desempenho consistente.

### Bancos de dados não relacionais
Em um banco de dados não relacional, você cria tabelas. Uma tabela é um lugar em que você pode armazenar e consultar dados.
Bancos de dados não relacionais também são chamados de “bancos de dados NoSQL” porque usam estruturas diferentes de linhas e colunas para organizar dados. Um tipo de abordagem estrutural para bancos de dados não relacionais é o uso de pares de chave-valor. Com pares de chave-valor, os dados são organizados em itens (chaves) e cada item tem um atributo (valores). Pode-se pensar em atributos como sendo diferentes características de seus dados.
Em um banco de dados de chave-valor, você pode adicionar ou remover atributos de itens na tabela a qualquer momento. Além disso, nem todos os itens na tabela precisam ter os mesmos atributos. 

### Comparação do Amazon RDS e DynamoDB

| Amazon RDS | Amazon Dynamo DB |
|------------|------------------|
| Bnaco de dados relacional | Banco de dados não relacional |
| Alta disponibilidade e recuperação automática | Chave Valor |
| cliente proprietário dos dados | Capacidade de produção maciva
| cliente proprietário do sistema  | potencial tamanho de PB |
| cliente controla a rede | Acesso a API granular |

## Amazon Redshift
um serviço de data warehouse que você pode usar para análise de Big Data. Ele oferece a capacidade de coletar dados de muitas fontes além de ajudar a entender relações e tendências em todos os seus dados.

## AWS Database Migration Service (AWS DMS)
Permite migrar bancos de dados relacionais e não relacionais e outros tipos de armazenamentos de dados.
Com o AWS DMS, você move dados entre bancos de dados de origem e de destino. Os bancos de dados de origem e de destino(opens in a new tab) podem ser do mesmo tipo ou de tipos diferentes. Durante a migração, o banco de dados de origem permanece operacional, reduzindo o tempo de inatividade em qualquer aplicativo que dependa do banco de dados. 
Por exemplo, suponha que você tenha um banco de dados MySQL armazenado on-premises em uma instância do Amazon EC2 ou no Amazon RDS. Pense no banco de dados MySQL como seu banco de dados de origem. Usando o AWS DMS, você pode migrar seus dados para um banco de dados de destino, por exemplo, um banco de dados do Amazon Aurora.

### Outros casos de uso do AWS DMS
#### Desebvolvimento de teste de migrações de banco de dados
Os desenvolvedores conseguem testar as aplicações com dados de produção sem afetar os usuários de rpodução

#### consolidação de Banco de Dados
Combinação de vários bancos em un único banco de dados.

#### Replicação continua
Envio de cópias contínuas dos dados para outras fontes de destino em vez de fazer uma migração única.

## Serviços de banco de dados adicionais
- **Amazon DocumentDB**
Um serviço de banco de dados de documentos compatível com cargas de trabalho do MongoDB. (MongoDB é um programa de banco de dados de documentos.)

- **Amazon Neptune**
Um serviço de banco de dados de grafo. 
Você pode usar o Amazon Neptune para criar e executar aplicações que funcionam com conjuntos de dados altamente conectados, como mecanismos de recomendação, detecção de fraude e grafos de conhecimento.

- **Amazon Quantum Ledger Database (Amazon QLDB)**
um serviço de banco de dados ledger. 
Você pode usar o Amazon QLDB para ver um histórico completo de todas as alterações feitas nos dados da aplicação.

- **Amazon Managed Blockchain**
um serviço para criar e gerenciar redes de blockchain com frameworks de código aberto. 
O Blockchain é um sistema de registro distribuído que permite que várias partes executem transações e compartilhem dados sem uma autoridade central.

- **Amazon ElastiCache**
um serviço que adiciona camadas de cache sobre bancos de dados para ajudar a melhorar os tempos de leitura de solicitações comuns. 
Ele é compatível com dois tipos de armazenamentos de dados: Redis e Memcached.

- **Amazon DynamoDB Accelerator**
um cache em memória do DynamoDB. 
Ele ajuda a melhorar os tempos de resposta de milissegundos para microssegundos.

