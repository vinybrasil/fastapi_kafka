# A asynchronous Consumer and Producer API for Kafka with FastAPI in Python

Create a simple asynchronous API that works the same time as a Kafka's producer and consumer with Python's FastAPI library. The entire explation of the projects can be found at my [blog post](https://vinybrasil.github.io/portfolio/kafkafastapiasync/).

To run Kafka:
```
> docker-compose -f docker-compose.yml up
```

Create a new topic:
```
> docker exec -ti kafka /opt/kafka/bin/kafka-topics.sh --create --zookeeper zookeeper:2181 --replication-factor 1 --partitions 1 --topic test1
```

Run the API:
```
> cd API
> uvicorn main:app --reload
```

Test it with cURL:
```
curl -X POST -d {\"name\":\"salve\"} -H "Content-Type: application/json"  http://localhost:8000/producer/test1
```