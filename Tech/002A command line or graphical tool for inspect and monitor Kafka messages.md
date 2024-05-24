For inspecting and monitoring Kafka messages, you have a few options available:

**Command-Line Tools:**
- **Kafka Console Consumer**: This is a command-line tool that comes with Kafka and allows you to view messages produced on a topic. You can use it with the following command:
  ```shell
  kafka-console-consumer.sh --bootstrap-server localhost:9092 --topic your_topic --from-beginning
  ```
  This will display the messages as they are received¹.

- **kcat (formerly known as kafkacat)**: A versatile command-line utility that allows you to produce, consume, and manage Kafka messages. Here's a simple command to display messages from a topic:
  ```shell
  kcat -C -b <bootstrap_server_host:port> -t <topic>
  ```

**Graphical Tools:**
- **Kafka Magic**: Kafka Magic is a GUI tool for working with Apache Kafka clusters. It can find and display messages, transform and move messages between topics, review and update schemas, manage topics, and automate complex tasks³.

These tools can help you effectively monitor and inspect messages in your Kafka setup. Remember to replace placeholders like `localhost:9092`, `your_topic`, and `<bootstrap_server_host:port>` with your actual server details and topic names.

Source: Conversation with Bing, 12/04/2024
(1) Kafka Command-Line Interface (CLI) Tools - Confluent. https://docs.confluent.io/kafka/operations-tools/kafka-tools.html.
(2) Explorer : Kafka Magic Tool. https://www.kafkamagic.com/.
(3) How to view kafka message? - Stack Overflow. https://stackoverflow.com/questions/44239027/how-to-view-kafka-message.
(4) Kafka monitoring: Tutorials and best practices - Redpanda. https://redpanda.com/guides/kafka-performance/kafka-monitoring.
(5) Kafka Tutorial: Using Kafka from the command line - Cloudurable. http://cloudurable.com/blog/kafka-tutorial-kafka-from-command-line/index.html.