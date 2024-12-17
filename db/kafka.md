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

---

## Set Topic Retention

```bash {copyable}
kafka-configs.sh --bootstrap-server localhost:9092 --entity-type topics --entity-name foo --alter --add-config retention.ms=86400000
```

---

## Get Topic Config

```bash {copyable}
kafka-configs.sh --bootstrap-server localhost:9092 --describe --entity-type topics --entity-name foo
```

---

## Get Topic Size

```bash {copyable}
kafka-log-dirs.sh --bootstrap-server localhost:9092 --describe --topic-list foo
```
