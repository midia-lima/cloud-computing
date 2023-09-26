## Global Infrastructure
- A infraestrutura da AWS é criada em regiões e zonas de disponibilidade.
- Uma região geralmente recebe o nome da cidade onde se encontra.
- Cada região é um local físico com várias zonas de disponibilidade.
- As zonas de disponibilidade consistem em um ou mais data centers, cada um com energia, rede e conectividade redundantes, alojados em instalações separadas.
- São Paulo, por exemplo, é uma região da AWS. E dentro dessa região, há 3 espaços físicos que possuem sub-redes conectadas entre si. Estes espaços físicos são chamados de zonas de disponibilidade.
- As zona de disponibilidade é tolerante a falhas, proporcionando alta disponibilidade.

## Regions
- A região foi projetada para ser completamente isolada das outras regiões. Isso atinge a maior tolerância a falhas e estabilidade possíveis.

## Availability Zone
- A zona de disponibilidade é isolada, mas as zonas de disponibilidade em uma região são conectadas por meio de links de baixa latência.
- A zona de disponibilidade foi projetada como uma zona de falha independente.
- O mínimo de zonas de disponibilidade por região existente, hoje são duas.
- As zonas de disponibilidade são fisicamente separadas.
- As zonas de disponibilidade apresentam uma fonte de alimentação ininterrupta discreta (UPS) e geração de backup no local.
  
## Edge Locations
Pontos de presença são endpoints da AWS usados para armazenar conteúdo em cache.

## Como escolhemos a região certa para provisionar o serviço? A AWS recomenda considerar esses pontos
- Considerar as leis locais no armazenamento dos dados.
- Latência para usuários finais.
- Existem serviços que são globais e existem serviços que são regionais, nem todos os serviços estão distribuídos em todas as regiões.

## Acesso a serviços
- A interface gráfica é chamada de console
- Linha de comando
- SDKs