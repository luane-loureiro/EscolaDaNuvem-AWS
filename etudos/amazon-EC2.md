# Amazon EC2 
## Tipos de Instacias Do Amazon EC2
- São otmizados para tarefas diferentes. Ao selecionar um tipo de instância, considere as nececidades específicas de suas cargas de trabalho e suas aplicações.
- Esses recursos podem incluir requisitos para recursos de computação, memória ou armazenamento.

### Instância de uso geral - Equilíbrio
Essas instancias equilibram os recurss de computação, memória e rede.
Você pode usa-las para diversas cargas de trabalho, como:
- Servidores de aplicações
- Servidores de Jogos
- Servidores de back-end para aplicações emporesariais
- Bancos de dados pequenos e médios.

### Instâncias otmizadas para Computação - Alto desepenho de processamento
São ideais para aplicações de computação que usam processadores de alto desempenho. assim como as instâncias de uso geral, você pode usar as intâncias otmizadas para computação para cargas de trabalho, como servidores de web, de aplicações e de jogos.
A diferença é que as aplicações otmizadas para computação ão ideiais para:
- servidores web de alto desempenho
- servidores de aplicações de computação intensiva
- servidores dedicados de jogos.

### Instâncias Otmizadas para memória - carregamento rápido para cargas de trabalho
as inâncias otmizadas para memória permitem que você execute cargas de trabalho com altas nececidades de memoria e tenha um otimo desempenho.
Tem desempenho rapido para cargas de trabalho que processam grandes consuntos de dados na memória. Na computação, a memória é uma área de armazenamento temporário.  Ela contem todos os dados e instruçoes de que uma unidade central de processamento (CPU) precisa para conseguir realizar ações. Antes que um programa de computador ou aplicativo posa ser executado ele é carregado e armazenado para a memória.
suponha que uma carga de trabalho exija o pré-carregameto de muitos dados antes de executar uma ação, como por exemplo:
- banco de dados de alto desempenho
- cargas de trabalho que envolva a execução de processamento em tempo real de uma grande quantidade de dados não estruturado

### Instâncias de computação aceleda - Aceleradores Graficos
usam celeradores de hadware ou co processadores, para executar algumas funçoes de maneira mais eficientes do que é possivel em um software executados em CPUS
exemplos dessas funções são:
- Calculos acelerados de números com virgulas flutuantes
- aplicativos gráficos gráficos
- correspondencias de padroes de dados
- streeming de jogos e de aplicativos

### Instancias otmizadas para armazenamenro - alta velocidade de leitura e gravação
São projetadas para cargas de trabalho que exigem alto acesso sequencial de leitura e gravação de dados no armazenamento local.
Exemplos de cargas de trabalho são:
- armazenamnto de sistemas de arquivos distribuidos
- aplicação de data werehouse
- sistemas de processamentos online de alta frequencia


## Definições de Preços do Amazon EC2
Com o amazon EC2, você paga apenas pelo tempo de computação que usar. O amazon EC2 oferece diversas opções de preço para diferentes casos de uso.

### Sob Demanda
- Ideais para cargas de trabalho irregulares de curto prazo que não podem ser iterrompidas. 
- Custos antecipados ou contratos não se aplicam.
- As instancias são executadas continuamnente até que sejam interrompidas, e você paga apenas pelo tempo de computação usado.

### Instancias Reservadas
- São um desconto de cobrança aplicado ao uso de instâncias sob demanda na sua conta. Há dois tipos disponíveis de instância reservada:
    **-  Standard Reservad Instances** essa opção será adequada se você souber o tipo e tamanho da instancia EC2 de que precisa para suas aplicações com estado pronto em qual Região da aws planeja executa-las. As instancias reservadas exigem que você declare as seguintes qualificações: tipo etamanho da instancia, descricao da plataforma (sistema operacional) e tenancy padrão.
  
    **-  Instâncias reservadas conversiveis** se você precisar executar suas instancias do EC2 em diferentes zonas de disponibilidade ou diferentes zonas de disponibilidade ou diferentes tipos de instancias, as instancias reservadas conversiveis poderão ser adequadas para você.

  No final de um preríodo de vigência de instancia reservada você pode continuar usando a instancia do amazon EC2sem interrupção . No entanto, são cobrados os preços de instancias sob demanda até um dos procedmentos a seguir seja feito:
  - Trminar a Instância
  - Adquirir uma nova instância reservada que corresponda aos atributos de instância (tamanho e familia de instância, região, plataforma e tenancy)


