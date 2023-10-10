## EC2 - Amazon Elastic Compute Cloud
![AWS EC2](/aws/icon/aws-ec2.png)

É um serviço web que fornece capacidade de computação segura e redimensionável na nuvem. Uma instância é um servidor virtual na nuvem.
Reduz o tempo necessário para obter e inicializar novas instâncias de servidor para minutos.
Pague apenas pela capacidade que você realmente usa.

Por que é chamado Elastic Compute Cloud?

- **Elastic** porque você pode facilmente aumentar ou diminuir o número de servidores executados para oferecer suporte a uma aplicação automaticamente. Você também pode aumentar ou diminuir o tamanho dos servidores existentes.

- **Compute** porque a maioria dos usuários executa servidores para hospedar aplicações em execução ou processar dados, que exigem recursos de computação. Esses recursos incluem potência de processamento (CPU) e memória (RAM).

- **Nuvem** porque as instâncias do EC2 executadas estão hospedadas na nuvem

## Tipos de EC2

**On-Demand (Sob Demanda)** <br>
Com instâncias sob demanda, você paga pela capacidade de computação por hora sem compromissos de longo prazo.

**Reserved Instances (Instâncias Reservadas)** <br>
Permitem adquirir reservas de capacidade que se repetem diariamente, semanalmente ou mensalmente.

**Dedicated Hosts (Host e Instância Dedicada)**<br>
Hardware dedicado <br>
Servidor físico EC2 exclusivo para você.

**Spot Instances (Instâncias Spot)** <br>
Até 90% de desconto em comparação de instâncias por demanda
São terminadas quando o preço do spot, é maior que o preço que você estabeleceu para pagar.

## [Tipos de Instância](https://docs.aws.amazon.com/pt_br/AWSEC2/latest/WindowsGuide/instance-types.html#current-gp)

## AMI - Imagens de máquina da Amazon
Uma AMI é um modelo que contém a configuração do software (sistema operacional, servidor de aplicações e aplicações) necessária para executar a instância. Você deve especificar uma AMI ao executar uma instância. Também temos a opção de criar as nossas próprias imagens e criar instância a partir dela. 

**Fontes de AMI**
- Quick Start - AMIs do Linux e do Windows fornecidos pela AWS.
  
- Minhas AMIs - Todas as AMIs que você criou.
  
- AWS Marketplace - Modelos pré-configurados de terceiros.

- AMIs da comunidade - AMIs compartilhadas por outras pessoas. Use por sua conta e risco.


## SG - Security Groups (Grupos de segurança)
Os grupos de segurança funcionam como o "firewall" da AWS, bloqueando e permitindo acesso de entrada e de saída da instância. O grupo de segurança define em quais portas o tráfego de rede é permitido

## IPs Elásticos (Elastic IP)
O serviço de registro de IP da Amazon. Garante que a sua máquina mantenha um IP único, mesmo que seja desligada. 
Um IP por EC2 é gratuito, caso a máquina mantenha-se ligada.
Caso haja mais IPs anexados a uma instância ou a instância seja desligada, você será cobrado.

## Elastic Load Balancing (Balanceamento de carga)
![Load Balancing](/aws/icon/aws-elb.png)

Distribui automaticamente o tráfego de entrada de aplicativos entre diversos destinos, como instâncias EC2, containers, endereços IP e funções Lambda. 
O Elastic Load Balancing é compatível com os seguintes tipos de balanceadores de carga:

- Application Load Balancer
- Network Load Balancer
- Gateway Load Balacer

## Target Groups (Para grupos de destino)
Para usarmos o load balancer da AWS nós precisamos definir um target group que pode ser para instâncias, IPs, etc.




