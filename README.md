# Microservice-console
# Creation of Project (via Command Line)
Setup
First lets verify that you have .NET Core toolchain in PATH:

dotnet --help
should produce a help message.

Now let's generate two projects, one for the publisher and one for the consumer:

dotnet new console --name Send
mv Send/Program.cs Send/Send.cs
dotnet new console --name Receive
mv Receive/Program.cs Receive/Receive.cs
This will create two new directories named Send and Receive.

Then we add the client dependency.

cd Send
dotnet add package RabbitMQ.Client
dotnet restore
cd ../Receive
dotnet add package RabbitMQ.Client
dotnet restore
Now we have the .NET project set up we can write some code.

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
