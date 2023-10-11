## EBS - Elastic Block Store
![AWS EBS](/aws/icon/aws-ebs.png)

O EBS fornece volume de armazenamento em nível de bloco, semelhantes a um disco rígido externo, para uso com instâncias do EC2. Os volumes do EBS são altamente disponíveis e confiáveis que podem ser associados à rede para instâncias em execução na mesma zona de disponibilidade.
O EBS deve ser associado a apenas uma instância de cada vez.

- Os volumes do EBS fornecem armazenamento persistente conectado à rede para uma instância do EC2.

- Características
  - Armazenamento em nível de bloqueio persistente
  - Pode associar a qualquer instância na mesma zona de disponibilidade
  - Usa HDD ou SSD
  - Pode ser criptografado
  - Suporte a snapshots que persistem no S3
  - Os dados persistem independentemente da vida útil da instância

- Exemplos de casos de uso
  - Banco de dados autônomo
  - Armazenamento de dados de aplicações gerais