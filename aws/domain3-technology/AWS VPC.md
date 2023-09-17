## VPC - Virtual Private Cloud
![AWS VPC](/aws/icon/aws-vpc.png)

VPC significa virtual private cloud ou nuvem virtual privada e é basicamente uma rede virtual. Sempre que criamos uma conta na AWS cada uma das regiões da conta possui uma VPC padrão e cada zona de disponibilidade possui sua própria sub-rede por padrão. 
Sempre que criamos uma instância ou vários outros serviços, precisamos adicionar isso a uma rede. Por padrão sempre vem uma VPC habilitada.

**Benefícios**
- Mesmo conceito on-premises;
- Total controle na configuração;
- Oferece camadas de segurança;
- Conectividade com outros serviços;

**Características**
- Região e Zonas de disponibilidade;
- Sub-redes [Pública e Privada];
- Tabela de roteamento;
- Internet Gateway [sub-rede pública];
- Nat Gateway [sub-rede privada];
- Security Group [SG] e Access Control List [ACLs];

## SG - Security Groups (Grupos de segurança)
Os grupos de segurança funcionam como o "firewall" da AWS, bloqueando e permitindo acesso de entrada e de saída da instância.

## ACL - Access Control List (Lista de Controle de Acesso)
Funciona como um firewall a única diferença é que temos várias listas e cada uma dessas listas possui várias regras. As ACLs ficam na camada de rede, os SG não é aplicado a uma rede inteira, ele é aplicado a um serviço específico.

## Gateways NAT
Um gateway NAT permite o acesso da nossa sub-rede privada para a internet.

## Internet Gateway
Ao criarmos a nossa VPC criamos uma sub-rede pública e uma sub-rede privada e a principal diferença entre elas duas são as conexões de rede. 
Para a rede pública, é realizada a conexão entre a sub-rede em um Internet Gateway.
O Internet Gateway é o serviço da AWS que libera o acesso vindo da internet para alguma sub-rede de uma VPC. Se, na tabela de rotas da sub-rede privada, nós configurarmos a ligação para um Internet Gateway, essa sub-rede se tornará pública.

## Endpoint
Permite que acessemos algum serviço da AWS sem precisar passar pela internet.



