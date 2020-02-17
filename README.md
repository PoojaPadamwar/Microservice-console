# Microservice-console
 
# How to execute the program
Open two terminals.

Run the consumer:

cd Receive
dotnet run
Then run the producer:

cd Send
dotnet run
The consumer will print the message it gets from the publisher via RabbitMQ. The consumer will keep running, waiting for messages (Use Ctrl-C to stop it), so try running the publisher from another terminal.

after sending the message on server look for the queue in Rabit MQ list

http://localhost:15672/#/queues

You will find the Messgae in the queue of the RabitMq
