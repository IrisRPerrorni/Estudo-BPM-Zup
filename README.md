# Estudo-BPM-Zup
Estudo para o BPM da ZUP

# Prova sobre AWS CLI
### 1) Qual é o propósito principal do AWS CLI (Command Line Interface)?

a) Gerenciar instâncias EC2 apenas.

b) Interagir com serviços da AWS usando comandos de linha de comando.

c) Fornecer uma interface gráfica para gerenciar recursos da AWS.

d) Monitorar o tráfego de rede na sua infraestrutura da AWS.

#### Resp: B

### 2) Como você pode instalar o AWS CLI no seu sistema operacional local?

a) A AWS CLI só pode ser acessada através do console web da AWS.

b) Usando o npm para instalar o pacote AWS CLI globalmente.

c) Através do gerenciador de pacotes do sistema operacional, como apt-get, yum ou Homebrew.

d) Baixando e executando um instalador específico do site da AWS.

#### Resp: C

### 3) Qual comando AWS CLI você usaria para listar todas as regiões disponíveis na AWS?

a) aws list-regions

b) aws ec2 describe-regions

c) aws s3 list-regions

d) aws configure regions

#### Resp: B

### 4) Qual das seguintes opções mostra a sintaxe correta para criar um novo bucket S3 usando o AWS CLI?

a) aws s3 create-bucket --bucket my-bucket

b) aws s3 new-bucket --name my-bucket

c) aws s3 make-bucket --bucket-name my-bucket

d) aws create-bucket --name my-bucket --service s3

####  Resp: C

### 5)  Qual comando AWS CLI você usaria para listar todos os buckets S3 em sua conta?

a) aws s3 ls

b) aws s3 list-buckets

c) aws s3 get-buckets

d) aws s3 buckets

####  Resp: B

### 6) Qual comando AWS CLI você usaria para fazer upload de um arquivo local para um bucket S3?

a) aws s3 upload-file

b) aws s3 cp

c) aws s3 put-file

d) aws s3 send-file

####  Resp: B

### 7) Qual opção abaixo descreve corretamente a finalidade do arquivo ~/.aws/credentials?

a) Armazenar configurações globais para a AWS CLI.

b) Armazenar credenciais de acesso para autenticar-se com a AWS.

c) Armazenar configurações de região padrão para a AWS CLI.

d) Armazenar chaves de criptografia para dados sensíveis.

####  Resp: B

### 8) Qual comando AWS CLI você usaria para exibir informações detalhadas sobre uma instância EC2 específica?

a) aws ec2 get-instance

b) aws ec2 describe-instance

c) aws ec2 show-instance

d) aws ec2 describe-instances

####  Resp: D

### 9) Qual comando AWS CLI você usaria para criar um novo grupo de segurança para uma instância EC2?

a) aws ec2 create-security-group

b) aws ec2 new-security-group

c) aws ec2 add-security-group

d) aws ec2 authorize-security-group-ingress

####  Resp: A

### 10) Qual comando AWS CLI você usaria para iniciar uma instância EC2?

a) aws ec2 start-instance

b) aws ec2 run-instance

c) aws ec2 launch-instance

d) aws ec2 start-instances

####  Resp: A
__________________________________
# Prova sobre AWS SQS 

### 1) Qual das seguintes afirmações sobre o Amazon SQS está correta?

a) O SQS é um banco de dados relacional totalmente gerenciado pela AWS.

b) O SQS é um serviço que permite o processamento em tempo real de grandes volumes de dados.

c) O SQS é um serviço de mensagens totalmente gerenciado pela AWS, que permite a comunicação assíncrona entre diferentes partes de uma aplicação.

d) O SQS é usado principalmente para armazenar e distribuir conteúdo estático, como imagens e vídeos.

####  Resp: C

Questão 2: Qual é a principal vantagem de usar o Amazon SQS em arquiteturas distribuídas de microsserviços?

a) Redução da latência de rede.

