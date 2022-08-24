1.Now open command prompt and change the directory to the kafka folder. 
cd c:\kafka
First start zookeeper using the command given below:
.\bin\windows\zookeeper-server-start.bat .\config\zookeeper.properties
2.Now open another command prompt and change the directory to the kafka folder. 
cd c:\kafka
Run kafka server using the command:
.\bin\windows\kafka-server-start.bat .\config\server.properties
3.Now open another command prompt and go to kafka\bin\windows folder
cd c:\kafka\bin\windows
Create topic t2
.\kafka-topics.bat --create --zookeeper localhost:2181 --replication-factor 1 --partitions 1 --topic analysis
4. Now open another command prompt and go to elasticsearch folder
cd C:\graph\elasticsearch-7.13.4\bin
Run elasticsearch
.\elasticsearch
5. Now open another command prompt and go to kibana folder
cd C:\graph\kibana-7.13.4-windows-x86_64\bin
Run kibana
.\kibana
6. Now open another command prompt and go to python code folder
cd c:\progra~1\python\A3-BD
Run main file, format as python pythonfile.py searchterm
python twitter.py utd
7. Now open another command prompt and go to spark home directory
cd C:\Spark\spark-3.1.2-bin-hadoop3.2
Run command
./bin/spark-submit  --packages org.apache.spark:spark-sql-kafka-0-10_2.11:2.2.0,org.apache.spark:spark-streaming-kafka-0-8-assembly_2.11:2.1.1 /C:\Progra~1\Python\A3-BD\analysis.py utd
8. Go to logstash home directory
cd C:\graph\logstash
Run command
logstash -f logstash.conf
The logstash.conf should create as following format: 
input {
  kafka {

	bootstrap_servers => "localhost:9092"

	topics => ["Your-topic"]

  }
}
output {
  elasticsearch {
      hosts => ["localhost:9200"]
      index => "Your-topic"
  }
}