### Savings Plans da Instância EC2
os savings plans reduzem o custo da intância do EC2 quando você assume um compromissso de gasto por hora com uma familia  de instância e uma região por um periodo de um ou três anos.
esse compromisso com o periodo de vigênciaresulta em uma economia de 72% em comparação com as taxas sob demanda. Qualquer uso até o compromisso é cobrado de acordo com o preço de saving plans, quaqluer uso além do compromisso é cobrado de acordo com as normas de instância sob demanda.
Ao contrario das instancias reservadas, no entanto, você não precisa especificar antecipadamente qual tipo e tamanho da instância do EC2, sistema operacional, e tenancy para receber desconto.  Além disso , você você não precisa se comprometer com um determinado numero de instâncias do EC2 durante um periodo de vigencia de um ou três anos.

### Instâncias Spot 
São ideais para cargas de trabalho com horarios de início e termino flexiveis ou que toleram interrupições. As Instâncias spot usam a capacidade de computção não utilizadas do amazon EC2 e tem até 90% de desconto em relação ao preços de instâncias sob demanda.

### Host dedicados
são servodores físicos com capacidade de instancia EC2 totalmente dedicada ao uso do cliente.
você pode usar suas licenças de software por soquete, por nucleo ou por VM para manter a conformidade da licença. Você pode adquirir hosts dedicados sob demanda e reservas de hosts dedicados. De todas as opçoçoes do amazon EC2 que foram abordadas, od hosts dedicados são os mais caros.


## Scaling do Amazon EC2 - Dimencionamento
O **dimensionamento** significa começar apenas com os recursos necessários e projetar a arquitetura para responder automaticamente às alterações de demanda, fazendo aumentos ou reduções de quantidade. Como resultado, você paga apenas pelos recursos que usa. Você não precisa se preocupar com a falta de capacidade de computação para atender às necessidades dos clientes.
Se você quisesse que o processo de scaling acontecesse automaticamente, qual serviço da AWS você usaria? 
O serviço da AWS que fornece essa funcionalidade para instâncias do Amazon EC2 é o **Amazon EC2 Auto Scaling**.

### Amazon EC2 Auto Scaling
Se você já tentou acessar um site que não carregava e atingiu o tempo limite algumas vezes, ele pode ter recebido mais solicitações do que conseguia atender.

O Amazon EC2 Auto Scaling permite que você adicione ou remova automaticamente instâncias do Amazon EC2 em resposta à alteração da demanda da aplicação. Ao fazer auto scaling das instâncias, aumentando ou reduzindo a quantidade conforme a necessidade, você tem maior percepção de disponibilidade de aplicações
No Amazon EC2 Auto Scaling, há duas abordagens disponíveis: 
- **Scaling dinâmico** responde às alterações na demanda. 
- **Scaling preditivo** programa automaticamente o número correto de instâncias do Amazon EC2 com base na demanda prevista.

### Exemplo: Amazon EC2 Auto Scaling
Já que na nuvem a capacidade computacional é um recurso programático, você pode adotar uma abordagem mais flexível para o problema de scaling. 
Ao adicionar o Amazon EC2 Auto Scaling a uma aplicação, você poderá adicionar novas instâncias à aplicação quando for necessário e terminá-las quando não for mais necessário.
Suponha que você esteja se preparando para iniciar uma aplicação em instâncias do Amazon EC2. 
Ao configurar o tamanho do seu grupo do Auto Scaling, você pode definir o número mínimo de instâncias do Amazon EC2 como sendo um. 
Isso significa que, em qualquer momento, precisa haver pelo menos uma instância do Amazon EC2 em execução.