b) Maior consistência de dados.

c) Desacoplamento entre componentes do sistema.

d) Melhor desempenho de computação.

####  Resp: C

Questão 3: Qual dos seguintes é um tipo de fila do Amazon SQS?

a) Fila FIFO (First-In-First-Out)

b) Fila LIFO (Last-In-First-Out)

c) Fila LRU (Least Recently Used)

d) Fila MRU (Most Recently Used)

####  Resp: A

### 4) Qual é a maneira correta de excluir uma mensagem de uma fila SQS após ser processada usando o AWS SDK for Java?

java
``` bash
a)
import com.amazonaws.services.sqs.AmazonSQS;
import com.amazonaws.services.sqs.AmazonSQSClientBuilder;
import com.amazonaws.services.sqs.model.DeleteMessageRequest;

AmazonSQS sqs = AmazonSQSClientBuilder.standard().build();
String queueUrl = "https://sqs.us-east-1.amazonaws.com/123456789012/my-queue";
String receiptHandle = "AQEBDYWNX0Jy......DvI3OSzg4NTA";

sqs.deleteMessage(new DeleteMessageRequest(queueUrl, receiptHandle));
```
``` bash
b)
import com.amazonaws.services.sqs.AmazonSQS;
import com.amazonaws.services.sqs.AmazonSQSClientBuilder;
import com.amazonaws.services.sqs.model.DeleteMessageRequest;

AmazonSQS sqs = AmazonSQSClientBuilder.standard().build();
String queueUrl = "https://sqs.us-east-1.amazonaws.com/123456789012/my-queue";
String messageId = "AQEBDYWNX0Jy......DvI3OSzg4NTA";

sqs.deleteMessage(new DeleteMessageRequest(queueUrl, messageId));
```
``` bash
c)
import com.amazonaws.services.sqs.AmazonSQS;
import com.amazonaws.services.sqs.AmazonSQSClientBuilder;

AmazonSQS sqs = AmazonSQSClientBuilder.standard().build();
String queueUrl = "https://sqs.us-east-1.amazonaws.com/123456789012/my-queue";
String receiptHandle = "AQEBDYWNX0Jy......DvI3OSzg4NTA";

sqs.removeMessage(queueUrl, receiptHandle);
```
``` bash
d)
import com.amazonaws.services.sqs.AmazonSQS;
import com.amazonaws.services.sqs.AmazonSQSClientBuilder;

AmazonSQS sqs = AmazonSQSClientBuilder.standard().build();
String queueUrl = "https://sqs.us-east-1.amazonaws.com/123456789012/my-queue";
String messageId = "AQEBDYWNX0Jy......DvI3OSzg4NTA";

sqs.removeMessage(queueUrl, messageId);
```
####  Resp: A

### 7): Qual é a maneira correta de configurar um SQS Listener em uma aplicação Java usando o AWS SDK for Java?

``` bash
a)
import com.amazonaws.services.sqs.AmazonSQS;
import com.amazonaws.services.sqs.AmazonSQSClientBuilder;
import com.amazonaws.services.sqs.model.ReceiveMessageRequest;
import com.amazonaws.services.sqs.model.ReceiveMessageResult;

AmazonSQS sqs = AmazonSQSClientBuilder.standard().build();
String queueUrl = "https://sqs.us-east-1.amazonaws.com/123456789012/my-queue";

ReceiveMessageRequest receiveRequest = new ReceiveMessageRequest(queueUrl);
ReceiveMessageResult receiveResult = sqs.receiveMessage(receiveRequest);
List<Message> messages = receiveResult.getMessages();

for (Message message : messages) {
    System.out.println("Message: " + message.getBody());
}
```

