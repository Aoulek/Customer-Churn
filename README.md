# Customer-Churn
Il s’agit de développer une application Web basée sur l’API Apache KAFKA Stream, permettant de faire  l’analyse des données, dans le but de « prédire en temps réel le désabonnement des clients d’une entreprise »
Afin comprendre le fonctionnement de Kafka, il faut d'abord se familiariser avec le vocabulaire suivant : 
Topic: Un flux de messages appartenant à une catégorie particulière. Les données sont stockées dans des topics. 
Partitions: Chaque topic est divisé en partitions. Pour chaque topic, Kafka conserve un minimum d'une 
partition. Chaque partition contient des messages dans une séquence ordonnée immuable. Une partition est 
implémentée comme un ensemble de segments de tailles égales. 
Brokers: Les brokers (ou courtiers) sont de simples systèmes responsables de maintenir les données publiées. 
Chaque courtier peut avoir zéro ou plusieurs partitions par topic. 
Producers: Les producteurs sont les éditeurs de messages à un ou plusieurs topics Kafka. Ils envoient des 
données aux courtiers Kafka. Chaque fois qu'un producteur publie un message à un courtier, ce dernier rattache 
le message au dernier sègment, ajouté ainsi à une partition. Un producteur peut également envoyer un message à 
une partition particulière. 
Consumers: Les consommateurs lisent les données à partir des brokers. Ils souscrivent à un ou plusieurs topics,
et consomment les messages publiés en extrayant les données à partir des brokers.
![image](https://github.com/Aoulek/Customer-Churn/assets/101673062/f65e9456-be9d-4a92-a9ba-ae0a562f6ccd)
Pour Lancer le code:
1- telecharger et installer kafka sur le site officiel : https://kafka.apache.org/downloads

2- Lancer kafka et Zookpper en utilisant les commandes:

C:\kafka> .\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties

C:\kafka> .\bin\windows\kafka-server-start.bat .\config\server.properties

3- Dans le chemin C:\kafka\bin\windows creation d'une topic kafka pour le producer et cosumer kafka en utilisant cette commande:
kafka-topics.bat --create --bootstrap-server localhost:9092 --topic costumerchurn

5- l'execution de producer.py et cusomer.py
avec les deux commandes (sur le repertoire du projet):
python Producer.py
python Cusomer.py

6- l'entrainement du model pour la preduction
python Model.py

7- creation d'une nouvelle topic pour produire et consomer les donnees de prediction avec la commande:
kafka-topics.bat --create --bootstrap-server localhost:9092 --topic test3

8- l'execution du file app.py pour l'affichage du formulaire:
python app.py
![image](https://github.com/Aoulek/Customer-Churn/assets/101673062/11d10a96-e3a2-457f-817b-eafafabce8ce)

9- remplissage du formulaire:
![image](https://github.com/Aoulek/Customer-Churn/assets/101673062/386b5c9a-50c7-48cd-9591-cae1fb33d8fd)

10- prediction
![image](https://github.com/Aoulek/Customer-Churn/assets/101673062/d2f8d269-3d85-433e-ad73-aa323e29e60a)






