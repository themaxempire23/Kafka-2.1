#Description:	Ubuntu 22.04.3 LTS 
[Any Ubuntu version is alright]

# 1. Check if Java is installed --> java -version 
file:///home/clutchcoder99/Documents/Distributed%20systems%20Applications/Kafka-2.1/images/java%20version.png

## if not installed run this command:
             --> sudo apt install openjdk-11-jdk

2. Download Kafka --> Open up your favourite web browser, search Kafka  download
![Kafka download](https://github.com/themaxempire23/Kafka-2.1/assets/83220484/3ac5a194-6198-4cd3-af6f-045ba3a3e6c4)

![download](https://github.com/themaxempire23/Kafka-2.1/assets/83220484/97589d11-92ce-4bb8-b232-78b0fc241961)
select any file under binary downloads. *NB: Only 1 


3. extract the kafka zip file  in your home directory:
                       Command--->tar -xvf kafka_2.13-3.5.1.tgz
                              --> confirm that you see the new kafka diretory. 
                              ---> rename it to just kafka
                                 ![rename to kafka](https://github.com/themaxempire23/Kafka-2.1/assets/83220484/6a6694c0-3117-4d29-a6ea-0910ef17a503)

-->cd into new directory, ls to view whats inside (normally you would find 8 files, based on the latest version)
file:///home/clutchcoder99/Documents/Distributed%20systems%20Applications/Kafka-2.1/images/ls%208%20files.png
file:///home/clutchcoder99/Documents/Distributed%20systems%20Applications/Kafka-2.1/images/8%20files.png

# Note don't close any terminal, unless instructed to. Keep terminals open.

# How to run kafka in Ubuntu:

# 1. open new terminal,
# 2. Navigate to your kafka directory,
   ![ls 8 files](https://github.com/themaxempire23/Kafka-2.1/assets/83220484/b2023e0f-e4ca-4cb6-996e-e03da507429a)
# 3. To run Kafka we will need run zookeeper
   
  ## Starting Zookeeper

   Run this command:
     ------------> bin/zookeeper-server-start.sh config/zookeeper.properties
output:

a. make sure you see the zookeper image like in the image below,
![zooK1](https://github.com/themaxempire23/Kafka-2.1/assets/83220484/e23d8b8b-f6e7-4f6b-93e7-31a6e775cccb)

b. scroll down, 
![sqlStatus](https://github.com/themaxempire23/Kafka-2.1/assets/83220484/2705396c-bc81-480d-ac14-802bfa134216)

   Zookeeper is officially running, Enabling us to run Kafka.

# 4. Starting the Kafka Environment, 

## Starting Kafka

Open new terminal,
   run the following command:
       ----------------> bin/kafka-server-start.sh config/server.properties

  ## Output:

   a. 
   
  ![kafka 1](https://github.com/themaxempire23/Kafka-2.1/assets/83220484/e0be51fa-7af3-49bf-9626-f089b1cb55c0)

   b. 
    
   file:///home/clutchcoder99/Documents/Distributed%20systems%20Applications/Kafka-2.1/images/kafka3.png

   c. 

  ![kafka 2](https://github.com/themaxempire23/Kafka-2.1/assets/83220484/130ec8c5-115e-4292-a82b-e27af4edb7d4)

    
   the above command starts our kafka server, situated in the config file, no need to worry about the config file.
   From her on we can create topics and partitions all running to our kafka server.
   Lets dive in!

# 5. Creating our topics:
Open a new terminal,

## We use the following command,
 ----------------> bin/kafka-topics.sh --create --topic quickstart-events --bootstrap-server localhost:9092



## output:
file:///home/clutchcoder99/Documents/Distributed%20systems%20Applications/Kafka-2.1/images/creating%20topic.png

# 6. writting some events into the topic

Open new terminal,

## use this command:

--------> bin/kafka-console-producer.sh --topic quickstart-events --bootstrap-server localhost:9092

it will promt show you this symbol " > "
write anything next to it.

## output:

file:///home/clutchcoder99/Documents/Distributed%20systems%20Applications/Kafka-2.1/images/writting.png

# 7. Consuming the written events.

## command: 
 ------------------> bin/kafka-console-consumer.sh --topic quickstart-events --from-beginning --bootstrap-server localhost:9092

## output:
it should output what you have written in the previouse step.

![consumer](https://github.com/themaxempire23/Kafka-2.1/assets/83220484/ed855460-84cc-49b8-b25a-e81df4950115)




Hope it helped you.

#Clutch Coder99                                                                   2023



   