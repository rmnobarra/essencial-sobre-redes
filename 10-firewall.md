# Firewall

## O que é um firewall?

Os firewalls podem ser vistos como barreiras ou gateways que gerenciam o percurso de atividades da Web permitidas e proibidas em uma rede privada. O termo vem do conceito de paredes físicas como barreiras para retardar a propagação do fogo até que os serviços de emergência possam extingui-lo. Em comparação, os firewalls de segurança de rede são usados para gerenciamento de tráfego da Web. Normalmente, são destinados a retardar a propagação de ameaças da Web.

Os firewalls criam "pontos de obstrução" para afunilar o tráfego da Web, em que ele é analisado de acordo com um conjunto de parâmetros programados e medidas adequadas são tomadas. Alguns firewalls também rastreiam o tráfego e as conexões em registros de auditoria para referenciar o que foi permitido ou bloqueado.

Normalmente, os firewalls são usados para delimitar as fronteiras de uma rede privada ou dos dispositivos host dela. Assim, os firewalls são uma ferramenta de segurança na categoria mais ampla de controle de acesso de usuário. Essas barreiras costumam ser configuradas em dois locais: em computadores dedicados na rede ou nos computadores dos usuários e em outros endpoints (hosts).

## Tipos de Firewall

Firewall de proxy

Um firewall de proxy é um dos primeiros tipos de firewall e funciona como a passagem de uma rede para outra de uma aplicação específica. Servidores proxy podem oferecer recursos adicionais, como armazenamento em cache e segurança de conteúdo ao evitar conexões diretas de fora da rede. No entanto, isso também pode afetar a capacidade de taxa de transferência e as aplicações que eles podem comportar.

Firewall com inspeção de estado

Atualmente conhecido como o firewall tradicional, um firewall com inspeção de estado permite ou bloqueia tráfego de acordo com o estado, a porta e o protocolo. Ele monitora toda atividade desde o momento em que uma conexão é aberta até que ela seja fechada. As decisões de filtragem são tomadas de acordo com as regras definidas pelo administrador e com o contexto, o que significa o uso de informações de conexões e pacotes anteriores que pertencem à mesma conexão.

Firewall de Gerenciamento unificado de ameaças (UTM)

Normalmente, um dispositivo UTM combina, de maneira flexível, as funções de um firewall com inspeção de estado e prevenção contra intrusões e antivírus. Ele também pode incluir serviços adicionais e, às vezes, gerenciamento em nuvem. O UTM concentra-se em simplicidade e facilidade de uso.

Firewall de próxima geração (NGFW)

Os firewalls evoluíram para além da simples filtragem de pacotes e inspeção stateful. A maioria das empresas está implantando firewall de próxima geração para bloquear ameaças modernas, como malware avançado e ataques na camada da aplicação.

De acordo com a definição do Gartner, Inc., um firewall de próxima geração deve incluir:

Recursos padrão de firewall, como inspeção stateful
Prevenção de invasão integrada 

Reconhecimento e controle da aplicação para detectar e bloquear aplicativos nocivos
Atualização de caminhos para incluir feeds futuros de informação.

Técnicas para lidar com as ameaças à segurança em evolução .Embora esses recursos estejam se tornando cada vez mais a norma para a maioria das empresas, os NGFWs podem fazer mais.

NGFW focado em ameaças

Esses firewalls incluem todos os recursos de um NGFW tradicional e também oferecem detecção e remediação avançadas de ameaças. Com um NGFW focado em ameaças, você pode:

Saber quais recursos sofrem um risco maior com reconhecimento completo de contexto
Reagir rapidamente a ataques com automação de segurança inteligente que define políticas e fortalece suas defesas de forma dinâmica detectar melhor as atividades evasivas e suspeitas com a correlação de eventos de rede e endpoint.

Reduzir expressivamente o tempo entre a detecção e a limpeza com segurança retrospectiva que monitora continuamente atividades e comportamentos suspeitos mesmo após a inspeção inicial.

Facilitar a administração e reduzir a complexidade com políticas unificadas que oferecem proteção durante todo o ciclo de ataque

## statefull vs stateless

Filtragem stateless ou sem estado

A filtragem sem estado oferece um recurso de avaliação de pacotes de maneira independente, onde não há conhecimento sobre a conexão. Isso quer dizer que cada pacote que passa pelo firewall, independente de ser uma nova conexão ou já existente, é avaliado pelas regras estabelecidas pelo administrador.

É comum nestas arquiteturas criar uma regra para cada direção de tráfego, prevendo tanto a saída (envio) de um pacote, quanto a entrada (recebimento) – o que ocorre comumente em interfaces de redes diferentes. Como não há conhecimento das conexões, não é possível prever o retorno da conexão.

Os ambientes que possuem esse mecanismo de filtragem têm a tendência comum de ter um número maior de regras, por causa da necessidade de sempre se prever os dois sentidos de uma comunicação (entrada e saída).

Os firewalls stateless são cada vez menos utilizados. Ainda assim, está está presente em dispositivos de rede cujo principal foco não é segurança e garante que regras básicas de acesso possam ser criadas, evitando exposições desnecessárias.

O conceito mais importante a ser registrado sobre os firewalls stateless é que não possuem conhecimento acerca das conexões e, por causa disso, aplicam suas regras em todos os pacotes que atravessam o dispositivo.

Firewall stateful ou com estado

Os firewalls stateful foram concebidos posteriormente, a fim de solucionar aspectos de segurança que surgiram com a primeira geração, como por exemplo o caso de forjar (spoof) informações de conexão.

A importância fundamental foi de orientar a filtragem para conexão e permitir que o mecanismo de filtragem passasse a conhecer as conexões. Com base nisso, legitimaria um pacote ou não. Esse recurso auxiliar ficou conhecido como tabela de conexões ou tabela de estados.

Com a tabela de estados, todo início de conexão é devidamente registrado (um novo estado é criado). Quando o pacote retorna, antes de iniciar o processo de avaliação das regras de acesso, o firewall stateful verifica a tabela de estados, valida se há alguma conexão associada e, caso afirmativo, aceita a conexão, sem processar as regras. Do contrário, descarta o pacote.

A segurança do ambiente é incrementada consideravelmente com a utilização de firewall stateful, tendo em vista que há rastreabilidade de parâmetros utilizados para validar uma conexão ativa na estrutura. O nível e complexidade do tracking depende do fabricante. Alguns utilizam somente parâmetros de endereços e portas de origem e destino, enquanto outros utilizam número de sequência e reconhecimento, tamanho de janela etc (no caso do protocolo TCP).

A medida que a conexão evolui em termos de trocas de pacotes, a tabela de estados é sempre atualizada com as informações para garantir a continuidade de segurança e integridade. Este processo também garante a validade da conexão, sem que seja necessário avaliar as regras de acesso definidas pelo administrador.

Em um firewall stateful há uma economia considerável de recursos computacionais, uma vez que há um esforço inicial para a criação de novas conexões, que é recompensado até o encerramento pela não necessidade de processar as regras de acesso. É muito comum encontrar esse mecanismo de filtragem nas mais modernas soluções, que continua sendo um elemento fundamental na estratégia de defesa em profundidade.

## Material de suporte

[Link do site da Cisco sobre Firewall](https://www.cisco.com/c/pt_br/products/security/firewalls/what-is-a-firewall.html#~tipos-de-firewall)

[Link do site da kaspersky sobre Firewall](https://www.kaspersky.com.br/resource-center/definitions/firewall)

[Stateful vs Stateless](https://www.fortinet.com/br/resources/cyberglossary/stateful-vs-stateless-firewall)
