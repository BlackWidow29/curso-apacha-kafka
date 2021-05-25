#  Formação Apacha Kafka

## Curso - Kafka: Produtores, Consumidores e streams

### Instalação - linux

- Local
```
https://kafka.apache.org/downloads
```
<ol>
    <li>Selecione a versão mais  recente com suporte a Scala</li>
    <img src="https://github.com/BlackWidow29/curso-apacha-kafka/blob/main/.github/Passo1.png" alt="passo 1" srcset="">
    <li>Descompacte o arquivo tar.gz na sua máquina</li>
    <img src="https://github.com/BlackWidow29/curso-apacha-kafka/blob/main/.github/Passo2.png" alt="passo 2" srcset="">
    <li>Suba o zookeeper e o kafka conforme mostrado em</li> <a href="#comandosuteis">Comandos úteis</a>
    <li></li>
</ol>


<a id="comandosuteis"></a>
* Comandos úteis

```java
 //Subindo o  zookeeper 
bin/zookeeper-server-start.sh config/zookeeper.properties
 //Subindo o kafka
bin/kafka-server-start.sh config/server.properties
 //Criando um novo tópico
bin/kafka-topics.sh --create --bootstrap-server localhost:9092 --replication-factor 1 --partitions 1  --topic NOME_TÓPICO
 //Criando um produtor(producer)
bin/kafka-console-producer.sh --broker-list  localhost:9092  --topic LOJA_NOVO_PEDIDO
 //Criando um consumidor(consumer) sem historico anterior
bin/kafka-console-consumer.sh --bootstrap-server  localhost:9092  --topic LOJA_NOVO_PEDIDO
 //Criando um consumidor(consumer) com historico anterior
bin/kafka-console-consumer.sh --bootstrap-server  localhost:9092  --topic LOJA_NOVO_PEDIDO --from-beginning