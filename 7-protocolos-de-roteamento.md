# Protocolos de roteamento

## Rotas conectadas e estáticas

Os roteadores precisam ter rotas em suas tabelas de roteamento IP para que o processo de encaminhamento (roteamento) de pacotes funcione. Dois dos modos mais básicos pelos quais um roteador adiciona rotas em sua tabela de roteamento são através do aprendizado a respeito das sub-redes conectadas em suas interfaces, e através da configuração de uma rota via um comando de configuração global (chamada de rota estática).

## Rotas conectadas

Um roteador adiciona rotas em sua tabela de roteamento para as sub-redes conectadas a cada uma das interfaces do roteador. Para que isto ocorra, o roteador deve ter um endereço IP e uma máscara configurados na interface (estaticamente, através do comando ip address, ou dinamicamente usando DHCP (Dynamic Host Conjiguration Protocol, ou Protocolo de Configuração Dinâmica de Host» , e ambos os códigos de estado da interface devem estar "up". 

O conceito é simples:

se um roteador possui uma interface em uma sub-rede, o roteador tem uma maneira de encaminhar pacotes para dentro desta sub-rede, portanto o roteador precisa de uma rota em sua tabela de roteamento.

## Rotas estáticas

## Rotas default

Como parte do processo de roteamento (encaminhamento), um roteador compara o endereço IP de destino de cada pacote com a tabela de roteamento do roteador. Se o roteador não encontrar nenhuma rota, o roteador descarta o pacote e não faz nenhuma tentativa para recuperar esta perda.

Considera-se uma rota default a rota que casa todos os endereços IP de destino. Com uma rota default, quando o endereço IP de destino de um pacote não casar com nenhuma outra rota, o roteador usará a rota default para encaminhar o pacote.

## Visão geral sobre protocolos de roteamento

Protocolos de roteamento IP possuem um objetivo principal: preencher a tabela de roteamento IP com as melhores rotas atuais que puderem encontrar. O objetivo é simples, mas o processo e as opções podem ser complicados.

Protocolos de roteamento ajudam os roteadores a aprender rotas fazendo com que cada roteador anuncie as rotas que conhece. Cada roteador começa conhecendo apenas as rotas conectadas. Depois, cada roteador envia mens1agens, definidas pelo protocolo de roteamento, que listam as rotas. Quando um roteador ouve uma mensagem de atualização de roteamento de outro roteador, o roteador que está ouvindo a atualização aprende a respeito das sub-redes e adiciona as rotas em sua tabela de roteamento. Se todos os roteadores participarem, todos os roteadores podem aprender a respeito de todas as sub-redes em uma interconexão de redes.

Quando estiverem aprendendo rotas, os protocolos de roteamento também devem impedir loops de acontecerem. Um loop ocorre quando um pacote fica voltando para o mesmo roteador devido a erros nas rotas nas tabelas de roteamento coletivas dos roteadores. Estes loops podem acontecer com protocolos de roteamento, a menos que o protocolo de roteamento faça um esforço para evitar os loops.

Basicamenta há dois tipos de modos de roteamento:

* Estático = rotas estáticas

* Dinâmico = RIP, EIGRP, IGRP entre outros