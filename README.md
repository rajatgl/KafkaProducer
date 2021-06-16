# KafkaProducer
Kafka-producer implementation using spring-framework


## Reference Commands and steps:

### start zookeeper:
at its path ---> zkserver

### start kafka server:
at kafka folder-->
	.\bin\windows\kafka-server-start.bat .\config\server.properties

at kafka/bin/windows
###	create topic:
kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 2 --topic TOPIC_NAME
	list available topics:
kafka-topics.bat --list --zookeeper localhost:2181
	delete a topic
kafka-topics.bat --delete --zookeeper localhost:2181 --topic TOPIC_NAME



### new cmd prompt: create producer:
	kafka-console-producer.bat --broker-list localhost:9092 --topic test
### new cmd prompt: create consumer:
	kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic test --partition 0

### Additional commands:
List Topics: kafka-topics.bat --list --zookeeper localhost:2181 
Describe Topic: kafka-topics.bat --describe --zookeeper localhost:2181 --topic [Topic Name]
Read messages from the beginning
Before version < 2.0: kafka-console-consumer.bat --zookeeper localhost:2181 --topic [Topic Name] --from-beginning
After version > 2.0:  kafka-console-consumer.bat --bootstrap-server localhost:9092 --topic [Topic Name] --from-beginn
Delete Topic: kafka-run-class.bat kafka.admin.TopicCommand --delete --topic [topic_to_delete] --zookeeper localhost:2181

### Note
in case of errors: check with java path, delete zookeeper data and kafka-logs for a complete refresh...also change log.dir from server.log.