![image](https://github.com/luane-loureiro/EscolaDaNuvem-AWS/assets/100947092/53874b69-10f8-44b4-aca3-4a61954a9609)

1. Ao criar um grupo do Auto Scaling, você pode definir o número mínimo de instâncias do Amazon EC2. A capacidade mínima é o número de instâncias do Amazon EC2 que são iniciadas imediatamente após a criação do grupo do Auto Scaling. Neste exemplo, o grupo do Auto Scaling tem uma capacidade mínima de uma instância do Amazon EC2.
2. Em seguida, você pode definir a capacidade desejada como duas instâncias do Amazon EC2, mesmo que a aplicação precise de um mínimo de uma única instância do Amazon EC2 para que seja executada.
3. A próxima configuração que você pode definir em um grupo do Auto Scaling é a capacidade máxima. Por exemplo, você pode configurar o grupo do Auto Scaling para aumentar a quantidade em resposta à demanda elevada, mas apenas para um máximo de quatro instâncias do Amazon EC2.

Como o Amazon EC2 Auto Scaling usa instâncias do Amazon EC2, você vai pagar apenas pelas instâncias que usar, e somente quando elas forem usadas. Você agora tem uma arquitetura econômica que proporciona a melhor experiência do cliente e ao mesmo tempo reduz custos.


## Elastic Load Balancing - Direcionamento de tráfego
O Elastic Load Balancing é o serviço da AWS que distribui automaticamente o tráfego de entrada de aplicações entre vários recursos, como instâncias do Amazon EC2. 

Um balanceador de carga atua como um ponto único de contato para todo o tráfego na web de entrada para o grupo do Auto Scaling. Isso significa que, à medida que você adiciona ou remove instâncias do Amazon EC2 em resposta à quantidade de tráfego de entrada, essas solicitações são direcionadas para o balanceador de carga primeiro. Em seguida, as solicitações se espalham por vários recursos que lidarão com elas. Por exemplo, se você tiver várias instâncias do Amazon EC2, o Elastic Load Balancing distribuirá a carga de trabalho entre elas para que nenhuma instância tenha que carregar a maior parte. 

Embora o Elastic Load Balancing e o Amazon EC2 Auto Scaling sejam serviços separados, eles trabalham juntos para que as aplicações executadas no Amazon EC2 tenham alto desempenho e disponibilidade.



### Exemplo: Elastic Load Balancing

#### Período de baixa demanda
![image](https://github.com/luane-loureiro/EscolaDaNuvem-AWS/assets/100947092/9a34e1ab-97c4-40af-b032-504cc0d9ea3a)

Aqui está um exemplo de como o Elastic Load Balancing funciona. Suponha que alguns clientes vieram à cafeteria e estão prontos para fazer seus pedidos. 

Se apenas algumas caixas registradoras estão abertas, isso corresponde à demanda dos clientes que precisam do serviço. A cafeteria tem menos probabilidade de ter caixas registradoras abertas sem clientes. Nesse exemplo, você pode pensar nas caixas registradoras como instâncias do Amazon EC2.


#### Período de alta demanda
![image](https://github.com/luane-loureiro/EscolaDaNuvem-AWS/assets/100947092/9971e653-1981-4c1a-942e-8b819736e79d)

Ao longo do dia, à medida que o número de clientes aumenta, a cafeteria abre mais caixas registradoras para atendê-los. 

Além disso, um funcionário da cafeteria direciona os clientes para a caixa registradora mais adequada para que o número de solicitações possa ser distribuído uniformemente entre as caixas registradoras abertas. Você pode pensar nesse funcionário da cafeteria como um balanceador de carga. 


## Sistema de mensagens e enfileiramento
### Aplicações monolíticas e microsserviços
![image](https://github.com/luane-loureiro/EscolaDaNuvem-AWS/assets/100947092/95cb7ade-f976-42d9-baa8-f5a5070c63c6)

As aplicações são formadas por vários componentes. Os componentes se comunicam entre si para transmitir dados, atender solicitações e manter o aplicativo em execução. 

Suponha que você tenha uma aplicação com componentes com acoplamento forte. Esses componentes podem ser bancos de dados, servidores, interface do usuário, lógica de negócios e assim por diante. Esse tipo de arquitetura pode ser considerado uma aplicação monolítica. 

Nessa abordagem sobre a arquitetura da aplicação, se um único componente falhar, vai ocorrer falha de outros componentes e possivelmente de toda a aplicação.

Para manter a disponibilidade da aplicação quando um único componente falha, você pode projetar essa aplicação com uma abordagem de **microsserviços**.
Em uma abordagem de microsserviços, os componentes da aplicação têm um acoplamento fraco. Neste caso, se um único componente falhar, os outros componentes continuarão funcionando porque estarão em comunicação uns com os outros. O acoplamento fraco evita a falha completa do aplicativo. 

![image](https://github.com/luane-loureiro/EscolaDaNuvem-AWS/assets/100947092/31cca5f1-e105-46fb-84d8-cda13b7feb85)


Ao projetar aplicações na AWS, você pode adotar uma abordagem de microsserviços com serviços e componentes que cumprem funções diferentes. Dois serviços facilitam a integração de aplicativos: Amazon Simple Notification Service (Amazon SNS) e Amazon Simple Queue Service (Amazon SQS).


### Amazon Simple Notification Service (Amazon SNS)
O Amazon Simple Notification Service (Amazon SNS) é um serviço de publicação/assinatura. Usando tópicos do Amazon SNS, um editor publica mensagens para assinantes. Isso é semelhante à cafeteria: o operador de caixa entrega os pedidos ao barista que, por sua vez, prepara as bebidas.

No Amazon SNS, os assinantes podem ser servidores da web, endereços de e-mail, funções do AWS Lambda ou várias outras opções. 


### Amazon Simple Queue Service (Amazon SQS)
O Amazon Simple Queue Service (Amazon SQS) é um serviço de enfileiramento de mensagens. 

Use o Amazon SQS para enviar, armazenar e receber mensagens entre componentes de software, sem perder mensagens nem precisar que outros serviços estejam disponíveis. No Amazon SQS, uma aplicação envia mensagens para uma fila. Um usuário ou serviço recupera uma mensagem da fila, processa-a e a apaga da fila.