``` bash
b)

java
Copy code
import com.amazonaws.services.sqs.AmazonSQS;
import com.amazonaws.services.sqs.AmazonSQSClientBuilder;
import com.amazonaws.services.sqs.model.Message;
import com.amazonaws.services.sqs.model.ReceiveMessageRequest;
import com.amazonaws.services.sqs.model.ReceiveMessageResult;

AmazonSQS sqs = AmazonSQSClientBuilder.standard().build();
String queueUrl = "https://sqs.us-east-1.amazonaws.com/123456789012/my-queue";

ReceiveMessageRequest receiveRequest = new ReceiveMessageRequest(queueUrl);
ReceiveMessageResult receiveResult = sqs.receiveMessage(receiveRequest);
List<Message> messages = receiveResult.getMessages();

for (Message message : messages) {
    System.out.println("Message: " + message.getBody());
}
```

``` bash
c)

java
Copy code
import com.amazonaws.services.sqs.AmazonSQS;
import com.amazonaws.services.sqs.AmazonSQSClientBuilder;
import com.amazonaws.services.sqs.model.Message;
import com.amazonaws.services.sqs.model.ReceiveMessageRequest;

AmazonSQS sqs = AmazonSQSClientBuilder.standard().build();
String queueUrl = "https://sqs.us-east-1.amazonaws.com/123456789012/my-queue";

ReceiveMessageRequest receiveRequest = new ReceiveMessageRequest(queueUrl);
List<Message> messages = sqs.receiveMessage(receiveRequest).getMessages();

for (Message message : messages) {
    System.out.println("Message: " + message.getBody());
}
```

``` bash
d)

java
Copy code
import com.amazonaws.services.sqs.AmazonSQS;
import com.amazonaws.services.sqs.AmazonSQSClientBuilder;
import com.amazonaws.services.sqs.model.Message;
import com.amazonaws.services.sqs.model.ReceiveMessageRequest;

AmazonSQS sqs = AmazonSQSClientBuilder.standard().build();
String queueUrl = "https://sqs.us-east-1.amazonaws.com/123456789012/my-queue";

ReceiveMessageRequest receiveRequest = new ReceiveMessageRequest(queueUrl);
List<Message> messages = sqs.receiveMessage(receiveRequest).getMessages();

for (Message message : messages) {
    System.out.println("Message: " + message.getBody());
}
```
####  Resp: B

Questão 8: Qual é o objetivo principal do código abaixo?
``` bash
import boto3

sqs = boto3.resource('sqs')
queue = sqs.get_queue_by_name(QueueName='my-queue')

for message in queue.receive_messages():
    print('Message Body:', message.body)
```

a) Enviar uma mensagem para uma fila SQS.

b) Excluir uma mensagem de uma fila SQS após ser processada.

c) Receber mensagens de uma fila SQS e imprimir seus corpos.

d) Criar uma nova fila SQS.

####  Resp: C
___________________________
# Prova sobre AWS Lambda

### Questão 1: O que é o AWS Lambda?

a) Um serviço de armazenamento de objetos na nuvem.

b) Um serviço de banco de dados relacional totalmente gerenciado pela AWS.

c) Um serviço de computação serverless que permite executar código sem provisionar ou gerenciar servidores.

d) Um serviço de balanceamento de carga para aplicativos web.

####  Resp: C


### Questão 2: Qual das seguintes linguagens de programação pode ser usada para escrever funções Lambda?

a) JavaScript/Node.js

b) Python

c) Java

d) Todas as opções acima

####  Resp: D

### Questão 3: Qual é o tempo máximo de execução padrão para uma função Lambda?

a) 1 minuto

b) 5 minutos

c) 15 minutos

d) 30 minutos

####  Resp: B

### Questão 4: Como você pode acionar uma função Lambda para ser executada periodicamente?

a) Por meio de uma API Gateway.

b) Por meio de um gatilho do Amazon SQS.

c) Por meio de um evento do Amazon S3.

d) Por meio de um evento do Amazon CloudWatch Events.

####  Resp: C

### Questão 5: Qual é a maneira correta de criar uma função Lambda usando o AWS CLI?

