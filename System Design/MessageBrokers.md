### Kafka:

Kafka is a platform to build pipeline of data in real-time

### Producer

- The producer is responsible for sending messages to a topic in Kafka
- It acts as a source generational of data and send them to Kafka.
- You can send messages for multiple topics
- Example: a system of sensors that sends data for processing

---

### Consumer

- Responsible for reading messages from one or more topics from Kafka
- Consumers are part of Consumer Groups, that allow scalability and load balancing
- Every consumer reads one or more partitions
- The consume is made in way ordered inside partitions
- Example: a system that process data in real time of sensors

---

### How it works:

1. Producer sends message to a topic
2. Kafka records the messages at the partitions of the topic
3. Consumers, organized in groups reads the messages in a distributed way
4. Consumers process and confirm the receive of the messages

### What's good about this?

- High scalability and tolerance to fails
- Last long saving of messages until the consume
- decoupling between producers and consumers
