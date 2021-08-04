# Spring Boot App:

1. Start ZooKeeper: c:\kafka> .\bin\windows\zookeeper-server-start.bat ./config\zookeeper.properties

2. Stat Kafka: .\bin\windows\kafka-server-start.bat .\config\server.properties

3. Create input, output topics

	kafka-topics.bat --create    --bootstrap-server localhost:9092     --replication-factor 1    --partitions 1 --topic streams-json-input
	
	kafka-topics.bat --create     --bootstrap-server localhost:9092   --replication-factor 1     --partitions 1   --topic streams-json-output
  	
4. 

RUN the program


kafka-console-producer.bat --bootstrap-server localhost:9092 --topic streams-json-input

	> {"key":"somekey","words":["word1"]}
	> {"key":"somekey","words":["word2"]}



kafka-console-consumer.bat --bootstrap-server localhost:9092    --topic streams-json-output --from-beginning  --formatter kafka.tools.DefaultMessageFormatter     --property print.key=true --property print.value=true --property print.key=true --property print.value=true
	> OP