a) aws lambda create-function --function-name my-function --runtime nodejs14.x --handler index.handler --role arn:aws:iam::123456789012:role/lambda-execution-role --zip-file fileb://function.zip

b) aws lambda new-function --name my-function --runtime nodejs14.x --handler index.handler --role arn:aws:iam::123456789012:role/lambda-execution-role --code file://function.zip

c) aws lambda add-function --function-name my-function --runtime nodejs14.x --handler index.handler --role arn:aws:iam::123456789012:role/lambda-execution-role --code fileb://function.zip

d) aws lambda deploy-function --function-name my-function --runtime nodejs14.x --handler index.handler --role arn:aws:iam::123456789012:role/lambda-execution-role --package function.zip

####  Resp: A

### Questão 6: Qual é a maneira correta de definir variáveis de ambiente para uma função Lambda usando o console AWS Lambda?

a) No código da função Lambda, usando a palavra-chave environment.

b) Na configuração do gatilho associado à função Lambda.

c) No arquivo de configuração da função Lambda no console AWS Lambda.

d) Na configuração da função Lambda, em "Configurações avançadas".

####  Resp: D

### Questão 7: Qual é a maneira correta de invocar uma função Lambda síncrona usando o SDK do AWS Lambda para Python (Boto3)?

```bash
a) 
import boto3

client = boto3.client('lambda')
response = client.invoke(
    FunctionName='my-function',
    InvocationType='RequestResponse',
    Payload=b'{}'
)
```
```bash
b) 
import boto3

lambda = boto3.resource('lambda')
function = lambda.get_function(FunctionName='my-function')
response = function.invoke()
```bash
```
c)
import boto3

client = boto3.client('lambda')
response = client.run_function(
    FunctionName='my-function',
    InvocationType='RequestResponse',
    Payload=b'{}'
)
```bash
```
```bash
d) 
import boto3

