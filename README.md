# Tutorial 8 - Subscriber

## Reflection
a. What is ***amqp***?

***amqp*** stands for Advanced Message Queuing Protocol. It is a protocol used for sending messages between applications or systems. It operates on a message-oriented middleware model, meaning it facilitates the communication through a messaging infrastructure, enabling different systems to communicate by sending messages to each other, regardless of their internal architectures.
b. What it means? guest:guest@localhost:5672 , what is the first quest, and what is
the second guest, and what is localhost:5672 is for?

- The first guest is the username used to authenticate the connection.
- The second guest is the password associated with the username.
- localhost refers to the local machine, indicating that the service is running on the same system from which the attempt to connect is being made.
- 5672 is the port number used by the AMQP protocol to establish the connection.
