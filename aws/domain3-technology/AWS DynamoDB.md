## DynamoDB
![AWS DynamoDB](/aws/icon/aws-dynamodb.png)

O Amazon DynamoDB é um banco de dados não relacional (NoSQL) de chave-valor e documento totalmente gerenciado, rápido e flexível para qualquer escala. Oferece performace abaixo de 10 milissegundos em qualquer escala.

**Características**
- Serverless (AWS gerencia os recursos)
- Escalável (Virtualmente ilimitado)
- Confiável (Criptografia em repouso por padrão)
- Rápido (Latência em microsegundos)

**Lembre-se**
- DynamoDB é NoSQL
- Tabela é uma coleção de itens
- Cada item possui um atributo
- Chave primária é obrigatória e é utilizada para identificar um item na tabela
- Chave secundária é opcional e fornece flexibilidade na consulta

**Criando uma tabela**

Chave de partição (partition key) faz parte da nossa chave primária que identificará um item

A Chave de partição pode ser a junção da chave de partição com a chave de chave de classificação (sort key)

Podemos ter somente uma chave ou uma composição de duas chaves para formar a minha chave primaria

Temos duas formas de buscar itens: utilizando o **Modo Query** ou o 
**Modo Scan**

**Modo Scan - Verificar**

O Modo Scan deve ser evitado a todo custo, pois, apesar de funcionar, ele verificará, linha a linha, se o filtro corresponde.
O modo Scan percorre toda a tabela aplicando o filtro item a item.

**Modo Query - Consulta**

Limitamos os dados a serem trazidos. A partir deles, podemos aplicar filtros em um de cada vez.
No modo Query, as chaves da tabela são utilizadas. Isso garante que um número muito reduzido de itens será verificado baseado nos valores dessas chaves.

**Índices**

O banco de dados DynamoDB possui dois tipos de índices secundários: os locais e os globais. Os índices são chamados de secundários pois ao criar a tabela nós já definimos uma chave primária (junção entre partition key e sort key) e esse é nosso índice “primário”, embora esse termo não seja muito comum.

Os índices secundários locais (Local Secondary Index ou LSI) e índices secundários globais (Global Secondary Index ou GSI) são muito semelhantes, tendo apenas as seguintes diferenças:

- Um LSI precisa ser implementado no momento da criação da tabela. Não é possível criá-los depois. Já um GSI pode ser feito a qualquer momento após a criação da tabela;

- LSI não pode ter como sua definição uma outra partition key. Apenas a sort key pode ser diferente. Já um GSI pode ter tanto partiion key quanto sort key, diferentes do que foi definido na tabela.

**O que a projeção de atributos configurado faz no índice?**

Define quais atributos serão recuperados ao realizar uma consulta no índice. Ao realizar uma consulta (Query) utilizando o índice em questão, apenas os atributos definidos em "projeções de atributos" serão trazidos. Isso pode significar que vamos buscar todos os atributos (opção All), apenas as chaves do índice (opção Only keys) ou além das chaves, alguns atributos específicos (opção Include).

**Tabelas globais**

Tabelas globais são um recurso muito interessante para tornar a disponibilidade do seu banco de dados ainda maior. Uma tabela global é basicamente uma tabela que não pertence a uma região específica da AWS, mas sim está replicada em todas as regiões.

Segundo a própria documentação da AWS, ela consiste em diversas tabelas replicadas (uma por região da AWS), que o DynamoDB trata como uma única unidade. Cada réplica possui o mesmo nome de tabela e o mesmo esquema de chave primária. Quando uma aplicação grava dados em uma tabela-réplica em uma região, o DynamoDB propaga automaticamente a gravação nas outras tabelas-réplicas nas outras Regiões da AWS.

**DAX**

O DynamoDB Accelerator (DAX) é um cache em memória totalmente gerenciado e altamente disponível para o Amazon DynamoDB. O DAX faz todo o trabalho pesado necessário para adicionar aceleração em memória às tabelas do DynamoDB, sem que devs tenham de gerenciar invalidação de cache, preenchimento de dados ou gerenciamento de clusters.

Sendo assim, essa funcionalidade, quando habilitada, adiciona uma camada de cache ao seu banco de dados DynamoDB para aumentar ainda mais a performance, mas isso vem com um custo, claro. O DynamoDB cobra pela capacidade de DAX por hora.

**Precificação**

O DynamoDB cobra pela leitura, gravação e armazenamento de dados e suas tabelas.