lambda = boto3.resource('lambda')
function = lambda.Function('my-function')
response = function.invoke()
```
####  Resp: A

### Questão 8: Qual das seguintes opções descreve corretamente a diferença entre invocação síncrona e assíncrona de uma função Lambda?

a) Na invocação síncrona, a função Lambda é invocada automaticamente em intervalos regulares. Na invocação assíncrona, a função Lambda é invocada manualmente pelo usuário.

b) Na invocação síncrona, a função Lambda é invocada de forma que a resposta é retornada imediatamente após a conclusão da execução. Na invocação assíncrona, a função Lambda é invocada sem esperar pela resposta imediata.

c) Na invocação síncrona, a função Lambda é invocada apenas uma vez, enquanto na invocação assíncrona ela é invocada continuamente em loop até que seja interrompida.

d) Na invocação síncrona, a função Lambda é invocada manualmente pelo usuário. Na invocação assíncrona, a função Lambda é invocada automaticamente em intervalos regulares.

####  Resp: B

### Questão 9: Qual é a maneira correta de conceder permissões a uma função Lambda para acessar recursos da AWS?

a) Apenas usando políticas de acesso do IAM anexadas à função Lambda.

b) Apenas usando chaves de acesso da AWS configuradas na função Lambda.

c) Apenas usando grupos de segurança associados à função Lambda.

d) Apenas usando tags de identificação associadas à função Lambda.

####  Resp: A

### Questão 10: Qual é o principal benefício de usar AWS Lambda em comparação com servidores tradicionais?

a) AWS Lambda oferece maior controle e personalização do ambiente de execução.

b) AWS Lambda elimina a necessidade de provisionamento e gerenciamento de servidores.

c) AWS Lambda oferece melhor desempenho em aplicações de alto tráfego.

d) AWS Lambda é mais adequado para aplicativos monolíticos do que para arquiteturas de microsserviços.

####  Resp: B

________________________________________________
# Prova sobre Amazon API Gateway

### Questão 1: Qual das seguintes afirmações sobre o Amazon API Gateway está correta?

a) O Amazon API Gateway é um banco de dados relacional totalmente gerenciado pela AWS.

b) O Amazon API Gateway é um serviço de armazenamento de objetos na nuvem.

c) O Amazon API Gateway é um serviço que permite a criação, publicação, manutenção, monitoramento e proteção de APIs.

d) O Amazon API Gateway é um serviço de processamento em tempo real de grandes volumes de dados.

####  Resp: C

### Questão 2: Qual é o principal objetivo do Amazon API Gateway?

a) Facilitar a implantação de aplicativos web.

b) Permitir a comunicação síncrona entre diferentes partes de uma aplicação.

c) Expor back-ends de aplicativos como APIs gerenciadas.

d) Armazenar e distribuir conteúdo estático, como imagens e vídeos.

####  Resp: C

### Questão 3: Qual é o tipo de API oferecido pelo Amazon API Gateway?

a) API RDBMS (Relational Database Management System)

b) API RCU (Request-Response Communication Unit)

c) API RESTful (Representational State Transfer)

d) API LSM (Least Recently Used)

####  Resp: C

### Questão 4: O que é um recurso no contexto do Amazon API Gateway?

a) Um endpoint que fornece acesso a um serviço da AWS.

b) Uma etapa no processamento de uma solicitação HTTP.

c) Uma representação de uma entidade de negócios na API.

d) Um contêiner de objetos armazenados no serviço.

####  Resp: C

### Questão 5: Qual é a principal vantagem de usar o Amazon API Gateway para expor back-ends de aplicativos como APIs?

a) Aumenta a latência do sistema.

b) Melhora a segurança da aplicação.

c) Reduz a escalabilidade da aplicação.

d) Torna os back-ends mais complexos de gerenciar.

####  Resp: B

### Questão 6: Qual é a maneira correta de definir um endpoint no Amazon API Gateway?

a) No código fonte da função Lambda associada à API.

b) Na configuração do gatilho associado à API.

c) No arquivo de configuração da API no console AWS API Gateway.

d) Na definição de recursos e métodos da API no console AWS API Gateway.

####  Resp: D

### Questão 7: Qual é a diferença entre os tipos de integração "Lambda Proxy" e "Lambda" no Amazon API Gateway?

a) Não há diferença; ambos os tipos de integração são usados para integrar funções Lambda à API.

b) A integração "Lambda Proxy" passa todos os detalhes da solicitação para a função Lambda, enquanto a integração "Lambda" permite uma transformação da solicitação antes de ser enviada para a função Lambda.

c) A integração "Lambda Proxy" permite a execução de funções Lambda em contêineres, enquanto a integração "Lambda" só suporta a execução de funções Lambda sem contêineres.

d) A integração "Lambda Proxy" só suporta a execução de funções Lambda de forma assíncrona, enquanto a integração "Lambda" suporta a execução de funções Lambda de forma síncrona.

####  Resp: B

### Questão 8: Qual é a diferença entre uma API RESTful e uma API WebSocket?

a) Uma API RESTful é usada para comunicação síncrona, enquanto uma API WebSocket é usada para comunicação assíncrona.

b) Uma API RESTful é baseada no protocolo HTTP, enquanto uma API WebSocket é baseada no protocolo WebSocket.

c) Uma API RESTful é mais adequada para comunicação em tempo real, enquanto uma API WebSocket é mais adequada para comunicação ocasional.

d) Uma API RESTful requer uma conexão persistente entre cliente e servidor, enquanto uma API WebSocket não requer essa conexão.

####  Resp: B

### Questão 9: Como você pode controlar o acesso à sua API no Amazon API Gateway?

a) Usando políticas de controle de acesso integradas ao AWS Lambda.

b) Apenas configurando regras de firewall no Amazon EC2.

c) Usando chaves de API e políticas de controle de acesso no Amazon API Gateway.

d) Permitindo apenas acesso interno à API.

####  Resp: C

Questão 10: Qual é o principal benefício de usar o Amazon API Gateway?

a) Melhorar o desempenho de computação em seus aplicativos.

b) Reduzir a escalabilidade dos back-ends dos aplicativos.

c) Facilitar a integração de back-ends de aplicativos como APIs gerenciadas.

d) Aumentar a complexidade de gerenciamento de back-ends de aplicativos.

####  Resp: C
_______________________________
# Prova sobre Arquitetura Hexagonal

### Questão 1: O que é a Arquitetura Hexagonal?

a) Um modelo de arquitetura de software baseado em seis camadas distintas.

b) Um padrão de arquitetura que usa um hexágono como representação visual das camadas do sistema.

c) Um modelo de arquitetura que enfatiza a separação de preocupações e a dependência de interfaces.

d) Um modelo de arquitetura que organiza o sistema em torno de um núcleo central.

####  Resp: C

### Questão 2: Qual é o principal objetivo da Arquitetura Hexagonal?

a) Simplificar a estrutura de código do sistema.

b) Reduzir o acoplamento entre os componentes do sistema.

c) Aumentar a complexidade da arquitetura para melhorar o desempenho.

d) Tornar o sistema mais difícil de manter e entender.

####  Resp: B

### Questão 3: Em um sistema que segue os princípios da Arquitetura Hexagonal, onde as regras de negócio devem residir?

a) No banco de dados.

b) No controlador da interface do usuário.

c) Em classes dedicadas conhecidas como "portas" ou "adapters".

d) Nas camadas de infraestrutura.

####  Resp: C

### Questão 4: Na Arquitetura Hexagonal, o que são as "portas"?

a) Interfaces que expõem os serviços do sistema para uso externo.

b) Componentes que lidam com a lógica de negócios do sistema.

c) Camadas que interagem diretamente com o banco de dados.

d) Classes de teste que simulam comportamentos externos ao sistema.

####  Resp: A

### Questão 5: Qual é a principal vantagem de usar a Arquitetura Hexagonal em um sistema?

a) Maior complexidade e acoplamento entre os componentes.

b) Maior facilidade de manutenção e testabilidade do código.

c) Redução da modularidade e reutilização de código.

d) Melhoria do desempenho do sistema.

####  Resp: B

### Questão 6: O que são os "adapters" na Arquitetura Hexagonal?

a) Componentes que convertem dados entre o formato interno do sistema e os formatos externos.

b) Classes responsáveis por executar as operações de persistência no banco de dados.

c) Interfaces que definem os contratos entre os diferentes componentes do sistema.

d) Componentes que encapsulam a lógica de negócios do sistema.

####  Resp: A

### Questão 7: Qual é o princípio fundamental da Arquitetura Hexagonal relacionado à dependência de frameworks e bibliotecas externas?

a) Dependência de Alto Nível.

b) Dependência de Baixo Nível.

c) Inversão de Dependências.

d) Acoplamento Forte.

####  Resp: C

### Questão 8: Como a Arquitetura Hexagonal contribui para a testabilidade do sistema?

a) Aumentando a dependência de bibliotecas de mocking.

b) Simplificando a estrutura do código para facilitar a escrita de testes.

c) Ocultando a lógica de negócios dentro dos adaptadores.

d) Tornando os testes de unidade mais difíceis de serem escritos.

####  Resp: B

### Questão 9: O que é o "core" na Arquitetura Hexagonal?

a) A camada que contém as regras de negócio do sistema.

b) O módulo que implementa a interface do usuário.

c) Um conjunto de serviços que lidam com a comunicação externa.

d) O banco de dados principal do sistema.

####  Resp: A

### Questão 10: Qual é a relação entre a Arquitetura Hexagonal e os princípios SOLID?

a) A Arquitetura Hexagonal não está relacionada aos princípios SOLID.

b) A Arquitetura Hexagonal viola os princípios SOLID.

c) A Arquitetura Hexagonal é uma aplicação prática dos princípios SOLID.

d) Os princípios SOLID são usados apenas em arquiteturas monolíticas.

####  Resp: C
