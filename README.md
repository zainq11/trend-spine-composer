This is it. Coming soon:
- Node.js
- Kafka
- Go
- Scala

docker run --net=host --rm confluentinc/cp-kafka:5.0.0 kafka-topics --create --topic foo --partitions 4 --replication-factor 2 --if-not-exists --zookeeper localhost:32181


- Consume messages from topic "foo" and partition 0
kafkacat -C -b localhost:19092,localhost:29092,localhost:39092 -t foo -p 0

- Publish to partition 1
echo 'publish to partition 1' | kafkacat -P -b localhost:19092,localhost:29092,localhost:39092 -t foo -p 1