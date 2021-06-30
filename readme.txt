cd kafka-container


//start kafka container
docker-compose up -d


// to check all containers are spinned up
docker ps 


//to enter the container CLI
docker-compose exec kafka bash


//produce messages
kafka-console-producer --topic mockup-topic-for-poc --bootstrap-server kafka:9092 \
  --property parse.key=true \
  --property key.separator=":"
  

//consume messages
kafka-console-consumer --topic example-topic --bootstrap-server kafka:9092 --from-beginning