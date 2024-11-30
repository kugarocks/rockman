# Intro

Distributed streaming platform.

---

## List Topics

```bash {copyable}
kafka-topics.sh --bootstrap-server foo:9092 --list
```

---

## Consume Message

```bash {copyable}
kafka-console-consumer.sh --bootstrap-server foo:9092 --topic foo
```

---

## Produce Message

```bash {copyable}
kafka-console-producer.sh --broker-list foo:9092 --topic foo
```
