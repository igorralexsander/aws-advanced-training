# AWS SQS


## Delay Queue

When we needs to add a "unavailability time" to consumers for all messages. In the other words, after message sended it wiil not visible for consumer for x seconds.

## Visibility timeout

After message received by consumer how long will the message stay unavailable by other consumers.
After processing successfull, the consumer shoud delete message from queue.
In case when message is lost on the way to the consumer either error occurs in consumer or delete is not called, after the visibility timeout is reached the message back to queue.