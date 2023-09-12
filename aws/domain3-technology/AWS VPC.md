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
- Security Group [SG] e Network Access List [NACLS];

## SG - Security Groups (Grupos de segurança)

Os grupos de segurança funcionam como o "firewall" da AWS, bloqueando e permitindo acesso de entrada e de saída da instância.

## ACL - Access Control List (Lista de Controle de Acesso)
Funciona como um firewall a única diferença é que temos várias listas e cada uma dessas listas possui várias regras. As ACLs ficam na camada de rede, os SG não é aplicado a uma rede inteira, ele é aplicado a um serviço específico.


