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

## Simulation slow subscriber
The total queue count peaked at around 20. This occurred because the cargo run command was executed five separate times, and ideally, it should have been spread out over 20 seconds (with 5 messages per run across 5 runs). However, because the cargo run commands were executed back-to-back without intentional delays between them, the maximum number of messages that accumulated in the queue at any given time was limited to 20.
<img width="1014" alt="Screenshot 2024-04-24 at 03 01 42" src="https://github.com/mariagrizelda/tutorial8-subscriber/assets/134635504/79cbb92d-84fd-43e1-a913-3f4184d4368b">

I executed the cargo run command five times and observed a quicker reduction in message queue spikes compared to previous attempts. This enhancement is due to the subscriber using multithreading to manage the incoming messages from the publisher, allowing for parallel processing. To further improve this, introducing parallelism on the publisher’s side could allow it to send multiple requests at the same time, creating a more realistic simulation of high-traffic conditions.
<img width="1014" alt="Screenshot 2024-04-24 at 03 05 19" src="https://github.com/mariagrizelda/tutorial8-subscriber/assets/134635504/818a9ebf-46f4-4107-87bd-5bc221c0843b">
