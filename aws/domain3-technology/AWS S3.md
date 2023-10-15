## S3 (Simple Storage Service)
![AWS S3](/aws/icon/aws-s3.png)

O AmazonS3 é um serviço de armazenamento de objetos. Ele permite que você armazene quantidades praticamente ilimitadas de dados. Os arquivos de dados são armazenados como objetos. Você coloca objetos em um bucket, que você define. Cada bucket deve ter um nome que seja globalmente exclusivo em várias regiões. Isso significa que o nome do bucket deve ser exclusivo em todas as contas de clientes da AWS.

- Armazena quantidade enormes (ilimitadas) de dados não estruturados
- Os arquivos de dados são armazenados como objetos em um bucket que você define
- 5 TB é o tamanho de arquivo máximo de um único objeto
- Todos os objetos têm uma URL exclusivo e acessível globalmente por REST (namespace universal)
- Todos os objetos têm uma chave, um ID de versão, um valor, metadados e sub-recursos

## Benefícios do Amazon S3

- Durabilidade
  - Garante que os dados não sejam perdidos
  - O Armazenamento S3 Standard oferece 99,999999999% de durabilidade
  
- Disponibilidade
  - Acesse seus dados quando for necessário
  - A classe de armazenamento S3 Standard foi criada para disponibilidade de 99,99%
  
- Escalabilidade
  - Capacidade praticamente ilimitada
  - Qualquer objeto únito de 5 TB ou menos

- Segurança
  - Oferece controle de acesso refinado 
  
- Performace
  - É compatível com vários padrões de design

## Uso comuns que usam o Amazon S3

### 1. Armazenar e distribuir conteúdo e mídia da Web
   
Crie uma infraestrutura redundante, escalável e altamente disponível para hospedar vídeos, fotos ou músicas com recursos de upload e download.

### 2. Hospede sites estáticos

Podemos usar o S3 para hospedar um site estático. Em um site estático, as páginas da Web individuais incluem o conteúdo estático. Elas também podem conter sccripts do lado do cliente.

### 3. Armazenamento de dados para computação e análise em grande escala

Podemos usar o S3 como um armazenamento de dados para computação ou análise em grande escala, como análise de transações financeiras, análise de fluxo de cliques e transcodificação de mídia.

### 4. Backup e arquivamento de dados críticos

O S3 é usado como uma solução de backup de dados. Devido à sua natureza resiliente e escalável, o S3 também funciona bem como uma ferramenta de backup e arquivamento. Além disso, você pode mover dados de longo prazo do armazenamento do Amazon S3 Standard para o Amazon Simple Storage Service Glacier. 

### Proteção de buckets e objetos do Amazon S3
- **Os buckets e objetos do S3 recém-criados são privados e protegidos por padrão**
  
- **Quando os casos de uso devem compartilhar dados do Amazon S3**
  - Gerencie e controle o acesso aos dados
  - Adote o princípio do privilégio minímo

- **Ferramentas e opções para controlar o acesso aos dados do Amazon S3**
  - Recursos de bloqueio de acesso público: ativado em novos buckets por padrão, simples de gerenciar
  - Politícas do IAM: uma boa opção quando o usuário pode autenticar usando o IAM
  - Politícas do bucket: defina o acesso a um objeto ou bucket específico
  - Listas de controle de acesso(ACLs): um mecanismo de controle de acesso herdado.
  - Pontos de acesso do S3: você pode conceder acesso por tempo limitado a outras pessoas com URLs temporárias
  - Verificação de permissão do bucket do AWS Trusted Advisor: um recurso gratuito

### Três abordagens gerais para configurar o acesso

- **Configuração de segurança padrão do Amazon S3**

Por padrão, todos os buckets do S3 e os objetos armazenados neles são privados (protegidos). As únicas entidades com acesso a um bucket recém-criado e não modificado são o administrador da conta e o usuário raiz. 

- **Configurações de segurança do Amazon S3 para acesso público**

As configurações de segurança do S3 podem ser desabilitadas e qualquer pessoa pode acessar publicamente os objetos armazenados.

