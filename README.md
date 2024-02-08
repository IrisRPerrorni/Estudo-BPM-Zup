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
