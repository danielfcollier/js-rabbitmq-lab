# Getting Started with RabbitMQ

Reference: https://www.rabbitmq.com/getstarted.html

For:
- JS examples, run: `npm install`
- PHP example, run: `composer install`

## Run RabbitMQ with Docker:

### Run:

```bash
sudo docker compose up -d
```

### Access the admin panel at:

http://localhost:15672

```yaml
username: guest
password: guest
```

### Stop:

```bash
sudo docker compose down
```

### RabbitMQ CLI Commands:

- List Queues

```bash
sudo rabbitmqctl list_queues
```

- Forgotten Acks

```bash
sudo rabbitmqctl list_queues name messages_ready messages_unacknowledged
```

- List Exchanges

```bash
sudo rabbitmqctl list_exchanges
```

- List Bindings

```bash
sudo rabbitmqctl list_bindings
```

## 01 Hello World

- Send messages with:

```bash
npm run send
```

- Receive messages with:

```bash
npm run receive
```

## 02 Work Queues

- Run workers/receivers in parallel and see the round-robin queue behavior.

@Shell_1

```bash
npm run receive
```

@Shell_2

```bash
npm run receive
```

- Send new tasks in a third shell:

@Shell_3

```bash
npm run send -- 'First message...'
npm run send -- 'Second message...'
npm run send -- 'Third message...'
npm run send -- 'Fourth message...'
npm run send -- 'Fifth message...'
```

## 03 Publish/Subscribe

- Send messages with:

```bash
npm run send
```

- Receive messages with:

```bash
npm run receive
```

## 04 Routing

- Send messages with:

```bash
npm run send -- error "Run. Run. Or it will explode."
```

- Receive messages with:

```bash
npm run receive -- info warning error
```

## 05 Topics

- Receive messages with:

```bash
npm run receive -- "kern.*"
```

- Send messages with:

```bash
npm run send -- "kern.critical" "A critical kernel error."
```

## 06 RPC

## 07 Publisher Confirms

```bash
php receiver.php
```

```bash
php send.php
```