- **Política de acesso aplicada às configurações de segurança do S3**

Podemos configurar o bucket para fornecer acesso controlado. Por exemplo: O usuário A recebeu acesso aos objetos do bucket, mas o acesso do usuário B foi negado.

### Considere criptografar objetos no Amazon S3

- **A criptografia codifica dados com uma chave secreta, o que os torna ilegíveis**
  - Somente quem tem a chave secreta pode decodificar os dados
  - Opcionalmente, use o AWS KMS para gerenciar chaves secretas
  
- **Criptografia no lado do servidor**
  - No bucket, habilite esse recurso selecionando a opção de criptografia padrão
  - O S3 criptografa objetos antes de salvá-los em disco e os descriptografa quando você faz o download deles

- **Criptografia no lado do cliente**
  - Criptografe os dados no lado do cliente e faça upload dos dados criptografados no S3


### Versionamento
- Protege contra substituições e exclusões acidentais sem afetar a performace
- Gera uma nova versão a cada upload
- Permite fácil recuperação de objetos excluídos ou retorno a versões anteriores
- Três estados possíveis de um bucket S3
    
  1. Padrão: versionamento não habilitado
  2. Versionamento habilitado
  3. Versionamento suspenso  

### Suporte para compartilhamento de recursos entre origens (CORS)
O compartilhamento de recursos entre origens (CORS) define uma maneira para as aplicações Web, carregadas em um domínio, interagirem com recursos em outro domínio. Com o suporte do CORS, você pode criar aplicações Web e permitir seletivamente o acesso de origem de várias origens aos recursos do S3.

Para configurar o bucket para permitir solicitações entre origens, crie uma configuração CORS. Uma configuração CORS é um documento XML com regras que identificam:
- As origens que você permitirá acesso ao bucket.
- As operações (métodos HTTP) que darão suporte a cada origem. 
- Outras informações específicas da operação

## Classes de armazenamento do S3

*S3 Standard* - Dados acessados com frequência

*S3 Standard IA* - Dados duradouros acessados com pouca frequência

*S3 One Zone IA* - Dados duradouros, não críticos e acessados com pouca frequência

*Amazon S3 Glacier ou Deep Archive* - Arquivamento de dados raramente acessados

[Categorias de armazenamento do Amazon S3](https://aws.amazon.com/pt/s3/storage-classes/)

## Políticas de ciclo de vida do S3
Configure uma política de ciclo de vida do S3 para excluir ou mover objetos com base na idade deles. Uma configuração de ciclo de vida é um conjunto de regras que definem ações aplicadas pelo S3 a um grupo de objetos.

Assim que uma política de ciclo de vida do S3 é definida, os dados migram automaticamente para uma classe de armazenamento diferente sem causar alterações às aplicações.

## Custos do Amazon S3

| Pague apenas pelo uso, incluindo | 
| ----------- | 
| GBs de objetos armazenados (por mês). Preços diferentes por região e por classe de armazenamento. | 
| Transfira para outras regiões ou para a internet |
| PUT, COPY, POST, LIST GET, SELECT, transição do ciclo de vida, solicitações de recuperação de dados. | 
|| 

| Não há cobrança para |
| ----------- |
| Transferência de dados DE ENTRADA da internet para o S3 |
| Transferência entre os buckets do S3 ou do S3 para qualquer serviço na mesma região da AWS |
| Transferência para o CloudFront |
| Solicitações de DELETE e CANCEL |
||

## Multipart Upload



## Perguntas
O uso de multithreading em suas solicitações do Amazon S3 por meio da API Multipart Upload é um exemplo de qual prática recomendada da nuvem AWS?
> Pense paralelo

Você tem um grande número de arquivos de log que serão arquivados na AWS por um longo tempo e devem ter um tempo de recuperação de 12 horas ou menos. Qual serviço é a classe de armazenamento mais econômica para essa finalidade?
> Amazon S3 Glacier

Você deseja hospedar um site estático próprio na AWS a um custo baixo. Qual serviço deve ser usado para esse fim?
> Amazon S3 Standard











